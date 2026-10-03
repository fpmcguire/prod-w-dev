---
artifact:
  type: step
  id: STEP-06
  version: 0.1
  created: 2026-10-04
  updated: 2026-10-04
  status: Approved
---

# STEP-06 - Produce Methodology Guidance and Templates

---

## Goal

Produce human-usable PROD-W methodology guidance aligned with the accepted protocol semantics, evidence model, gate semantics, rule/judgment boundary, and representation-options memo.

This step turns the accepted semantics into practitioner guidance, role charters, evidence guidance, gate templates, escalation practice, and worked examples. It does not change protocol semantics, select a final representation, implement tooling, run a pilot, or prepare the publication package.

---

## Governance Context

**This artifact is authored and reviewed under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-06 acceptance for `prod-w-dev`.

The future PROD-W Product Moderator is a protocol role being defined by the product. It has no authority over this STEP-06 work unless MOD-W governance explicitly grants it.

For STEP-06, the expected review sequence is:

| MOD-W point | Expected handling |
| --- | --- |
| 2a Plan approval | Development Team may proceed from this work package unless the Moderator requests a checkpoint. |
| 2b Development Team work product | Development Team drafts methodology artifacts under `prod-w/`. |
| 3a Tech Lead review | Expected before final Moderator acceptance. Samples alignment with accepted semantics and checks for accidental new rules. |
| 3b QA | Expected before final Moderator acceptance unless the Moderator explicitly waives it before final acceptance. Samples template completeness, traceability, and usability for STEP-07. |
| 3c Product Owner sign-off | Expected before final Moderator acceptance unless waived. Confirms the guidance is usable by intended product teams. |
| 4a Moderator acceptance | Final acceptance only after required reviews or recorded waivers. |

---

## Related Requirements

- G-4 - PROD-W must include usable human methodology.
- AC-2 - Practical methodology guidance must include role charters, decision workflow examples, evidence procedures, gate criteria with worked examples, escalation procedures, and templates for key artifacts.
- FR-1 - Roles and authority must remain explicit.
- FR-3 - Evidence requirements must remain visible and traceable.
- FR-4 - Self-approval invalidity must remain operationally clear.
- FR-5 - Unresolved disagreement must remain visible.
- FR-6 - Provenance must support challenge history, acceptance history, and current standing.
- FR-7 - Material hypotheses must be validated or handled as visible unresolved assumptions.
- NG-1 / NG-2 - Do not select representation or build tooling prematurely.

---

## Scope

- Produce a methodology guide under `prod-w/`.
- Produce role charters for the practical role positions a PROD-W project needs.
- Produce templates for project establishment, evidence records, claims, challenges, gates, exceptions, conditional progression, revalidation, and formal-check results.
- Define practice guidance for the `DM-*` items routed to STEP-06:
  - DM-01 evidence categories and threshold practice.
  - DM-02 role positions and conferral/gate/validation scopes.
  - DM-03 project establishment and root-grant practice.
  - DM-04 independence practice for teams of one or two.
  - DM-05 producing-configuration and source-comparability conventions.
  - DM-06 deciding whether criteria are decidable.
  - DM-07 recovery by new project and carry-over practice.
  - DM-08 formal-check result and finding-content practice.
  - DM-09 practice for consequential commitments that are not acceptances.
- Address STEP-05 routed practice questions RQ-02, RQ-03, RQ-04, RQ-05, RQ-07, RQ-08, RQ-10, RQ-14, RQ-15, and RQ-17 at the practice level without creating new protocol rules.
- Provide worked examples suitable as inputs to STEP-07.

---

## Out of Scope

- Changing accepted STEP-01 to STEP-05 semantics.
- Selecting a final schema, state vocabulary, storage model, workflow engine, validator, CLI, database, transport, prompt format, agent harness, or runtime integration.
- Running the STEP-07 proof-of-concept pilot.
- Disposing STEP-08 research hypotheses.
- Preparing the final separate `prod-w` publication package.
- Claiming that any representation proves a human acted.
- Adding numeric evidence sufficiency scores, weights, confidence percentages, or artificial precision.

---

## Required Outputs

At minimum:

1. `prod-w/methodology-guidance.md`
2. `prod-w/role-charters.md`
3. `prod-w/templates.md`

The Development Team may add more files if doing so improves usability without fragmenting the method.

---

## Acceptance Checks

- [ ] Methodology guidance is added under `prod-w/` and states it is guidance, not protocol revision.
- [ ] Role charters distinguish actor identity, role labels, authority grants, participation capacity, and work assignment.
- [ ] Guidance describes project establishment practice and root-grant practice without modifying D10.
- [ ] Guidance describes independence practice for small teams, including authority gaps.
- [ ] Evidence guidance distinguishes evidence, counter-evidence, negative findings, assumptions, hypotheses, inferences, and decisions.
- [ ] Evidence guidance gives category and threshold practice without making universal sufficiency scores.
- [ ] Gate guidance includes gate-definition slots, acceptance, refusal, deferral, exception, conditional progression, and escalation practice.
- [ ] Templates exist for key artifacts and preserve producer, reviewer/challenger, verifier, acceptor, authority, provenance, and standing-record distinctions.
- [ ] Worked examples show at least one valid progression and one visible non-progression or unresolved-disagreement case.
- [ ] Formal-check guidance records findings without letting checks become gate acceptance.
- [ ] Guidance addresses actor-kind binding practice without claiming the protocol proves a human acted.
- [ ] Guidance addresses source comparability and producing-configuration version binding at the practice level.
- [ ] Guidance keeps recovery by new project visible and does not define carry-over as accepted unless expressly marked as project practice.
- [ ] The artifact routes pilot-validation questions to STEP-07 and research/hypothesis disposition to STEP-08.
- [ ] No representation, schema, validator, lifecycle graph, serialized state vocabulary, tool, or publication package is selected or implemented.
- [ ] Any concrete transferability evidence encountered is proposed under the research governance process.
- [ ] STEP-06 final acceptance is not recorded until Phase 3a, 3b, and 3c have occurred or been waived.

---

## Plan

1. Extract the guidance-owned items from accepted STEP-01 to STEP-05 artifacts.
2. Draft `methodology-guidance.md` as the user-facing operating method.
3. Draft `role-charters.md` for practical role positions and authority boundaries.
4. Draft `templates.md` with copyable human-readable templates.
5. Add traceability from the guidance back to AC-2, `DM-*`, and STEP-05 routed questions.
6. Self-check for accidental protocol changes, representation selection, numeric sufficiency, and hidden authority grants.
7. Submit for Tech Lead, QA, Product Owner, and Moderator review according to this work package.

---

## Change Notes

| Date | Change | Reason |
| --- | --- | --- |
| 2026-10-04 | Initial STEP-06 work package | Begin methodology guidance and templates after STEP-05 readiness. |
| 2026-10-04 | STEP-06 work package approved | MOD-W Moderator accepted the Tech Lead's STEP-06 package and authorized Development Team implementation. See `mod-w/reviews/MODERATOR-REVIEW-STEP-06-SETUP.md`. |

---

MOD-W v5.0.1
