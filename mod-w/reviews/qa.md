# QA: Step STEP-02

**Project:** prod-w-dev
**Step:** STEP-02 — Define Evidence, Knowledge, and Provenance Model
**Tester:** QA (MOD-W v5.0.1), read-only validation
**Date:** 2026-09-30

**Scope and method:** Read in full: `mod-w/step-02.md`, `prod-w/evidence-knowledge-model.md`, `prod-w/protocol-semantics.md` (relevant parts), `mod-w/domain-language.md`, `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02.md`, `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`, `research/mod-w-transferability/observations.md`. Checked git history from `dcbcbe4` to `HEAD` (commits `e0e9097`, `818aa56`). Ran a forbidden-term scan on the model and compared accepted domain terms with the model's usage. Nothing was modified. QA validates and reports only; it does not approve fixes.

---

## Summary

**Result:** Fail

The content of STEP-02 passes all 15 acceptance checks. The Fail comes from gate and record defects:

- Acceptance was recorded before QA (3b) and Product Owner (3c) ran.
- No STEP-02 waiver exists for either gate.
- The disposition of the pending terms and observations is unclear.
- The required MW-ADAPT-001 re-evaluation is not recorded.
- Several authority-adjacent choices were made but not declared.

No defect requires rewriting the model's substance. All need a Moderator disposition or a record correction; none has been applied.

---

## Requirement Coverage

| Requirement | Tested | Result |
| --- | --- | --- |
| AC-01 Classes distinguished | Yes | Pass (§4.2 to 4.4, EKR-01) |
| AC-02 Counter-evidence and negative findings first-class | Yes | Pass (§7.4, 7.5; EKR-15, EKR-16) |
| AC-03 Agent agreement excluded | Yes | Pass (§7.6, EKR-17, EKR-06) |
| AC-04 Material-claim provenance | Yes | Pass (§6.2 to 6.4, EKR-08, EKR-35) |
| AC-05 Presence versus sufficiency | Yes | Pass (§7.9, §11, EKR-19, EKR-41) |
| AC-06 Assumption versus hypothesis; validation | Yes | Pass (§8, EKR-21 to 25) |
| AC-07 Inference is not evidence | Yes | Pass (§9.1, EKR-26, EKR-27) |
| AC-08 Decisions, without changing gate authority | Yes | Pass (§9.3 to 9.5, EKR-29; STEP-01 untouched) |
| AC-09 Dependencies identify downstream items | Yes | Pass (§10.1 to 10.4, EKR-37) |
| AC-10 Triggers without state names or lifecycle | Yes | Pass (EKR-02, §10.5) |
| AC-11 Disagreement without forced consensus or `DIVERGENT` | Yes | Pass (§5.4, EKR-05, EKR-06) |
| AC-12 Evaluators advisory | Yes | Pass (§7.8, EKR-20) |
| AC-13 Undecided Architecture Declaration present | Yes | Pass on existence. Completeness challenged in D-05. |
| AC-14 No premature technology selection | Yes | Pass |
| AC-15 Transferability evidence proposed, not self-accepted | Yes | Pass on Dev Team conduct. Dispositions unclear, see D-03. |
| Required structure (15 sections) | Yes | Pass |
| MOD-W Phase 3 gates (3a, 3b, 3c) for STEP-02 | Yes | Fail, see D-01 |

---

## Test Cases

