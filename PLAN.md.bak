# Plan: Rework docs/index.md as a 3-Stage Methodology Entry Story

## Context

The current `docs/index.md` is a flat list of topics (what is EA, what is CMM, BPT, AI) with informational character. It does not tell a **customer journey story**. The goal is to reshape it into a staged narrative that a prospective customer reads top-to-bottom, understanding *what they will go through* when engaging with ICL EA.

## Structure of the new `docs/index.md`

Preserve the existing front matter. Rewrite the body as follows:

### Opening — EA as the Overarching Authority

Frame the entire page under the premise that **Enterprise Architecture (TOGAF-based) is the governing authority** across all three stages. This is not one topic among many — it is the lens through which everything else is viewed.

- The existing "EA aligns business and technology" block quote + cogs diagram stays, but is now explicitly positioned as the **governing principle** of the methodology
- One sentence: ICL EA is a TOGAF subset tailored for guided, measurable delivery
- Make clear: **EA is present and governing in every stage** — it is not introduced later
- Link to [Commercial Enterprise](pages/commercial_enterprise.md) for context of where the enterprise sits

### The Three Stages (all under EA governance)

**Stage 1 — Preparing for the CMM Ladder** *(EA governs: assessment and baseline)*
- EA leads the assessment of current organisational maturity (where are you on M0–M5?)
- EA introduces shared vocabulary via [Taxonomy](pages/taxonomy/index.md)
- EA identifies capability gaps using the ACMM scorecard
- EA sets a realistic target (typically M2)
- **Deliverable:** CMM baseline assessment + EA-guided improvement roadmap
- Link to existing [CMM page](pages/cmm.md) for full detail

**Stage 2 — Climbing to CMM Level 2** *(EA governs: process definition and governance)*
- EA defines and documents architecture processes (moving from ad-hoc to repeatable)
- EA establishes governance structures and secures senior management involvement
- EA introduces architecture communication practices across the organisation
- EA builds the Taxonomy as a living organisational asset
- **Deliverable:** organisation operating at M2 with EA-documented processes
- Links to [CMM](pages/cmm.md) and [Taxonomy](pages/taxonomy/index.md)

**Stage 3 — The BPT Infinity Loop** *(EA governs: continuous operational cycle — detailed)*
- This is the operational methodology for CMM-ready organisations
- **EA is the meta-layer** — it does not participate in the loop, it governs it
- Activity sequence with actor responsibilities (EA present in every transition):

  | Activity | What happens | Key actors |
  |----------|-------------|------------|
  | **Require** | Business declares product needs; EA ensures alignment with strategy | Business, EA |
  | **Develop** | Technology builds to product specifications; EA governs coherence | Technology, Product, EA |
  | **Deploy** | Product is released into operations; EA validates architecture compliance | Technology, Product, EA |
  | **Evaluate** | Measure outcomes against business objectives; feed back into next cycle | Business, Product, EA |

- Explain the "infinity loop" nature: Evaluate feeds back to Require — the loop never stops
- Actor roles summary:
  - **Business** — declares products, owns outcomes
  - **Product** — bridges business needs and technical capabilities (the alignment point)
  - **Technology** — implements products
  - **EA** — governs the meta-layer, guides all transitions without bottlenecking
- Link to existing [BPT Meta Loop](pages/bpt.md) for the diagram and full conceptual description

### AI is Inside
- Keep the existing AI section as-is (brief, links to the AI page)

### Footer
- Keep existing copyright line

## Files to modify

1. **`docs/index.md`** — full rewrite of body content (front matter preserved)

No new files created. All links point to existing pages.

## What is NOT changed
- `docs/pages/bpt.md`, `docs/pages/cmm.md`, `docs/pages/taxonomy/index.md` — left as-is
- `docs/_config.yml` — unchanged
- No new images needed (the existing cogs image and BPT loop diagram are referenced)

## Verification
- After editing, run `bundle exec jekyll serve` locally (if Jekyll is available) or push to staging and check `https://ironcodelabs-com.github.io/EA_STG/`
- Confirm: all internal links resolve, stage narrative reads top-to-bottom as a customer journey, existing detail pages remain accessible
