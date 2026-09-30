---
artifact:
  type: step
  id: STEP-02
  version: 0.1
  created: 2026-09-30
  updated: 2026-09-30
  status: Accepted
---

# STEP-02 - Define Evidence, Knowledge, and Provenance Model

---

## Goal

Define PROD-W's evidence and knowledge model for claims, evidence, counter-evidence, assumptions, hypotheses, inferences, decisions, challenges, dependencies, provenance, and revalidation triggers.

This step produces product specification artifacts only. It does not implement tooling, validators, schemas, workflow engines, state machines, or a serialized protocol format.

The output must extend the accepted STEP-01 protocol semantics without changing the authority model, self-approval invalidity rules, or gate authority rules defined in `prod-w/protocol-semantics.md`.

---

## Governance Context

**This artifact is authored and reviewed under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-02 acceptance for `prod-w-dev`.

The future PROD-W Product Moderator is a protocol role being defined by the product. It has no current authority over this STEP-02 work unless MOD-W governance explicitly grants it in a later accepted artifact.

STEP-02 follows the local adaptation authorized after STEP-01: Development Team deliverables must identify any decisions they had to make that were not already decided by accepted upstream architecture or protocol artifacts, and route them for Tech Lead review.

---

## Related Requirements

- FR-3 - Protocol must define evidence requirements.
- FR-6 - Protocol must track provenance.
- FR-7 - Material hypotheses require validation or visible unresolved-assumption handling.
- FR-2 - Protocol must define governance semantics for progression, where evidence and knowledge relationships affect valid progression.
- FR-5 - Protocol must surface unresolved disagreement, where challenges and counter-evidence create visible disagreement conditions.

---

## Related Architecture Decisions

| Decision | Relevance to STEP-02 |
| -------- | -------------------- |
| D1 - Protocol Semantics Are Normative | Evidence and knowledge concepts must be defined semantically before representation choices. |
| D2 - Protocol, Schema, and State Remain Separate | The model must not select schemas, state names, workflow engines, or storage formats. |
| D3 - Knowledge Classes Are First-Class Domain Concepts | STEP-02 is the primary operationalization of this decision. |
| D5 - Disagreement Is a Preserved Condition, Not Necessarily a State Name | Challenges, counter-evidence, and conflicting inferences must remain visible without hardening final state names. |
| D6 - Objectively Checkable Governance Is Separated from Human Judgment | Presence, provenance, and dependency conditions must be distinguished from sufficiency judgments. |
| D7 - Provenance and Dependencies Support Revalidation | STEP-02 must define the conceptual dependency and revalidation-trigger model. |
| D8 - External Evaluators Are Advisory Interfaces Unless Explicitly Granted Authority | Evaluator findings may be evidence, counter-evidence, challenge, or verification input, but not gate acceptance by default. |

---

## Assigned Dev Team Interface

- [x] Claude Code (default)
- [ ] Claude Design (visual / chart / interaction-heavy Step)

---

## Scope

- Define each knowledge class in protocol-operational terms: claim, material claim, evidence, counter-evidence, assumption, hypothesis, inference, decision, challenge, dependency, provenance, advisory finding, validation, invalidation, and revalidation trigger.
- Define the relationships among knowledge items: supports, contradicts, qualifies, depends on, derives from, challenges, validates, invalidates, supersedes, and requires revalidation.
- Define what makes a claim material, while preserving materiality as a contextual human judgment unless a later step defines objective criteria.
- Define evidence expectations in representation-neutral terms: source identification, producer, time, target claim or decision, evidence type/category, evidence basis, limitations, and provenance.
- Define counter-evidence as first-class evidence, not a note or exception.
- Define assumptions and hypotheses distinctly, including when an untested hypothesis must be handled as a visible unresolved assumption.
- Define inference as a separate item that cites evidence and/or assumptions without becoming evidence itself.
- Define decision records as authorized commitments that cite supporting claims, evidence, assumptions, challenges, and authority.
- Define provenance requirements for material claims, evidence items, inferences, decisions, challenges, and dependency changes.
- Define dependency concepts needed to detect when downstream items may require revalidation.
- Define initial revalidation-trigger semantics caused by material support changes, contradiction, invalidation, supersession, or dependency changes.
- Define which STEP-02 concepts are objectively checkable versus contextual human judgments at an initial level, without replacing STEP-04's full rule catalog.
- Identify open questions that belong to STEP-03, STEP-04, or STEP-05.

