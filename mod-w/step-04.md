---
artifact:
  type: step
  id: STEP-04
  version: 0.1
  created: 2026-10-02
  updated: 2026-10-02
  status: Approved
---

# STEP-04 - Separate Machine-Checkable Rules from Human Judgment

---

## Goal

Define PROD-W's representation-neutral boundary between objectively checkable protocol conditions and contextual human judgments.

This step produces a product specification artifact only. It does not implement validators, schemas, workflow engines, lifecycle graphs, state machines, serialized state vocabularies, storage models, prompts, agent harnesses, or tooling.

The Development Team must identify which accepted STEP-01, STEP-02, and STEP-03 rules and conditions can be checked from available records, which require contextual human judgment, and which have an objective check paired with a separate judgment. The output must make later representation and validator work possible without choosing that representation or validator.

---

## Governance Context

**This artifact is authored and reviewed under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-04 acceptance for `prod-w-dev`.

The future PROD-W Product Moderator is a protocol role being defined by the product. It has no current authority over this STEP-04 work unless MOD-W governance explicitly grants it in a later accepted artifact.

STEP-04 must apply active local adaptation **MW-ADAPT-001**. The Development Team deliverable must include an Undecided Architecture Declaration listing choices not already decided by accepted upstream artifacts, especially choices about what is considered objectively checkable, what requires human judgment, and what is merely a candidate for later validation. After that declaration, **Tech Lead or QA sampling for unlisted choices is expected before Moderator acceptance**, with particular attention to authority, independence, evidence standing, revalidation, and any hidden representation choices.

For STEP-04, the expected review sequence is:

| MOD-W point | Expected handling |
| --- | --- |
| 2a Plan approval | Development Team may proceed directly from this work package unless the Moderator requests a separate plan checkpoint. |
| 2b Development Team work product | Development Team drafts the STEP-04 product artifact. |
| 3a Tech Lead review | Expected before final Moderator acceptance. Must include MW-ADAPT-001 sampling unless QA is explicitly assigned that sampling. |
| 3b QA | Expected before final Moderator acceptance unless the Moderator explicitly waives it before final acceptance. QA should sample rule/judgment classifications, traceability, and forbidden representation choices. |
| 3c Product Owner sign-off | Expected before final Moderator acceptance unless the Moderator explicitly waives it before final acceptance. |
| 4a Moderator acceptance | Final acceptance only after required reviews or explicit recorded waivers. |

---

## Related Requirements

- FR-3 - Protocol must define evidence requirements, including objectively checkable evidence conditions and contextual sufficiency judgments.
- FR-4 - PROD-W governance must make self-approval invalid or detectable as invalid.
- FR-6 - Protocol must track provenance sufficient to identify current status, challenge history, and acceptance history.
- G-3 - PROD-W must support a machine-readable protocol that can validate objectively checkable rules while remaining human-reviewable and auditable.
- PE-1 - Material claims require traceable evidence.
- PE-2 - Agent agreement is not independent evidence.
- PE-3 - Inference and fact remain distinct.
- PE-4 / GR-4 - Do not hide uncertainty behind artificial precision.
- HA-1 / HA-2 - Consequential decisions require explicitly authorized human judgment.
- WD-2 - Unresolved disagreement may remain visible.
- WD-6 - Dependent decisions require revalidation when material support changes.
- NG-1 / NG-2 - Do not select implementation technology or build tooling prematurely.

---

## Related Architecture Decisions

| Decision | Relevance to STEP-04 |
| --- | --- |
| D1 - Protocol Semantics Are Normative | The rule/judgment boundary is a semantic artifact, not a validator implementation. |
| D2 - Protocol, Schema, and State Remain Separate | STEP-04 must not select schemas, state names, lifecycle graphs, storage models, or serialized forms. |
| D3 - Knowledge Classes Are First-Class Domain Concepts | Machine-checkable rules must preserve accepted distinctions among claims, evidence, assumptions, hypotheses, inferences, decisions, challenges, dependencies, provenance, validation, invalidation, withdrawal, supersession, correction, exposure, and revalidation. |
| D4 - Authority Is Modeled Separately from Role Labels | Checkable authority and independence conditions must be grounded in actor identity, grants, scope, and participation capacity, not role-name matching. |
| D5 - Disagreement Is a Preserved Condition, Not Necessarily a State Name | STEP-04 may classify disagreement-related checks, but must not pick whether disagreement is represented as state, relationship, property, or record pattern. |
| D6 - Objectively Checkable Governance Is Separated from Human Judgment | STEP-04 is the main boundary artifact for this decision. |
| D7 - Provenance and Dependencies Support Revalidation | STEP-04 must classify revalidation trigger, exposure, reliance, closure, and provenance checks without deciding storage or graph mechanics. |
| D8 - External Evaluators Are Advisory Interfaces Unless Explicitly Granted Authority | STEP-04 must keep evaluator findings from becoming automated acceptance. |
| D9 - Working Product Artifacts Live Under `prod-w/` in `prod-w-dev` | The accepted STEP-04 product artifact must live under `prod-w/`. |

