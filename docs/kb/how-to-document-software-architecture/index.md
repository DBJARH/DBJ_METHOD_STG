---
layout: default
title: How to Document Software Architecture
description: ICL approach to software architecture documentation — simpler and better than legacy ways.
---

[← Knowledge Base](../index.md)

# How to Document Software Architecture

Documenting software architecture is not about choosing a notation or filling a template. It is about communicating the right structure to the right audience at the right level of abstraction.

> We do not mandate symbology
{: note}

Every diagram can indeed use only boxes and arrows. That is not the point. Neither is a symbology what we mandate. The point is that **each diagram represents one level of abstraction** — and that level defines what a box means. The same box symbol means a System at the Conceptual level, a Product at the Logical level, a Module at the Physical level, and a Deployment Unit at the Implementation level. Although it is not "forbiden", mixing levels on one diagram can destroy the meaning of it.

Existing industry visualisation frameworks — C4, arc42 — do not follow these principles consistently. They are reviewed in [Legacy Ways of Software Documenting](legacy_ways_of_softwae_documenting.md).

<p id="partitioning">&nbsp;</p>

> We favour visualisation that follows partioning logic. Which is based on ICL Taxonomy.

### Logical and physical partitioning

| Abstraction Level | Digrams Shows | As Made of | Comment |
|---|---|---|---|
| [Conceptual](../../taxonomy.md#conceptual) | Business Landscape | Systems | Non-functional view. In the wider environment of the [commercial enterprise](../../enterprise_architecture.md) |
| [Logical](../../taxonomy.md#logical) | Systems Landscape | Components | Usualy systems are made of products and other components. They exist as a re-action to business requirements |
| [Physical](../../taxonomy.md#physical) | Components Landscape | Modules | Fuctional view. Modules exhibit functional end points|
| [Implementation](../../taxonomy.md#implementation) | Modules Landscape | End Points | Functional End Points are implemented as APIs. Code is behind API's|


## The level of abstraction defines a diagram's context

---

> © dbj@dbj.org , CC BY SA 4.0
