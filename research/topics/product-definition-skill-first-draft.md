---
artifact:
  type: research-note
  version: 0.1
  created: 2026-10-13
  updated: 2026-10-13
  evidence_as_of: 2026-10-04
context:
  project: prod-w-dev
  status: Proposed (research only)
  source_conversations:
    - "Claude Opus 5.5 chat on claude.ai in the PROD-W-DEV project, 2026-10-04 to 2026-10-13: VS Code agent-skill practices, then a first draft of the product-definition skill (not archived under research/conversations/)"
  related:
    - research/topics/product-definition-skill.md
    - research/topics/agent-skills-and-protocol-relationship.md
notes:
  - "Derived note. Nothing here is a PROD-W requirement, an architectural decision, or a change to MOD-W."
  - "The draft was produced by a Claude-family session, as is the Development Team's producing configuration. Under PR-27 and PR-28 this is not independent corroboration, and a review by the same model family shares its blind spots."
  - "Per the Moderator's decision of 2026-10-03, the skill is built outside prod-w-dev and considered for PROD-W v2. No skill files are added to this repository."
---

# Product-Definition Skill: First Draft

## Research status

A first draft of the skill described in `product-definition-skill.md` exists
as `defining-products-w`, version 0.1.2-draft. It lives outside this
repository. It has not been run against its test prompts.

## How the draft was built

The session started from general VS Code agent-skill practice and Matt
Pocock's `grill-me` skill, then applied them to the direction recorded on
2026-10-03: build on `om-discover`'s structure, borrow `office-hours`'
pushback for the concept path and `brainstorming`'s approval rule, and take
claim classes from `prod-w/evidence-knowledge-model.md`.

Practices carried into the draft:

- A lean main `SKILL.md` (about 110 lines) with detail in reference files that
  load only when needed.
- A description that says what the skill does and when to use it.
- One skill, one job. No scripts, so the skill stays instructions rather
  than tooling.

## What the draft contains

| File | Content |
|---|---|
| `SKILL.md` | Interview rules, the common walk, marking summary, drafting and approval steps, limits |
| `references/entry-pain-point.md` | Shortest path: make the pain specific and find out how the user knows |
| `references/entry-concept.md` | Work back from an idea until the problem can be stated without it |
| `references/entry-domain.md` | Collect the user's observations before offering candidates; candidates are marked as agent hypotheses |
| `references/claim-marking.md` | Plain-Markdown markers using the classes in evidence model Section 4.2 |
| `references/product-template.md` | MOD-W v5.0.1 `PRODUCT.md` section order, plus marked PROD-W additions |
| `references/producing-configuration.md` | Template 11 elements; the skill and its version sit inside the instructions statement (UAD4-11) |
| `README.md` | Status, design choices, six test prompts, decisions |

All three entry paths converge on one point: a stated problem, who has it,
and how the user knows.

## Main rules in the draft

- **One question per turn.** Stricter than `om-discover`'s small batches,
  because bundled questions are a known failure of `grill-me`.
- **Research and decision questions are kept apart.** Research questions never
  suggest an answer. Decision questions may carry a recommendation only with
  its basis stated. A user accepting a recommendation is recorded as the
  user's decision, not as evidence.
- **Plain-Markdown claim marking**, for example
  `[claim · user statement · changes decision if false: yes]`. STEP-05 selects
  no representation, so the format must work as ordinary text.
- **No scoring.** No confidence scores, weights, or readiness percentages
  (PE-4, GR-4, EKR-19).
- **No approval.** The skill never writes approved, accepted, validated, or
  verified into the file.

## Decisions by the Moderator (2026-10-04)

1. **Single skill.** Finding the problem and writing the file stay together.
2. **Gerund name.** The skill is `defining-products-w`. The `-w` suffix marks
   skills shared by MOD-W and PROD-W.
3. **Materiality in plain words.** The draft does not use the word
   "material". For each key claim the skill asks: "Would this change your
   decision if it were false?" The user's answer is recorded as `yes`, `no`,
   or `not asked`. The skill never answers it for the user (EKJ-01). A `yes`
   corresponds to a material claim in evidence model Section 4.2.

## Alignment with STEP-07 pilot findings

Checked against `79ccb6a` (provisional STEP-07 approval). Two pilot issues
changed the draft:

- **ISS-11.** A source that is the claim's own producer looks sourced unless
  marked. The draft uses the pilot's term `self-generated`, for the user's
  testimony about their own pain and for any search or test the agent runs.
- **ISS-06 and finding S-3.** A reviewer who supplies better wording becomes a
  producer and can no longer accept. When asked to review someone else's
  definition, the skill raises challenges and questions but does not supply
  replacement wording.

One burden is flagged for testing: the pilot needed about fourteen prompts
per evidence item and found the records heavy (findings G §7, S-1). The
one-question-per-turn rule could add to that, so test runs should count turns.

The repository was rechecked at `6924cc6` (2026-10-04). The two commits after
`79ccb6a` do not change the sources the draft relies on.

## Open items

- Run the six test prompts in the draft's README and record turn counts.
- The domain entry path is the least developed.
- A reviewer outside the Claude family has not looked at the draft.
