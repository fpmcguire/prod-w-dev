---
artifact:
  type: step
  id: STEP-07
  version: 0.1
  created: 2026-10-04
  updated: 2026-10-04
  status: Approved
---

# STEP-07 - Proof-of-Concept Product Opportunity Trial

---

## Goal

Run one small product opportunity through PROD-W to test whether the accepted protocol semantics and STEP-06 methodology can be used coherently by a product team.

This step produces pilot evidence. It does not revise protocol semantics, select a final representation, build tooling, publish PROD-W, or prove broad product effectiveness. One successful trial may support feasibility, coherence, usability, gate behavior, role interaction, and protocol execution. It does not prove commercial value, universal applicability, robustness across product categories, or that PROD-W should be adopted without further trials.

---

## Governance Context

**This artifact is authored and reviewed under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-07 acceptance for `prod-w-dev`.

The pilot may simulate or instantiate PROD-W product roles inside the trial. Those product-role acts are pilot subject matter only. They do not grant authority over this MOD-W step unless MOD-W governance separately grants it.

For STEP-07, the expected review sequence is:

| MOD-W point | Expected handling |
| --- | --- |
| 2a Plan approval | Development Team may proceed from this work package only after Moderator setup approval. |
| 2b Development Team work product | Development Team runs and records the pilot under `prod-w/`. |
| 3a Tech Lead review | Required before final Moderator acceptance. Checks protocol conformance, evidence quality, traceability, and accidental scope expansion. |
| 3b QA | Required before final Moderator acceptance unless explicitly waived. QA samples records, gate artifacts, issue log, role independence, and acceptance-check coverage. |
| 3c Product Owner sign-off | Required before final Moderator acceptance unless explicitly waived. Confirms whether the pilot evidence is useful from the intended product-team perspective. |
| 4a Moderator acceptance | Final acceptance only after required reviews or recorded waivers. |

---

## Related Requirements

- AC-3 - At least one small product opportunity is taken through PROD-W workflow.
- E-1 - Protocol feasibility.
- E-2 - User applicability.
- E-3 - Discipline enforcement.
- E-4 - MOD-W transferability.
- E-5 - Role model coherence.
- E-6 - Evidence quality.
- E-7 - Authority clarity.
- E-8 - Workflow progression semantics.
- E-9 - Automated enforceability boundary.
- FR-1 - Roles and authority remain explicit.
- FR-3 - Evidence requirements remain visible and traceable.
- FR-4 - Self-approval remains invalid.
- FR-5 - Unresolved disagreement remains visible.
- FR-6 - Provenance supports acceptance history, challenge history, and current standing.
- FR-7 - Material hypotheses are validated or visibly handled as unresolved assumptions.
- NG-1 / NG-2 - Do not select representation or build tooling prematurely.

---

## Inputs

Accepted inputs:

- `mod-w/product.md`
- `mod-w/architecture.md`
- `mod-w/domain-language.md`
- `mod-w/roadmap.md`
- `prod-w/protocol-semantics.md`
- `prod-w/evidence-knowledge-model.md`
- `prod-w/gate-challenge-revalidation-semantics.md`
- `prod-w/rule-judgment-boundary.md`
- `prod-w/representation-options.md`
- `prod-w/methodology-guidance.md`
- `prod-w/role-charters.md`
- `prod-w/templates.md`
- `prod-w/worked-examples.md`
- `mod-w/reviews/MODERATOR-REVIEW-STEP-06-ACCEPTANCE.md`
- `mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-06.md`

Useful supporting inputs:

- `research/mod-w-transferability/README.md`
- `research/mod-w-transferability/observations.md`
- `research/mod-w-transferability/adaptations.md`

---

## Assigned Dev Team Interface

- [x] Claude Code (default)
- [ ] Claude Design (visual / chart / interaction-heavy Step)

---

## Scope

