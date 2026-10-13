---
artifact:
  type: research-note
  version: 0.1
  created: 2026-10-12
  updated: 2026-10-13
  evidence_as_of: 2026-10-13
context:
  project: prod-w-dev
  status: research
  source_conversations:
    - "research/conversations/2026-10-12-mod-w-project-workflow-observations.md (Moderator-authored, archived verbatim)"
notes:
  - "Derived note. Nothing here is a PROD-W requirement, an architectural decision, or a change to MOD-W or to any accepted artifact."
  - "The source observations come from a separate MOD-W project run by the same Moderator. They are cross-project evidence, not prod-w-dev events, so no MW-OBS number is assigned here."
  - "Drafted by a Claude-family model (Claude Code, 2026-10-12). Mappings to accepted artifacts were checked by searching for terms and reading the passages cited. They are not independent verification (PR-27, PR-28)."
---

# Moderator Workflow Observations from a Second MOD-W Project

## Research status

This is a **routing note**. It records where each of six Moderator observations from a separate MOD-W project lands in `prod-w-dev`, what it adds to the existing records, and what remains for the Moderator to decide.

It does not reopen any accepted Step and does not change the roadmap. It does not modify canonical MOD-W templates under `mod-w/templates/` (Canonical MOD-W Protection Rule, `research/mod-w-transferability/README.md`) or accepted PROD-W artifacts under `prod-w/`.

## Why it matters here

`research/mod-w-transferability/README.md` defers conclusions about canonical MOD-W changes "until sufficient evidence from multiple projects" accumulates. This source is the first written evidence from a second MOD-W project. It bears most directly on MW-OBS-020 and on the product-definition skill topic.

### Limits of the source

- **Domain unknown.** The source says "a new Mod W project" and mentions code review, build and tests, which suggests software. It does not state the domain. Readings below that depend on domain are marked. *Resolved 2026-10-13: software. See "Source project identified" below.*
- **Same Moderator.** Both projects have the same human Moderator. The second project is a different setting, but the observer is the same person.
- **No artifacts.** The source names no repository, files or commits from the other project. Its claims cannot be checked from here.
- **Proposals included.** Each observation mixes what happened with proposed changes. Only the "Observation" parts are evidence. The "Idea", "Decision" and "For consideration" parts are proposals.

## Routing summary

| # | Source observation | Closest existing record in `prod-w-dev` | What it adds | Action taken in this repository |
|---|---|---|---|---|
| 1 | Role handoffs and review replies need to be self-explanatory | MW-OBS-020; `mod-w/id-glossary.md`; MW-OBS-014 (numbered-list collision); MW-OBS-018 (one identifier, two meanings) | Recurrence in a second project; a spell-out rule for cited identifiers | Cross-project evidence appended to MW-OBS-020 |
| 2 | MOD-W now has a traceable history (positive) | `mod-w/reviews/`, roadmap status, step tags; PROD-W Gate Decision Record (`prod-w/templates.md` §15) | Positive evidence for the review record; asks for a commit hash in each entry | None. Recorded here |
| 3 | Tech Lead's architecture and roadmap need fuller explanation | `mod-w/templates/ARCHITECTURE.md`, `ROADMAP.md`; `prod-w/representation-options.md`; `research/topics/model-depth-tech-lead-self-review.md` | A gap in the canonical templates: no alternatives or ordering rationale | None. Template proposal deferred (see below) |
| 4 | No product ideation facility: propose Discover-W | `research/topics/product-definition-skill.md`; `research/topics/product-owner-definition-mode.md` | Moderator decision to create the skill; a naming convention; open questions | Update section added to `product-definition-skill.md` |
| 5 | Step-by-step moderation lets the Moderator steer mid-development (positive) | STEP-04 revision and fold-in reviews; `prod-w/gate-challenge-revalidation-semantics.md`; WD-6 | Positive evidence; asks for a named change-request path | None. Recorded here |
| 6 | Every gate approval must trigger record, commit, and next prompt | MW-OBS-020 (proposed local adaptation) | A stricter rule than MW-OBS-020 proposes; a rejection path | Cross-project evidence appended to MW-OBS-020; tension listed below |

## Observation by observation

### 1 and 6. Gate closing protocol and readable identifiers

**Relation to MW-OBS-020.** MW-OBS-020 (2026-10-07, Proposed) records the same burden in `prod-w-dev`: the Moderator repeatedly asks for the next gate, a summary, and the next role's prompt, then asks for the approval to be recorded and committed. Its proposed local adaptation is a six-item gate-transition summary after every Moderator decision.

**What the source adds:**

