---
layout: default
title: Business & Technology Landscape
description: Clickable EA landscape diagram — Business and Technology landscapes aligned by Enterprise Architecture.
---

[← Knowledge Base](../index.md)

# Enterprise Architecture — Business & Technology Landscape

Click any box in the diagram to jump to its explanation.

---

<svg width="100%" height="500" viewBox="0 0 680 500" xmlns="http://www.w3.org/2000/svg" style="background:#fff;">
<defs>
  <marker id="arrow" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
    <path d="M2 1L8 5L2 9" fill="none" stroke="#000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
  </marker>
  <style>
    .node { cursor: pointer; }
    .node:hover rect { opacity: 1; stroke-width: 1.2; }
    .box-title { font-family: sans-serif; font-size: 14px; font-weight: 500; fill: #000; }
    .box-sub   { font-family: sans-serif; font-size: 12px; font-weight: 400; fill: #000; opacity: 0.65; }
    .label     { font-family: sans-serif; font-size: 13px; font-weight: 500; fill: #000; }
    .small     { font-family: sans-serif; font-size: 11px; fill: #000; opacity: 0.5; }
  </style>
</defs>

<!-- Business landscape container -->
<rect x="30" y="30" width="270" height="300" rx="10" fill="none" stroke="#000" stroke-width="1" stroke-dasharray="6 4" opacity="0.5"/>
<text class="label" x="165" y="22" text-anchor="middle" dominant-baseline="central">Business landscape</text>

<a href="#business-capabilities"><g class="node">
  <rect x="50" y="50" width="230" height="52" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.7"/>
  <text class="box-title" x="165" y="69" text-anchor="middle" dominant-baseline="central">Business capabilities</text>
  <text class="box-sub"   x="165" y="88" text-anchor="middle" dominant-baseline="central">What the org can do</text>
</g></a>

<a href="#products-and-services"><g class="node">
  <rect x="50" y="115" width="230" height="52" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.7"/>
  <text class="box-title" x="165" y="134" text-anchor="middle" dominant-baseline="central">Products &amp; services</text>
  <text class="box-sub"   x="165" y="153" text-anchor="middle" dominant-baseline="central">Declared by business</text>
</g></a>

<a href="#business-processes"><g class="node">
  <rect x="50" y="180" width="230" height="52" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.7"/>
  <text class="box-title" x="165" y="199" text-anchor="middle" dominant-baseline="central">Business processes</text>
  <text class="box-sub"   x="165" y="218" text-anchor="middle" dominant-baseline="central">How value is delivered</text>
</g></a>

<a href="#information-assets"><g class="node">
  <rect x="50" y="245" width="230" height="52" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.7"/>
  <text class="box-title" x="165" y="264" text-anchor="middle" dominant-baseline="central">Information assets</text>
  <text class="box-sub"   x="165" y="283" text-anchor="middle" dominant-baseline="central">Data with business value</text>
</g></a>

<!-- Technology landscape container -->
<rect x="380" y="30" width="270" height="300" rx="10" fill="none" stroke="#000" stroke-width="1" stroke-dasharray="6 4" opacity="0.5"/>
<text class="label" x="515" y="22" text-anchor="middle" dominant-baseline="central">Technology landscape</text>

<a href="#application-portfolio"><g class="node">
  <rect x="400" y="50" width="230" height="52" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.7"/>
  <text class="box-title" x="515" y="69" text-anchor="middle" dominant-baseline="central">Application portfolio</text>
  <text class="box-sub"   x="515" y="88" text-anchor="middle" dominant-baseline="central">Implements business products</text>
</g></a>

<a href="#infrastructure"><g class="node">
  <rect x="400" y="115" width="230" height="52" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.7"/>
  <text class="box-title" x="515" y="134" text-anchor="middle" dominant-baseline="central">Infrastructure</text>
  <text class="box-sub"   x="515" y="153" text-anchor="middle" dominant-baseline="central">Containerised platforms</text>
</g></a>

<a href="#integrations"><g class="node">
  <rect x="400" y="180" width="230" height="52" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.7"/>
  <text class="box-title" x="515" y="199" text-anchor="middle" dominant-baseline="central">Integrations</text>
  <text class="box-sub"   x="515" y="218" text-anchor="middle" dominant-baseline="central">APIs and data flows</text>
</g></a>

<a href="#technology-debt"><g class="node">
  <rect x="400" y="245" width="230" height="52" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.7"/>
  <text class="box-title" x="515" y="264" text-anchor="middle" dominant-baseline="central">Technology debt</text>
  <text class="box-sub"   x="515" y="283" text-anchor="middle" dominant-baseline="central">Gaps and consolidation items</text>
</g></a>

<!-- Aligned by EA arrow -->
<line x1="302" y1="180" x2="378" y2="180" stroke="#000" stroke-width="1" marker-end="url(#arrow)" marker-start="url(#arrow)" opacity="0.7"/>
<text class="small" x="340" y="170" text-anchor="middle" dominant-baseline="central">aligned by EA</text>

<!-- Arrows down to EA box -->
<line x1="165" y1="332" x2="165" y2="388" stroke="#000" stroke-width="1" marker-end="url(#arrow)" opacity="0.6"/>
<line x1="515" y1="332" x2="515" y2="388" stroke="#000" stroke-width="1" marker-end="url(#arrow)" opacity="0.6"/>

<!-- EA box -->
<rect x="30" y="390" width="620" height="96" rx="10" fill="none" stroke="#000" stroke-width="1" opacity="0.7"/>
<text class="label" x="340" y="410" text-anchor="middle" dominant-baseline="central">Enterprise architecture — alignment &amp; consolidation</text>

<a href="#capability-mapping"><g class="node">
  <rect x="50" y="424" width="170" height="48" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.6"/>
  <text class="box-title" x="135" y="442" text-anchor="middle" dominant-baseline="central">Capability mapping</text>
  <text class="box-sub"   x="135" y="460" text-anchor="middle" dominant-baseline="central">Business ↔ tech</text>
</g></a>

<a href="#governance"><g class="node">
  <rect x="255" y="424" width="170" height="48" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.6"/>
  <text class="box-title" x="340" y="442" text-anchor="middle" dominant-baseline="central">Governance</text>
  <text class="box-sub"   x="340" y="460" text-anchor="middle" dominant-baseline="central">Standards and principles</text>
</g></a>

<a href="#roadmap"><g class="node">
  <rect x="460" y="424" width="170" height="48" rx="6" fill="none" stroke="#000" stroke-width="0.5" opacity="0.6"/>
  <text class="box-title" x="545" y="442" text-anchor="middle" dominant-baseline="central">Roadmap</text>
  <text class="box-sub"   x="545" y="460" text-anchor="middle" dominant-baseline="central">Target state planning</text>
</g></a>

<!-- Arrows from EA title to sub-boxes -->
<line x1="135" y1="418" x2="135" y2="422" stroke="#000" stroke-width="0.8" marker-end="url(#arrow)" opacity="0.5"/>
<line x1="340" y1="418" x2="340" y2="422" stroke="#000" stroke-width="0.8" marker-end="url(#arrow)" opacity="0.5"/>
<line x1="545" y1="418" x2="545" y2="422" stroke="#000" stroke-width="0.8" marker-end="url(#arrow)" opacity="0.5"/>

</svg>

---

## Overview

The model has three obligations.

**Business Landscape** declares intent — strategy, products, capabilities, and accountability. It must be internally consolidated: no duplicate ownership, no conflicting product definitions, no orphaned processes.

**Technology Landscape** implements what business declares — applications, data, infrastructure, and operations. It too must be internally consolidated: rationalised application portfolio, no redundant platforms, consistent standards.

**EA's role** sits between them with three specific duties: align, consolidate, and govern. Technology constraints inform what business can declare, and business change drives technology evolution.

The key principle: *business declares the product, technology implements it*. EA ensures that chain is intact, traceable, and free of drift in both directions.

---

## Business Landscape

### Business capabilities {#business-capabilities}

A business capability is a stable expression of **what the organisation can do** — independent of how it is done or who does it. Capabilities change slowly; they survive organisational restructures and technology replacements.

EA uses capability maps as the primary bridge to the technology landscape. Each capability must be owned, funded, and traceable to at least one technology realisation. Gaps and overlaps in capability coverage are primary inputs to the roadmap.

### Products & services {#products-and-services}

Products and services are **declared by business** — not by IT. The business states what it sells or delivers; technology implements that declaration. This is the core decoupling principle.

EA's role is to ensure every declared product has a traceable implementation in the application portfolio, and that no technology component exists without a corresponding business product or capability to justify it.

### Business processes {#business-processes}

Processes describe **how value is delivered** — the sequenced activities, decisions, and handoffs that turn a capability into an outcome. They sit between capabilities (what) and applications (how it is automated).

EA governs process at the level of integration points and handoffs — where processes cross system or organisational boundaries. Process sprawl and duplication are consolidation targets.

### Information assets {#information-assets}

Information assets are **data with recognised business value** — customer records, contracts, product catalogues, financial transactions. They are owned by the business, not by the systems that store them.

EA maintains a canonical data model that defines authoritative sources for each asset class. Duplication of authoritative data across systems is technology debt.

---

## Technology Landscape

### Application portfolio {#application-portfolio}

The application portfolio is the set of software systems that **implement business products and capabilities**. Each application must be justified by a business capability or product; applications without a business owner are consolidation candidates.

EA governs the portfolio by maintaining a current-state inventory, assessing fitness-for-purpose, identifying redundancy, and driving rationalisation. The target state is the smallest portfolio that fully covers declared business needs.

### Infrastructure {#infrastructure}

Infrastructure provides the **containerised platforms** on which applications run. The preference for containerisation decouples application deployment from underlying hardware and simplifies consolidation.

EA sets infrastructure standards — container orchestration, networking, storage, and cloud placement. Infrastructure decisions must be driven by application requirements, not by vendor relationships or historical inertia.

### Integrations {#integrations}

Integrations are **APIs and data flows** that connect applications to each other and to external parties. They are first-class architecture artefacts — not afterthoughts.

EA governs integration by enforcing API-first design, maintaining an integration catalogue, and preventing point-to-point sprawl. Every integration must have a defined contract, owner, and SLA.

### Technology debt {#technology-debt}

Technology debt records **gaps and consolidation items** — the delta between the current state and the target state. It includes unsupported platforms, redundant applications, undocumented integrations, missing security controls, and deferred standards adoption.

EA owns the technology debt register and ensures it is visible to business stakeholders. Debt items feed directly into the roadmap as prioritised remediation work.

---

## Enterprise Architecture Functions

### Capability mapping {#capability-mapping}

Capability mapping is the EA practice of **connecting business capabilities to technology components**. It makes the alignment between the two landscapes explicit and auditable.

A capability map answers: which applications support this capability? Which capabilities are unsupported or over-supported? Where does technology investment align with business priority, and where does it not?

### Governance {#governance}

EA governance establishes the **standards and principles** that both landscapes must conform to. It is not a committee — it is a set of enforceable decisions about technology choices, integration patterns, data ownership, and architectural style.

Governance outputs include architecture principles, technology standards, reference architectures, and decision records. Compliance is verified at project initiation and design review gates.

### Roadmap {#roadmap}

The EA roadmap is the **target state plan** — the sequenced programme of work that moves the organisation from its current architecture to its target architecture.

It is derived from three inputs: business strategy (where the business is going), technology debt (what needs fixing), and capability gaps (what is missing). The roadmap is the primary instrument by which EA translates alignment into funded delivery.

---

EA Navigates ™ / Subject to change&nbsp;© dbj@dbj.org , CC BY SA 4.0
