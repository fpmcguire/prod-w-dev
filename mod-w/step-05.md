---
artifact:
  type: step
  id: STEP-05
  version: 0.1
  created: 2026-10-03
  updated: 2026-10-03
  status: Approved
---

# STEP-05 - Evaluate Representation Options

---

## Goal

Evaluate candidate technical representations for PROD-W against the accepted protocol semantics, evidence model, gate semantics, and rule/judgment boundary without treating any one representation as predetermined.

This step produces a product decision memo only. It may recommend a narrow initial representation experiment if the evidence supports one. It must not implement a schema, validator, CLI, workflow engine, storage layer, agent harness, lifecycle graph, prompt format, runtime integration, or publication package.

---

## Governance Context

**This artifact is authored and reviewed under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-05 acceptance for `prod-w-dev`.

The future PROD-W Product Moderator is a protocol role being defined by the product. It has no current authority over this STEP-05 work unless MOD-W governance explicitly grants it in a later accepted artifact.

STEP-05 must preserve accepted architecture decision D2: protocol, schema, and state remain separate. A representation option may support one or more of those layers, but the memo must not collapse structural validity, recorded state, and governance validity into one mechanism.

For STEP-05, the expected review sequence is:

| MOD-W point | Expected handling |
| --- | --- |
| 2a Plan approval | Development Team may proceed directly from this work package unless the Moderator requests a separate plan checkpoint. |
| 2b Development Team work product | Development Team drafts the STEP-05 product artifact. |
| 3a Tech Lead review | Expected before final Moderator acceptance. Must sample for hidden representation selection, protocol/schema/state collapse, and loss of STEP-04 rule/judgment boundaries. |
| 3b QA | Expected before final Moderator acceptance unless the Moderator explicitly waives it before final acceptance. QA should sample option coverage, traceability, comparison criteria, and carry-forward routing. |
| 3c Product Owner sign-off | Expected before final Moderator acceptance unless the Moderator explicitly waives it before final acceptance. |
| 4a Moderator acceptance | Final acceptance only after required reviews or explicit recorded waivers. |

---

## Related Requirements

- G-3 - PROD-W must support a machine-readable protocol that can validate objectively checkable rules while remaining human-reviewable and auditable.
- NG-1 - Do not select a representation before the protocol semantics justify it.
- NG-2 - Do not build implementation tooling prematurely.
- FR-3 - Protocol must define evidence requirements, including objectively checkable evidence conditions and contextual sufficiency judgments.
- FR-4 - PROD-W governance must make self-approval invalid or detectable as invalid.
- FR-6 - Protocol must track provenance sufficient to identify current status, challenge history, and acceptance history.
- FR-7 - Hypothesis validation and visible assumption handling must be preserved.
- D2 - Protocol, schema, and state remain separate.
- D6 - Objectively checkable governance is separated from human judgment.

---

## Related Architecture Decisions

| Decision | Relevance to STEP-05 |
| --- | --- |
| D1 - Protocol Semantics Are Normative | Representation options are projections of semantics, not replacements for them. |
| D2 - Protocol, Schema, and State Remain Separate | Core evaluation boundary for every option and hybrid. |
| D3 - Knowledge Classes Are First-Class Domain Concepts | Options must preserve claim, evidence, assumption, hypothesis, inference, decision, challenge, dependency, provenance, and revalidation distinctions. |
| D4 - Authority Is Modeled Separately from Role Labels | Options must support actor identity, participation capacity, authority grants, scope, and independence. |
| D5 - Disagreement Is a Preserved Condition, Not Necessarily a State Name | Options must not require disagreement to become a fixed serialized state unless justified by evidence and routed. |
| D6 - Objectively Checkable Governance Is Separated from Human Judgment | Options must support objective checks without automating contextual sufficiency. |
| D7 - Provenance and Dependencies Support Revalidation | Options must be evaluated for provenance, dependency, exposure, and revalidation support. |
| D8 - External Evaluators Are Advisory Interfaces Unless Explicitly Granted Authority | Options must preserve the distinction between evaluator findings, verification, and acceptance. |
| D9 - Working Product Artifacts Live Under `prod-w/` in `prod-w-dev` | The accepted STEP-05 product artifact must live under `prod-w/`. |
| D10 - Authority Grants Are Conferred by Human-Held Conferral Scope from a Single Establishing Act | Options must support one establishing act, authority-chain reconstruction, grant effectiveness, revocation/narrowing, and self-conferral detection. |

