---
layout: default
title: Knowledge Base
description: Iron Code Labs EA knowledge base — structured reference material on enterprise architecture topics
---

# Knowledge Base

Structured reference material on enterprise Method and Enterprise Architecture topics. Each section is self-contained and can be read independently.

---

<details markdown="1">
<summary><strong>Conceptual</strong> — Business · Information · Application · Technology</summary>

## [ICL ADM](icl-adm/index.md)

The ICL Architecture Development Method — a simplified ADM cycle adapted from TOGAF for organizations without a dedicated architecture team. Covers the phase-to-category mapping, the role of the ICL Taxonomy, ADM deliverables, and the five-step ICL governance wheel.

> The ICL ADM "wheel" delivers architecture. Delivery is what the business authorizes.
{: .important}

---

## [TOGAF CMM](togaf-cmm/togaf-cmm.md)

The TOGAF Architecture Capability Maturity Model (ACMM) — the EA-practice-focused foundation from which the ICL CMM is derived. Covers the six maturity levels (M0–M5), the nine ACMM characteristics, the scorecard structure, and the M3 prerequisite for running the ICL ADM.

> The TOGAF CMM measures the EA practice. The [ICL CMM](../cmm.md) measures the whole organization.
{: .important}

---

## [Business & Technology Landscapes](Business_Technology_Landscapes/index.md)

Enterprise Full View — the Business and Technology landscapes, and EA's position between them. Covers business capabilities, products and services, information assets, application portfolio, infrastructure, integrations, and the capability mapping EA performs across both landscapes.

> Business declares. Technology implements. EA aligns.
{: .important}

---

## [Business, Product, Technology](Business_Product_Technology/index.md)

The three BPT segments in depth — purpose, boundaries, repositories, and the event-driven handoff model. Covers the ICL ADM wheel's relationship to each segment, the repository as decoupling mechanism, naming conventions (Application vs Product, Engineering vs Technology), and the prerequisites for a functioning loop. Includes the segment articles: [Business](Business_Product_Technology/Buiness.md), [Product](Business_Product_Technology/Product.md), [Technology](Business_Product_Technology/Technology.md).

> The repository is the only channel. Segments never communicate directly.
{: .important}

---

## [Roles, Actors and Jurisdictions](Roles_Actors_Jurisdictions/index.md)

Who works where in the BPT loop — roles, their segment jurisdictions, and the EA overarching role. Covers the boundary between roles and segments, why jurisdiction is not hierarchy, and the Engineering/Technology naming distinction.

> Jurisdiction defines the work, not the person.
{: .important}

---

## [ANI Is Not AGI](ani_is_not_agi/ani_is_not_agi.md)

Why AGI is an unreachable milestone — and why the distinction matters for the business restarting the AI strategy. Covers the ANI/AGI feature gap, the four strongest arguments against AGI ever existing (stochastic parrots, the Chinese Room, embodiment, the scaling wall), and the governance implication: Enterprise Architecture evaluates capability, not marketing position on a notional AGI scale.

> ANI is real, deployable, and governable. AGI is a philosophical milestone whose reachability is genuinely in dispute.
{: .important}

</details>

---

<details markdown="1">
<summary><strong>Logical</strong> — Data Management · Integration · Platform · Security</summary>

## [ITIL Role](itil/ITIL_role.md)

Establishes ITIL as the alternative benchmarking and standards measurement framework for IT operations within the ICL Method. Clarifies the boundary with TOGAF: TOGAF governs state transition; ITIL measures operational fitness. Covers the Service Value Chain, Four Dimensions, 34 Management Practices, key benchmarking metrics, ADM integration points, and ITIL CMM alignment.

> TOGAF governs the *state transition*. ITIL measures *operational fitness*.
{: .important}

---

## [AI-Enabled Legacy Solution](ai-enabled-legacy-solution/ai-enabled-legacy-solution.md)

Integration architecture for connecting new AI-enabled systems to existing enterprise knowledge. Covers the New System → Agents → MCP Servers → Legacy Knowledge pattern, the role of LLMs as a peer input (not gateway), MCP Servers as the anti-corruption layer across heterogeneous legacy data sources, and the decoupling principles that keep legacy knowledge authoritative in place.

> The tool contract is the only interface that matters — the Agent never knows what sits behind the MCP Server.
{: .important}

---

## [Agent-Actor Architecture](agent-actor-model/index.md)

