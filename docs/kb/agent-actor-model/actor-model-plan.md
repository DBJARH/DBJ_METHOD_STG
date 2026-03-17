---
layout: default
title: Actor Model KB — Restructuring Plan
description: Working spec and decision log for restructuring the actor model KB section.
---

# Actor Model KB — Restructuring Plan

This file is a working spec / context document for restructuring `actor-model.md`.

---

## Goal

Restructure the actor model knowledge base article to follow the Iron Code Labs Common Taxonomy — four top-level categories: **Conceptual**, **Logical**, **Physical**, **Implementation**.

The motivating novelty: using safe, fast binary messaging (Protobuf) on top of the actor model as the foundation for a **resilient agentic system**.

---

## Proposed Structure

### Conceptual

- What an actor is (anatomy, inbox, private state, behavior)
- No shared state — the design constraint, not a limitation
- Message passing as the only interaction model (fire-and-forget, async by design)
- Why binary messaging: the case for Protobuf over JSON at actor message volume
- The agentic framing: actors as autonomous agents — resilience through isolation and message-passing contracts

### Logical

- Actor system design for a concrete use case (organisational email management)
- Actor inventory: roles, responsibilities, state ownership
- Actor conversation map: primary message flows
- State ownership summary table
- Protobuf contract summary: key `.proto` message types
- The train pattern as a logical protocol for large payload flows

### Physical

- Actor placement across nodes and process boundaries
- Network topology: which actors are co-located vs. distributed
- Fault domains: actor supervision trees, restart strategies
- Broker placement: selective use of async brokers (Kafka/RabbitMQ/SQS) vs. direct actor-to-actor

### Implementation

- Protobuf schema tooling: `protoc`, generated code, polyglot support
- Schema governance: `buf breaking` enforcement at CI, review and sign-off process
- The train pattern as a concrete wire protocol: HEAD / PACKET / TAIL packet types, sequence numbers, checksum
- `correlation_id` as tracing identifier across actor hops
- Operational concerns: audit log, quota enforcement, dead-letter handling

---

## Mermaid Diagrams Planned

| Diagram | Category | Description |
|---|---|---|
| Actor topology | Conceptual | Single actor: inbox, state, behavior. Basic actor-to-actor message flow. |
| Conversation map | Logical | All actors in the email system, labelled message flows between them. |
| Deployment topology | Physical | Actor placement across nodes, broker position, fault domain boundaries. |
| Schema pipeline | Implementation | `.proto` → `protoc` → generated stubs → `buf breaking` in CI. |

---

## Open Questions / Decisions Needed

| Question | Answer |
|---|---|
| **Protobuf / train pattern placement** — move train pattern detail and `.proto` schemas to Implementation; keep only the "why binary messaging" argument in Conceptual. Confirm? | Yes. The core problem with the initial doc is that material is not properly structured to followo the top level taxonomy  |
| **Agentic framing** — introduce the actor-as-agent concept within Conceptual (motivating the whole article), or as a standalone section after all four categories? | make separate actor-agent.md. it will be added to as we go. It will be cross linked with actor-model.md  |
| **Email use case scope** — keep as the running example threaded through all four categories, or treat as a self-contained Logical appendix? | keep as email-use-case.md tobe cross reference from/to actor-model.md and actor-agent.md |
| **Physical section** — currently deferred. Fold into this article or keep separate? | fold into actor-model.md |

---

## Status

- [x] Agree on structure above
- [x] Draft Conceptual section with actor topology diagram
- [x] Draft Logical section (migrate + expand current Section 2)
- [x] Draft Physical section
- [x] Draft Implementation section
- [x] Add Mermaid diagrams. As many as needed.
- [x] Final review and then stop. Do not publish anywhere

<!-- Standard Footer -->
<div style="clear: both;"></div>
<div style="float: center; margin: 1em; text-align: center;">
<img src="../../assets/icl_logo.png" width="64px" /><br/>
<a href="https://ironcodelabs.ai">&copy; Iron Code Labs Ltd</a>
</div>