---

## Assigned Dev Team Interface

- [x] Claude Code (default)
- [ ] Claude Design (visual / chart / interaction-heavy Step)

---

## Scope

- Produce a representation-neutral rule/judgment boundary artifact under `prod-w/`.
- Define what makes a condition **objectively checkable**: decidable from the available record without interpreting the world the record describes or judging sufficiency, persuasion, risk, acceptability, or materiality beyond recorded designations.
- Define what makes a condition a **contextual human judgment**: a decision requiring interpretation of sufficiency, relevance, risk, persuasion, adequacy, materiality, warrant, independence in substance, or acceptability.
- Define the allowed middle pattern: an objective check may confirm that a judgment was recorded by an authorized actor, but must not decide the substance of that judgment.
- Create a candidate catalog of checkable conditions from STEP-01 `OBJ-*`, STEP-02 `EKO-*`, STEP-03 `GCO-*`, and any rule IDs whose violation is objectively detectable.
- Create a paired catalog of human judgments from STEP-01 `HJ-*`, STEP-02 `EKJ-*`, STEP-03 `GCJ-*`, and any accepted rule whose application requires contextual judgment.
- For every catalog entry, trace to the accepted source ID or explain that it is a derived grouping over accepted IDs.
- Carry forward and address STEP-03 open questions routed to STEP-04, especially:
  - `GC-OQ-01` - which GCO conditions become catalog rules, and whether violations are blocked, flagged, or escalated.
  - `GC-OQ-02` - authority grants: creation, scope, change, revocation, audit, and self-conferral.
  - `GC-OQ-03` - whether AI agents may hold AUTH-V, and what rule form carries verifier independence.
  - `GC-OQ-09` - whether authorizations may carry protocol-effective terms, such as lapse dates.
  - `GC-OQ-11` - whether assumption-rooted identification and never-a-correction tripwires become catalog rules.
  - `EK-OQ-09` - producing-configuration and evidence-lineage granularity, and whether insufficient provenance invalidates an action or weakens it.
  - `EK-OQ-14` - which EKO conditions become machine-checkable rules and how detected violations are handled.
- Address upstream related questions routed to STEP-04, including `PS-OQ-02`, `PS-OQ-05`, `PS-OQ-08`, `PS-OQ-10`, and `PS-OQ-13`, where not already resolved by STEP-03.
- Define violation-handling categories at the semantic level, such as invalidating, blocking candidate, flagging, escalating, or recording as unresolved, without selecting an enforcement mechanism or runtime behavior.
- State how invalid action detection relates to protocol effect: an invalid action does not produce its intended protocol effect, but the record of the attempt remains visible.
- Require an Undecided Architecture Declaration under MW-ADAPT-001.
- Identify open questions that belong to STEP-05, STEP-06, STEP-07 pilot work, STEP-08 research synthesis, or later publication work.

---

## Out of Scope