The actor model as the foundation for resilient distributed and agentic systems. Covers the model from first principles through to AI agent integration: actor anatomy, message passing, Protobuf binary contracts, the Train Pattern for large payloads, fault domains, and schema governance. A separate article applies the model to a full organisational email management use case. A third covers how AI agents attach externally — entering the system through typed inboxes as the translation layer between LLM text and Protobuf contracts.

> Actors first. Agents are additive.
{: .important}

---

## [Engagement Architecture](engagement_architecture/index.md)

How ICL structures customer engagements — from the ADM Boot Camp through to a deployable product. Covers the three-party workflow (Business, Product, Engineering), the customer AI layer, IT landscape analysis, and the traceable output back to Business architecture decisions.

> No need to dive into the code if design is wrong.
{: .important}

---

## [AI Compliance](ai-compliance/ai-compliance.md)

Enterprise architecture lens on AI regulatory compliance. Covers what the EU AI Act, NIST AI RMF, SOC 2, HIPAA, and SEC guidance each require, and why pre-execution governance is the only architecture that structurally satisfies all five frameworks. The EU AI Act compliance deadline for high-risk AI systems is August 2026.

> Regulators won't ask what your AI did — they will ask whether governance was active and correctly configured.
{: .important}

</details>

---

<details markdown="1">
<summary><strong>Physical</strong> — Compute · Infrastructure · Network · Storage</summary>

## [LLM Adoption](llm-adoption/llm-adoption.md)

Enterprise architecture governance framework for introducing Large Language Models into an organization. Covers capability justification, the 4-level decision model, governance checklist, TOGAF ADM integration, and the Architecture Board approval template.

> LLM complexity must be earned, not assumed.
{: .important}

---

## [Win32 Monolith Modernization](win32-monolith/win32-monolith.md)

Enterprise architecture approach for modernizing a legacy Win32 monolith with a web front end. Covers the Strangler Fig pattern as the governing migration strategy, the Anti-Corruption Layer as Phase 1, progressive service extraction in Phase 2, the recommended stack (.NET 8, Azure SQL, HTMX), and the key constraints to validate before starting.

> The monolith shrinks — it does not get rewritten in one shot.
{: .important}

</details>

---

<details markdown="1">
<summary><strong>Implementation</strong> — Deployment · Development · Monitoring · Operations</summary>

## [AI Compliance](ai-compliance/ai-compliance.md)

Enterprise architecture lens on AI regulatory compliance. Covers what the EU AI Act, NIST AI RMF, SOC 2, HIPAA, and SEC guidance each require, and why pre-execution governance is the only architecture that structurally satisfies all five frameworks. The EU AI Act compliance deadline for high-risk AI systems is August 2026.

> Regulators won't ask what your AI did — they will ask whether governance was active and correctly configured.
{: .important}

---

## [Win32 Monolith Modernization](win32-monolith/win32-monolith.md)

Enterprise architecture approach for modernizing a legacy Win32 monolith with a web front end. Covers the Strangler Fig pattern as the governing migration strategy, the Anti-Corruption Layer as Phase 1, progressive service extraction in Phase 2, the recommended stack (.NET 8, Azure SQL, HTMX), and the key constraints to validate before starting.

> The monolith shrinks — it does not get rewritten in one shot.
{: .important}

---

## [DORA AI Capabilities Model](dora/dora.md)

ICL usage of the DORA AI Capabilities Model as AI guidance for software development organizations. Covers the seven capabilities that amplify AI benefits: clear AI strategy, high-quality internal platforms, clean data, developer experience, learning-oriented culture, modular architecture, and user-centric thinking.

> LLM of your choice is your own assistant — but you are accountable for your output.
{: .important}

---

## [How to Document Software Architecture](documenting-architecture/index.md)

Appraisal of *Documenting Software Architectures: Views and Beyond, 2nd Edition* (Clements et al., SEI, 2010). Covers the three-viewtype framework (Module, C&C, Allocation), stakeholder-driven view selection, interface and rationale documentation, and how the book stands against lighter modern frameworks (C4, arc42, ADRs).

> Read it to understand the foundations; return to it when the lighter framework runs out of answers.
{: .important}

---

## [ISO27001 != GDPR Compliance](ISO27001/ISO27001.md)

**ISO 27001 is not sufficient for full GDPR compliance** because it focuses on information security management (the CIA triad) rather than the legal, data privacy rights mandated by GDPR. While ISO 27001 provides a robust framework for technical safeguards and risk management, it lacks GDPR-specific requirements like consent management, data subject access requests (DSARs), and strict legal bases for processing.

> ISO27001 != GDPR Compliance
{: .important}

</details>

---

> © dbj@dbj.org , CC BY SA 4.0