---

## Assigned Dev Team Interface

- [x] Claude Code (default)
- [ ] Claude Design (visual / chart / interaction-heavy Step)

---

## Scope

- Produce a representation evaluation memo under `prod-w/`.
- Compare at least these representation families:
  - Markdown body conventions and tables.
  - YAML frontmatter.
  - JSON documents.
  - JSON Schema or equivalent structural schemas.
  - Markdown plus sidecar files.
  - Centralized protocol-state or registry file.
  - Graph or ledger-style relationship records.
  - Hybrid representations.
  - Agent instructions or skill/prompt conventions as representation-adjacent mechanisms.
- Evaluate each option against accepted semantics, especially:
  - protocol/schema/state separation;
  - actor identity, participation capacity, authority grants, conferral scope, and independence;
  - provenance, producing configuration, source lineage, and evidence basis;
  - knowledge-class distinctions;
  - challenge, disagreement, gate basis, standing record, exception, exposure, and revalidation semantics;
  - objectively checkable rules and recorded-judgment checks from `prod-w/rule-judgment-boundary.md`;
  - human readability, auditability, diffability, and review ergonomics;
  - representation portability into a later separate `prod-w` repository.
- Define comparison criteria and use them consistently across options.
- Identify which accepted semantic requirements cannot be carried by a given option alone.
- Identify which options are suitable only as schema support, state support, methodology support, or advisory tooling support.
- Address STEP-04 carry-forward item QA5-03: define the record element that "evidence-only form" refers to, or explain why the element remains unresolved and route it explicitly.
- Address STEP-04 carry-forward F-5: representation implications for authenticating actor kind, while preserving that no protocol representation alone can guarantee that a human acted.
- Address representation-owned routed items from STEP-04, including derived conditions, item identity across change, accepted-set closure computation, serialized state vocabulary, lifecycle graphs, machine views, formal-check result form, and record order.
- Recommend one of:
  - no representation experiment yet;
  - a narrow experiment with one representation family;
  - a narrow hybrid experiment;
  - a set of prerequisites that must be settled before any experiment.
- If an experiment is recommended, define its purpose, scope, inputs, success/failure signals, exclusions, and review gate. The experiment must be a later step or later authorized task, not implementation inside STEP-05.
- Identify open questions routed to STEP-06, STEP-07, STEP-08, publication work, or later architecture.

---

## Out of Scope

- Implementing schemas, validators, CLIs, tests, workflow engines, state machines, databases, graph stores, ledgers, MCP servers, A2A integrations, APIs, prompt formats, agent harnesses, or runtime integrations.
- Selecting a final representation for PROD-W publication.
- Treating the recommended experiment, if any, as accepted implementation architecture.
- Rewriting accepted STEP-01, STEP-02, STEP-03, or STEP-04 product artifacts.
- Changing architecture decisions D1 to D10.
- Creating methodology templates, role charters, evidence worksheets, gate templates, examples, or practitioner guidance; STEP-06 owns those.
- Running the proof-of-concept product opportunity trial; STEP-07 owns that.
- Deciding whether Product Skeptic, Product Advocate, Product Knowledge Ledger, null-hypothesis framing, external evaluator contracts, or agent harness conformance tooling are core product scope.
- Granting external evaluators, schemas, validators, or agent tools consequential gate authority.
- Using confidence scores, numeric sufficiency weights, or artificial precision for evidence strength or judgment quality.

---

## Inputs

Accepted inputs:

- `mod-w/product.md`
- `mod-w/architecture.md`
- `mod-w/domain-language.md`
- `mod-w/roadmap.md`
- `mod-w/step-04.md`
- `mod-w/reviews/MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md`
- `mod-w/reviews/MODERATOR-REVIEW-STEP-04-POST-ACCEPTANCE-TECH-LEAD.md`
- `prod-w/protocol-semantics.md`
- `prod-w/evidence-knowledge-model.md`
- `prod-w/gate-challenge-revalidation-semantics.md`
- `prod-w/rule-judgment-boundary.md`

Useful supporting inputs if needed:

