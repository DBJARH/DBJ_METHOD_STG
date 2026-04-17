---
layout: default
title: Agent-Actor Architecture — Plan and Decision Log
description: Working spec and decision log for the agent-actor KB restructuring.
---

[← Knowledge Base](../index.md)

# Agent-Actor Architecture — Plan and Decision Log

This file is a working spec / context document for restructuring the agent-actor KB section.

---

## Contents

- [Agent-Actor Architecture — Plan and Decision Log](#agent-actor-architecture--plan-and-decision-log)
  - [Contents](#contents)
  - [Goal](#goal)
  - [Proposed Structure](#proposed-structure)
    - [Conceptual](#conceptual)
    - [Logical](#logical)
    - [Physical](#physical)
    - [Implementation](#implementation)
  - [Mermaid Diagrams Planned](#mermaid-diagrams-planned)
  - [Open Questions / Decisions Needed](#open-questions--decisions-needed)
  - [Restructuring Session — 2026-03-18](#restructuring-session--2026-03-18)
    - [The New Primary Thesis](#the-new-primary-thesis)
    - [Key Clarification on Actor Behavior](#key-clarification-on-actor-behavior)
    - [Structural Decisions for `index.md`](#structural-decisions-for-indexmd)
    - [Taxonomy Partitioning](#taxonomy-partitioning)
  - [Status](#status)

---

## Goal

Restructure the actor model knowledge base article to follow the Iron Code Labs Common Taxonomy — four top-level categories: **Conceptual**, **Logical**, **Physical**, **Implementation**.

The motivating novelty: using safe, fast binary messaging (Protobuf) on top of the actor model as the foundation for a **resilient agentic system**.

---

## Proposed Structure

### Conceptual

- What an Actor is (anatomy, inbox, private state, behavior)
- No shared state — the design constraint, not a limitation
- Message passing as the only interaction model (fire-and-forget, async by design)
- Why binary messaging: the case for Protobuf over JSON at Actor message volume
- The agentic framing: Actors as autonomous Agents — resilience through isolation and message-passing contracts

### Logical

- Actor system design for a concrete use case (organisational email management)
- Actor inventory: roles, responsibilities, state ownership
- Actor conversation map: primary message flows
- State ownership summary table
- Protobuf contract summary: key `.proto` message types
- The Train Pattern as a logical protocol for large payload flows

### Physical

- Actor placement across nodes and process boundaries
- Network topology: which Actors are co-located vs. distributed
- Fault domains: Actor supervision trees, restart strategies
- Broker placement: selective use of async brokers (Kafka/RabbitMQ/SQS) vs. direct Actor-to-Actor

### Implementation

- Protobuf schema tooling: `protoc`, generated code, polyglot support
- Schema governance: `buf breaking` enforcement at CI, review and sign-off process
- The Train Pattern as a concrete wire protocol: HEAD / PACKET / TAIL packet types, sequence numbers, checksum
- `correlation_id` as tracing identifier across Actor hops
- Operational concerns: audit log, quota enforcement, dead-letter handling

---

## Mermaid Diagrams Planned

| Diagram | Category | Description |
|---|---|---|
| Actor topology | Conceptual | Single Actor: inbox, state, behavior. Basic Actor-to-Actor message flow. |
| Conversation map | Logical | All Actors in the email system, labelled message flows between them. |
| Deployment topology | Physical | Actor placement across nodes, broker position, fault domain boundaries. |
| Schema pipeline | Implementation | `.proto` → `protoc` → generated stubs → `buf breaking` in CI. |

---

## Open Questions / Decisions Needed

| Question | Answer |
|---|---|
| **Protobuf / train pattern placement** — move train pattern detail and `.proto` schemas to Implementation; keep only the "why binary messaging" argument in Conceptual. Confirm? | Yes. The core problem with the initial doc is that material is not properly structured to followo the top level taxonomy  |
| **Agentic framing** — introduce the Actor-as-Agent concept within Conceptual (motivating the whole article), or as a standalone section after all four categories? | make separate actor-agent.md. it will be added to as we go. It will be cross linked with actor-model.md  |
| **Email use case scope** — keep as the running example threaded through all four categories, or treat as a self-contained Logical appendix? | keep as email-use-case.md tobe cross reference from/to actor-model.md and actor-agent.md |
| **Physical section** — currently deferred. Fold into this article or keep separate? | fold into actor-model.md |

---

## Restructuring Session — 2026-03-18

### The New Primary Thesis

> **An [Agent](https://en.wikipedia.org/wiki/Intelligent_agent) is a highly configurable [Actor](https://en.wikipedia.org/wiki/Actor_model) — with an optional LLM/CPM link.**
{: .important}

Not a new concept. Not a special case. An [Actor](https://en.wikipedia.org/wiki/Actor_model) where the behavior function can be wired to a language model or a classical probabilistic model (CPM) instead of deterministic logic. The inbox contract, isolation, and failure containment are all inherited unchanged.

The "Agent layer" is not an architecture layer. It is a behavior configuration choice at the Actor level.

### Key Clarification on Actor Behavior

Actor behavior is **not** business logic. It is 2026 Agent logic of message processing, dispatching, and replying — as it has been since Hewitt 1973. Business logic is what happens inside that processing step. This distinction matters: it means Agents are not a new thing layered on top of Actors — they are Actors, recognised as such.

### Structural Decisions for `index.md`

- `index.md` becomes the single document covering **Conceptual** and **Logical** categories in full.
- Physical and Implementation sections are commented out — may never be revealed at this level.
- The existing `.md` files (`actor-model.md`, `email-use-case.md`, `actor-agent.md`) remain as the knowledge base — deep references, not the primary reading.
- Email use case may be mentioned as a conceptual/logical illustration of Actor topology and messaging only. No Protobuf. No worked-example detail.
- No direct link to `email-use-case.md` from `index.md` — avoid confusing the reader with implementation detail.

### Taxonomy Partitioning

Primary partitioning of content follows the taxonomy categories:

| Category | Content |
|---|---|
| **Conceptual** | Actor anatomy; messages (type/instance/attribute); message passing; no shared state. Then: Agent as configurable Actor, optional LLM/CPM behavior. Synergy argument. |
| **Logical** | Actor topology; state ownership; Train Pattern (concept only); broker placement. Then: Agent at logical level — enters via inbox, narrow scope, translation surface. |
| **Physical** | Commented out |
| **Implementation** | Commented out |

---

## Status (original)

- [x] Agree on structure above
- [x] Draft Conceptual section with Actor topology diagram
- [x] Draft Logical section (migrate + expand current Section 2)
- [x] Draft Physical section
- [x] Draft Implementation section
- [x] Add Mermaid diagrams. As many as needed.
- [x] Final review and then stop. Do not publish anywhere

---

## Status 2026-03-18

- [x] Capitalise Actor and Agent (as concepts) consistently across all `.md` files in this folder: `actor-model.md`, `email-use-case.md`, `actor-agent.md`, `index.md`
- [x] Rewrite `index.md` as the primary document — Conceptual and Logical categories in full, Physical and Implementation commented out
- [x] Conceptual: Actor anatomy, messages, message passing, no shared state — then Agent as configurable Actor with optional LLM/CPM link, synergy argument
- [x] Logical: Actor topology, state ownership, Train Pattern (concept only), broker placement — then Agent at logical level (inbox entry, narrow scope, translation surface)
- [x] Remove email use case as a direct link from `index.md` — mention only as a passing illustration of topology
- [x] Keep `actor-model.md`, `email-use-case.md`, `actor-agent.md` as knowledge base deep references — do not merge them
- [x] Introduce `AgentActor` as the unified concept — Actor and Agent are the same thing
- [x] Introduce binary messaging and selective deserialisation as a key architectural distinction
- [x] Move `actor-agent.md` and `actor-model.md` to `unused/` — superseded by `index.md`
- [x] Update `email-use-case.md` to use `AgentActor` framing throughout
- [x] Remove `AgentActor` suffix from diagram node labels — role name only
- [x] Simplify Messages section — Type / Instance / Attribute, no redundant "Message" prefix
- [ ] Merge branch `agent-actor-model` to `main` when `index.md` is reviewed and approved

---

| <img src="../../assets/dbj/dbj-org-logo.jpg" width="64px" /> | &nbsp; |
|---|---|
| CC BY SA 4.0 | &copy; dbj@dbj.org |
