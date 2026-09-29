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

# Protocol, Schema, and State

## Core distinction

A **schema** describes the shape and validity of data.

A **protocol** describes the rules of interaction and change over time.

**State** records where a particular artifact or workflow currently is.

## Summary table

| Concept | Primary question | Example |
|---|---|---|
| Schema | What does valid data look like? | What fields must a Review contain? |
| Protocol | What is allowed to happen? | Who may approve a Review and under what conditions? |
| State | Where are we now? | `Claim C-017 = CHALLENGED` |

## Example

A schema may permit:

```text
reviewer: Development Team
verdict: PASS
```

because the data is structurally valid.

The protocol can still reject it because:

```text
artifact.author == reviewer
→ independent_review = INVALID
```

## Likely PROD-W architecture

PROD-W will likely need all three:

```text
             PROD-W PROTOCOL
                    │
        Defines allowed behavior
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
       SCHEMAS               STATE
          │                   │
 What does valid       Where are we
 data look like?       right now?
```

## Principle

> **Protocols often use schemas, but schemas alone cannot express authority, sequencing, or legal transitions.**
