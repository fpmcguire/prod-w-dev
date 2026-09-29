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

# PROD-W: Protocol-First Rationale

## Core direction

PROD-W is intended to be **protocol-first rather than instruction-first**.

Markdown and human-readable documents may remain important, but they should not be the sole normative source of workflow behavior.

A protocol-first approach can define:

- roles
- authority
- states
- permitted actions
- transitions
- evidence requirements
- challenge requirements
- artifact contracts
- validation rules
- decision gates
- escalation
- revalidation
- provenance
- human authorization

## Why this matters

Natural-language instructions such as:

> “The agent should not approve its own work.”

are weaker than protocol rules that make the same transition structurally invalid.

The long-term direction is toward:

> **governance semantics that are machine-checkable and independent of any one model, agent harness, or prompt format.**

## Candidate architecture

```text
                 PROD-W PROTOCOL
                 (authoritative)
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
     Agent views   Human views   Validation
      / prompts      / docs        engine
          │            │            │
          └────────────┼────────────┘
                       ▼
                    ARTIFACTS
```

## Important current constraint

The exact protocol representation has not been selected.

Open possibilities include:

- YAML
- JSON
- JSON Schema
- TypeScript/Zod
- a custom DSL
- another representation discovered during research

## Early invariants

Candidate protocol invariants include:

1. Human authority must be explicit.
2. No agent may approve its own work.
3. Product intent precedes product evaluation.
4. Evidence and inference are distinct.
5. Material claims require provenance.
6. Material hypotheses require counter-evidence or independent challenge.
7. Agent agreement is not independent evidence.
8. Unresolved disagreement must remain visible.
9. Absence of discovered competition is not evidence of novelty.
10. Technical feasibility does not establish commercial viability.
11. Implementation evidence may trigger product reconsideration.
12. Marketing claims must trace to evidence.
13. Uncertainty should not be hidden behind artificial precision.
14. Consequential decisions require explicitly authorized human judgment.
