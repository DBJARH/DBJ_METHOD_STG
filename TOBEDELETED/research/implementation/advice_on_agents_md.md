
- [Architecture Governance for AI-Assisted Development](#architecture-governance-for-ai-assisted-development)
  - [The problem with traditional architecture documentation](#the-problem-with-traditional-architecture-documentation)
  - [A new audience: AI agents](#a-new-audience-ai-agents)
  - [Why constraints outlast prompts](#why-constraints-outlast-prompts)
  - [Structuring an AGENTS.md](#structuring-an-agentsmd)
    - [Architecture (highest to lowest abstraction)](#architecture-highest-to-lowest-abstraction)
    - [Engineering](#engineering)
  - [A minimal example](#a-minimal-example)
  - [Practical patterns](#practical-patterns)
  - [Implications for architects](#implications-for-architects)
- [The ecosystem](#the-ecosystem)
  - [Getting started](#getting-started)

# Architecture Governance for AI-Assisted Development

## The problem with traditional architecture documentation

(leaving ADR's in the glorious past)

Architecture documentation has a shelf-life problem. Decisions get made, written down, and then forgotten. Confluence pages go stale. Diagrams stop reflecting reality. The gap between "what we decided" and "what actually happens" widens with every late-night commit.

Architecture Decision Records (ADRs) improved on this by keeping documentation close to code. ADR's are Physical and Software Architecture Artifacts. But ADRs are retrospective — they explain *why* a decision was made. They don't prevent violations.

## A new audience: AI agents

The rise of AI coding assistants changes who reads your documentation. When Claude, Codex, or Copilot generates code in your repository, it needs to know the rules — not the history.

This is where `AGENTS.md` (and `CLAUDE.md`) come in. These files answer a different question:

- **ADR**: "What did we decide, and why?"
- **AGENTS.md**: "What must always be true, and what must never happen?"

One is historical context. The other is active governance.

## Why constraints outlast prompts

Prompt engineering is tactical — it gets you good output today. Constraints are strategic — they hold across models, across team members, across time.

When the next model ships with different behaviour, your prompts may need rewriting. Your architectural invariants should remain stable.

An `AGENTS.md` encodes those invariants in a format that both humans and AI agents can follow.

## Structuring an AGENTS.md

A well-structured `AGENTS.md` separates architecture from engineering. These are distinct disciplines:

- **Architecture** defines *what* the system is and *how it is structured*
- **Engineering** defines *how* it is built, operated, and kept healthy

### Architecture (highest to lowest abstraction)

**1) Conceptual Architecture** — business capabilities and domain boundaries

- Each bounded context owns its data; no shared databases across domains.
- Customer-facing and back-office capabilities communicate only through defined integration points.

**2) Logical Architecture** — component relationships, data flows, integration patterns

- Cross-service communication is event-driven; publish through the outbox, never write directly to another service's store.
- PII is handled only in designated services; never logged.

**3) Physical Architecture** — deployment topology, infrastructure, network

- No new network egress without allowlist approval.
- Services deploy across availability zones; no single-region dependencies.

**4) Software Architecture** — code structure, layering, dependency rules

- Controllers call Application services only; no direct infrastructure access.
- Domain layer does not import from adapters.
- Cross-module imports only through public interfaces.

### Engineering

**5) Reliability Engineering** — error handling, resilience

- Message handlers are idempotent.
- Retries are bounded with exponential backoff.
- Errors are never swallowed; return typed failures.

**6) Observability Engineering** — logging, tracing, metrics

- Every request carries a correlation ID.
- Structured logging only.
- Defined metric names and required tags.

**7) Quality Engineering** — testing, quality gates

- PRs include unit tests for business rules, integration tests for API boundaries.
- Local verification: lint, test, contract tests.

**8) Security Engineering** — guardrails, compliance

- Secrets via vault; never committed in env files.
- OWASP Top 10 violations are forbidden.

## A minimal example

```md
# AGENTS.md

## Architecture

### Conceptual — domain boundaries
- Each bounded context owns its data. No shared databases.
- Domains communicate only through defined integration points.

### Logical — data flows and integration
- All cross-service communication is event-driven via the outbox.
- Customer identifiers and contact fields are PII. Never log them.

### Physical — infrastructure and network
- No network egress without allowlist update.

### Software — code structure and layering
- Controllers call Application services only.
- No database access from API handlers; use repositories.

## Engineering

### Reliability — error handling and resilience
- Handlers are idempotent. Deduplicate by requestId/messageId.
- Retries bounded with exponential backoff; dead-letter after N attempts.

### Observability — logging, tracing, metrics
- Structured logs only. Include correlationId, tenantId, operation name.
- Emit latency and failure metrics on every external call.

### Quality — testing and quality gates
- Run: make lint && make test && make integration-test
- Every behaviour change requires a test.

### Security — guardrails and compliance
- Secrets via vault only.
- OWASP Top 10 violations forbidden.
```

This is for repositories containing code. This is small, but it operates at the moment decisions are made — before the code is written, not after.

## Practical patterns

**Start with repeated mistakes.** Every codebase has antipatterns that keep returning. Document them explicitly, with context on why they're forbidden.

**Layer rules hierarchically.** A root `AGENTS.md` at repo level sets system-wide invariants. Services or modules can extend with their own constraints.

**Make rules testable.** Where possible, back constraints with linting rules or architecture tests. Agents can follow the rule *and* verify compliance.

**Keep it living.** Unlike ADRs (often immutable after approval), `AGENTS.md` evolves with the architecture. When you refactor, update the rules.

**Use it for onboarding.** The same file that guides AI agents is valuable for new team members. If a constraint isn't clear enough for an AI, it probably isn't clear enough for humans either.

## Implications for architects

Traditional governance: architect decides → documents → hopes people read → catches problems in review.

That model breaks when AI-assisted developers output code at 10x velocity. Software Architect cannot review everything.

`AGENTS.md` inverts the flow: guidance is provided *before* code is written. Architectural judgment gets distributed to every coding session — human or AI — across the project or even organisation.

This is how to scale senior engineering guidance without scaling headcount.

# The ecosystem

2026Q1 the tooling is converging:

- **Claude Code** loads `CLAUDE.md` and supports skills (markdown with YAML metadata).
- **OpenAI Codex** reads `AGENTS.md` and follows project rules.
- **Kiro** formalises steering rules as a core feature.
- **GitHub** and others are exploring similar concepts.

The pattern is model-agnostic. Any capable agent pointed at a well-structured `AGENTS.md` will adapt.

## Getting started

Keep it boring, specific and opinionated.

Aim for 30–60 lines covering: boundaries, data rules, error handling, logging, and tests. Evolve it based on real failures and real learnings.

The most valuable software architecture artifact in 2026 isn't a historical record of decisions made. It's a specification of constraints that must hold — not *what we decided*, but *what must be true*.

That's the document worth maintaining.