---

## Out of Scope

- Selecting YAML, JSON, JSON Schema, TypeScript/Zod, DSL, MCP, A2A, workflow engine, document metadata, centralized state, graph database, ledger, or any other representation.
- Defining final condition names, state names, lifecycle graphs, or transition mechanics.
- Implementing validators, schemas, CLI tooling, prompts, agent harnesses, or runtime integrations.
- Defining complete gate mechanics, challenge routing, disagreement resolution, waiver mechanics, or escalation paths; these belong primarily to STEP-03.
- Producing the full machine-checkable rule catalog; STEP-04 owns that catalog.
- Defining customer-evidence sufficiency thresholds for all possible product categories.
- Granting external evaluators consequential gate authority.
- Modifying `mod-w/product.md`, `mod-w/architecture.md`, or canonical templates under `mod-w/templates/`.
- Treating Product Skeptic, Product Advocate, Product Knowledge Ledger, DIVERGENT state, null hypothesis, document metadata model, or external evaluator contract as accepted requirements.

---

## Inputs

- `mod-w/product.md`
- `mod-w/architecture.md`
- `mod-w/domain-language.md`
- `mod-w/roadmap.md`
- `mod-w/step-01.md`
- `prod-w/protocol-semantics.md`
- `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md`
- `research/topics/protocol-schema-state-distinction.md`
- `research/topics/prod-w-protocol-first-rationale.md`
- `research/topics/document-metadata-and-human-machine-views.md`
- `research/topics/model-depth-tech-lead-self-review.md`
- `research/mod-w-transferability/README.md`
- `research/mod-w-transferability/observations.md`
- `research/mod-w-transferability/adaptations.md`

---

## Expected File Changes

- Add `prod-w/evidence-knowledge-model.md`.
- Update `mod-w/domain-language.md` only if new accepted terms are introduced or existing pending terms need routing for Moderator disposition.
- Add a proposed transferability observation under `research/mod-w-transferability/observations.md` if this step reveals concrete MOD-W transferability evidence.

Do not modify accepted Product Definition, Architecture, Roadmap, STEP-01 deliverables, or MOD-W templates unless a separate Moderator-authorized correction explicitly requires it.

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

- [x] `prod-w/evidence-knowledge-model.md` distinguishes claim, material claim, evidence, counter-evidence, assumption, hypothesis, inference, decision, challenge, dependency, provenance, and revalidation trigger. _(Implements D3, FR-3, FR-6, FR-7)_
- [x] The model treats counter-evidence and negative findings as first-class evidence artifacts. _(Implements AH-3, FR-3)_
- [x] Agent agreement is explicitly excluded as independent evidence unless source evidence is separately present and attributable. _(Implements PE-2)_
- [x] Material claims require traceable provenance sufficient to identify producer, time, evidence basis, challenge/acceptance history where applicable, and dependency links. _(Implements PE-1, FR-6)_
- [x] Evidence presence and provenance are separated from contextual sufficiency judgments. _(Implements D6, FR-3)_
- [x] Assumptions and hypotheses remain distinct; unvalidated material hypotheses cannot be treated as validated without required evidence and authorized acceptance. _(Implements AH-1, AH-2, FR-7)_
- [x] Inferences are represented as interpretations derived from evidence or assumptions, not as evidence or observed facts. _(Implements PE-3)_
- [x] Decisions cite supporting claims/evidence/assumptions/challenges and retain authority/provenance links without changing STEP-01 gate authority rules. _(Implements D4, D7, FR-6)_
- [x] Dependencies identify downstream items that may require revalidation when material support changes. _(Implements D7, WD-6)_
- [x] Revalidation triggers are defined conceptually without selecting state names, lifecycle graphs, workflow engines, or protocol serialization. _(Implements D2, D7)_
- [x] Challenges, counter-evidence, and conflicting inferences can create visible unresolved disagreement without forcing consensus or adopting a final `DIVERGENT` state. _(Implements D5, FR-5)_
- [x] External evaluator outputs remain advisory findings unless authority is explicitly granted by accepted PROD-W protocol. _(Implements D8)_
- [x] The artifact includes an "Undecided Architecture Declaration" section listing any decisions the Development Team had to make beyond accepted upstream architecture, or explicitly states that none were made. _(Implements MW-ADAPT-001)_
- [x] No implementation technology, schema language, storage model, protocol transport, or validator is selected prematurely. _(Implements D2, NG-1)_
- [x] Any transferability evidence encountered has been proposed under the research governance process. _(Implements RG-1 / AC-4 boundary)_

