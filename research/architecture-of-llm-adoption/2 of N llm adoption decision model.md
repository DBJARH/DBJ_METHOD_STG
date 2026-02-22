
# Iron Code Labs EA, LLM Adoption Decision Model (4-Level Test)

>[!TIP]
> This document content maps directly to "dbj taxonomy" **four architectural levels** and defines a crisp decision rules.
> Please make sure you understand the [Iron Code Labs Enterprise Taxonomy](#icl_taxonomy).

---


## 1️⃣ Conceptual Level — *Capability Legitimacy*

**Question:**
Is the required business capability inherently semantic and probabilistic?

LLM is legitimate solution only if the capability requires:

* Interpretation of unstructured language
* Contextual reasoning
* Knowledge synthesis
* Ambiguous intent resolution

If the capability can be described as:

* Rule execution
* Deterministic transformation
* Structured workflow
* CRUD + search

→ **LLM is architecturally unjustified.**

**Decision rule:**

> If the capability can be specified exhaustively as business rules, do not use LLM.

---

## 2️⃣ Logical Level — *Service Pattern Fit*

LLM must appear as:

* A bounded domain service
* With explicit input/output contract
* With measurable confidence or evaluation metric

It must NOT appear as:

* Central orchestrator
* Enterprise brain
* Cross-domain decision authority

**Decision rule:**

> LLM is allowed only as a specialized service, never as architectural core.

---

## 3️⃣ Physical Level — *Operational Justification*

You must prove:

* Latency is acceptable
* GPU/compute cost is sustainable
* Observability and monitoring are defined
* Failure modes are bounded

If you cannot define:

* Fallback path
* Cost envelope
* SLA model

→ You are building the right side of the Brooks’ diagram. (see: https://en.wikipedia.org/wiki/Second-system_effect)

**Decision rule:**

> No LLM without defined cost, SLA, and fallback path.

---

## 4️⃣ Implementation Level — *Containment Strategy*

Implementation must ensure:

* Swappable model (no vendor lock at domain level)
* No prompt logic embedded across system
* No business rules hidden in prompts
* Anti-corruption boundary around AI layer

**Decision rule:**

> If removing the LLM would collapse the architecture, you overengineered it.

---

# Executive Summary

LLM is justified only when:

```
Semantic necessity
+ Bounded service
+ Operational control
+ Replaceability
```

If any one of these is missing →
You are building your [Fred Brooks "Second system"](https://en.wikipedia.org/wiki/Second-system_effect).

---

### References

<br id="icl_taxonomy">

#### 1. [Iron Code Labs Enteprise Taxonomy](https://ea.ironcodelabs.com/taxonomy.html)
