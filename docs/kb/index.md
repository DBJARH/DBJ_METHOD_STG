---
layout: default
title: Knowledge Base
description: Iron Code Labs EA knowledge base — structured reference material on enterprise architecture topics
---

# Knowledge Base

Structured reference material on enterprise architecture topics. Each section is a self-contained and can be read independently.

---

## 1 [ICL ADM](icl-adm/icl_adm.md)

The ICL Architecture Development Method — a simplified ADM cycle adapted from TOGAF for organizations without a dedicated architecture team. Covers the phase-to-category mapping, the role of the ICL Taxonomy, ADM deliverables, and the five-step ICL governance wheel.

> The ICL ADM "wheel" delivers architecture. Delivery is what the business authorizes.

---

## 2 [LLM Adoption](llm-adoption/llm-adoption.md)

Enterprise architecture governance framework for introducing Large Language Models into an organization. Covers capability justification, the 4-level decision model, governance checklist, TOGAF ADM integration, and the Architecture Board approval template.

> LLM complexity must be earned, not assumed.

---

## 3 [TOGAF CMM](togaf-cmm/togaf-cmm.md)

The TOGAF Architecture Capability Maturity Model (ACMM) — the EA-practice-focused foundation from which the ICL CMM is derived. Covers the six maturity levels (M0–M5), the nine ACMM characteristics, the scorecard structure, and the M3 prerequisite for running the ICL ADM.

> The TOGAF CMM measures the EA practice. The [ICL CMM](../cmm.md) measures the whole organization.

---

## 4 [ITIL Role](itil/ITIL_role.md)

Establishes ITIL as the alternative benchmarking and standards measurement framework for IT operations within the ICL Method. Clarifies the boundary with TOGAF: TOGAF governs state transition; ITIL measures operational fitness. Covers the Service Value Chain, Four Dimensions, 34 Management Practices, key benchmarking metrics, ADM integration points, and ITIL CMM alignment.

> TOGAF governs the *state transition*. ITIL measures *operational fitness*.

---

## 5 [AI Compliance](ai-compliance/ai-compliance.md)

Enterprise architecture lens on AI regulatory compliance. Covers what the EU AI Act, NIST AI RMF, SOC 2, HIPAA, and SEC guidance each require, and why pre-execution governance is the only architecture that structurally satisfies all five frameworks. The EU AI Act compliance deadline for high-risk AI systems is August 2026.

> Regulators won't ask what your AI did — they will ask whether governance was active and correctly configured.

---

## 6 [AI-Enabled Legacy Solution](ai-enabled-legacy-solution/ai-enabled-legacy-solution.md)

Integration architecture for connecting new AI-enabled systems to existing enterprise knowledge. Covers the New System → Agents → MCP Servers → Legacy Knowledge pattern, the role of LLMs as a peer input (not gateway), MCP Servers as the anti-corruption layer across heterogeneous legacy data sources, and the decoupling principles that keep legacy knowledge authoritative in place.

> The tool contract is the only interface that matters — the Agent never knows what sits behind the MCP Server.

---

## 7 [ANI Is Not AGI](ani_is_not_agi/ani_is_not_agi.md)

Why AGI is an unreachable milestone — and why the distinction matters for the business restarting the AI strategy. Covers the ANI/AGI feature gap, the four strongest arguments against AGI ever existing (stochastic parrots, the Chinese Room, embodiment, the scaling wall), and the governance implication: Enterprise Architecture evaluates capability, not marketing position on a notional AGI scale.

> ANI is real, deployable, and governable. AGI is a philosophical milestone whose reachability is genuinely in dispute.

---

## 8 [Win32 Monolith Modernization](win32-monolith/win32-monolith.md)

Enterprise architecture approach for modernizing a legacy Win32 monolith with a web front end. Covers the Strangler Fig pattern as the governing migration strategy, the Anti-Corruption Layer as Phase 1, progressive service extraction in Phase 2, the recommended stack (.NET 8, Azure SQL, HTMX), and the key constraints to validate before starting.

> The monolith shrinks — it does not get rewritten in one shot.

---

## 9 [DORA AI Capabilities Model](dora/dora.md)

ICL usage of the DORA AI Capabilities Model as AI guidance for software development organizations. Covers the seven capabilities that amplify AI benefits: clear AI strategy, high-quality internal platforms, clean data, developer experience, learning-oriented culture, modular architecture, and user-centric thinking.

> LLM of your choice is your own assistant — but you are accountable for your output.

---

## 10 [Agent-Actor Architecture](agent-actor-model/index.md)

The actor model as the foundation for resilient distributed and agentic systems. Covers the model from first principles through to AI agent integration: actor anatomy, message passing, Protobuf binary contracts, the Train Pattern for large payloads, fault domains, and schema governance. A separate article applies the model to a full organisational email management use case. A third covers how AI agents attach externally — entering the system through typed inboxes as the translation layer between LLM text and Protobuf contracts.

> Actors first. Agents are additive.

--- 

<div style="float: center; margin: 1em; text-align: center;">
<br/>
EA Navigates &trade;
<hr/>
Subject to change, material in this site is <br/>&copy; dbj@dbj.org , CC BY SA 4.0
</div>
<div style="clear: both;"></div>


