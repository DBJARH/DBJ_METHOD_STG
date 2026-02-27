# CLAUDE.md

This repo contains only documentation (markdown files and media). No code.

The primary focus is **enterprise architecture** and **methodology** — not software or technical architecture.

## Repository structure

- `/docs` — staging area for Jekyll site, deployed to EA repo `/docs`. Use kramdown.
- `/research` — plain markdown, includes TAXONOMY_FINAL as single source of truth.
- `/external` — customer-facing leaflets and external content. Plain markdown, no kramdown.
- `/internal` — internal documentation for Iron Code Labs company members. Plain markdown.
- `/blog` — blog posts. Plain markdown.

## Taxonomy

The Common Taxonomy (`research/TAXONOMY_FINAL/taxonomy_final.md`) is the single source of truth, organization wide. It defines the hierarchy, the names, and the vocabulary. All roles use these names with no changes or reinterpretations.

Published at https://ea.ironcodelabs.com/taxonomy.html (full) and https://ea.ironcodelabs.com/taxonomy_core.html (core).

### Categories and Capabilities

1. **Conceptual** — Business, Information, Application, Technology
2. **Logical** — Data Management, Integration, Platform, Security
3. **Physical** — Compute, Infrastructure, Network, Storage
4. **Implementation** — Deployment, Development, Monitoring, Operations

"Categories" are the four first-level nodes. "Capabilities" are the second-level nodes.

### Architecture vs. Engineering

Architecture and engineering are distinct disciplines. Architecture defines *what* the system is and *how it is structured*; engineering defines *how it is built, operated, and kept healthy*. Architecture scope spans all four Categories. The lower the Category, the more engineering roles participate — but the structural decisions remain architecture's responsibility.

When writing or organizing content, place each concern at the correct Category. Do not mix Categories within the same section.

## The BPT Loop

Published at https://ea.ironcodelabs.com/bpt.html

## Capability Maturity Model (CMM)

Published at https://ea.ironcodelabs.com/cmm.html — ACMM levels: https://ea.ironcodelabs.com/cmm#levels

## Iron Code Labs brand

- Motto: **EA AI ROI**
- External leaflets (`/external`) should end each section with a punch line tying back to the motto.
- Preferred title style: declarative and confident (e.g., "The Case for X") — avoid hedging phrases like "Just why".

## Output

- Be succinct.
- Pay attention to kramdown vs markdown differences.

## Kramdown conventions

- Use kramdown only in `/docs`. All other folders use plain markdown.
- Always use `markdown="1"` on HTML block elements (`<details>`, `<div>`, etc.) so kramdown renders markdown inside them.
- Never use `.html` as link targets in source `.md` files — Jekyll resolves `.md` to `.html` at publish time.
