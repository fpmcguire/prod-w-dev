---
type: qa-review
from: QA
to: MOD-W Moderator, Tech Lead, Product Owner, Development Team
date: 2026-10-04
review_artifacts:
  - mod-w/step-07.md
  - mod-w/reviews/MODERATOR-REVIEW-STEP-07-SETUP.md
  - prod-w/proof-of-concept-trial.md
  - prod-w/proof-of-concept-records.md
  - prod-w/proof-of-concept-issues.md
  - prod-w/proof-of-concept-findings.md
  - research/mod-w-transferability/observations.md#MW-OBS-019
  - mod-w/reviews/TECH-LEAD-REVIEW-STEP-07.md
  - mod-w/reviews/MODERATOR-REVIEW-STEP-07-TECH-LEAD.md
review_status: PASS_WITH_NOTES
---

# QA Review: STEP-07 (Phase 3b)

## Recommendation

**PASS_WITH_NOTES.**

There are **no blocking findings**. The package is a labeled, simulated, scripted pilot. It supports only the narrow claim it makes for itself: PROD-W's records and rules can be followed to a coherent, traceable, visibly non-progressing result in one bounded case. I found no place where a finding treats a simulated act as a real human determination.

This review does **not** record STEP-07 final acceptance. Product Owner sign-off (3c) and Moderator acceptance (4a) remain pending. This review does not waive either.

## Method and Coverage

**Read in full:**

- `mod-w/step-07.md`
- the Tech Lead review
- the Moderator Tech Lead review
- `proof-of-concept-trial.md`
- `proof-of-concept-findings.md`
- `proof-of-concept-issues.md`
- MW-OBS-019

**Read in part:**

- `proof-of-concept-records.md`: the header and §0; R-001; R-033; R-044; R-045 to R-049; R-054 to R-057 (headings and R-055 in full). Record counts were taken mechanically.

**Checked mechanically:**

- git diff of the accepted-artifact set
- rule-ID existence and content, by grep against the accepted semantics files
- SIMULATED/SCRIPTED label counts

**Not done:** I did not read all 58 records line by line. I did not re-run the Standing Card staleness test (S-5, "four of nine answers wrong") or the T-1/T-2 tests. I did not verify the stated 12-minute authoring time, which cannot be verified from the artifacts. These are limits of this review.

## Moderator-Directed Checks

### 1. SIMULATED/SCRIPTED labels across artifacts — satisfied

| Artifact | Where the boundary is stated or carried |
| --- | --- |
| Trial | §1 "Reading rule"; §3 simulation boundary and the five SCRIPTED events; §7 ("Simulated determination"; "No claim relies on R-054 being valid"); §8 strength key; §10 limits 1 to 5 |
| Records | §0, which says no human performed any H-A or H-B act and no outcome is a determination. 15 SIMULATED/SCRIPTED markers sit at the point of use. R-033, R-044, R-045, R-047, R-048, R-054, R-057 and R-001 are labeled in their headings or bodies. R-055 carries the same-session limit. |
| Issues | Header "Reading the pilot's limit"; ISS-01 (the whole-pilot statement) |
| Findings | "Read first"; "Wording used"; §3 N-1 to N-3; §7 "Net statement" |
| MW-OBS-019 | Observation 2 and the Interpretation section state one author and scripted outcomes |

The boundary is consistent across all five artifacts. The scripted events named in the trial (R-033, R-045, R-047, R-048, R-054) match the records' own labels.

### 2. No finding relies on simulated acts as real human determinations — satisfied

- Findings D-1 to D-11 are worded as record-shape and rule-application statements. The "What these do not show" line, the "Net statement", and E-2 with no demonstrated finding all keep that boundary.
- D-3, D-5, D-6, D-8 and D-9 rest on scripted outcomes. Each is bounded by the opening note, and D-5 states that "no pilot claim relies on it".
- S-2, S-3 and S-4 are labeled "suggests" with the scripting reason stated.

See note QN-1 for one wording point.

### 3. Independent sampling of rule citations and cross-references — materially sound, with minor notes

Each ID below was checked against the accepted text.

**Confirmed to exist and to say what the pilot uses them for:**

