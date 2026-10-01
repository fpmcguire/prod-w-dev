---
artifact:
  type: step
  id: STEP-03
  version: 0.1
  created: 2026-10-01
  updated: 2026-10-01
  status: Draft
---

# STEP-03 - Define Gate, Challenge, Disagreement, and Revalidation Semantics

---

## Goal

Define PROD-W's gate, challenge, unresolved disagreement, escalation, conditional progression, correction/supersession, withdrawal, and revalidation semantics.

This step produces product specification artifacts only. It does not implement tooling, validators, schemas, workflow engines, state machines, or a serialized protocol format.

The output must extend the accepted STEP-01 and STEP-02 product artifacts without editing them unless the MOD-W Moderator explicitly authorizes a correction or accepted STEP-03 artifact change.

---

## Governance Context

**This artifact is authored and reviewed under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-03 acceptance for `prod-w-dev`.

The future PROD-W Product Moderator is a protocol role being defined by the product. It has no current authority over this STEP-03 work unless MOD-W governance explicitly grants it in a later accepted artifact.

STEP-03 must apply active local adaptation **MW-ADAPT-001**. The Development Team deliverable must include an Undecided Architecture Declaration listing choices not already decided by accepted upstream artifacts. After that declaration, Tech Lead or QA should sample for unlisted choices in authority, independence, evidence standing, and revalidation before acceptance.

STEP-02's Phase 3b and 3c records were ratified after initial acceptance as a visible sequence deviation. For STEP-03, Phase 3a Tech Lead review, Phase 3b QA, and Phase 3c Product Owner sign-off must be held before final acceptance, unless the MOD-W Moderator explicitly records a waiver before final acceptance.

---

## Related Requirements

- FR-2 - Protocol must define governance semantics for progression.
- FR-3 - Protocol must define evidence requirements.
- FR-5 - Protocol must surface unresolved disagreement.
- FR-7 - Material hypotheses require validation or visible unresolved-assumption handling.
- FR-4 - Self-approval invalidity remains a constraint on gate acceptance, correction designation, and revalidation closure.
- FR-6 - Provenance tracking must support gate decisions, challenge history, correction/supersession history, withdrawal history, and revalidation outcomes.
- HA-3 - Escalation paths are explicit.
- WD-2 - Unresolved disagreement may remain visible.
- WD-6 - Dependent decisions require revalidation when material support changes.
- GR-7 - Gate exceptions and waivers remain visible as exceptions.

---

## Related Architecture Decisions

| Decision | Relevance to STEP-03 |
| --- | --- |
| D1 - Protocol Semantics Are Normative | STEP-03 defines protocol semantics, not tooling or representation. |
| D2 - Protocol, Schema, and State Remain Separate | STEP-03 must not select schemas, lifecycle graphs, storage models, state machines, or state names as implementation choices. |
| D3 - Knowledge Classes Are First-Class Domain Concepts | Gate and challenge semantics must preserve claim, evidence, counter-evidence, assumption, hypothesis, inference, decision, challenge, dependency, provenance, validation, invalidation, withdrawal, supersession, correction, exposure, and revalidation distinctions. |
| D4 - Authority Is Modeled Separately from Role Labels | Correction designation, gate acceptance, challenge closure, conditional progression, and revalidation outcomes must be grounded in scoped authority grants and actor identity, not role names alone. |
| D5 - Disagreement Is a Preserved Condition, Not Necessarily a State Name | STEP-03 owns whether disagreement is represented as a named condition, relationship, artifact property, or record pattern, without forcing false consensus. |
| D6 - Objectively Checkable Governance Is Separated from Human Judgment | STEP-03 must separate objective presence/provenance/authority checks from human sufficiency judgments. |
| D7 - Provenance and Dependencies Support Revalidation | STEP-03 must define what happens when dependencies are exposed, triggered, reaffirmed, revised, retired, or conditionally relied on. |
| D8 - External Evaluators Are Advisory Interfaces Unless Explicitly Granted Authority | Evaluator challenges, findings, and verification may inform gate decisions but must not become consequential gate acceptance by default. |
| D9 - Working Product Artifacts Live Under `prod-w/` in `prod-w-dev` | The accepted STEP-03 product artifact should live under `prod-w/`. |

---

## Assigned Dev Team Interface

- [x] Claude Code (default)
- [ ] Claude Design (visual / chart / interaction-heavy Step)

---

## Scope

