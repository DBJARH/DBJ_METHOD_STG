---
layout: default
title: Business — BPT
description: The Business segment of the BPT loop — declaration, ADM wheels, and the boundary with Product.
---

[← Business, Product, Technology](index.md)

# Business

**Business** is the first segment of the BPT loop. It is where the organisation declares intent — what it needs, what it sells, and what capabilities it must develop or sustain.

Business does not implement. It declares. Everything the Business segment produces is an input to Product.

---

## What happens in Business

The [ICL ADM wheel](../icl-adm/icl_adm.md) operates in the EA governance layer — above BPT, not inside any segment. It is the project container. It spans the full Taxonomy and produces artifacts at every level. Business, Product, and Technology consume those artifacts according to their jurisdiction.

---

## Business Artifacts

**Business Artifacts** are the Conceptual-level outputs of the ICL ADM wheel — the artifacts that belong to the Business segment's jurisdiction. They declare intent; they are not designs or implementations.

- **Principles** — the constraints and non-negotiables that govern the engagement
- **Architecture Vision** — business case, scope, stakeholder sign-off
- **Business Architecture** — capability map, product declarations, information assets

See [ICL Project Deliverables](../icl-adm/icl_adm.md#icl-project-deliverables) for the full deliverable list.

Business Artifacts are placed in the **Business repository** — the persistent store of Conceptual-level ICL ADM deliverables for this segment. Product segment monitors the Business segment repository and picks up what arrives there.

>This is architectural decoupling, not organisational ignorance. 
{: .important}

Business roles are of course aware of Product and Technology — organisations are not compartments. What the repository enforces is that the **formal architectural handoff** goes through a governed, persistent, auditable mechanism rather than through informal channels, meetings, or direct requests. The repository is the boundary that EA governs; what happens between people is outside its scope.

---

## The conceptual boundary

Business owns the *what* and the *why*. It does not touch the *how*. Technology and implementation concerns that surface during Business architecture work are not resolved in the Business Architecture step — they are logged as requirements and passed to the ADM's central [Requirements Management](../icl-adm/icl_adm.md#requirements-management) entity. Every subsequent ADM step begins by re-checking requirements left there by previous steps. The wheel resolves them at the appropriate step and Taxonomy Category; the Business layer does not.

---

## BPT is event driven

The Business segment always contains at least one wheel. In larger organisations or complex engagements it contains many — each scoped to a domain or capability cluster, all governed by EA. See [One wheel or many](../icl-adm/icl_adm.md#one-or-many) for the full treatment. The BPT loop is event-driven — the event is a wheel deliverable.

A wheel that produces a purely Conceptual outcome — strategy, compliance assessment, capability map — completes without triggering P or T segments. When a wheel deliverable declares a product, it triggers the Product segment. Product's output in turn triggers Technology. 

---

> EA Navigator ™ /  © dbj@dbj.org , CC BY SA 4.0