- `research/topics/protocol-schema-state-distinction.md`
- `research/topics/agent-harness-conformance.md`
- `research/topics/agent-skills-and-protocol-relationship.md`
- `research/topics/product-definition-skill.md`
- `research/topics/prod-w-compliance-skills-pattern.md`
- `research/topics/document-metadata-and-human-machine-views.md`
- `research/mod-w-transferability/observations.md`
- `research/mod-w-transferability/adaptations.md`

---

## Expected File Changes

Add:

- `prod-w/representation-options.md`

Optional, only if concrete evidence emerges:

- Append proposed transferability evidence to `research/mod-w-transferability/observations.md` under the research governance process.

Do not modify accepted STEP-01, STEP-02, STEP-03, or STEP-04 product artifacts unless the MOD-W Moderator separately authorizes a correction.

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

`prod-w/representation-options.md` must include, at minimum:

1. Purpose and standing.
2. Governance context.
3. Relationship to accepted architecture D1 to D10.
4. Representation-neutral vocabulary: protocol representation, schema representation, state representation, record element, adapter, formal-check result, machine view, and experiment.
5. Evaluation criteria, including protocol/schema/state separation, semantic coverage, auditability, human readability, diffability, provenance support, independence support, revalidation support, portability, and premature-selection risk.
6. Option comparison for the representation families listed in Scope.
7. A protocol/schema/state fit table for each option.
8. A rule/judgment boundary fit table showing how candidate rule catalog entries, recorded-judgment checks, and contextual judgments would be supported or not supported.
9. Authority and identity analysis, including D10 support and actor-kind authentication limits.
10. Evidence and provenance analysis, including producing configuration, source lineage, evidence-only form, and record order.
11. Challenge, disagreement, gate, exception, exposure, and revalidation analysis.
12. Handling of derived conditions, item identity across change, accepted-set closure, machine views, lifecycle graph questions, serialized state vocabulary, and formal-check result form.
13. Representation options explicitly rejected for now, with rationale.
14. Recommended next experiment, if evidence supports one, or an explanation that no experiment should be run yet.
15. Open questions and routing.
16. Traceability to STEP-01, STEP-02, STEP-03, STEP-04, and architecture decisions.
17. Acceptance-check traceability.
18. Change notes.

The Development Team may adjust section order if useful, but every acceptance check must remain traceable to a specific section.

---

## Acceptance Checks

- [ ] `prod-w/representation-options.md` is added and states that STEP-05 is evaluation only.
- [ ] The memo compares Markdown conventions, YAML frontmatter, JSON, structural schemas, sidecars, centralized state or registry files, graph or ledger-style relationship records, hybrids, and agent instruction or skill/prompt conventions.
- [ ] The memo preserves D2 by evaluating protocol, schema, and state support separately for every option.
- [ ] The memo states that schema validity does not equal governance validity.
- [ ] The memo states that recorded state does not equal protocol authority.
- [ ] The memo states that a representation adapter is replaceable and subordinate to accepted protocol semantics.
- [ ] The memo evaluates each option against actor identity, participation capacity, authority grants, conferral scope, independence, and D10 authority-chain reconstruction.
- [ ] The memo evaluates each option against provenance, producing configuration, source lineage, evidence basis, and revalidation support.
- [ ] The memo evaluates each option against challenge, disagreement, gate basis, standing record, exception, exposure, and revalidation semantics.
- [ ] The memo evaluates each option against STEP-04 candidate rules, recorded-judgment checks, contextual judgments, and violation-handling categories.
- [ ] The memo defines or explicitly routes the record element for STEP-04 QA5-03's "evidence-only form" issue.
- [ ] The memo addresses actor-kind authentication for STEP-04 F-5 without claiming that protocol representation alone proves a human acted.
- [ ] The memo addresses derived conditions, item identity across change, accepted-set closure computation, formal-check result form, record order, machine views, lifecycle graph questions, and serialized state vocabulary.
- [ ] The memo distinguishes what a representation can check from what an authorized human must judge.
- [ ] The memo identifies which semantics each option cannot carry alone.
- [ ] The memo identifies which options would create hidden architecture decisions if selected now.
- [ ] The memo recommends no experiment, one narrow experiment, a narrow hybrid experiment, or prerequisites before experimentation, with rationale.
- [ ] Any recommended experiment includes purpose, scope, inputs, success/failure signals, exclusions, and required review gate.
- [ ] Any recommended experiment is not implemented in STEP-05 and does not become accepted final representation by recommendation alone.
- [ ] The memo routes methodology guidance to STEP-06 and pilot validation questions to STEP-07 without duplicating ownership.
- [ ] The memo routes research synthesis or hypothesis disposition to STEP-08 where applicable.
- [ ] The memo does not implement or select a final schema language, storage model, workflow engine, validator implementation, lifecycle graph, serialized state vocabulary, protocol transport, CLI, prompt format, agent harness, runtime integration, database, API, or publication package.
- [ ] The memo does not introduce confidence scores, numeric sufficiency weights, or artificial precision for evidence strength or judgment quality.
- [ ] Any concrete transferability evidence encountered is proposed under the research governance process.
- [ ] STEP-05 final acceptance is not recorded until Phase 3a Tech Lead review, Phase 3b QA, and Phase 3c Product Owner sign-off have occurred, or the MOD-W Moderator has explicitly waived any missing review before final acceptance.

