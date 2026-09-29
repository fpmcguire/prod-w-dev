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

# External Evaluators and DeepPattern

## Research hypothesis

A protocol-based governance layer may make it easier to integrate external evaluators such as DeepPattern without tightly coupling them to the core workflow.

## Desired separation

An external evaluator should be able to:

- inspect task intent
- inspect constraints
- inspect acceptance criteria
- inspect implementation rationale
- inspect evidence
- identify unsupported assumptions
- identify evidence gaps
- surface disagreement

without automatically acquiring authority to approve or advance the workflow.

## Possible interface

```text
VerificationRequest
  work_item
  intent
  constraints
  acceptance_criteria
  implementation
  rationale
  evidence
  known_assumptions
  current_protocol_state
```

Possible response:

```text
VerificationResult
  evaluator
  findings[]
  unsupported_assumptions[]
  evidence_gaps[]
  disagreements[]
  confidence/context
```

## Authority principle

A likely rule:

```text
external_evaluator:
  MAY challenge
  MAY add evidence
  MAY identify discrepancies
  MUST NOT authorize gate transition
```

## Why this matters

This preserves evaluator independence while keeping human Moderator authority intact.

It also makes external verification pluggable: DeepPattern could be one evaluator among many rather than becoming a fixed MOD-W component.

## Future research question

> **What is the minimum stable evaluation contract that would let independent evaluators participate without becoming workflow authorities?**