- Select or define one small product opportunity suitable for a short PROD-W trial.
- Establish a pilot project record using the STEP-06 templates and methodology.
- Run the opportunity through at least:
  - one project establishment/root-grant act;
  - role-position and grant records sufficient for the trial;
  - one source register;
  - material claim, evidence, counter-evidence or negative-finding, assumption, hypothesis, and inference records as needed;
  - at least one challenge;
  - at least one discovery-style gate;
  - at least one build/no-build or proceed/stop gate.
- Exercise, or explicitly record why the trial could not exercise:
  - self-approval prevention;
  - independence declaration;
  - authority-gap handling;
  - unresolved disagreement or visible non-progression;
  - conditional progression or exception handling;
  - revalidation trigger or revalidation request;
  - consequential commitment recording;
  - record-versus-document distinction;
  - formal-check result boundary.
- Produce a pilot case record, issue log, and validation findings under `prod-w/`.
- Propose concrete MOD-W transferability observations if the trial generates evidence.

---

## Out of Scope

- Changing accepted STEP-01 to STEP-06 artifacts.
- Selecting a final representation, schema language, state vocabulary, lifecycle graph, storage model, workflow engine, validator, CLI, database, transport, prompt format, agent harness, runtime integration, API, or publication package.
- Building tooling or automated validators.
- Treating templates as schemas or parsable formats.
- Treating the pilot as evidence that PROD-W is broadly effective across all product categories.
- Treating agent agreement as independent evidence.
- Treating a formal-check result as gate acceptance.
- Treating Product Skeptic, Product Advocate, external evaluator, Product Knowledge Ledger, null-hypothesis framing, or agent-harness conformance as accepted core product scope unless already supported by an accepted artifact.
- Disposing STEP-08 research hypotheses.
- Preparing the STEP-09 publication package.

---

## Pilot Design Requirements

The Development Team must keep the pilot small enough to finish in one step while still exercising meaningful governance pressure.

The product opportunity should:

- have a clear target user and problem claim;
- be plausible enough that a build/no-build gate is meaningful;
- be narrow enough that evidence collection can be recorded without pretending to run a full market study;
- include at least one material uncertainty that cannot honestly be resolved by agent synthesis alone;
- allow counter-evidence or negative findings to be searched for and recorded;
- include at least one technical or operational feasibility claim separate from commercial desirability;
- avoid relying on confidential, inaccessible, or unverifiable external data.

The Development Team may use an invented or internal opportunity only if it clearly marks the opportunity as pilot material and does not draw real-market conclusions beyond the evidence recorded. If real external evidence is used, sources must be recorded with retrieval markers and limitations.

---

## Required Outputs

Add, at minimum:

1. `prod-w/proof-of-concept-trial.md`
2. `prod-w/proof-of-concept-records.md`
3. `prod-w/proof-of-concept-issues.md`
4. `prod-w/proof-of-concept-findings.md`

The Development Team may add supporting files if they improve readability. If additional files are added, `proof-of-concept-trial.md` must index them and explain their standing.

---

## Required Output Structure

### `prod-w/proof-of-concept-trial.md`

Must include:

1. Purpose and standing.
2. Pilot opportunity description.
3. Pilot boundaries and non-claims.
4. Role setup and authority model.
5. Pilot record location and record-order practice.
6. Trial flow summary.
7. Gates attempted and outcomes.
8. What was exercised and what was not exercised.
9. Burden and usability notes.
10. Limits of the evidence.
11. Traceability to AC-3 and E-1 to E-9.

### `prod-w/proof-of-concept-records.md`

Must include the filled pilot records, or a stable index to separate filled-record files, using the STEP-06 template language as human-readable prompts rather than schemas.

At minimum, include records corresponding to templates:

- 1 Project Establishment Record
- 2 Role-Position Entry
- 3 Grant Act Record, if any grant changes after establishment
- 4 Source Register Entry
- 5 Claim Record
- 6 Evidence Record
- 7 Attempt and Negative-Finding Record
- 8 Inference Record
- 9 Assumption Record
- 10 Hypothesis Record
- 11 Producing-Configuration Statement for AI-produced records or analysis
- 12 Challenge Record
- 13 Gate Definition
- 14 Gate Readiness Checklist
- 15 Gate Decision Record
- 16 Independence Declaration
- 20 Authority-Gap Record, if an authority gap occurs or is intentionally tested
- 21 Revalidation Request and Closure Record, if a revalidation trigger is exercised
- 22 Formal-Check Result
- 24 Consequential Commitment That Is Not an Acceptance, if such a commitment occurs or is intentionally tested
- 25 Actor-Kind Binding Note for consequential human AUTH-G acts
- 28 Method Issue Log Entry references