| ID | Description | Expected | Actual | Status |
| --- | --- | --- | --- | --- |
| TC-01 | Check each of the 15 acceptance checks in `step-02.md` against the model §14.3 and the cited sections | Each check met in the cited section | All 15 verified in the text, not just the traceability table | Pass |
| TC-02 | Scan the model for selected technology, schemas, storage, state names, engines, validators or serialization | None selected | Hits for YAML, JSON, ledger, graph store, `DIVERGENT` occur only in negations (lines 56, 57, 62, 901, 1010, 1011). `EKR-`, `EKO-`, `TRG-` labels are declared expository. §7.3 categories are explicitly illustrative. | Pass |
| TC-03 | `prod-w/protocol-semantics.md` unchanged by STEP-02 | No diff | Empty diff since `8c3fda7`; working tree clean | Pass |
| TC-04 | Model does not alter authority, self-approval or gate rules | PR-01 to PR-28, ACT-05, ACT-07 preserved | §3.1 preserves them; §9.3 and EKR-29 restate without change. Two declared extensions (ACT-03 targets, PR-26 scope) checked in TC-08. | Pass, with notes D-05, D-06 |
| TC-05 | Distinct treatment of counter-evidence, negative findings, assumptions, hypotheses, inferences, decisions, dependencies, provenance, triggers | Each has its own definition, test and rules | Yes; see also §4.3, §7.5 (attempt record vs inference), §8.1, §10.4 (trigger vs requirement vs revalidation) | Pass |
| TC-06 | §12 exists and Tech Lead review addresses it | Section present and dispositioned | §12 has 16 UADs, working test, self-assessed levels, priority order, decisions not made. Tech Lead review has a "UAD Disposition" section confirming UAD-01 to UAD-16. | Pass on existence. Completeness: D-05. |
| TC-07 | Tech Lead required revisions resolved | Both findings and editorial note fixed | Finding 1: §3.3, 10.4, 10.7, 10.8, EKR-37, EKR-38, EKO-19, UAD-06, AC-09 and WD-6 rows all say "every dependent item with a material dependency"; no residual decision-only wording. Finding 2: D9 row (line 993) corrected. Editorial: EK-OQ-16 exists; EK-OQ-02 narrowed. | Pass |
| TC-08 | Declared STEP-01 extensions (ACT-03 targets, PR-26 scope) are explicit, not silent | Declared and Tech Lead-confirmed | Declared in §3.3, UAD-03, UAD-06. No new authority. Confirmed by Tech Lead. | Pass |
| TC-09 | `domain-language.md` edit procedurally appropriate, no self-acceptance | Separate pending section; accepted table untouched | Section titled "Pending MOD-W Moderator Acceptance", separate from the accepted table, which is unchanged. See D-02 for the later record problem. | Pass (Dev Team), Fail (record) |
| TC-10 | `observations.md` edit procedurally appropriate, no self-acceptance | Proposed status; disposition Pending | MW-OBS-011 and -012 are "Proposed", disposition "Pending Moderator review". See D-03. | Pass (Dev Team), Fail (record) |
| TC-11 | All STEP-02 gates run or visibly waived | 3a, 3b, 3c run, or GR-7/OBJ-12 waivers recorded | 3a run. 3b is this report, produced after acceptance. No 3c and no waiver for either. | Fail |
| TC-12 | Status text consistent across artifacts | No stale text | Stale text found (D-03, D-07) | Fail |

---

## Defects

