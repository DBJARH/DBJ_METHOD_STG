---
layout: default
title: Architecture Board Decision Template — LLM Approval
description: Ten-question approval gate for Architecture Board LLM decisions
---

# Architecture Board Decision Template — LLM Approval

## What is this document?

Every organization that uses AI models (LLMs) in a professional context needs a process for deciding *whether* and *how* to use them. Without that process, teams add AI wherever it seems useful — which leads to unpredictable costs, unmaintainable systems, and decisions no one can explain or reverse.

This template is a **formal approval gate**. Before any team ships a feature that depends on a Large Language Model (LLM), they complete this form and present it to the Architecture Board. The board reviews it and either approves or rejects the usage.

### Why a board?

LLM usage is an architectural commitment — it affects cost structure, maintainability, risk, and accountability across the organization. These decisions should not be made unilaterally by a single team.

If a team adds an LLM to their product and it fails, costs explode, or the model gets deprecated, the problem doesn't stay contained to that team. Other teams, systems, and customers feel it. The Architecture Board exists to catch those cross-cutting risks before they become everyone's problem.

### Why 10 yes/no questions? What are the deliverables?

To prevent vague or aspirational answers. Each question targets a specific failure mode that has caused real project failures. A "No" on any question means the design has a structural problem — not a minor gap.

**What are the deliverables?** This form does not stand alone. To answer "Yes" to most questions, the team must have already produced written evidence. Before submitting, the team is expected to have:

| # | Deliverable | Who produces it | Why it is required |
|---|---|---|---|
| Q2 | Written justification for rejecting a deterministic alternative | Team architect or tech lead | Proves AI was chosen deliberately, not by default |
| Q3 | A named business KPI with a measurement method | Product owner or business analyst | Ties the AI feature to a real outcome that can be evaluated |
| Q6 | Cost ceiling and scaling model (e.g. estimated token usage × price) | Engineer or architect | Prevents runaway spend as usage grows |
| Q7 | Latency and availability targets, plus a defined fallback behavior | Engineer or architect | Ensures the system degrades safely when the model is slow or unavailable |
| Q8–Q9 | Architecture diagram showing model as a bounded service, with business logic in code | Architect | Proves the system can survive a model swap or removal |

These documents do not need to be polished reports. A diagram, a spreadsheet, and a one-page rationale are sufficient. What matters is that the answers are grounded in something written — not verbal assurances during the meeting.

**Who fills this out?** The team requesting LLM usage (engineers, product, or architects on that team). They present it to the Architecture Board, which includes senior architects who have cross-project visibility.

**What is an Architecture Board?** A standing group of senior architects and decision-makers who review proposals that create organization-wide risk or commitment. They are not gatekeepers for political reasons — they exist because some decisions cannot be undone cheaply, and they need people with the full picture.

---

**Subject:** Approval Request — LLM Usage for `<Capability Name>`

**Presented by:** `<Team / Project>`
**Date:** `<YYYY-MM-DD>`

---

## Instructions

Answer each question with **Yes** or **No**. No partial credit. Any "No" requires redesign before resubmission.

Questions are grouped by [ICL Enterprise Taxonomy](https://ea.ironcodelabs.com/taxonomy.html) level.

---

## The 10 Questions

**Conceptual Level — Business Capability**

| # | Question | Answer |
|---|---|---|
| 1 | Is the capability inherently semantic or probabilistic — not solvable by rules or workflow? | |
| 2 | Has a deterministic alternative been formally evaluated and rejected, with written justification? | |
| 3 | Is there a measurable business KPI tied specifically to this LLM usage? | |

**Logical Level — Service Design**

| # | Question | Answer |
|---|---|---|
| 4 | Is the LLM a bounded service — not a central orchestrator or cross-domain decision engine? | |
| 5 | Does a human remain accountable for all binding decisions the system influences? | |

**Physical Level — Operations**

| # | Question | Answer |
|---|---|---|
| 6 | Is the monthly cost ceiling and scaling behavior documented? | |
| 7 | Are latency targets, availability targets, and failure fallback paths defined? | |

**Implementation Level**

| # | Question | Answer |
|---|---|---|
| 8 | Can the model be swapped or removed without rewriting domain logic? | |
| 9 | Does all business logic live in code — not in prompts or model behavior? | |
| 10 | Is usage strictly limited to the approved capability, with no platform or ecosystem scope? | |

---

## Board Decision

**Score:** `__ / 10`

| Result | Action |
|---|---|
| 10 / 10 | **Approved** — proceed with Implementation Governance checkpoints |
| Any "No" | **Rejected** — redesign required before resubmission |

**Decision:** `Approved / Rejected`
**Board chair signature:** `___________________`
**Date:** `___________________`

---

## Notes

*(Record any conditions, scope constraints, or required checkpoints here)*

---

*A score below 10/10 is not a negotiation — it means the architecture has a gap. Fix the gap, not the question.*

*Reference: [Fred Brooks — Second-System Effect](https://en.wikipedia.org/wiki/Second-system_effect)*