---

## Tech Lead Recommendations to the Development Team

These recommendations are not themselves accepted product semantics. They are intended to keep STEP-05 from becoming accidental implementation work.

1. Start by building a criteria matrix, not by arguing for a favorite format.
2. Keep the option analysis layered: protocol semantics, structural schema, state record, human document, and machine view.
3. Treat "hybrid" as a family of designs with tradeoffs, not as an automatic compromise.
4. Be explicit when an option needs a second mechanism to carry authority, provenance, identity, or dependency semantics.
5. Separate record elements from serialized field names. STEP-05 may define that a semantic record element is needed without naming its final key, table column, graph edge, or state value.
6. Use small worked examples only to test coverage. Do not let examples become methodology templates or final syntax.
7. If recommending an experiment, keep it small enough to be rejected without reworking accepted semantics.
8. Prefer routing uncertainty visibly over selecting a representation to make the memo feel complete.

---

## Plan

1. Read the accepted inputs and extract the representation-relevant requirements, decisions, deferred items, and carry-forward questions.
2. Define comparison criteria that preserve D2 and the STEP-04 rule/judgment boundary.
3. Compare the required representation families against the criteria.
4. Test each option against authority, evidence, challenge, gate, disagreement, dependency, exposure, and revalidation semantics.
5. Resolve or route QA5-03, F-5, and the representation-owned STEP-04 routed items.
6. Identify options rejected for now and the reasons.
7. Decide whether evidence supports a narrow representation experiment.
8. Add traceability tables and acceptance-check coverage.
9. Propose transferability observations if concrete evidence emerges.
10. Hold Tech Lead review, QA, and Product Owner sign-off before Moderator final acceptance, unless explicitly waived beforehand.

---

## Research Governance Route

As STEP-05 work proceeds, if the Development Team observes concrete evidence about how MOD-W's planning, implementation, review, QA, Product Owner sign-off, or acceptance mechanisms transfer or do not transfer to representation-evaluation work, propose an observation to the MOD-W transferability register:

1. Record the observation draft in `research/mod-w-transferability/observations.md` following the existing observation structure.
2. Include concrete evidence: references to artifacts, pattern descriptions, and effect on work.
3. Use the classification vocabulary from `research/mod-w-transferability/README.md`: `TRANSFERS_UNCHANGED`, `TRANSFERS_WITH_REINTERPRETATION`, `REQUIRES_LOCAL_ADAPTATION`, `DOMAIN_COUPLED`, or `NOT_YET_TESTED`.
4. Set disposition/status to proposed. The MOD-W Moderator decides whether to accept, modify, or reject the observation.

Observations are not blocking on STEP-05 completion unless the Moderator explicitly makes one blocking.

---

## Change Notes

| Date | Change | Reason |
| --- | --- | --- |
| 2026-10-03 | STEP-05 work package approved | MOD-W Moderator approved the Tech Lead's STEP-05 package for Development Team implementation. See `mod-w/reviews/MODERATOR-REVIEW-STEP-05-SETUP.md`. |
| 2026-10-03 | Initial STEP-05 draft | Prepare representation-options work package after STEP-04 completion and post-acceptance carry-forward routing. |

---

MOD-W v5.0.1
