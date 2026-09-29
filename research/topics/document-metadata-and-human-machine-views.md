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

# Document Metadata and Human/Machine Views

## Research idea

A MOD-W or PROD-W project can become overwhelming to a human because governance state, evidence, history, instructions, and working content are all exposed together.

A possible future design principle is:

> **Humans should see the work they need to reason about. Machines should see the structure they need to enforce.**

## Possible split

```text
                    PROJECT
                      │
           ┌──────────┴──────────┐
           ▼                     ▼
     HUMAN VIEW              MACHINE VIEW

 Product meaning           Artifact identity
 Decisions                 State
 Goals                     Authority
 Requirements              Dependencies
 Explanations              Evidence requirements
 Findings                  Validation status
 Open questions            Provenance
 Review summaries          Allowed transitions
```

## Candidate implementation approaches

1. Embedded metadata in Markdown/front matter.
2. Sidecar metadata files.
3. Central protocol state.
4. Hybrid model.

## Current preference to investigate

A hybrid may be promising:

- stable identity/provenance stays with the artifact;
- richer mutable workflow state lives centrally.

Possible distinction:

```text
DOCUMENT
  human-readable content

METADATA
  identity / provenance / relationships

PROTOCOL STATE
  mutable workflow condition
```

## Potential advantages

- lower human cognitive load
- role-specific views
- reduced AI context noise
- simpler external evaluation
- better machine validation
- human-readable documents remain approachable

## Important status

> **Using document metadata to carry protocol/state is a research idea only. It is not yet a PROD-W architectural decision.**

## Future design goal

> **Separate normative machine-readable governance state from human-readable working views, while preserving traceability between them.**

And:

> **Humans should not have to understand the entire protocol representation in order to use MOD-W correctly.**