If a listed record kind is not produced, the file must state why it was not applicable or could not be exercised.

### `prod-w/proof-of-concept-issues.md`

Must record method issues, ambiguities, burdens, failed attempts, and open questions found during the trial.

Each issue must route to one of:

- STEP-07 pilot evidence;
- STEP-08 research disposition;
- MOD-W Moderator protocol question;
- Product Owner usability follow-up;
- later architecture or representation work;
- later methodology correction.

### `prod-w/proof-of-concept-findings.md`

Must state findings conservatively:

- what the pilot demonstrates;
- what the pilot suggests but does not demonstrate;
- what the pilot failed to exercise;
- which STEP-06 practice defaults were workable, burdensome, unclear, or not tested;
- what evidence supports each finding;
- which findings are Product Owner usability findings, Tech Lead protocol-conformance findings, QA verification findings, or Development Team observations.

---

## Required Pilot Focus

The Development Team must directly address the focus carried forward from STEP-06 final acceptance:

- Solo-founder usability without false self-approval.
- Three-human plus AI-agent execution of the common block, source/evidence records, independence declarations, and gate decision records.
- Two-human avoidance of accidental co-production.
- Gate readiness checklist usefulness.
- Time and burden to complete the minimum artifact set for discovery and build/no-build gates.
- Same-day counter-evidence recording.
- Consequential-commitment recording through template 24.
- Grant review and authority-gap handling before a crisis.
- Record-versus-document usability.
- Continued clarity that worked examples are scenarios, not evidence.

The pilot does not need to run three separate full projects. It may use the primary pilot plus targeted sub-scenarios or table-top exercises for solo-founder, two-human, and three-human-plus-agent cases, provided the output clearly distinguishes full pilot evidence from scenario observations.

---

## Acceptance Checks

- [ ] `prod-w/proof-of-concept-trial.md` is added and states that STEP-07 is a pilot, not protocol revision, representation selection, tooling implementation, or publication preparation.
- [ ] The pilot opportunity is small, bounded, and described with clear non-claims.
- [ ] The pilot establishes a project record with explicit human identity, root grants, role positions, authority scopes, and record-order practice.
- [ ] The pilot records actor identity, actor kind, participation capacity, authority grants, producers, challengers, verifiers, acceptors, and producing configuration where applicable.
- [ ] The pilot includes at least one material claim with evidence, counter-evidence or negative finding, assumptions, hypotheses, and inference separated.
- [ ] Agent agreement is not treated as independent evidence.
- [ ] At least one challenge is recorded, and its standing is visible.
- [ ] At least one discovery-style gate and one build/no-build or proceed/stop gate are defined before use and attempted.
- [ ] Gate readiness and gate decision records identify accepted set, standing-record treatment, formal-check result, contextual sufficiency rationale, and independence declaration.
- [ ] Self-approval is avoided or recorded as invalid/non-progression; no pilot success claim relies on self-approval.
- [ ] Unresolved disagreement, if present, remains visible; if no real disagreement occurs, the pilot records this as a limitation and tests non-progression or residual acceptance by scenario.
- [ ] Authority-gap handling is exercised or explicitly recorded as unexercised with a reason.
- [ ] Conditional progression, exception handling, revalidation, and consequential commitment handling are exercised or explicitly recorded as unexercised with reasons.
- [ ] The record-versus-document distinction from STEP-06 is applied and assessed.
- [ ] Formal-check results are recorded without becoming gate acceptance.
- [ ] The pilot measures or estimates artifact burden, including time, number of records, repeated fields, unclear prompts, and points where the team was tempted to skip or collapse distinctions.
- [ ] `prod-w/proof-of-concept-issues.md` records method issues and routes them without resolving out-of-scope questions.
- [ ] `prod-w/proof-of-concept-findings.md` maps findings to AC-3 and E-1 to E-9 and distinguishes demonstrated evidence from suggestions and non-claims.
- [ ] The pilot does not modify accepted STEP-01 to STEP-06 product artifacts.
- [ ] The pilot does not select or implement a final schema, validator, lifecycle graph, serialized state vocabulary, storage model, workflow engine, CLI, database, transport, prompt format, agent harness, runtime integration, API, or publication package.
- [ ] Any concrete MOD-W transferability evidence is proposed under the research governance process and not treated as accepted unless separately accepted.
- [ ] STEP-07 final acceptance is not recorded until Tech Lead review, QA, and Product Owner sign-off have occurred or been explicitly waived by the MOD-W Moderator.