- GCR-03, GCR-05, GCR-08, GCR-09, GCR-10, GCR-12, GCR-13, GCR-17, GCR-25, GCR-39, GCR-48, GCR-58
- TRG-2, including the STEP-03 narrowing, which ISS-13 reads correctly
- PR-06, PR-08, PR-11, PR-13, PR-17, PR-27, PR-28
- CRC-15, CRC-19, CRC-39, CRC-45, CRC-47, CRC-51, CRC-59, CRC-64
- EKR-11, EKR-21
- RJ-OQ-12 and MG-N3 (the latter in `methodology-guidance.md`)
- RQ-04, RQ-05, RQ-08, RQ-16, RQ-17, and the existence of GC §8.6 and RO §9.5

**Specific checks:**

- **R-055's three rules.** The three rules it asserts violated are decidable from the record. They are the producer of a set member, CRC-19/FC-3, and GCR-17. Its fourth item is correctly marked "not violated". The findings' "names three violated rules" is accurate.
- **ISS-08.** It is consistent with RQ-16, which is about same-vendor review and PR-27/PR-28.
- **ISS-10.** It is consistent with RQ-04, whose scope text names STEP-07 backdating evidence.

**Notes:**

- **EKR-17.** ISS-11 cites it. The ID is not defined in `evidence-knowledge-model.md` (only EKR-11 and EKR-21 were found there). It appears only inside a CRC-36 line in `rule-judgment-boundary.md`. This looks like a stale or mis-cited ID. See QN-2.
- **CRC-62.** ISS-15 cites it for the root-grant nudge. CRC-62 invalidates non-root self-conferral and expressly exempts root grants, so GCR-05 is the on-point citation and CRC-62 is only tangential. See QN-2.
- **"GC §5.4 condition 4".** R-055 cites it. I confirmed §5.4 exists, but did not confirm that "condition 4" is the right numbering. Low risk, because GCR-03 and FC-2 are cited alongside it.

The Development Team's own disclosure (trial §10.10) that rule IDs were taken from the guidance and not checked at source was warranted. The sample found two imprecise citations and no misstated rule.

### 4. ISS-08 and ISS-10 routing — satisfied

- **ISS-08** is routed to a MOD-W Moderator protocol question (existing RQ-16). It says "The pilot adds a data point and decides nothing." The same-session limit is stated in R-008 and at each result.
- **ISS-10** is routed to later architecture or representation work (RQ-04). Its stated pilot evidence is "the weak point is real in a one-writer file".
- The findings (§6) and the trial (§5) describe both as routed, not resolved.
- Neither is treated as resolved anywhere I read. The findings §4 and S-8 phrasing ("cannot show whether exploitable") preserves this.

### 5. STEP-07 acceptance checks — met, or visibly marked not exercised with reasons

All checks are either met in the artifacts or marked in the trial §8 and findings §3.

| Item | QA assessment |
| --- | --- |
| Four required files present | Met |
| Pilot-not-revision/tooling/publication statement; non-claims | Met (trial §1, §3) |
| Establishment, root grants, positions, record-order practice | Met, simulated (R-001) |
| Claim, evidence, counter-evidence, negative finding, assumption, hypothesis and inference separated | Met in sampled records, and the trial's record-group map is coherent |
| Agent agreement not treated as evidence | Met (R-019; the claim is stated and the agent reader is set aside) |
| Challenge standing, gates defined before use and attempted | Met (R-020/R-021 before evidence; CH-01 to CH-03) |
| Self-approval | Met: R-054 is kept visible as invalid and R-055 is its finding |
| Disagreement | Visible, but the pilot records that no real disagreement occurred. The step asks for exactly this limitation statement, and it is made. |
| Authority gap, conditional progression, revalidation, consequential commitment | Exercised as scripted events |
| **Exception handling** | **Not exercised.** Reason: nothing waivable was unsatisfied. Scenario S-2 only. Visibly marked. |
| **Grant Act Record (T-3)** | **Not produced.** Reason: no grant changed. Visibly marked. |
| **Revalidation closure** | **Not exercised.** Reason: AG-1. Visibly marked. |
| **T-26** | **Not applicable**, with reason |
| Record-versus-document | Applied and assessed (ISS-09) |
| Formal-check results are not acceptance | Met ("effect claimed / not claimed") |
| Burden | Counts and AI elapsed time are reported. They are not human burden, and the artifacts say so (ISS-20). |
| Issues routed without resolving out-of-scope questions | Met |
| Findings map to AC-3 and E-1 to E-9 | Met (findings §7; trial §11) |

