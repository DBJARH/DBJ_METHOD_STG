---
layout: default
title: Actor-Agent Architecture
description: How AI agents attach externally to an actor-model foundation — entering through typed inboxes as the translation layer between LLM text and Protobuf contracts.
---

# Actor-Agent Architecture

> This document explores how AI Agents may be added externally to a system built on the [Actor Model Architecture](actor-model.md). It is a living document — added to as patterns emerge.
{: .tip}

---

## Foundation First

> The Actor model with Protobuf binary messaging produces a sound, resilient distributed system on its own. Actors communicate through typed, schema-governed inbox contracts. State is fully encapsulated. The system is correct and operable without any AI component.
{: .note}

> Agents are **not** the foundation. They are external additions that bring AI capabilities to specific, well-defined points in the system — where the structured, deterministic logic of Actors reaches the boundary of what rules can cover.
{: .warning}

> This distinction matters. A system designed around Agents as the core becomes fragile: behaviour is probabilistic, contracts are implicit, and failure modes are harder to reason about. A system designed around Actors, with Agents as optional bolt-ons, remains predictable at its core.
{: .important}

---

## Where Agents Fit

An Agent enters the Actor system through an inbox — exactly like any other Actor. From the system's perspective, an Agent is a specialised Actor with one difference: its behavior is driven by a language model rather than deterministic logic.

```mermaid
graph LR
    subgraph Actor System
        MB[Mailbox Actor]
        PL[Policy Actor]
        NT[Notification Actor]
    end

    subgraph Agent Layer - External
        AG[AI Agent Actor]
    end

    MB -->|event message| AG
    AG -->|action message| MB
    AG -->|action message| NT
```

The Agent receives messages, processes them (using an LLM or other AI capability), and sends messages back into the system. It does not bypass the inbox. It does not reach into Actor state directly. The Protobuf contract is the boundary — the Agent must conform to it.

### The Agent as Translation Layer

LLMs operate on text. Protobuf is binary. The Agent Actor is the explicit translation layer between the two:

```mermaid
graph LR
    IN[Inbox\nProtobuf message] -->|deserialize| CTX[Build LLM context\ntext / JSON]
    CTX -->|LLM call| OUT[Parse LLM response]
    OUT -->|serialize| ACT[Outbox\nProtobuf message]
```

The LLM call — and everything text-based — happens entirely inside the Agent. The Actor system sees only typed Protobuf messages arriving and leaving. The Agent is responsible for the fidelity of that translation: deserializing the inbound message into context the LLM can reason about, and mapping the LLM's response back into a valid, schema-governed outbound message.

This is why Agent scope must be narrow. A wide-scope Agent translating complex, multi-step context is harder to keep honest at the schema boundary. A narrow-scope Agent — one job, one message type in, one message type out — keeps the translation surface small and testable.

---

## Candidate Integration Points

The following are candidate points in the [email use case](email-use-case.md) where an Agent could add value. None are mandatory — each is a conscious choice to introduce probabilistic behaviour at a specific, bounded location.

| Integration point | Actor | What the agent does |
|---|---|---|
| Spam and content classification | Gateway Actor | Classifies inbound messages beyond rule-based policy |
| Smart folder suggestion | Mailbox Actor | Suggests folder placement based on message content and history |
| Search query understanding | Search Actor | Translates natural language queries to structured search parameters |
| Policy anomaly detection | Policy Actor | Flags unusual quota or usage patterns for admin review |
| Notification summarisation | Notification Actor | Summarises digest notifications rather than listing raw events |

---

## Constraints

When adding an Agent to an Actor system, the following constraints apply:

- **The Agent communicates via inbox only.** No direct state access.
- **The Agent's input and output are Protobuf-typed.** The `.proto` schema is the contract. The Agent is a consumer and producer of schema-governed messages, not a free-form text processor at the system boundary.
- **Agent failure is isolated.** A crashed or unresponsive Agent does not cascade. The Actor system continues. The specific capability the Agent provided degrades gracefully.
- **Agent scope is narrow.** Each Agent has one job. It does not orchestrate other Actors. Orchestration remains in deterministic Actor logic.

---

*This document will grow as patterns are validated. See also: [Actor Model Architecture](actor-model.md) and [Email Use Case](email-use-case.md) — how AI Agents may be added externally to this system.*

---

| <img src="../../../assets/dbj/dbj-org-logo.jpg" width="64px" /> | &nbsp; |
|---|---|
| CC BY SA 4.0 | &copy; dbj@dbj.org |