- Define gate semantics in representation-neutral terms: gate, gate basis, required evidence, required challenge criteria, formal checks, contextual sufficiency judgment, acceptance, refusal, deferral, conditional progression, waiver/exception, and escalation.
- Define how gate acceptance relates to consequential decisions, validation of hypotheses, and decision records from STEP-01 and STEP-02.
- Resolve **EK-OQ-05 as first-priority work**: define what counts as "the accepted item" for independence when a decision or gate cites items produced by the acceptor or by other actors.
- Resolve **EK-OQ-17**: who may designate a post-acceptance change as a correction rather than supersession; whether the original acceptor must be notified or consulted; whether producer correction designation can retain acceptance; and how producer withdrawal of its own item, including counter-evidence against its own claim, works.
- Resolve **EK-OQ-04 / QA D-08** after widening it to cover both challenges and bare contradicting claims/inferences: state whether each produces exposure, a revalidation requirement, or no dependent effect, and why.
- Resolve **EK-OQ-06** and D-05b: separate producer-owned withdrawal/supersession from authority over another actor's item for reliance purposes.
- Define challenge lifecycle semantics: raising a challenge, target scope, challenge basis, response, closure, escalation, unresolved status, and visibility.
- Define disagreement semantics: when disagreement exists, what remains visible, how progression may occur under disagreement, and who may decide whether residual disagreement is acceptable for a gate.
- Define conditional progression semantics and their relationship to assumptions, unvalidated hypotheses, gate waivers, and exceptions.
- Define revalidation semantics beyond STEP-02's initial trigger model: open requirement, exposure, reliance while open, authorized reaffirmation, revision, retirement, escalation, and closure.
- Address who may reaffirm, revise, or retire dependent non-decision items when revalidation is open, including EK-OQ-16.
- Address who may accept validation of a material hypothesis not tied to a consequential gate, including EK-OQ-02.
- Address disputed materiality designations and dependency redesignations, including EK-OQ-07.
- Address whether elapsed time or evidence age can create exposure, a revalidation request, a revalidation requirement, or no direct effect, including EK-OQ-10.
- Address actor identity and delegation only to the extent needed for gate authority, independence, and challenge/revalidation routing, including EK-OQ-03 and PS-OQ-06.
- Address whether verification carries a normative independence requirement or whether independent acceptance is sufficient, including PS-OQ-02, without taking over STEP-04's full rule catalog.
- Define the initial boundary between objectively checkable STEP-03 conditions and contextual human judgments, without replacing STEP-04.
- Include an Undecided Architecture Declaration as required by MW-ADAPT-001.
- Identify open questions that belong to STEP-04, STEP-05, STEP-06, pilot/proof-of-concept, or later publication work.

---

## Out of Scope

- Selecting YAML, JSON, JSON Schema, TypeScript/Zod, DSL, MCP, A2A, workflow engine, document metadata, centralized state, graph database, ledger, or any other representation.
- Implementing validators, schemas, CLI tooling, prompts, agent harnesses, or runtime integrations.
- Defining final serialized state names or lifecycle-transition mechanics unless stated purely as semantic options; STEP-05 owns representation.
- Producing the full machine-checkable rule catalog; STEP-04 owns that catalog.
- Producing methodology templates, role charters, worked examples, or detailed evidence collection guidance; STEP-06 owns methodology guidance.
- Defining complete evidence-category thresholds for all product categories; STEP-03 may define gate-level semantic slots and route detailed guidance to STEP-06.
- Granting external evaluators consequential gate authority by default.
- Modifying accepted STEP-01 or STEP-02 product artifacts without a separate Moderator-authorized correction or accepted STEP-03 artifact change.
- Modifying accepted Product Definition, Architecture, Roadmap, or canonical MOD-W templates unless a separate Moderator-authorized governance correction explicitly requires it.
- Treating Product Skeptic, Product Advocate, Product Knowledge Ledger, DIVERGENT state, null hypothesis, document metadata model, or external evaluator contract as accepted requirements.

---

## Inputs

- `mod-w/product.md`
- `mod-w/architecture.md`
- `mod-w/domain-language.md`
- `mod-w/roadmap.md`
- `mod-w/step-02.md`
- `mod-w/reviews/STEP-03-CARRY-FORWARD.md`
- `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`
- `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02-FOLLOWUP.md`
- `prod-w/protocol-semantics.md`
- `prod-w/evidence-knowledge-model.md`
- `research/mod-w-transferability/adaptations.md`
- `research/mod-w-transferability/observations.md`

Useful additional inputs:

- `mod-w/reviews/qa.md`
- `mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-02.md`
- `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02.md`
- `mod-w/step-01.md`
- `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md`

---

## Expected File Changes

- Add `prod-w/gate-challenge-revalidation-semantics.md`.
- Update `mod-w/domain-language.md` only if STEP-03 introduces accepted terms or revises STEP-02 load-bearing terms, and only in a way that preserves source-step provenance.
- Add a proposed transferability observation under `research/mod-w-transferability/observations.md` if STEP-03 reveals concrete MOD-W transferability evidence, especially around plan gates, document-native QA, review sequencing, or MW-ADAPT-001 effectiveness.