---

## Tech Lead Recommendations to the Development Team

1. Start by choosing the smallest opportunity that can still produce real pressure on evidence, authority, and gate behavior.
2. Keep pilot records boring and explicit. This step is testing whether the method works, not whether the documents are elegant.
3. Do not optimize away repetition during the pilot. Record repetition as burden evidence instead.
4. Separate the full pilot from table-top sub-scenarios. Label each observation by its evidence strength.
5. Prefer a visible refusal, deferral, authority gap, or unresolved disagreement over a neat-looking acceptance that the record cannot support.
6. Record temptations and friction. If a template feels too heavy or a distinction feels artificial, that is useful evidence.
7. Do not patch STEP-06 methodology during the pilot. Record issues in the issue log and route them.
8. Keep findings modest. A pilot can show that PROD-W can be followed in one bounded case; it cannot show that PROD-W works everywhere.

---

## Plan

1. Read accepted STEP-01 to STEP-06 artifacts and this work package.
2. Select a bounded product opportunity and state pilot non-claims.
3. Establish the pilot record with root grants, role positions, record-order practice, and actor-kind binding practice.
4. Record initial claims, sources, evidence, counter-evidence/negative findings, assumptions, hypotheses, and inferences.
5. Define the discovery and build/no-build or proceed/stop gates before use.
6. Run challenge, gate readiness, formal-check, independence, and gate decision records.
7. Exercise or table-top authority gap, conditional progression, exception, revalidation, consequential commitment, and small-team scenarios.
8. Maintain the issue log as friction, ambiguity, and invalid-transition risks appear.
9. Write findings against AC-3 and E-1 to E-9.
10. Propose transferability observations if concrete evidence emerges.
11. Submit the pilot package for Tech Lead review, QA, Product Owner sign-off, and Moderator acceptance.

---

## Research Governance Route

If STEP-07 produces concrete evidence about MOD-W's transferability to methodology/protocol development, propose an observation in `research/mod-w-transferability/observations.md`.

Use the existing research-governance structure and mark any new observation as proposed. The Development Team must not treat proposed observations as accepted findings. The MOD-W Moderator decides whether to accept, modify, defer, or reject them.

Candidate STEP-07 transferability topics include:

- whether "implementation" as pilot execution is coherent for a protocol/methodology product;
- whether QA review of filled records is a useful analogue to software testing;
- whether Product Owner sign-off can judge method usability from a bounded trial;
- whether MOD-W role boundaries remain stable when the product being developed is itself a governance method;
- whether issue routing and evidence burden expose software-specific assumptions.

---

## Change Notes

| Date | Change | Reason |
| --- | --- | --- |
| 2026-10-04 | Initial STEP-07 work package | Prepare proof-of-concept product opportunity trial for Development Team implementation after STEP-06 acceptance. |
| 2026-10-04 | STEP-07 work package approved | MOD-W Moderator accepted the Tech Lead's STEP-07 package and authorized Development Team implementation. See `mod-w/reviews/MODERATOR-REVIEW-STEP-07-SETUP.md`. |

---

MOD-W v5.0.1
