# EA Governance Checklist — LLM Adoption

Use this checklist before approving any LLM introduction. It maps to the [4-Level Decision Model](2%20of%20N%20llm%20adoption%20decision%20model.md) and follows the [ICL Enterprise Taxonomy](https://ea.ironcodelabs.com/taxonomy.html) levels: Conceptual, Logical, Physical, Implementation. Every item must be answered "yes" for approval.

Work through the four sections and bring the completed checklist to the Architecture Board.

**Capability:** `<name>`

---

## Section 1 — Business Capability (Conceptual Level)

Does this capability genuinely require language reasoning?

- [ ] The capability involves unstructured text, ambiguous intent, or contextual reasoning
- [ ] A deterministic alternative (rules, workflow, search) was evaluated and ruled out
- [ ] Written justification exists for why non-LLM approaches are insufficient

**Gate:** If a rule-based solution could do the job — stop here. ADR rejected.

---

## Section 2 — Service Design (Logical Level)

Is the LLM architecturally contained?

- [ ] LLM is implemented as a single, isolated service
- [ ] There is a defined input/output contract for the service
- [ ] The LLM does not act as orchestrator, policy engine, or cross-domain decision maker
- [ ] Success metrics are defined (accuracy, error rate, hallucination rate, or equivalent)

**Gate:** If the LLM is central to the architecture — stop here. The proposal is rejected: do not proceed, do not submit to the Architecture Board. Redesign so the LLM is a peripheral service, then restart the checklist.

---

## Section 3 — Operations (Physical Level)

Is production readiness defined?

- [ ] Monthly cost projection is documented, including scaling behavior
- [ ] Response time target is defined
- [ ] Availability target is defined
- [ ] Monitoring plan is in place
- [ ] Fallback behavior is defined (what happens when the LLM fails or returns unusable output)

**Gate:** If failure mode is undefined — stop here. ADR rejected.

---

## Section 4 — Implementation (Implementation Level)

Can the LLM be removed or replaced cleanly?

- [ ] The model can be swapped without rewriting domain logic
- [ ] No vendor API leaks into core business code
- [ ] Business rules exist in code, not in prompts
- [ ] An anti-corruption layer separates the LLM from the rest of the system

**Gate:** If removing the LLM would collapse the system — stop here. ADR rejected.

---

## Approval Condition

All four sections must pass. No exceptions.

```
Semantic necessity
AND bounded service
AND operational readiness
AND replaceability
```

Any failed gate = architectural violation. Redesign before resubmitting.

---

*Reference: [Fred Brooks — Second-System Effect](https://en.wikipedia.org/wiki/Second-system_effect)*
