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

# Agent Harness Conformance

## Research hypothesis

A protocol-based MOD-W could make agent harnesses objectively testable against the same governance contract.

Possible targets include:

- Claude Code
- Codex
- OpenAI agent tooling
- LangGraph-based agents
- local agent harnesses
- future systems

## Example conformance questions

Can the harness:

- preserve role boundaries?
- prevent unauthorized transitions?
- prevent self-approval?
- produce required evidence?
- preserve provenance?
- resume from protocol state?
- surface unresolved disagreement?
- integrate an external verifier without granting it gate authority?

## Example tests

### Self-approval

```text
Given:
  role = Development Team

When:
  ACCEPT_IMPLEMENTATION is attempted

Expect:
  DENIED
```

### Missing evidence

```text
Given:
  Tech Lead verdict = PASS
  required evidence = absent

When:
  transition to ACCEPTED is attempted

Expect:
  DENIED
```

### Upstream change

```text
Given:
  requirement R5 changes
  STEP-03 depends on R5

Expect:
  STEP-03 = REVALIDATION_REQUIRED
```

## Broader value

A common protocol could help separate:

- model quality
- harness quality
- governance quality

This is important because those factors are often conflated in current AI workflows.

## Future research question

> **Can MOD-W conformance be tested independently of the specific model or harness executing it?**
