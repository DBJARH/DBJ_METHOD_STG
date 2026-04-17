---
layout: default
title: Technology — BPT
description: The Technology segment of the BPT loop — implementation, the Engineering roles, and the Evaluate feedback.
---

[← Business, Product, Technology](index.md)

# Technology

**Technology** is the third segment of the BPT loop. It is where the organisation builds, deploys, and operates what Product has defined.

Technology does not declare and it does not align. It implements.

---

## What happens in Technology

Technology monitors the **Product repository**. When the Product segment places Logical and Physical specifications there — interface contracts, data models, deployment constraints — the Technology segment picks them up and acts.

Acting means: building, deploying, and operating the product. Applications, infrastructure, integrations, pipelines. These are the Physical and Implementation-level realisations of what Product specified.

Technology does not reach back into Product to renegotiate the specification. It works with what the Product repository contains. Where a specification is ambiguous or incomplete, that is a signal back to Product — not a licence to improvise.

---

## Technology Artifacts

Technology Artifacts are the Physical and Implementation-level outputs produced inside the Technology segment — and also the Physical/Implementation deliverables the DBJ ADM wheel places directly into the Technology repository.

- **Deployed applications** — running software that implements declared products
- **Infrastructure** — containerised platforms, cloud placements, network configuration
- **Integrations** — APIs, data pipelines, and event streams connecting systems
- **Operations artefacts** — runbooks, monitoring configuration, SLA definitions

---

## "Engineering" and "Technology"

The roles inside this segment are Engineers and Developers — the people who build and run things. The BPT segment that contains them is called **Technology**. Engineering describes the roles; Technology is the segment name. Throughout this KB, Technology is always the segment name.

---

## The Evaluate feedback

Technology is not a terminal segment. After Deploy, the loop continues: **Evaluate**. Operational outcomes — performance data, incident patterns, user feedback, cost — are the input to Evaluate. Evaluate feeds back to Business, closing the loop and informing the next Require.

Technology owns the signal. Business interprets it. EA ensures the feedback is visible and acted on.

---

## The boundary

Technology owns the *how it is built and run*. It does not own what is built (Business) or what the specifications are (Product). Architectural decisions that surface during Technology work — structural changes to the product, new capability requirements — are escalated to EA, not resolved inside the Technology segment.

---

| <img src="../../assets/dbj/dbj-org-logo.jpg" width="64px" /> | &nbsp; |
|---|---|
| CC BY SA 4.0 | &copy; dbj@dbj.org |
