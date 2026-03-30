---
layout: default
title: How to Document Software Architecture
description: Practical frameworks for documenting software architecture — C4, arc42, and ADRs.
---

[← Knowledge Base](../index.md)

# How to Document Software Architecture

The theoretical foundation is well established — see *Documenting Software Architectures: Views and Beyond, 2nd Edition* (Clements et al., SEI, 2010): [SEI library](https://www.sei.cmu.edu/library/documenting-software-architectures-views-and-beyond-second-edition/) · [InformIT](https://www.informit.com/store/documenting-software-architectures-views-and-beyond-9780321552686) · [Google Books](https://books.google.com/books?id=UTZbsrA4qAsc). The book introduced the three-viewtype framework (Module, Component-and-Connector, Allocation) and stakeholder-driven view selection. It remains the rigorous reference. It is not a practical handbook for modern delivery teams.

The frameworks below are.

---

## C4 Model

**Author:** Simon Brown, 2018
**Reference:** [c4model.com](https://c4model.com)

Four diagram types, four audiences, one consistent notation:

| Level | [ICL Taxonomy](../../taxonomy.md) | Audience | Shows |
|---|---|---|---|
| Context | Conceptual | Business, non-technical | System in its environment — users and external dependencies |
| Container | Logical | Architects, developers | Major deployable units — apps, databases, services |
| Component | Physical | Developers | Internal structure of a single container |
| Code | Implementation | Developers | Classes, interfaces — usually auto-generated |

Start at Context and stop at the level your audience needs. Most conversations are resolved at Container. Code-level diagrams are almost never worth maintaining by hand.

> The term "Container" is unfortunate — since 2013 it reads as Docker container to most engineers, which is one specific deployment technology, not the general concept C4 intends. A clearer synonym is **Deployable Unit**: it captures the essential meaning (something that runs independently and communicates over a network) without the Docker collision. When introducing C4 to a team, use "Deployable Unit" in conversation and reserve "Container" only when citing the C4 spec directly.
{: .note}

C4 uses a simple, tool-agnostic notation. Diagrams can be produced in any diagramming tool or as code via [Structurizr](https://structurizr.com) (Brown's own tool) or the [C4-PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML) library.

> Four diagrams cover most of what teams actually need to communicate.

---

## arc42

**Authors:** Gernot Starke and Peter Hruschka
**Reference:** [arc42.org](https://arc42.org)

arc42 is a lean, structured template for architecture documentation — twelve sections covering context, solution strategy, building blocks, runtime, deployment, decisions, quality, and risks. It is worth knowing it exists.

Teams working within the [ICL ADM](../../kb/icl-adm/index.md) should not adopt arc42 as a documentation structure. The ICL ADM already defines the documentation scaffold through its phases and deliverables; introducing arc42 alongside it creates two competing structures for the same content. arc42 is designed for teams without a governing ADM — it fills the gap that TOGAF and ICL ADM already fill here.

> Know it. Do not use it here.

---

## Architecture Decision Records (ADRs)

**Origin:** Michael Nygard, 2011
**Reference:** [adr.github.io](https://adr.github.io)

An ADR captures one decision: the context that forced it, the options considered, the decision taken, and its consequences.

**Within the ICL ADM, ADRs are redundant at the architecture level.** The ICL ADM produces hierarchical requirements with decisions already embedded as deliverables — that is precisely what an ADR is attempting to construct from scratch. Where a governing requirements hierarchy exists, ADRs duplicate it.

The more accurate name for what development teams actually use them for is **Development Decision Records (DDRs)**: a way to trace code-level choices back to architecture. That is a legitimate and useful practice — but it belongs entirely within the Development aka [Technology segment](../Business_Product_Technology/Technology.md) of the [BPT](../Business_Product_Technology/index.md). DDRs are a private engineering artefact, disconnected from the BPT flow. Architecture does not read them; they are a breadcrumb trail for the dev. team that owns the code.

> If the team wants DDRs, that is fine. They are internal to Development and invisible to the BPT loop.

**Tooling:** [adr-tools](https://github.com/npryce/adr-tools) (CLI), [Log4brains](https://github.com/thomvaill/log4brains) (web UI), or plain files in a `/decisions` folder.

---

## In Practice

| Concern | Tool |
|---|---|
| Visual communication across levels | C4 |
| Documentation structure and decision hierarchy | ICL ADM deliverables |
| Code-level traceability (Development only) | DDRs (ADRs repurposed) |

***A minimal viable documentation practice*** within the ICL ADM: C4 Context and Container diagrams for stakeholder communication, ICL ADM deliverables for decisions and requirements. DDRs are optional and internal to the Development team.

---

> © dbj@dbj.org , CC BY SA 4.0
