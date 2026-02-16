
>[!TIP]
Below is a **concise 1-page EA Governance Checklist** suitable for mandatory ADR validation before approving any LLM usage.
ADR == Architecture Decision Record

---

# EA Governance Checklist — LLM Adoption Control

## ADR Title:

“Use of LLM for &lt;Capability Name&gt;”

---

# 1️⃣ Conceptual Validation — Capability Legitimacy

### ☐ C1. Capability Classification

* Is the capability inherently semantic, interpretative, or probabilistic?
* Does it require reasoning over unstructured language?

### ☐ C2. Deterministic Alternative Eliminated

* Have rule-based, search-based, or workflow solutions been explicitly evaluated and rejected?
* Is there written justification why deterministic methods are insufficient?

**Gate Rule:**
If deterministic specification is possible → ADR rejected.

---

# 2️⃣ Logical Validation — Architectural Containment

### ☐ L1. Bounded Service Definition

* Is the LLM implemented as a single, isolated domain service?
* Is there a strict input/output contract?

### ☐ L2. No Architectural Centralization

* Is the LLM prevented from acting as:

  * Enterprise orchestrator?
  * Cross-domain policy engine?
  * Source of business truth?

### ☐ L3. Measurable Outcome

* Are evaluation metrics defined (accuracy, precision, hallucination rate)?
* Is success objectively measurable?

**Gate Rule:**
If LLM becomes architectural core → ADR rejected.

---

# 3️⃣ Physical Validation — Operational Discipline

### ☐ P1. Cost Envelope Defined

* Monthly cost projection documented?
* Scaling characteristics understood?

### ☐ P2. SLA & Latency Defined

* Target response time?
* Availability target?
* Monitoring plan?

### ☐ P3. Failure Containment

* Defined fallback path?
* Clear degradation behavior?

**Gate Rule:**
If failure mode is undefined → ADR rejected.

---

# 4️⃣ Implementation Validation — Replaceability & Clean Boundaries

### ☐ I1. Model Swappability

* Is the model replaceable without domain rewrite?
* No vendor API leakage into core domain?

### ☐ I2. No Hidden Business Logic in Prompts

* Prompts do not encode domain rules?
* Domain logic exists outside LLM?

### ☐ I3. Anti-Corruption Layer

* Is there a clear AI boundary protecting the core system?

**Gate Rule:**
If removing LLM collapses business flow → Overengineered → ADR rejected.

---

# Final Approval Condition

LLM is approved only if:

```
Semantic necessity
AND
Bounded service architecture
AND
Operational containment
AND
Replaceability guaranteed
```

Failure of any one condition = architectural violation ([Fred Brooks Second-System](https://en.wikipedia.org/wiki/Second-system_effect) Risk).

---

<!-- If useful, I can now align this explicitly to TOGAF ADM phases (Preliminary → Implementation Governance) for integration into your governance model. -->