QA verified the record counts: 58 `### R-` records and 53 `CB:` lines, as stated. The record file is about 14,000 words and the issue log about 3,800. Both match the stated figures.

### 6. No accepted STEP-01 to STEP-06 artifact modified — satisfied

- `git diff 94512b6 HEAD --stat` ("Complete STEP-06" to HEAD) shows only these changes: the four `prod-w/proof-of-concept-*` files, the STEP-07 step file, the STEP-07 review records, and `research/mod-w-transferability/observations.md`.
- No `prod-w/` accepted artifact (`worked-examples.md`, `templates.md`, `methodology-guidance.md` and the rest) and no `mod-w/` product document was touched.
- `mod-w/roadmap.md` changed in the "Complete STEP-06" commit or earlier, before STEP-07 work began. It is not part of the STEP-07 diff.
- The working tree was clean at review start.

### 7. No schema, validator, lifecycle graph, state vocabulary, tooling, runtime integration or publication package — satisfied

- No such file exists in the diff.
- The `CB:` line and position numbers are described in the records as pilot practice and "not a format", with a note that they are not to be parsed.
- Findings D-1 and E-8/E-9 state "without a lifecycle graph or a state vocabulary" and that "no tool exists or was built".

### 8. MW-OBS-019 is proposed transferability evidence only — satisfied

- Status: **Proposed**. Disposition: "Awaiting Moderator disposition. Not blocking on STEP-07."
- It is classified `TRANSFERS_WITH_REINTERPRETATION` for one point and `NOT_YET_TESTED` for the points that depend on QA and Product Owner review.
- Its interpretation is deliberately limited.
- The only edit to the register outside the appended entry is that the "Future observations" placeholder was replaced by the entry (one line removed). The register's append-only rule is kept in substance.

## Blocking Findings

**None.**

## Non-Blocking Notes

- **QN-1 Wording of "Exercised" labels for scripted events.**
  - The trial §8 marks most scripted items "Exercised" (self-approval, authority gap, revalidation, commitment, independence declaration), with a strength column that says "scripted event" or "simulated".
  - The labels are honest, but a reader who skims only the Status column could read "Exercised" as demonstrated with real actors. Findings §3 (N-1 to N-3, N-9) corrects this.
  - Suggested handling for the final acceptance record: the standing statement the Moderator already planned (user applicability, human burden, real independence, actor-kind binding and real disagreement untested) covers it. No rework needed.

- **QN-2 Two imprecise citations.** EKR-17 in ISS-11 and CRC-62 in ISS-15 are, respectively, an ID not defined in the evidence model and a tangential rule. They do not change any finding, since the supporting rules (EKR-11, GCR-05) are correct. A later methodology correction pass can tidy them. They are not STEP-07 blockers.

- **QN-3 MW-OBS-019 count inconsistency.** Trial §11 (E-4) says "Two concrete observations are proposed", and findings §7 refers to MW-OBS-019 once. MW-OBS-019 itself and the Tech Lead review count three observations plus a routing note. The numbers do not change what the observation claims. A one-word alignment would remove the ambiguity.

- **QN-4 Burden figures are single-source.** The 12-minute timing, the 32-of-58 repetition count and the "four of nine card answers wrong" were not independently re-derived. They are stated as the Development Team's own AI-session figures with limits, and no finding relies on them for a human claim.

- **QN-5 Same-session verification (ISS-08).** Carry the Tech Lead's condition: no formal-check result in this pilot adds independent assurance beyond record-shape checking.

- **QN-6 Product Owner decision remains open.** Whether a simulated pilot is enough for STEP-07, or a later real-human pilot is needed before claiming AC-3 evidence beyond record-shape feasibility, remains for Product Owner sign-off (3c). QA does not decide it. QA's sampling supports the narrow reading only.

## Carried Forward for Final Acceptance (if any)

- The simulation boundary and the "untested" list: user applicability, human burden, real independence, actor-kind binding, real disagreement.
- ISS-08/RQ-16 and ISS-10/RQ-04 remain open and unresolved.
- MW-OBS-019 remains proposed.
- Product Owner sign-off (3c) and Moderator acceptance (4a) have not occurred. No final STEP-07 acceptance is recorded here.

MOD-W v5.0.1