Do not modify accepted `prod-w/protocol-semantics.md` or `prod-w/evidence-knowledge-model.md` unless the MOD-W Moderator separately authorizes a correction or STEP-03 acceptance explicitly calls for a new accepted artifact revision.

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

- [ ] `prod-w/gate-challenge-revalidation-semantics.md` defines gate, gate basis, required evidence, required challenge criteria, acceptance, refusal, deferral, conditional progression, waiver/exception, escalation, unresolved disagreement, exposure, revalidation requirement, revalidation closure, correction, supersession, withdrawal, reaffirmation, revision, and retirement in protocol-operational terms.
- [ ] EK-OQ-05 is resolved first in the artifact: "the accepted item" for consequential gate acceptance and consequential decisions is defined clearly enough to apply STEP-01 independence rules to the decision record and its material basis.
- [ ] EK-OQ-17 is resolved: correction designation authority, original-acceptor notice/consultation, acceptance inheritance, producer correction designation, and producer withdrawal of its own item/counter-evidence are defined without permitting self-approval through item identity.
- [ ] D-05b is resolved by separating producer-owned withdrawal/supersession from authority over another actor's item for reliance purposes, including visibility rules for withdrawn own counter-evidence.
- [ ] EK-OQ-04 / D-08 is resolved for challenges, source-identified counter-evidence, bare contradicting claims, and bare contradicting inferences: each is classified as producing exposure, a revalidation requirement, or no dependent effect, with rationale and any required thresholds.
- [ ] The artifact states whether reliance may continue while exposure exists or while a revalidation requirement is open, and who may authorize any such reliance.
- [ ] The artifact defines how unanswered challenges cited in a decision basis must be recorded, answered, escalated, waived, or accepted as residual risk at gates.
- [ ] Challenge lifecycle semantics include target scope, basis, response, closure, escalation, and unresolved visibility without forcing consensus.
- [ ] Disagreement semantics preserve unresolved disagreement visibly and define how, if at all, conditional progression can occur under it.
- [ ] Conditional progression is distinguished from validation, ordinary gate acceptance, waiver/exception, and reliance under assumption.
- [ ] Revalidation closure authority is defined for consequential decisions and for non-decision dependents, including EK-OQ-16.
- [ ] Validation authority for material hypotheses not tied to a consequential gate is defined or explicitly routed with a constrained interim rule, including EK-OQ-02.
- [ ] Disputed materiality and dependency redesignation handling is defined, including EK-OQ-07.
- [ ] Time/evidence-age effects are defined as exposure, request, requirement, or no direct effect, including EK-OQ-10.
- [ ] Actor identity, team/organization/agent-fleet identity, and delegation are addressed to the extent needed for STEP-03 authority and independence semantics, without over-taking later representation work.
- [ ] Verification independence is addressed at the semantic level or deliberately routed to STEP-04 with a safe interim constraint.
- [ ] External evaluator outputs remain advisory findings unless authority is explicitly granted by accepted PROD-W protocol.
- [ ] Objectively checkable conditions are separated from contextual human judgments at an initial level, without replacing STEP-04's full rule catalog.
- [ ] The artifact includes an Undecided Architecture Declaration that applies MW-ADAPT-001 and declares choices touching authority, actor identity, independence, evidence standing, disagreement, gates, correction/supersession, withdrawal, and revalidation.
- [ ] The Development Team declaration is followed by Tech Lead or QA sampling for unlisted choices in authority, independence, evidence standing, and revalidation before acceptance.
- [ ] The artifact identifies which open questions remain routed to STEP-04, STEP-05, STEP-06, pilot/proof-of-concept, or later work, without duplicating their ownership.
- [ ] No implementation technology, schema language, storage model, protocol transport, validator, workflow engine, lifecycle graph, or final serialized state vocabulary is selected prematurely.
- [ ] Any transferability evidence encountered has been proposed under the research governance process.
- [ ] STEP-03 final acceptance is not recorded until Phase 3a Tech Lead review, Phase 3b QA, and Phase 3c Product Owner sign-off have occurred, or the MOD-W Moderator has explicitly waived any missing review before final acceptance.

---

## Required Output Structure

`prod-w/gate-challenge-revalidation-semantics.md` should include, at minimum:

