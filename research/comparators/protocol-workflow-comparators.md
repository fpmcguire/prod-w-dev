---
artifact:
  type: comparator-research
  version: 0.1
  created: 2026-09-29
  updated: 2026-09-29
  evidence_as_of: 2026-09-29
context:
  project: prod-w-dev
  status: research
  source_conversation: research/conversations/2026-09-29-prod-w-origin-protocol-research-conversation.md
---

# Protocol / Workflow Comparators

## Purpose

Track existing systems that may inform PROD-W and a possible future protocol-based MOD-W.

These systems solve different problems. They should be treated as comparators and sources of architectural precedent, not as direct equivalents.

## Grove

Relevant for:

- formal workflow protocol for AI coding agents
- evidence-gated progression
- explicit project state
- dependencies constraining transitions
- human intervention states
- machine-enforced invariants

Important lesson:

> specification describes intended outcome; protocol determines whether the project is allowed to advance.

## Herdr Flow

Relevant for:

- adversarial review
- human gates
- typed artifacts
- deterministic transitions
- state not inferred from natural-language output
- downstream invalidation/revalidation after upstream changes

Especially relevant to the IDP-Align product-definition update after prior Step acceptance.

## SMALL Protocol

Relevant for:

- Schema
- Manifest
- Artifact
- Lineage
- Lifecycle

Useful for intent, lineage, lifecycle, resumability, and durable state.

## FCoP

Relevant for:

- behavior governance
- separating protocol from host/agent implementation
- application → host adapter → protocol → reference implementation → execution substrate

Supports the idea that Claude/Codex/Human should be a MOD-W profile, not MOD-W itself.

## A2A

Relevant for:

- canonical data model
- abstract operations
- protocol bindings
- interoperability independent of transport

Useful precedent for separating normative semantics from implementation.

## MCP

Relevant for:

- schema-first protocol design
- explicit capabilities
- lifecycle
- authorization
- RFC-style MUST / MUST NOT / SHOULD / MAY terminology

MCP is complementary to MOD-W, not a replacement.

## Open Workflow Specification

Relevant as an orchestration DSL precedent:

- tasks
- branches
- events
- retries
- nested workflows
- external calls

Less directly relevant to governance semantics.

## Agent Definition Language (ADL)

Relevant for:

- machine-readable identity
- permissions
- lifecycle
- compliance
- role capabilities

## Agent Governance Protocol (AGP)

Relevant as an emerging governance-oriented comparator.

## Initial relevance ranking for MOD-W

| Comparator | Relevance |
|---|---|
| Grove | Very high |
| Herdr Flow | Very high |
| SMALL | High |
| FCoP | High |
| A2A | Medium-high |
| MCP | Medium-high |
| ADL | Medium |
| Open Workflow Spec | Lower/core-adjacent |
| AGP | Watch |

## Research principle

Do not claim novelty merely because no exact equivalent is found.

Instead, identify:

- what existing systems already solve
- where PROD-W overlaps
- where PROD-W differs
- which ideas can be reused rather than reinvented
