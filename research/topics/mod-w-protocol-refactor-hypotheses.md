---
artifact:
  type: research-note
  version: 0.1
  created: 2026-09-29
  updated: 2026-09-29
  evidence_as_of: 2026-09-29
context:
  project: prod-w-dev
  status: research
  source_conversation: research/conversations/2026-09-29-prod-w-origin-protocol-research-conversation.md
---

# MOD-W: Protocol Refactor Hypotheses

## Research status

This is a **future research direction**, not a commitment to refactor MOD-W.

The current plan is:

> **MOD-W v5.0.1 → use it to develop PROD-W → learn from protocol-first PROD-W → evaluate protocol-based MOD-W → only then consider a MOD-W v6 architectural change**

## Primary hypothesis

A protocol-based MOD-W may make its governance semantics more durable, portable, enforceable, and testable across rapidly changing AI systems.

## Four primary objectives

### A. Governance independence

Separate MOD-W's normative governance semantics from specific:

- models
- harnesses
- vendors
- prompts
- execution environments

### B. Enforceable governance

Make critical authority, evidence, independence, and transition rules mechanically verifiable where practical.

### C. Interoperability and evaluation

Allow agents, harnesses, and independent evaluators to interact with MOD-W through stable contracts and be tested for conformance.

### D. Evolution resilience

Allow AI models, agent technologies, and execution environments to evolve independently of MOD-W's stable governance model.

## Derived advantages

Potential benefits include:

- provenance
- auditability
- resumability
- systematic revalidation
- generated role-specific instructions
- event observability
- agent-harness benchmarking
- protocol versioning
- capability/security enforcement
- external evaluator integration
- tooling ecosystem
- possible broader domain applicability

## Priority order

1. Separate governance from models/agents/harnesses.
2. Make governance constraints enforceable.
3. Enable independent evaluators.
4. Make harnesses objectively testable.
5. Improve auditability/provenance/reproducibility.
6. Support change impact and revalidation.
7. Make state resumable and portable.
8. Generate human/agent views from one authoritative definition.
9. Enable a broader MOD-W ecosystem.

## Counter-goal

> **Do not turn MOD-W into an elaborate orchestration platform.**

MOD-W should define governance semantics. Existing tools and runtimes should perform execution.
