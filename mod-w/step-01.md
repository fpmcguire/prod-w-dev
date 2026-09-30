---
artifact:
  type: step
  id: STEP-01
  version: 0.1
  created: 2026-09-30
  updated: 2026-09-30
  status: Accepted
---

# STEP-01 - Define Protocol Semantics and Authority Model

---

## Goal

Define PROD-W's initial normative protocol semantics for roles, authority, permitted actions, constraints, and self-approval invalidity.

This step produces product specification artifacts only. It does not implement tooling, validators, schemas, workflow engines, or a serialized protocol format.

---

## Governance Context

**This artifact is authored and reviewed under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-01 acceptance for `prod-w-dev`.

The future PROD-W Product Moderator is a protocol role being defined by the product. It has no current authority over this STEP-01 work unless MOD-W governance explicitly grants it in a later accepted artifact.

---

## Related Requirements

- FR-1 - Protocol must define roles and authority.
- FR-2 - Protocol must define governance semantics for progression.
- FR-4 - PROD-W governance must make self-approval invalid.
- FR-6 - Protocol must track provenance.

---

## Assigned Dev Team Interface

- [x] Claude Code (default)
- [ ] Claude Design (visual / chart / interaction-heavy Step)

---

## Scope

- Define actor, role, authority grant, action, artifact authorship, review/challenge participation, gate authority, and acceptance concepts.
- Define the distinction between producing evidence, assessing/challenging evidence, verifying formal criteria, and accepting consequential gates.
- Define normative self-approval invalidity in representation-neutral terms.
- Define initial action categories such as create claim, attach evidence, challenge claim, verify formal criteria, accept gate, request revalidation, and record decision.
- Define invalid action examples for downstream validation design.
- Identify which semantics require human authority and which can later be mechanically checked.
- Keep MOD-W Moderator and PROD-W Product Moderator distinct.

---

## Out of Scope

- Selecting YAML, JSON, JSON Schema, TypeScript/Zod, DSL, MCP, A2A, workflow engine, document metadata, or centralized state.
- Defining full evidence taxonomy or sufficiency criteria.
- Defining final state names.
- Implementing validators, CLI tooling, prompts, schemas, or runtime integrations.
- Granting external evaluators consequential gate authority.
- Modifying `mod-w/product.md` or canonical templates under `mod-w/templates/`.

---

## Inputs

- `mod-w/product.md`
- `mod-w/architecture.md`
- `mod-w/domain-language.md`
- `research/topics/protocol-schema-state-distinction.md`
- `research/topics/prod-w-protocol-first-rationale.md`
- `research/mod-w-transferability/README.md`

---

## Expected File Changes

- Add `prod-w/protocol-semantics.md`
- Update `mod-w/domain-language.md` only if new accepted terms are introduced.
- Add a proposed transferability observation under `research/mod-w-transferability/observations.md` if this step reveals concrete MOD-W transferability evidence.

---

## Reference Implementation

**Location:** `n/a`

**Disposition:**

- [ ] Adopt as-is - preserve approved behavior and relevant structure; adapt normally for production
- [ ] Adopt with modifications - see "Required Changes" below
- [ ] Reject - Dev Team implements from scratch per acceptance checks
- [x] None - no Reference Implementation exists for this Step

---

## Acceptance Checks

**Governance Note:** These acceptance checks operationalize Architectural Decisions D1-D8 documented in `mod-w/architecture.md`. STEP-01 produces the normative text that primarily operationalizes D1-D4 and validates relevant boundaries from D6 and D8; STEP-02 and STEP-03 will operationalize D5-D8 more fully. Reference the architecture for context and rationale.

- [x] Protocol semantics distinguish protocol, schema, and state. _(Implements D2, D3)_
- [x] Roles and authority are defined without relying on role names alone. _(Implements D4)_
- [x] Actor identity, artifact producer, reviewer/challenger, and approver are distinguishable. _(Implements D4)_
- [x] Self-approval invalidity is stated as a normative constraint. _(Implements D4, D6)_
- [x] Consequential gate acceptance remains explicitly human-authorized where required. _(Implements D6)_
- [x] External evaluator findings are advisory unless authority is explicitly granted. _(Implements D8)_
- [x] MOD-W Moderator and PROD-W Product Moderator are not conflated. _(Implements governance boundary)_
- [x] No implementation technology or serialization has been selected prematurely. _(Implements D2)_
- [x] Any transferability evidence encountered has been proposed under the research governance process. _(Implements research boundary)_

Checked 2026-09-30 per `mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-DEV-TEAM.md` Section 2 (all nine checks Pass) and `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md`. Phase 3a (Tech Lead review), 3b (QA), and 3c (Product Owner sign-off) were none of them run for this deliverable; all three are recorded as explicit waivers per GR-7/OBJ-12 (delta review Sections 5 and 9), not as satisfaction of this checklist by another means.

---

## Plan

1. Extract authority and role requirements from the accepted Product Definition.
2. Define representation-neutral protocol concepts and action categories.
3. Define self-approval invalidity and authority-conflict examples.
4. Classify initial objective checks versus contextual human judgments.
5. Identify unresolved design questions for later steps.
6. Record transferability observations if concrete evidence emerges.

### Research Governance Route

As STEP-01 work proceeds, if you observe concrete evidence about how MOD-W's Product Definition, Architecture, or Role concepts transfer (or don't transfer) to protocol development, propose an observation to the MOD-W transferability register:

1. **Record the observation draft** in `research/mod-w-transferability/observations.md` following the template structure (see existing observations MW-OBS-001 through MW-OBS-006).
2. **Include concrete evidence**: references to artifacts, pattern descriptions, and effect on work.
3. **Use an appropriate classification**: `TRANSFERS_UNCHANGED`, `TRANSFERS_WITH_REINTERPRETATION`, `REQUIRES_LOCAL_ADAPTATION`, `DOMAIN_COUPLED`, or `NOT_YET_TESTED`. See `research/mod-w-transferability/README.md` for definitions. (Corrected 2026-09-30: this list previously omitted `DOMAIN_COUPLED` and used the non-canonical name `LOCAL_ADAPTATION_PROPOSED`; see `mod-w/validation/dev-team-step-01-discrepancy-report.md` DTD-01/DTD-02 and `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Section 1.)
4. **Set disposition to "Proposed"**: the MOD-W Moderator will review and accept/modify during the next review gate.

Observations are **not** blocking on STEP-01 completion. They are recorded in parallel and reviewed independently by the Moderator. Do not treat a proposed observation as resolved or decided until the Moderator disposition is updated to "Accepted."

See `research/mod-w-transferability/README.md` for full research governance rules.

---

## Change Notes

| Date       | Change             | Reason                             |
| ---------- | ------------------ | ---------------------------------- |
| 2026-09-30 | Initial step draft | First architecture-planning phase. |