- Selecting YAML, JSON, JSON Schema, TypeScript/Zod, Markdown metadata, sidecars, a DSL, MCP, A2A, graph database, ledger, document metadata, centralized state, hybrid state, or any other representation.
- Selecting, designing, or implementing a validator, CLI tool, rules engine, workflow engine, agent harness, prompt format, runtime integration, database, API, schema, or test suite.
- Defining final serialized state names, condition names, transition names, event schemas, lifecycle graphs, state machines, graph traversal algorithms, or storage indexes.
- Defining how derived conditions are computed in a concrete representation; STEP-05 owns representation options.
- Producing methodology templates, role charters, evidence collection worksheets, gate templates, examples, or practitioner guidance; STEP-06 owns methodology guidance.
- Defining evidence category thresholds by product category, customer-evidence sufficiency criteria, or speed-versus-rigor tradeoffs; STEP-06 and STEP-07 own those as routed.
- Granting external evaluators consequential authority by default.
- Reopening accepted STEP-01, STEP-02, or STEP-03 semantics unless a direct conflict is discovered and routed as a Moderator-visible issue.
- Modifying accepted product artifacts unless explicitly required by this work package or separately authorized by the MOD-W Moderator.

---

## Inputs

Accepted inputs:

- `mod-w/product.md`
- `mod-w/architecture.md`
- `mod-w/domain-language.md`
- `mod-w/roadmap.md`
- `mod-w/step-03.md`
- `mod-w/reviews/MODERATOR-REVIEW-STEP-03.md`
- `prod-w/protocol-semantics.md`
- `prod-w/evidence-knowledge-model.md`
- `prod-w/gate-challenge-revalidation-semantics.md`
- `research/mod-w-transferability/observations.md`
- `research/mod-w-transferability/adaptations.md`

Useful supporting inputs if needed for traceability:

- `mod-w/step-01.md`
- `mod-w/step-02.md`
- `mod-w/reviews/STEP-03-CARRY-FORWARD.md`
- `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02-FOLLOWUP.md`
- `mod-w/reviews/TECH-LEAD-REVIEW-STEP-03-SETUP.md`

---

## Expected File Changes

Add:

- `prod-w/rule-judgment-boundary.md`

Optional, only if needed:

- Append proposed transferability evidence to `research/mod-w-transferability/observations.md` if STEP-04 reveals concrete evidence about MOD-W transferability, document-native QA, MW-ADAPT-001 effectiveness, or rule-catalog review.

Do not modify accepted STEP-01, STEP-02, or STEP-03 product artifacts unless the MOD-W Moderator separately authorizes a correction or STEP-04 acceptance explicitly calls for a new accepted artifact revision.

---

## Reference Implementation

**Location:** `n/a`

**Disposition:**

- [ ] Adopt as-is - preserve approved behavior and relevant structure; adapt normally for production
- [ ] Adopt with modifications - see "Required Changes" below
- [ ] Reject - Dev Team implements from scratch per acceptance checks
- [x] None - no Reference Implementation exists for this Step

---

## Required Output Structure

`prod-w/rule-judgment-boundary.md` must include, at minimum:

1. Purpose and standing.
2. Governance context, including MW-ADAPT-001.
3. Relationship to STEP-01, STEP-02, and STEP-03 artifacts.
4. Boundary definitions:
   - objectively checkable condition;
   - contextual human judgment;
   - recorded judgment check;
   - candidate rule;
   - detected violation;
   - unresolved or uncheckable condition.
5. Classification criteria and decision tests for assigning an entry to objective check, human judgment, recorded-judgment check, or deferred.
6. Candidate machine-checkable rule catalog.
7. Human judgment catalog.
8. Paired objective-check / human-judgment table.
9. Violation-handling semantics, including blocked, invalidating, flagged, escalated, visible exception, and no automated conclusion, without selecting a validator implementation.
10. Authority, independence, and self-approval rule boundary, including authority grants and self-conferral routing.
11. Provenance, producing-configuration, and lineage rule boundary, including `EK-OQ-09`.
12. Evidence, assumption, hypothesis, inference, disagreement, challenge, gate, correction, supersession, withdrawal, exposure, and revalidation rule boundary.
13. Open-question dispositions and routing, explicitly covering `GC-OQ-01`, `GC-OQ-02`, `GC-OQ-03`, `GC-OQ-09`, `GC-OQ-11`, `EK-OQ-09`, and `EK-OQ-14`.
14. Undecided Architecture Declaration under MW-ADAPT-001.
15. Traceability to STEP-01, STEP-02, and STEP-03 rule/condition/judgment IDs.
16. Acceptance-check traceability.
17. Change notes.

The Development Team may adjust section order if useful, but every acceptance check must remain traceable to a specific section.

---

## Acceptance Checks

