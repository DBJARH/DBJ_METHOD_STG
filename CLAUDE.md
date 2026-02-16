# CLAUDE.md

This repo contains only documentation (markdown files and media). No code.

The primary focus is **enterprise architecture** and **methodology** — not software or technical architecture.

## Taxonomy

The Common Taxonomy (`research/TAXONOMY_FINAL/taxonomy_final.md`) is the single source of truth, organization wide. It defines the hierarchy, the names, and the vocabulary. All roles use these names with no changes or reinterpretations.

### Categories and Capabilities

1. **Conceptual** — Business, Information, Application, Technology
2. **Logical** — Data Management, Integration, Platform, Security
3. **Physical** — Compute, Infrastructure, Network, Storage
4. **Implementation** — Deployment, Development, Monitoring, Operations

"Categories" are the four first-level nodes. "Capabilities" are the second-level nodes.

### Architecture vs. Engineering

Architecture and engineering are distinct disciplines. Architecture defines *what* the system is and *how it is structured*; engineering defines *how it is built, operated, and kept healthy*. Architecture scope spans all four Categories. The lower the Category, the more engineering roles participate — but the structural decisions remain architecture's responsibility.

When writing or organizing content, place each concern at the correct Category. Do not mix Categories within the same section.

## Output

- be succinct
- pay attention to kramdown vs markdown differences
