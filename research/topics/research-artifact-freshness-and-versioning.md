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

# Research Artifact Freshness and Versioning

## Current experiment scope

Timestamp/version metadata is restricted to **`prod-w-dev` research artifacts for now**.

It is not yet:

- a PROD-W requirement
- a MOD-W requirement
- a general repository standard

The goal is to use it first, evaluate its usefulness, and standardize only if evidence supports it.

## Minimal convention

Candidate fields:

```yaml
artifact:
  id: RESEARCH-007
  version: 0.1
  created: 2026-09-29T09:37:00+02:00
  updated: 2026-09-29T09:37:00+02:00
  evidence_as_of: 2026-09-29T09:37:00+02:00
```

## Why `evidence_as_of` matters

`updated` and `evidence_as_of` mean different things.

A document may be edited today while its external research was last checked weeks ago.

Therefore:

> **`updated != evidence_as_of`**

## Optional future field

```yaml
freshness:
  review_after: 2026-10-29
```

This could support states such as:

> **CURRENT → REVIEW_DUE → STALE**

without asserting that stale research is automatically false.

## Principle

> **Use first, evaluate later, standardize only if the evidence supports it.**