- [ ] `prod-w/rule-judgment-boundary.md` is added and is explicitly representation-neutral.
- [ ] The artifact defines objective checkability as decidability from the available record without interpreting the world described by the record or judging sufficiency, persuasion, risk, materiality, acceptability, or substantive independence.
- [ ] The artifact defines contextual human judgment as requiring authorized human interpretation of sufficiency, relevance, warrant, risk, materiality, acceptability, or substantive independence.
- [ ] The artifact distinguishes a check that a judgment was recorded by an authorized actor from the judgment's substance.
- [ ] The artifact defines candidate machine-checkable rule, detected violation, recorded judgment check, unresolved condition, and deferred-to-representation categories.
- [ ] The rule catalog traces every entry back to STEP-01, STEP-02, or STEP-03 IDs, including `PR-*`, `ACT-*`, `OBJ-*`, `HJ-*`, `EKR-*`, `EKO-*`, `EKJ-*`, `TRG-*`, `GCR-*`, `GCO-*`, and `GCJ-*` where applicable.
- [ ] The artifact explicitly classifies STEP-01 `OBJ-*`, STEP-02 `EKO-*`, and STEP-03 `GCO-*` conditions as catalogued rules, recorded-judgment checks, deferred candidates, or out-of-catalog with rationale.
- [ ] The artifact explicitly carries forward and disposes `GC-OQ-01`, including which GCO conditions become candidate catalog rules and the semantic handling categories for detected violations.
- [ ] The artifact explicitly carries forward and disposes `GC-OQ-02`, including authority grant creation, scope, change, revocation, audit, and whether self-conferral of AUTH-G over a scope is invalid, deferred, or governed by an interim constraint.
- [ ] The artifact explicitly carries forward and disposes `GC-OQ-03`, including AI-held AUTH-V and verifier independence rule form, without allowing verification to become acceptance.
- [ ] The artifact explicitly carries forward and disposes `GC-OQ-09`, including whether protocol-effective authorization terms are rule-catalog candidates, representation questions, pilot questions, or rejected.
- [ ] The artifact explicitly carries forward and disposes `GC-OQ-11`, including whether assumption-rooted identification and never-a-correction tripwires become candidate catalog rules.
- [ ] The artifact explicitly carries forward and disposes `EK-OQ-09`, including producing-configuration and evidence-lineage granularity and whether insufficiency invalidates an action, weakens standing, triggers a flag, or remains a human judgment.
- [ ] The artifact explicitly carries forward and disposes `EK-OQ-14`, including which EKO conditions become machine-checkable rule candidates and how detected violations are semantically handled.
- [ ] The artifact preserves STEP-03's boundary that STEP-05 owns representation choices for derived conditions, item identity across change, accepted-set closure computation, serialized state vocabulary, lifecycle graphs, and machine views.
- [ ] The artifact preserves STEP-03's boundary that STEP-06 owns methodology templates, role charters, evidence-category thresholds, gate templates, examples, and practitioner guidance.
- [ ] The artifact states that evaluator outputs, automated checks, verification records, and validator findings remain advisory or formal-check results unless accepted PROD-W protocol grants the relevant authority.
- [ ] The artifact states that mechanical detection may block, flag, escalate, or show invalidity only at the semantic level; it must not decide contextual sufficiency or replace human gate acceptance.
- [ ] The artifact states that absence of a mechanical check does not make a protocol requirement optional.
- [ ] The artifact does not introduce confidence scores, numeric sufficiency weights, or artificial precision for evidence strength or judgment quality.
- [ ] The artifact includes an Undecided Architecture Declaration under MW-ADAPT-001, including choices about catalog membership, violation handling, producing-configuration granularity, authority grants, verifier independence, and any derived rule groupings.
- [ ] The Development Team declaration is followed by Tech Lead or QA sampling for unlisted choices before Moderator acceptance, with a sampling note in the review record.
- [ ] The artifact identifies remaining open questions routed to STEP-05, STEP-06, STEP-07, STEP-08, or later work without duplicating ownership.
- [ ] No schema language, storage model, workflow engine, validator implementation, lifecycle graph, serialized state vocabulary, protocol transport, CLI, prompt format, or runtime integration is selected.
- [ ] Any concrete transferability evidence encountered is proposed under the research governance process.
- [ ] STEP-04 final acceptance is not recorded until Phase 3a Tech Lead review, Phase 3b QA, and Phase 3c Product Owner sign-off have occurred, or the MOD-W Moderator has explicitly waived any missing review before final acceptance.

