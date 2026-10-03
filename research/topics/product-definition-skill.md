---
artifact:
  type: research-note
  version: 0.1
  created: 2026-10-03
  updated: 2026-10-03
  evidence_as_of: 2026-10-03
context:
  project: prod-w-dev
  status: Proposed (research only)
  source_conversations:
    - "Claude Opus 5.5 chat on claude.ai, relayed by the Moderator, 2026-10-03: a second read of the Product Owner definition-mode observation draft, and an addendum on agent skills and naming (not archived under research/conversations/)"
    - "Claude Opus 5.5 chat on claude.ai, relayed by the Moderator, 2026-10-03: review of this session's findings and recommendations (not archived)"
    - "GitHub Copilot (Claude model) session in VS Code, 2026-10-03: checks against the repository files"
notes:
  - "Derived note. Nothing here is a PROD-W requirement, an architectural decision, or a change to MOD-W."
  - "Every reviewer named above is Claude-family, as is the Development Team's producing configuration. Under PR-27 and PR-28 this is not independent corroboration."
  - "Items marked relayed were reported by another session and not checked here."
---

# Product-Definition Skill

## Research status

This is a **research topic only**. Nothing is decided or built.

## Moderator decisions, 2026-10-03

| Item                                                               | Disposition            | Reason                                                                                                                                               |
| ------------------------------------------------------------------ | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| D1: the skill is a STEP-06 deliverable                             | **Withdrawn**          | The product-definition skill is a research topic only until PROD-W is complete. It will be built in its own repository and considered for PROD-W v2. |
| D2: override of the "earned skill" requirement, this instance only | **Withdrawn**          | Same reason. Nothing is added to `mod-w/skills/` or `prod-w/`, so nothing in this repository departs from MOD-W.                                     |
| D3: skill naming convention                                        | **Working convention** | Not recorded in any rule file in either repository. See "Naming, as a working convention".                                                           |
| D4: where the background goes                                      | This file              | Research topic, status Proposed.                                                                                                                     |

Nothing was written under D1 or D2. There is no roadmap edit, no adaptations-register entry, and no rule file.

## Plan

**Separate repository, PROD-W v2.** The skill is to be built in its own repository and considered for PROD-W v2. That repository is outside this one.

## What the Moderator wants to explore (background)

- Neither MOD-W nor PROD-W has an explicit process for helping the Moderator or user define a product.
- One agent skill, shared by both projects, would interrogate the user to define the product. The user would start from a domain, a pain point or a concept, and the skill would walk them to a product definition in the format MOD-W and PROD-W use.
- Research on similar skills comes before any design.
- Working names suggested: `discover-w` or `product-define-w`. Neither is decided.

## What an Agent Skill is (relayed, plus checks)

- A folder containing a `SKILL.md` file: YAML frontmatter with `name` and `description`, then Markdown instructions. Optional `scripts/`, `references/` and `assets/` folders. See `research/topics/agent-skills-and-protocol-relationship.md` for the Claude Code documentation summary.
- The agent always sees the name and description, loads the body when the skill triggers, and opens bundled files only as needed. (Relayed.)
- Anthropic's authoring guide (relayed; a second session reported reading it): body under 500 lines; name at most 64 characters, lowercase letters, numbers and hyphens, not containing "anthropic" or "claude" (these are rules); gerund names preferred (a suggestion), noun and action names acceptable, one pattern per collection.
- Upstream MOD-W v5 reserves `skills/` for `SKILL.md` procedures: "add skills only when a specific procedure becomes reusable", and its README layout shows `skills/` as "empty until a procedure earns one". Upstream has no top-level `skills/` folder. (Read at upstream commit `1eb5e1a`.)

## Proposal from the relaying chat (advisory, undecided)

- **Structure:** one skill, three entry paths (domain, pain point, concept) that converge on a stated problem, who has it, and how the user knows. Build the pain-point path first. The domain path is discovery, so anything the model suggests there is a hypothesis.
- **Output:** one MOD-W-compatible `product.md` with each claim marked by PROD-W class and source. How claims are marked depends on the outcome of STEP-05 (see below).
- **Interview rules taken from prior art:** ask what decision the definition serves; read sources before asking; research questions never suggest an answer; decision questions may carry a recommendation only with a stated basis; challenge solutions stated as requirements (compare MW-OBS-002).
- **Prior art (relayed, not read here):** three skills read by the relaying chat on 2026-10-03, commits not recorded: `om-discover` in `open-mercato/skills`, `brainstorming` in `obra/superpowers`, `office-hours` in `garrytan/gstack`. All three repositories carry an MIT licence file. `om-discover` was reported closest: it asks what decision the brief serves, separates research from decision questions, and marks claims by source tag and as observation, decision or hypothesis. Two of the three end in scorecards.
- **Candidate response:** a shared agent skill, working name `discover-w`, entered from a domain, pain point or concept.

## Findings from checking against the repository (advisory, same-vendor)

**No direct conflict with an accepted artifact.** Four points need care if the skill is ever taken forward:

1. **Skill name and version as configuration.** PR-27 places instructions and tooling in an action's provenance and outside actor identity. UAD4-11 (`prod-w/rule-judgment-boundary.md` Section 14, with Section 11.2) holds that a named skill is a kind of instructions and that the catalog adds no separate skill-name and version element. A separate element would need an accepted revision (BDR-16). Recording the skill and version inside the instructions statement is compatible.
2. **Scope.** NG-2 excludes CLI tools, agent harnesses, validators and integrations. NG-4 says research hypotheses are not requirements, and H-A to H-C about skills are among them. NG-3 says not to redesign MOD-W. UAD4-11 does not itself settle NG-2. The reading that a skill is instructions and not tooling is the Moderator's, to be stated in his own words if the skill is taken forward. A limit offered by a reviewer: no bundled scripts, since scripts would be tooling. That is a choice, not a requirement.
3. **User answers as evidence.** `prod-w/evidence-knowledge-model.md` Section 7.3 lists "testimony or statement, recorded as testimony" as a basis kind, and Section 7.1 says an assertion of a claim is not evidence for itself. Where the person defining the product is both source and producer, their testimony about their own pain point is not independent of the claim (EKO-04, EKJ-04).
4. **Cross-validation with the same skill.** Section 6.5 of `prod-w/protocol-semantics.md` says controlled re-execution runs share the same inputs and instructions, so a defect in either is invisible to both. That supports guidance that a cross-validating model should not run the same skill, but it is not a rule. It would be methodology guidance.

**Further checked points**

- Scorecards are excluded by PE-4 and GR-4 (`mod-w/product.md`), EKR-19 (no confidence score, weight or numeric strength) and BDR-14. They are not excluded by a Non-Goal.
- Materiality is a human judgment (EKJ-01). Evaluative claims are settled by an authorized decision and cannot be established by evidence alone (Section 9.2, EKR-28, EKJ-14). Goals are not named there, so whether goals count as value judgments is a reading, not a verified rule.
- Counter-evidence (7.4), negative findings (7.5) and limitations (7.2) are recorded elements of the evidence model.
- **STEP-05 may not settle the notation.** The roadmap says STEP-05 compares representation options "without premature selection" and produces a memo and, if evidence supports one, a recommended experiment. The skill may need a plain-prose way to mark claims that does not depend on a chosen representation.
- **GR-7 is a PROD-W requirement.** It governs gate exceptions in PROD-W the product. Applying its elements to an override in this repository would have been a choice, not an obligation. It is moot now, since D2 is withdrawn.
- Relayed and not checked here: Anthropic's naming rules; that `github.com/fpmcguire/mod-w` and `github.com/fpmcguire/moderated-ai-development-workflow` return the same commit `1eb5e1a` (reported by a second session); the contents of the three prior-art skills; the contents of upstream `agents/` and `rules/` files (file names only were seen).

## Naming, as a working convention

Not recorded in a rule file in either repository, and not binding.

- All skill names: lowercase letters, numbers and hyphens. This satisfies both the Agent Skills rule and MOD-W's lowercase-kebab-case file naming.
- A `-w` suffix for skills shared by both projects, for example `discover-w` (a working name, not decided).
- A `prod-w-` prefix for PROD-W-owned skills, as in `research/topics/prod-w-compliance-skills-pattern.md`, whose pattern is `prod-w-[domain]-[check|assessment|gate]`.
- Open: a `mod-w-` prefix for MOD-W-only skills. If adopted, it removes the ambiguity that a bare `-w` suffix and the `prod-w-` prefix both use the letter w, because a skill owned by one project would always carry that project's prefix.
- Open: noun, verb or gerund names. The compliance note uses noun phrases. Anthropic's guide, as relayed, prefers gerunds and asks for one pattern per collection.

**File-naming mismatches found** (so the rule is stated beside the convention):

- The upstream README says that inside `mod-w/` only `MOD-W.md` stays uppercase and every supporting artifact is lowercase-kebab-case. The rule is not recorded in this repository.
- Upstream `templates/` still has uppercase `ARCHITECTURE.md`, `ARCHITECTURE-NOTES.md`, `DESIGN-SPEC.md`, `PRODUCT.md`, `QA.md`, `REVIEW.md`, `ROADMAP.md` and `STEP-XX.md`, and tool-named `CLAUDE.md`, `GEMINI.md` and `MOD-W.md`.
- Files under `mod-w/reviews/` in this repository are uppercase, for example `MODERATOR-REVIEW-STEP-02.md` and `STEP-03-CARRY-FORWARD.md`.

## Format point on the compliance-skills note

`research/topics/prod-w-compliance-skills-pattern.md` shows skills as single `.md` files with `skill:`, `status:` and `owner:` frontmatter. Upstream `docs/artifacts.md` reserves `skills/` for `SKILL.md` procedures, and the Agent Skills format is a folder containing `SKILL.md` with `name` and `description` frontmatter. That note is the Tech Lead's. A format note on it goes through the Tech Lead, or is marked as a Moderator annotation. The proposed text is held for the Tech Lead and has not been applied:

> Format note (2026-10-03): upstream `docs/artifacts.md` reserves `skills/` for `SKILL.md` procedures. In the Agent Skills format each skill is a folder containing `SKILL.md`, with `name` and `description` in its frontmatter. It is not a single `.md` file with a `skill:` key. The tree and metadata template here show content only, not file format. The names follow a noun-phrase pattern, and the naming convention is pending.

## Open questions

- One skill, or two (`discover-w` to find the problem, a later `define-w` to write the file)?
- How are claims marked in the output if STEP-05 selects no representation?
- Where a shared skill lives, given it belongs to neither repository. Currently answered by the plan: its own repository, for PROD-W v2.
- The naming points listed above.

## Related

- `research/topics/agent-skills-and-protocol-relationship.md` (H-A to H-C stay open; this note does not settle them).
- `research/topics/prod-w-compliance-skills-pattern.md`.
- `research/observations/MW-OBS-DRAFT-product-owner-definition-mode.md` (unregistered draft observation on the thin Product Owner definition mode; separate from this note).

## Governance

This note lives in `research/topics/` and requires no gate. It adds no requirement, decision or change to MOD-W or to PROD-W. A skill built from it is outside this repository.
