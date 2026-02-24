# Capability Maturity Model (CMM)

## Contents

- [Capability Maturity Model (CMM)](#capability-maturity-model-cmm)
  - [Contents](#contents)
  - [Why CMM](#why-cmm)
  - [What is CMM](#what-is-cmm)
  - [Components of the ACMM](#components-of-the-acmm)
  - [Maturity Levels](#maturity-levels)
  - [Nine ACMM Characteristics](#nine-acmm-characteristics)
  - [ACMM as Foundational Capability for ADM Actors](#acmm-as-foundational-capability-for-adm-actors)
    - [Organisational Capability Implications](#organisational-capability-implications)
  - [Maturity Building Strategy](#maturity-building-strategy)
  - [Conclusion](#conclusion)
  - [History](#history)

>[!NOTE] Formal foundations are firmly embedded in the TOGAF CMM:
> https://www.opengroup.org/architecture/0310wash/presents/Judith_Jones-Maturity_Models.pdf
>

![](assets/TOGAF_CMM.png)
Classic TOGAF CMM enabled organization diagram


## Why CMM

Organizations seeking effective methods to enhance their business/technology processes and gain better control over their architectural endeavours benefit from the Architecture Capability Framework, deeply rooted in CMM and embedded within TOGAF. This framework provides a structured approach to gradually improve Technology-related processes. The central vehicle is the [Architecture Capabilities Maturity Model (ACMM)](https://pubs.opengroup.org/togaf-standard/architecture-maturity-models/).

## What is CMM

TOGAF's Architecture Capability Framework draws inspiration from various CMM variants, each tailored to specific aspects of organisational processes:

- **CMMI** — Capability Maturity Model Integration
- **SA-CMM** — Software Acquisition CMM
- **SE-CMM** — Systems Engineering CMM
- **P-CMM** — People CMM
- **ACMM** — [Enterprise Architecture Capabilities Maturity Model](https://pubs.opengroup.org/togaf-standard/architecture-maturity-models/)

## Components of the ACMM

The ACMM comprises three main sections:

1. **Architecture Maturity Model** — defines six maturity levels (M0–M5) across nine key architecture characteristics
2. **Architecture Characteristics at Different Maturity Levels** — provides comprehensive organisational capability assessment across all nine dimensions
3. **ACMM Scorecard** — monitoring and assessment tool for evaluating current maturity level per characteristic

<p id="levels"></p>

## Maturity Levels

| Level | Name | Description |
|-------|------|-------------|
| M0 | None | No architecture capability |
| M1 | Initial | Ad-hoc, unorganised |
| M2 | Under Development | Processes being defined |
| M3 | Defined | Documented and standardised |
| M4 | Managed | Measured and controlled |
| M5 | Optimising | Continuous improvement |

## Nine ACMM Characteristics

Each characteristic is assessed independently across M0–M5, giving a multi-dimensional view rather than a single score. An organisation might be M3 on Governance but M1 on Business Linkage.

<p id="chars"></p>

1. **Architecture Process** — how architecture work is performed (ad-hoc vs. repeatable vs. optimised)
2. **Architecture Development** — maturity of producing architecture artefacts and deliverables
3. **Business Linkage** — alignment between architecture and business strategy/goals
4. **Senior Management Involvement** — executive sponsorship and engagement with EA
5. **Operating Unit Participation** — involvement of business units in architecture processes
6. **Architecture Communication** — how architecture is communicated across the organisation
7. **IT Security** — integration of security into architecture practice
8. **Architecture Governance** — controls, compliance, decision-making structures
9. **IT Investment and Acquisition Strategy** — how architecture informs technology investment decisions

> Practical use: the CMM "meter" identifies specific capability gaps rather than blanket immaturity statements — useful for targeted improvement roadmaps.

## ACMM as Foundational Capability for ADM Actors

The [ICL Architecture Development Method](https://ea.ironcodelabs.com/kb/icl-adm/icl_adm.html) (ICL ADM) requires the client organisation to be at ACMM maturity level M3 or above. Deliverable quality is capability-gated by CMM foundations — effective ADM execution requires sufficient maturity across all nine dimensions.

### Organisational Capability Implications

| Level | Implication |
|-------|-------------|
| M0–M1 | EA becomes ineffective without foundational structures |
| M2 | Minimum viable governance emerging |
| M3+ | EA can function with documented standards and executive support |

Critical structural requirements include:

- Executive-level EA reporting relationships
- Cross-unit participation models
- Architecture Review Board with enforcement authority
- Strategic planning integration

## Maturity Building Strategy

Rather than immediately delivering architecture artifacts, effective ICL client engagement focuses on capability development first.

**Phased Approach:**

1. **Phase 1** (3–6 months): Organisational readiness — governance establishment, role definition, process frameworks
2. **Phase 2** (6–12 months): Pilot ADM cycle with limited scope
3. **Phase 3** (Ongoing): Scale and continuous optimisation

## Conclusion

The Architecture Capability Framework in TOGAF, and the ACMM in particular, empowers organisations to enhance their Technology-related development processes systematically. By leveraging maturity levels and the nine characteristics, organisations gain targeted insight into capability gaps and a structured path for continuous improvement.

## History

![](assets/TOGAF_CMM.png)
Classic TOGAF CMM enabled organization diagram

Capability Maturity Models (CMM) are frameworks developed by the [Software Engineering Institute (SEI)](https://en.wikipedia.org/wiki/Software_Engineering_Institute) at Carnegie Mellon University in 1987 to assess and improve software development processes. Originally created to help the U.S. Department of Defense evaluate contractor capabilities, CMM provides a structured, five-level evolutionary path to enhance process maturity, quality, and predictability. CMM has since evolved into CMMI (Capability Maturity Model Integration), covering broader business areas.

>[!NOTE]CMM level is Enteprise KPI
>
> CMM level is organisation-wide measure — it reflects process maturity across all units, not just IT, making it a legitimate enterprise metric. Leadership can set a target level (e.g. "reach M3 by year-end") and track progress against it like any strategic KPI. Since ADM effectiveness is capability-gated by CMM level, the metric directly predicts whether EA initiatives will succeed — giving executives the signal they need to justify investment in governance, training, and tooling in the language of business outcomes.

---

*Sources: [cmm.md](cmm.md) · [dbj_cmm.md](dbj_cmm.md) · [dbj.org/cmm](https://dbj.org/cmm/)*