- **Recurrence in a second project.** MW-OBS-020's interpretation says the burden "increases when work products are records and reviews rather than code changes with a familiar CI/release path". If the second project is a software project, the same burden appeared there too. That would weaken the reading that the burden comes from the non-software domain. It would favour a reading that it comes from MOD-W's gate structure. This depends on the unstated domain.
- **A rejection path.** On rejection: record the decision, do not commit, and generate a revision prompt for the same gate instead of the next gate's prompt. MW-OBS-020 does not distinguish rejection.
- **Ordering.** Log first, then commit, then add the commit hash to the log entry.
- **Spelled-out identifiers.** Each cited code should be followed by its plain-language wording, for example "AC2 (the form shows a validation error when the email is empty)". In `prod-w-dev`, `mod-w/id-glossary.md` explains prefixes only and says so ("Coverage: Prefixes only"). Identifier confusion is already on record here: MW-OBS-014 (a reviewer's "step 2" read as STEP-02), MW-OBS-018 (one identifier with two meanings), and the AC-4 against AC-04 collision noted in `mod-w/id-glossary.md` §1.1. A spell-out rule would address all three. Whether it would is untested.

**Tension, not resolved here.** The source's rule commits on every approval. MW-OBS-020's proposed adaptation says "the agent should also ask before committing or pushing unless the Moderator has already explicitly requested that action". These differ. The Moderator decides which applies in `prod-w-dev`. A standing instruction to commit on approval would satisfy MW-OBS-020's "explicitly requested" condition, if the Moderator issues one.

### 2. Traceable history (positive)

In `prod-w-dev` the equivalent record is the set of files under `mod-w/reviews/`, the roadmap Status and Notes columns, and step tags such as `step-04-complete`. Commit hashes are not recorded in review files as a rule. The roadmap-status drift noted in MW-OBS-020 shows that the record can drift without a hygiene step.

**PROD-W check requested by the source.** PROD-W has a Gate Decision Record template (`prod-w/templates.md` §15) and treats provenance as a requirement (FR-6, PR-27). Its protocol is representation-neutral and selects no tooling (NG-1, NG-2; STEP-05 acceptance). A version-control commit would be one possible provenance reference, not a required one. This note did not check whether any accepted PROD-W text names commit references.

### 3. Tech Lead explanation of architecture and roadmap

**Checked against canonical templates.** `mod-w/templates/ARCHITECTURE.md` gives each decision the fields Context, Decision, Rationale and Consequences. It has no field for alternatives considered or for the ramifications of each alternative. `mod-w/templates/ROADMAP.md` has Summary, Steps, Step Details and Coverage Check, with no field for ordering rationale. The source's complaint matches the templates.

**In `prod-w-dev`.** `mod-w/architecture.md` follows the template (D1 to D10) and adds a Deferred Decisions section. The one place this project compared alternatives explicitly was STEP-05, whose deliverable (`prod-w/representation-options.md`) is itself an options memo. That happened because the roadmap made option comparison a Step, not because the architecture template asked for it.

**Pre-workflow work.** The source says ideation done outside the workflow leaves no log entries. `prod-w-dev` partly avoided this by archiving its origin conversation (`research/conversations/2026-09-29-prod-w-origin-protocol-research-conversation.md`). That is a counterexample on record: the gap can be closed by archiving, without a new skill.

**Related.** `research/topics/model-depth-tech-lead-self-review.md` records that reasoning depth changed what a Tech Lead review surfaced. A required alternatives section would make some of that reasoning visible regardless of depth. This is a hypothesis, not a finding.

### 4. Discover-W

See the 2026-10-12 update in `research/topics/product-definition-skill.md`. In short: the source records a Moderator decision to create the skill, which is consistent with the 2026-10-03 plan to build it in its own repository for PROD-W v2. It also states a naming convention that conflicts with a pattern in another note, and it adds open questions.

### 5. Mid-cycle steering (positive)

In `prod-w-dev`, mid-step redirection has happened through revision briefs and fold-ins, for example `mod-w/reviews/MODERATOR-REVIEW-STEP-04-REVISION-BRIEF.md` and `MODERATOR-REVIEW-STEP-04-FOLD-IN.md`. These are ad hoc in form. MOD-W names no "accept with changes" or change-request decision.

For PROD-W, the closest accepted mechanism is revalidation: WD-6 (dependent decisions need revalidation) and `prod-w/gate-challenge-revalidation-semantics.md`. The source's request for an impact statement before a change is confirmed resembles revalidation triggered by an upstream change. This mapping is a reading and was not checked passage by passage.

## Proposals for canonical MOD-W (deferred)

The following are proposals for upstream MOD-W. Under the Canonical MOD-W Protection Rule they are **not** applied to `mod-w/templates/` here. They are listed so STEP-08 can dispose of them alongside the transferability findings.

1. A shared closing protocol referenced by every role prompt: summary, what the Moderator must review, decision request, record, commit on acceptance, next role and prompt. Sources: 1, 5, 6; MW-OBS-020.
2. A rejection path and an "accept with changes" path in that protocol. Sources: 5, 6.
3. A spell-out rule for every cited identifier, with a per-item lookup table. Source: 1; MW-OBS-014, MW-OBS-018.
4. A standard log entry: role or gate, date, decision, identifiers spelled out, change requests, commit hash. Sources: 2, 6.
5. The role sequence defined once, so each role can name its successor. Source: 1.
6. An "options and ramifications" section in `ARCHITECTURE.md` and a "roadmap rationale" section in `ROADMAP.md`, with the architecture accepted before the roadmap. Source: 3.
7. A defined hand-off from the Claude Designer prototyping path to the Tech Lead. Source: 3. `mod-w/templates/ARCHITECTURE-NOTES.md` already provides a prototype-to-Tech-Lead channel. Whether it covers this was not checked.

## Open questions for the Moderator

1. Should the cross-project evidence change MW-OBS-020's proposed classification or interpretation when it is disposed?
2. Commit on approval by default, or ask first (the tension above)? *Answered 2026-10-13: commit on approval by default. See below.*
3. Was the second project a software project? The answer changes how item 1 bears on MW-OBS-020. *Answered 2026-10-13: yes. See below.*
4. Should a spell-out rule be trialled in STEP-08 as a local practice? That would need a proposed adaptation in `adaptations.md` first.
5. Which naming convention governs skills (see `product-definition-skill.md`)?

## Moderator decision, 2026-10-12

The MOD-W Moderator approved the observation-related updates on 2026-10-12:

- the verbatim archive `research/conversations/2026-10-12-mod-w-project-workflow-observations.md`;
- this routing note;
- the cross-project evidence appended to MW-OBS-020 in `research/mod-w-transferability/observations.md`;
- the 2026-10-12 update section in `research/topics/product-definition-skill.md`;
- the later-evidence section appended to `research/topics/product-owner-definition-mode.md`.

**Scope of the approval.** It accepts these records into the research record. It does not dispose of MW-OBS-020, which remains Proposed. It does not answer the open questions above, adopt any proposal for canonical MOD-W, or authorize a local adaptation.

## Moderator decision, 2026-10-13: commit on approval

The MOD-W Moderator decided on 2026-10-13: **commit on approval by default.**

- **Applies to:** `prod-w-dev`. When the Moderator approves a change, the agent records the approval and makes a conventional commit without asking first.
- **Relation to MW-OBS-020.** The proposed adaptation there says to ask before committing "unless the Moderator has already explicitly requested that action". This decision is that explicit request, given as a standing instruction. It resolves the tension recorded in "1 and 6" above.
- **Not covered:** pushing, tagging, and rejected work. Pushing and tagging still need a request. A rejection is recorded but not committed, as the source proposes; this part is a reading, not a stated decision.
- **Not a disposition.** MW-OBS-020 remains Proposed, and no entry is added to `adaptations.md`.

## Source project identified, 2026-10-13

The Moderator stated on 2026-10-13 that the "new Mod W project" in the source is one of two repositories:

| Repository | Created | Last push | Code base | MOD-W artifacts |
|---|---|---|---|---|
| `https://github.com/fpmcguire/kira-n-calvin-memory` | 2026-10-10 | 2026-10-13 | Angular/TypeScript application (TypeScript, HTML, SCSS); Playwright e2e tests | `mod-w/` with product, architecture, architecture notes, design spec, roadmap, STEP-01 to STEP-06, QA, review, sign-off, `evidence/`; top-level `prototype/` |
| `https://github.com/fpmcguire/idp-align` | 2026-09-21 | 2026-09-27 | Angular/TypeScript application; Playwright e2e tests | `mod-w/` with product, architecture, roadmap, STEP-01 to STEP-10, cross-validation, `validation/`; described as a "MOD-W v5.0.1 proof-of-implementation and CAV ... research prototype" |

Read from the public GitHub API (repository metadata, language breakdown, top-level and `mod-w/` listings) on 2026-10-13. File contents were not read.

**Domain: software, whichever repository it is.** Both are conventional software projects with executable code and end-to-end tests. This settles the domain question in "1 and 6" above.

**Probably `kira-n-calvin-memory`.** It is new (created two days before the source's compile date), it was active on 2026-10-12, and its `prototype/` folder fits the source's Claude Designer prototyping path (Observation 3). `idp-align` had no pushes after 2026-09-27. This is an inference. The Moderator did not say which.

**Bearing on MW-OBS-020.** The gate-navigation burden recurred in a software MOD-W project. That weakens MW-OBS-020's reading that the burden grows because work products are "records and reviews rather than code changes". It favours a reading that the burden comes from MOD-W's gate structure in general. The limits still apply: same Moderator, a self-report, and no workflow-log entries from the other repository were read.

**Recording approved.** The MOD-W Moderator approved recording this section and the matching MW-OBS-020 line on 2026-10-13. This is not a disposition of MW-OBS-020.

## Related

- `research/mod-w-transferability/observations.md` (MW-OBS-014, MW-OBS-018, MW-OBS-020)
- `research/topics/product-definition-skill.md`
- `research/topics/product-owner-definition-mode.md`
- `research/topics/model-depth-tech-lead-self-review.md`
- `mod-w/id-glossary.md`

## Governance

This note lives in `research/topics/` and requires no gate.