---

## Tech Lead Recommendations to the Development Team

These recommendations are not themselves accepted product semantics. They are intended to keep STEP-04 from accidentally drifting into STEP-05 representation work or STEP-06 methodology guidance.

1. Start with the accepted ID sets, not prose themes. Build the catalog by extracting `OBJ-*`, `EKO-*`, `GCO-*`, `HJ-*`, `EKJ-*`, and `GCJ-*`, then add rule IDs only where a violation is objectively detectable.
2. Use a three-part test for objective checks: the required record elements are defined; the check can be answered from those records alone; the answer does not decide sufficiency, persuasion, materiality, or risk.
3. Treat "presence of an authorized judgment record" as checkable, but the judgment itself as human unless an accepted upstream artifact already made it purely objective.
4. Be conservative with invalidation. If insufficient provenance or missing configuration could either invalidate an action or weaken evidentiary standing, declare the choice under MW-ADAPT-001 and explain why the selected consequence follows from accepted semantics.
5. Keep violation handling semantic. "Blocked," "flagged," and "escalated" are allowed as protocol consequences; a validator, UI, CLI, schema keyword, or workflow engine is not.
6. Do not harden words like contested, exposed, open requirement, current, validated, invalid, retired, or superseded into serialized state names. They may appear as semantic conditions only.
7. When in doubt, route representation questions to STEP-05 and human-practice questions to STEP-06. STEP-04 should make those downstream steps cleaner, not pre-decide them.

---

## Plan

1. Read the accepted inputs and extract every STEP-01, STEP-02, and STEP-03 rule, objective condition, and judgment identifier.
2. Build a source-ID inventory, grouped by authority/independence, evidence/provenance, knowledge-class distinction, challenge/disagreement, gates/progression, correction/supersession/withdrawal, and revalidation.
3. Classify each candidate as objectively checkable, contextual human judgment, recorded-judgment check, deferred-to-representation, deferred-to-methodology, or out-of-catalog.
4. Resolve the STEP-04-routed open questions listed in Scope, especially `GC-OQ-01`, `GC-OQ-02`, `GC-OQ-03`, `GC-OQ-09`, `GC-OQ-11`, `EK-OQ-09`, and `EK-OQ-14`.
5. Define semantic violation-handling categories without choosing enforcement technology.
6. Add traceability tables to source IDs and to this work package's acceptance checks.
7. Add the required MW-ADAPT-001 Undecided Architecture Declaration.
8. Propose transferability observations if concrete evidence emerges.
9. Hold Tech Lead review, QA, and Product Owner sign-off before Moderator final acceptance, unless explicitly waived beforehand.

---

## Research Governance Route

As STEP-04 work proceeds, if the Development Team observes concrete evidence about how MOD-W's plan gate, build gate, Tech Lead review, QA, Product Owner sign-off, artifact acceptance, or MW-ADAPT-001 transfer or do not transfer to rule-catalog and boundary-specification work, propose an observation to the MOD-W transferability register:

1. Record the observation draft in `research/mod-w-transferability/observations.md` following the existing observation structure.
2. Include concrete evidence: references to artifacts, pattern descriptions, and effect on work.
3. Use the classification vocabulary from `research/mod-w-transferability/README.md`: `TRANSFERS_UNCHANGED`, `TRANSFERS_WITH_REINTERPRETATION`, `REQUIRES_LOCAL_ADAPTATION`, `DOMAIN_COUPLED`, or `NOT_YET_TESTED`.
4. Set disposition/status to proposed. The MOD-W Moderator decides whether to accept, modify, or reject the observation.

Observations are not blocking on STEP-04 completion unless the Moderator explicitly makes one blocking.

---

## Change Notes

| Date | Change | Reason |
| --- | --- | --- |
| 2026-10-02 | STEP-04 work package approved | MOD-W Moderator approved the Tech Lead's STEP-04 definition in preparation for Development Team implementation. See `mod-w/reviews/MODERATOR-REVIEW-STEP-04-SETUP.md`. |
| 2026-10-02 | Initial STEP-04 draft | Prepare rule/judgment boundary work package after STEP-03 completion and Moderator acceptance. |