| ID | Description | Severity | Status |
| --- | --- | --- | --- |
| D-01 | **Acceptance was recorded before the QA (3b) and Product Owner (3c) gates, and no STEP-02 waiver exists.** The STEP-01 waiver is expressly "specific to `prod-w/protocol-semantics.md` and STEP-01… not a standing decision" (`mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md:232`). MW-OBS-012 names this as an open Moderator decision (`research/mod-w-transferability/observations.md:889`). `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md` does not mention 3b or 3c. Acceptance checks are already ticked (`mod-w/step-02.md:142-158`), the roadmap says "Accepted" (`mod-w/roadmap.md:39`), and the model is marked Accepted. This is an unrecorded waiver and contradicts the MOD-W rule that QA precedes acceptance. | High | Open. Needs Moderator decision. |
| D-02 | **Pending domain terms have no recorded disposition, and records conflict.** The Moderator review lists "STEP-02 pending terms appended to `mod-w/domain-language.md`" under Accepted Artifacts. The section still says "Pending MOD-W Moderator Acceptance… not yet accepted" (`mod-w/domain-language.md:90-112`). There is no per-term accept, modify or return. The 16 terms include load-bearing ones (Validation, Invalidation, Material dependency, Revalidation requirement). The model also inherits pending status for STEP-01 terms (advisory finding, producer, independence, producing configuration). | Medium | Open |
| D-03 | **Observations have no disposition, and their text is stale.** MW-OBS-011 and MW-OBS-012 are "Proposed" with "Pending Moderator review", but the Moderator review lists "Proposed transferability observations" under Accepted Artifacts, which is ambiguous. Body text is stale after 3a ran: MW-OBS-011 says the Tech Lead review "has not occurred"; MW-OBS-012 says "No Phase 3a, 3b, or 3c has been run". The optional follow-up (Tech Lead samples unlisted choices at Moderator's discretion) is neither recorded as done nor declined. | Medium | Open |
| D-04 | **MW-ADAPT-001 re-evaluation not recorded.** `research/mod-w-transferability/adaptations.md:75` requires it at the STEP-02 gate: did the declaration produce findings, and did architecture-level content slip past it? The Tech Lead review confirms the declared UADs but does not answer the "slipped past" half. `adaptations.md` is unchanged and the Moderator review is silent. | Medium | Open |
| D-05 | **Some authority- and revalidation-touching choices are not in §12**, so the Tech Lead never confirmed them. (a) §5.2 and §7.7 allow counter-evidence attachment under AUTH-P or AUTH-A. STEP-01's ACT-02 row says AUTH-P only, while its authority table (`prod-w/protocol-semantics.md:138`) lets AUTH-A "attach counter-evidence"; the model resolves this tension silently. (b) §10.5 fixes who may withdraw, supersede and invalidate: a producer may withdraw or supersede its own item without acceptance; another actor's item needs acceptance authority. It is routed only as EK-OQ-06, not declared. (c) EKR-38 and §10.8 require a human closer for any dependent "cited by" a consequential decision, beyond PR-26's "authorized actor". (d) EKR-18 imposes a new affirmative duty on actors to record contradicting information. None changes STEP-01 text or AUTH-G rules, so none is classed as an authority change. All meet the model's own declaration test in §12.1 (authority, revalidation, what counts as evidence). | Medium | Open |
| D-06 | **Accepted domain terms now disagree with the model.** "Challenge" is defined against "a claim, inference, or decision", but UAD-03 extends targets to evidence and relationships. "Inference" is defined as "drawn from evidence", but the model allows inference from assumptions and other inferences. Neither revision is proposed in the pending table. | Low | Open |
| D-07 | **Stale delivery statement.** §15 says "No accepted… Roadmap… STEP-02 definition… was modified" (`prod-w/evidence-knowledge-model.md:1045`). Acceptance commit `e0e9097` modified `mod-w/roadmap.md` and `mod-w/step-02.md`. `mod-w/step-02.md:123` bars roadmap changes without a "separate Moderator-authorized correction", and the Moderator review does not record that authorization. The edits look like routine status updates but are unrecorded. | Low | Open |
| D-08 | **Internal ambiguity in the trigger rules, routed nowhere.** EKR-39 says "Contradiction and challenge take visible effect immediately", but §10.5 says "a challenge alone is not a trigger"; the intended effect (exposure vs requirement) is not stated. TRG-2 lets any contradicting claim create a requirement on all dependents by itself, nearly as cheap as a challenge, which §10.5 excludes for that reason. EK-OQ-04 covers challenges only. | Low | Open |

---

## Regression Check

- [x] No regressions to STEP-01 (`prod-w/protocol-semantics.md`, `mod-w/step-01.md`, `mod-w/architecture.md`, `mod-w/product.md` and `mod-w/templates/` unchanged since `8c3fda7`)
- [ ] Existing tests pass — N/A: the repository has no build, test or CI configuration (see MW-OBS-008, MW-OBS-012)

---

## Notes

**Findings that do not need a fix:**

- Scope discipline is good. The model repeatedly declines to choose representations, and the 20 EKO conditions are framed as an initial classification, not the STEP-04 catalog.
- §9.4 (decisions must cite opposition) and EKR-41 sit close to gate mechanics and implementation guidance. Both are declared or hedged; STEP-03 should revisit them.
- UAD-04 to UAD-07 (item identity across change, presumed materiality, layered revalidation, trigger set) are architecture-adjacent. The Tech Lead ruled they need no promotion. `mod-w/architecture.md` is unchanged, so these rules exist only in the product artifact.
- The Moderator review records approval but does not mention UAD dispositions, the level-A items or gate status.
- There is no `step-02-complete` tag, though STEP-01 had one.

**Recommended Moderator actions (not applied; QA does not approve fixes):**

1. D-01: either run 3c and formally ratify 3b using this report, or record a STEP-02-specific GR-7 waiver with authorized human, unsatisfied requirement and rationale.
2. D-02, D-03: issue explicit per-term and per-observation dispositions, then update the section headings and Disposition lines.
3. D-04, D-05: record the MW-ADAPT-001 re-evaluation, and decide whether the Tech Lead should confirm the items in D-05.

---

MOD-W v5.0.1
