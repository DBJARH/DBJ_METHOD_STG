---
layout: default
title: Actor Model Architecture
description: The actor model as the foundation for resilient distributed and agentic systems — covering the model, a worked email use case, and the agent layer.
---

<div style="float: center; margin: 1em; text-align: center;">
<img src="../../assets/aiwip.png" width="90%" /><br/>
</div>
<div style="clear: both;"></div>

[← Knowledge Base](../index.md)

# Agent-Actor Architecture

Three articles covering the actor model from first principles through to AI agent integration.

## [Actor Model Architecture](actor-model.md)

The foundational reference. Covers the model across all [four taxonomy categories](../../taxonomy_core.md#canonical): what an actor is and why no shared state is a design constraint (Conceptual); actor topology, state ownership, the Train Pattern for large payloads, and broker placement strategy (Logical); actor placement, fault domains, and node topology (Physical); Protobuf schemas, the train wire protocol, and schema governance tooling (Implementation).

---

## [Email Management System — Use Case](email-use-case.md)

A full worked example applying the actor model to organisational email management. Covers the complete actor inventory with state ownership and inbox contracts, actor conversation maps for all primary flows, and the three large-payload flows that use the Train Pattern.

---

## [Actor-Agent Architecture](actor-agent.md)

How AI agents are added externally to an actor-model foundation. Covers the design principle (actors first, agents additive), where agents enter the system, candidate integration points in the email use case, and the constraints that keep agent behaviour isolated and the system predictable. A living document.

---

<div style="float: center; margin: 1em; text-align: center;">
<!-- KB footer -->
<br/>
EA Navigates &trade;
<hr/>
Subject to chang&nbsp;&copy; dbj@dbj.org , CC BY SA 4.0
</div>
<div style="clear: both;"></div>
