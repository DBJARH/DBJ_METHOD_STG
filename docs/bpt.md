---
layout: default
title: The BPT Loop
description: Business, Product, Technology — the ICL operational methodology governing continuous delivery.
---

## Why the BPT Loop

>The underlying idea of ICL Method is to make simplified TOGAF artifacts, into the framework for feasible business management method.
{: .note}
* We transform Business Roles central, accountable and responsible to the conceptual architecture
  * We do this by onboarding them on simplified [Maturity Model](cmm.md)
  * Abbreviated name ICL CMM
* To make the [TOGAF ADM](https://en.wikipedia.org/wiki/The_Open_Group_Architecture_Framework) malleable to the business, we use the simplified version in which the business drives, not EA. 
    * TOGAF ADM is central structure for Enterprise Architecture projects, used by (many) Enterprise Architects producing only EA Artifacts
  * We have simplified the (TOGAF) ADM wheel into the [Development Management Concept](kb/icl-adm/index.md) where Business is driving.
  * Name is abbreviated to ICL ADM 
* At the helm of ICL ADM "wheel" is the business. Enterprise Architecture is "just" the navigator.
  * That is unlike TOGAF ADM, that is a domain of Enterprise Architects, producing EA Artifacts only.
* The core necessity of the BPT is to make the ICL ADM products easy to digest and use by the three key segments of any organisation: 
  * Business
  * Product
  * Technology

## The BPT Loop

> Continuous Product-Centric Cycle
{: .tip}

![](bpt_assets/bpt-meta-loop-simple.png)

The BPT Loop is the ICL operational methodology 

* **Business** — market strategy, stakeholders, and business owners — declares intent. 
* **Product** — the specification and delivery management layer — is the alignment point between them, decoupling each so both can evolve independently, while coupling them so delivery is coherent and traceable. 
* **Technology** — engineering and development teams — implements to product specifications.

The three segments are decoupled. That makes roles responsibilities clearly separated.

> Example: Business Analyst (EA) works inside the "Product" segment. It is informed by "Business" segment deliverables on WHAT is required, then it creates workflow diagrams to translate *what* into *how* , but only until the implementation. That is the responsibility of the "Technology" roles, operating in the "Technology" segment. And each of the roles mentioned has many other duties and "jurisdictions" completely encapsulated in their fields of expertise.
{: .note}

Each segment has a **repository** — a persistent store for the deliverables that belong to it. The [ICL ADM wheel](kb/icl-adm/index.md) does not hand deliverables to roles directly; it places them in the correct segment repository. Roles watch their repository; they never watch the wheel directly. This is what keeps the wheel and the segments decoupled.

> ADM deliverables by segment: Business receives Conceptual outputs. Product receives Logical and Physical outputs. Technology receives Physical and Implementation outputs.
{: .note}

Enterprise Architecture (EA) governs the loop from above. It does not participate in delivery — it defines the principles, governs the transitions, and measures alignment health through the Evaluate feedback.

> The entry ticket to the BPT cycle is [ACMM Level 3](cmm.md#levels). That is the precondition for smooth cycling and delivery.
{: .important}

---

## The Four Activity Streams

| Activity Stream | Intent | Key Roles |
|----------|--------|------------|
| **Require** | Business declares product needs; EA ensures alignment with strategy | Business, EA |
| **Develop** | Technology builds to product specifications; EA governs coherence | Technology, Product, EA |
| **Deploy** | Product is released into operations; EA validates architecture compliance | Technology, Product, EA |
| **Evaluate** | Measure outcomes against business objectives; feed back into next cycle | Business, Product, EA |

Evaluate Stream feeds back to Business so the next Require can commence — the loop never stops.

> **Product unifies; Loop validates.**
{: .tip}

---

## Bridge from EA to Return on Investment (ROI)

BPT is Architecture Governance as a productized execution model. The BPT Loop does not replace the ADM "Wheel" — it is the operational framework that the ADM governs. The [ICL ADM wheel](kb/icl-adm/index.md) runs inside the EA governance layer above BPT, producing the deliverables that the three segments consume.

<div markdown="1" style="text-align:center;">
<img src="bpt_assets/bpt-meta-loop-complex.png" style="width:75%;" />
</div>

## BPT Loop Segments Explained

- [Conceptual Foundations](kb/Business_Technology_Landscapes/)
- [Business, Product, Technology](kb/Business_Product_Technology/index.md) — the three segments in depth: boundaries, repositories, and the four Activity Streams
- [Roles, Actors and Jurisdictions](kb/Roles_Actors_Jurisdictions/index.md) — who works where in the BPT loop and why
- [ICL ADM](kb/icl-adm/index.md) — the governance ADM (aka wheel) that operates above BPT
- [CMM](cmm.md) — the maturity prerequisite



> © dbj@dbj.org , CC BY SA 4.0