1. Purpose and standing.
2. Governance context.
3. Relationship to `prod-w/protocol-semantics.md` and `prod-w/evidence-knowledge-model.md`.
4. Independence basis and "accepted item" semantics.
5. Gate model and gate outcomes.
6. Challenge model and lifecycle.
7. Contradiction, counter-evidence, bare contradicting claims/inferences, exposure, and requirements.
8. Disagreement handling and escalation.
9. Conditional progression, waivers, and exceptions.
10. Correction, supersession, withdrawal, and invalidation authority.
11. Revalidation requirement and closure semantics.
12. Hypothesis validation and assumption-rooted support handling.
13. Time/evidence-age effects.
14. Objectively checkable conditions versus contextual human judgments.
15. Undecided Architecture Declaration.
16. Open questions routed to later steps.
17. Traceability to requirements, architecture decisions, carry-forward items, and acceptance checks.
18. Change notes.

The structure may be adjusted if needed, but all acceptance checks must remain traceable to specific sections.

---

## Tech Lead Recommendations to the Development Team

The following recommendations are not themselves accepted product semantics. They are intended to keep the Development Team from accidentally re-opening settled STEP-02 dispositions or missing the main self-approval risks.

1. Treat EK-OQ-05 as the entry point. Define the independence basis before defining gate outcomes; otherwise every gate rule risks inheriting an ambiguous "accepted item."
2. For consequential gate acceptance and consequential decisions, strongly consider defining the accepted item as the decision record plus every material item necessary to its basis, including cited claims, evidence, assumptions, hypotheses, inferences, dependency/materiality designations, and challenge responses necessary to the sufficiency determination.
3. Treat a producer's correction designation on an accepted item as a proposal requiring independent confirmation when the item has been accepted or is cited by a consequential decision. If confirmation is absent, treat the change conservatively as supersession for reliance purposes.
4. Permit producer withdrawal of the producer's own item only as a visible historical event. Withdrawal of own counter-evidence must not erase the prior contradiction, decision-history relevance, exposure, or auditability.
5. Preserve the STEP-02 disposition that D-05a, D-05c, and D-05d are confirmed as operationalization. Do not re-litigate them unless STEP-03 semantics create a direct conflict.
6. For D-08, avoid making every cheap challenge an automatic requirement unless a threshold is defined. The likely useful split is: challenge creates contestation/exposure; source-identified counter-evidence creates a requirement on material dependents; bare contradicting claims/inferences need explicit thresholding before they receive trigger status.
7. Treat the all-dependents revalidation scope as a burden risk to manage and later test, not as a reason to weaken WD-6 prematurely.

---

## Plan

1. Development Team reads all listed inputs and extracts all STEP-03-routed open questions, carry-forward constraints, and accepted STEP-02 dispositions.
2. Resolve independence basis first, especially EK-OQ-05 and its relation to PR-16 to PR-21.
3. Resolve correction/supersession/withdrawal authority next, especially EK-OQ-17, EK-OQ-06, and D-05b.
4. Define gate semantics and gate outcomes using the resolved authority and independence basis.
5. Define challenge, disagreement, contradiction, exposure, and revalidation semantics, explicitly resolving D-08.
6. Define conditional progression, waivers/exceptions, escalation, and revalidation closure.
7. Separate objective checks from contextual human judgments.
8. Add the required MW-ADAPT-001 Undecided Architecture Declaration.
9. Add traceability tables to requirements, architecture decisions, carry-forward items, and acceptance checks.
10. Record transferability observations if concrete evidence emerges.
11. Hold Phase 3a Tech Lead review, Phase 3b QA, and Phase 3c Product Owner sign-off before Moderator final acceptance, unless explicitly waived beforehand.

---

## Research Governance Route

As STEP-03 work proceeds, if you observe concrete evidence about how MOD-W's plan gate, build gate, Tech Lead review, QA, Product Owner sign-off, artifact acceptance, or MW-ADAPT-001 transfer or do not transfer to protocol and knowledge-model development, propose an observation to the MOD-W transferability register:

1. Record the observation draft in `research/mod-w-transferability/observations.md` following the existing observation structure.
2. Include concrete evidence: references to artifacts, pattern descriptions, and effect on work.
3. Use the classification vocabulary from `research/mod-w-transferability/README.md`: `TRANSFERS_UNCHANGED`, `TRANSFERS_WITH_REINTERPRETATION`, `REQUIRES_LOCAL_ADAPTATION`, `DOMAIN_COUPLED`, or `NOT_YET_TESTED`.
4. Set disposition/status to proposed. The MOD-W Moderator decides whether to accept, modify, or reject the observation.

Observations are not blocking on STEP-03 completion unless the Moderator explicitly makes one blocking.

---

## Change Notes

| Date | Change | Reason |
| --- | --- | --- |
| 2026-10-01 | Initial STEP-03 draft | Prepare gate, challenge, disagreement, and revalidation semantics work package after STEP-02 completion and carry-forward disposition. |
