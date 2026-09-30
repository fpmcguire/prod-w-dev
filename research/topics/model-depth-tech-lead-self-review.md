---
artifact:
  type: research-note
  version: 0.1
  created: 2026-09-30
  updated: 2026-09-30
  evidence_as_of: 2026-09-30
context:
  project: prod-w-dev
  status: research
  source_session: Tech Lead repository-structure correction and self-review
---

# Model Depth and Tech Lead Self-Review

## Purpose

Record what surfaced when the same Tech Lead work was reviewed across two model-depth passes identified in the session as GPT-5.5 Low and GPT-5.5 High.

This note is research material for PROD-W and MOD-W transferability. It is not a benchmark, formal model evaluation, or claim about model capability in general.

## Context

During repository-structure correction, the initial Tech Lead pass focused on the explicitly named files:

- `prod-w/architecture.md`
- `prod-w/domain-language.md`
- `prod-w/roadmap.md`
- `prod-w/step-01.md`

Those files were correctly identified as MOD-W governance/process artifacts and moved conceptually under `mod-w/`.

After Moderator challenge and a higher-depth self-review, additional issues surfaced that were not caught by the narrower pass.

## What GPT-5.5 Low Surfaced

The lower-depth pass correctly handled the direct instruction:

- Verified that the named `prod-w/*.md` files were MOD-W development/governance artifacts, not concrete PROD-W product artifacts.
- Moved the named governance artifacts to `mod-w/`.
- Kept `prod-w/` reserved for future concrete product artifacts such as `prod-w/protocol-semantics.md`.
- Updated direct references from `prod-w/architecture.md`, `prod-w/domain-language.md`, and `prod-w/step-01.md` to their `mod-w/` locations.
- Left the work uncommitted.

The pass was useful for literal task execution but too narrow in scope.

## What GPT-5.5 Low Missed

The lower-depth pass missed adjacent structural and governance implications:

- Root-level artifacts also needed routing:
  - `MODERATOR-REVIEW-FEEDBACK-TECH-LEAD.md`
  - `moderator-prompt-matt-pocock-skills-comparator.md`
- The comparator prompt belonged under `research/comparators/`, not under a generic MOD-W prompts directory.
- Artifact statuses still said `Draft for Moderator Review` even though Moderator acceptance had been recorded.
- Architecture decisions D1-D9 still said `Proposed` while the review artifact said the architecture was accepted.
- STEP-01's governance note said D1-D6 while the acceptance checks explicitly referenced D8.
- Accepted transferability observations were edited in-place despite the register saying observations are preserved in original form.
- Governance context was added to architecture, but not consistently to domain-language, roadmap, and step-control artifacts.
- The review artifact still instructed a commit even after the new structure cleanup was pending Moderator approval.
- Encoding and marker artifacts remained in generated review/prompt text.
- An empty `mod-w/prompts/` directory was introduced during routing and then became stale.

## What GPT-5.5 High Surfaced

The higher-depth pass treated the work as a governance-system consistency problem rather than only a file-move problem.

It surfaced:

- Artifact purpose and artifact location must be reviewed together.
- Moving governance files changes the meaning of references, review records, and research evidence.
- Accepted observations should not be silently rewritten; if paths change, add a relocation note.
- Status fields are governance claims and must align with review disposition.
- Architecture decision status is part of the governance state, not decorative metadata.
- STEP acceptance checks must align with the architecture decision index.
- Comparator prompts are research artifacts when they direct comparator work, even if written as operational prompts.
- Review artifacts should not instruct commit while Moderator approval is pending.
- Empty directories and root-level process files are structural noise in a governance repository.

## Research Interpretation

The difference was not merely "better proofreading." The higher-depth review identified a broader class of errors:

- governance-state inconsistency;
- artifact taxonomy drift;
- evidence-history mutation risk;
- stale operational instructions;
- mismatch between accepted review state and document metadata;
- repository layout semantics beyond the explicitly named files.

This suggests that MOD-W/PROD-W work benefits from an explicit second-pass review mode that asks:

> If this change is correct locally, what governance records, artifact classifications, and downstream instructions does it invalidate or make stale?

## Potential PROD-W Implication

PROD-W may need to treat model/agent outputs as requiring different review depths depending on governance risk:

- **Literal execution review:** Did the requested change happen?
- **Structural review:** Did the change belong in the right artifact and location?
- **Governance review:** Did statuses, authority, review records, and historical evidence remain coherent?
- **Downstream handoff review:** Did prompts, step instructions, and future workflow guidance remain correct?

These are distinct review modes. A single acceptance check may not catch all of them.

## Potential MOD-W Transferability Observation

This may become concrete evidence that MOD-W needs an explicit "cross-artifact governance consistency" check when used for protocol/methodology development.

Do not record it as an accepted transferability observation yet unless the Moderator decides this session constitutes sufficient concrete evidence.

Possible classification if elevated later:

`LOCAL_ADAPTATION_PROPOSED`

Possible observation title:

> Higher-Depth Review Surfaced Governance-State Drift Missed by Literal Task Execution

## Limits

- This is one session, not a controlled model comparison.
- The labels GPT-5.5 Low and GPT-5.5 High are recorded as used in the session context.
- The evidence is qualitative and based on observed review behavior.
- The result should inform review-process design, not broad claims about model capability.

## Follow-up Questions

- Should MOD-W add a formal post-change cross-artifact consistency checklist?
- Should STEP artifacts require a "status coherence" validation before commit?
- Should research registers require correction notes rather than direct edits to accepted observations?
- Should product/governance repositories reserve root for only stable top-level project files?
- Should PROD-W distinguish model execution mode from model review mode in its protocol semantics?