Checked 2026-09-30 per `prod-w/evidence-knowledge-model.md` Section 14.3, Tech Lead approval in `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02.md`, and MOD-W Moderator approval in `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`.

---

## Required Output Structure

`prod-w/evidence-knowledge-model.md` should include, at minimum:

1. Purpose and standing.
2. Governance context.
3. Relationship to `prod-w/protocol-semantics.md`.
4. Knowledge class definitions.
5. Relationship model.
6. Provenance requirements.
7. Evidence and counter-evidence expectations.
8. Assumption and hypothesis handling.
9. Inference and decision support rules.
10. Dependency and revalidation-trigger semantics.
11. Objectively checkable conditions versus contextual human judgments.
12. Undecided Architecture Declaration.
13. Open questions routed to later steps.
14. Traceability to requirements, architecture decisions, and STEP-02 acceptance checks.
15. Change notes.

The structure may be adjusted if needed, but all acceptance checks must remain traceable to specific sections.

---

## Plan

1. Read accepted product, architecture, domain-language, roadmap, STEP-01, and STEP-01 review artifacts.
2. Extract all accepted requirements that mention evidence, knowledge classes, provenance, assumptions, hypotheses, dependencies, disagreement, and revalidation.
3. Define representation-neutral knowledge classes and relationship semantics.
4. Define provenance and dependency requirements without selecting schema or state representation.
5. Separate objective presence/provenance/reference checks from contextual sufficiency judgments.
6. Add the required Undecided Architecture Declaration.
7. Add traceability tables to requirements, architecture decisions, and acceptance checks.
8. Record transferability observations if concrete evidence emerges.

### Research Governance Route

As STEP-02 work proceeds, if you observe concrete evidence about how MOD-W's Product Definition, Architecture, or Role concepts transfer or do not transfer to protocol and knowledge-model development, propose an observation to the MOD-W transferability register:

1. Record the observation draft in `research/mod-w-transferability/observations.md` following the existing observation structure.
2. Include concrete evidence: references to artifacts, pattern descriptions, and effect on work.
3. Use the classification vocabulary from `research/mod-w-transferability/README.md`: `TRANSFERS_UNCHANGED`, `TRANSFERS_WITH_REINTERPRETATION`, `REQUIRES_LOCAL_ADAPTATION`, `DOMAIN_COUPLED`, or `NOT_YET_TESTED`.
4. Set disposition/status to proposed. The MOD-W Moderator decides whether to accept, modify, or reject the observation.

Observations are not blocking on STEP-02 completion unless the Moderator explicitly makes one blocking.

---

## Change Notes

| Date       | Change             | Reason                                                      |
| ---------- | ------------------ | ----------------------------------------------------------- |
| 2026-09-30 | STEP-02 deliverable accepted | MOD-W Moderator approved the Development Team's STEP-02 work and approved the Tech Lead's STEP-02 approval. |
| 2026-09-30 | Accepted by Moderator | Moderator approved STEP-02 definition for Development Team implementation. |
| 2026-09-30 | Initial step draft | Prepare evidence and knowledge model step for Dev Team use. |
