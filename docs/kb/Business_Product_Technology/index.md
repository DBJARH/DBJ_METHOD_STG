---
layout: default
title: Business, Product, Technology
description: The three BPT segments explained — structure, boundaries, repositories, and the four Activity Streams.
---

[← Knowledge Base](../index.md)

# Business, Product, Technology

The [BPT loop](../../bpt.md) operates across three segments: Business, Product, and Technology. This section explains each segment in depth — its purpose, its boundary, and what it consumes and produces.

The conceptual foundation — what Business and Technology landscapes contain, and EA's position between them — is established in the [Business & Technology Landscapes](../Business_Technology_Landscapes/index.md) article. This section builds on that foundation.

---

## The three segments

| Segment | Role | Taxonomy level |
|---------|------|---------------|
| [Business](Buiness.md) | Declares intent — what the organisation needs, sells, and can do | Conceptual |
| [Product](Product.md) | Aligns Business declarations with Technology — the decoupling/coupling point | Logical / Physical |
| [Technology](Technology.md) | Implements what Product defines | Physical / Implementation |

Each segment has defined roles, boundaries, and artifacts. No segment reaches into another — handoff is through the repository model below.

---

## The BPT Repository Model

ADM and BPT are decoupled by three ADM Deliverables Repositories — one per segment. Each repository is passive storage. It does not signal; it stores. B, P, and T repositories are conceptual/logical entities; how they are physically realised is an implementation decision left to the organisation.

The [ICL ADM wheel](../icl-adm/index.md) operates in the EA governance layer above BPT. Its deliverables land in the repository of the segment whose jurisdiction matches the deliverable's Taxonomy Category:

| Deliverable Category | Repository | Segment |
|---|---|---|
| Conceptual | Business repository | B |
| Logical / Physical | Product repository | P |
| Physical / Implementation | Technology repository | T |

The BPT loop itself is driven by the four Activity Streams. Activity Streams are the conceptual signaling mechanism between B, P, and T — distinct from the repositories, and distinct from the Activities that Roles perform inside each segment.

EA defines the repository structure, the naming, and the categorisation. It does not dictate how Product builds software or how Technology operates infrastructure.

---

## ADM and the Wheel

"Wheel" is the operational term for an ICL ADM cycle in motion. ADM is the formal governance term. Both coexist: ADM when referencing the formal structure and deliverables, Wheel when describing the operational motion. The deliverables are always ADM deliverables — the wheel is simply how the ADM runs.

---

## ADM Wheel and BPT Segments

The ICL ADM wheel governs from above. Its steps produce deliverables that land in the correct BPT repository by Taxonomy Category. The BPT loop runs continuously below.

![](../../bpt_assets/bpt-meta-loop-complex.png)

---

## Reading the diagram

**Everything shown is Conceptual Architecture.** No physical database is required or implied. The cylinder shapes are a conventional notation for persistent storage — used here because readers immediately recognise them as "something is stored here." What they represent is the **persistent repository of ICL ADM deliverables** for each segment. How an organisation physically realises that persistence is an implementation decision outside this model.

**"Application" and "Product" name the same layer.**
The diagram uses the TOGAF ADM term — Application Layer. The BPT operational term for the same position is Product. Both are correct in their context. Throughout this KB, "Product" is used as the operational name for that segment and its repository.

**"Engineering" and "Technology" name the same segment.**
The diagram labels the operational actor in the T circle as Engineering — the people who build and run things. The BPT segment that contains them is called Technology. The segment name is always Technology; Engineering describes the roles inside it.

**The repositories are the decoupling mechanism.**
The ADM wheel does not hand deliverables to people — it places them in the repository of the segment whose [Taxonomy](https://ea.ironcodelabs.com/taxonomy.html) Category matches the deliverable. Roles watch their repository, not the wheel. Segments never communicate directly.

**Prerequisites.**
The BPT loop assumes organisational readiness: established capabilities, governance, and stakeholder management. The entry condition is [ACMM Level 3](../../cmm.md). Below that threshold the loop cannot sustain itself.

---

| <img src="../../assets/dbj/dbj-org-logo.jpg" width="64px" /> | &nbsp; |
|---|---|
| CC BY SA 4.0 | &copy; dbj@dbj.org |
