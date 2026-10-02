---
artifact:
  type: moderator-review
  from: MOD-W Moderator
  to:
    - Tech Lead
    - Development Team
    - QA
    - Product Owner
  date: 2026-10-02
  review_artifacts:
    - mod-w/reviews/QA-REVIEW-STEP-04.md
    - prod-w/rule-judgment-boundary.md
  review_status: QA_REVIEW_APPROVED_RETURNED_FOR_REVISION
---

# MOD-W Moderator Review: STEP-04 QA Review

**Reviewer role:** MOD-W Moderator
**Date:** 2026-10-02
**Reviewed artifact:** `mod-w/reviews/QA-REVIEW-STEP-04.md`
**Status:** QA review approved as a valid Phase 3b record. `prod-w/rule-judgment-boundary.md` v0.1 is **returned to the Tech Lead for a narrow revision**. STEP-04 is **not accepted**.

---

## Decision

The MOD-W Moderator agrees with the QA assessment and its recommendation: **return for revision, narrowly.**

This decision:

- accepts the QA review as the Phase 3b record for v0.1;
- returns the deliverable to the Tech Lead, who directs the Development Team's revision;
- does **not** accept the STEP-04 product artifact;
- does **not** waive any review.

Of the two paths QA offered (narrow revision, or accept QA4-01 to QA4-04 as declared soft spots), the Moderator selects the narrow revision. The soft-spot alternative is not adopted.

---

## Disposition of QA Findings

| QA finding | Subject | Moderator disposition |
| --- | --- | --- |
| QA4-01 | Root grants: multiplicity, establishing act, and interaction with CRC-62 | **Required** before acceptance |
| QA4-02 | Conflicted conferral: chain evaluation of CRC-64; revocation limb; DP-04 owner and trigger | **Required** before acceptance |
| QA4-03 | CRC-59 finding of invalid acceptance: required content; non-human AUTH-V bound; "invalidation" wording in CRC-04 | **Required** before acceptance |
| QA4-04 | Revocation cascade; PR-04 and GCR-08 reading; "assignment" terminology | **Required** before acceptance |
| QA4-05 | CRC-52, CRC-09, CRC-45 fail the agreement corollary as worded | Recommended in the same revision |
| QA4-06 | Derived and view dependencies missing from DR-01 and DR-04; B tag on CRC-18 and CRC-19; CRC-47 "surfaced" | Recommended in the same revision |
| QA4-07 | CRC-22 closed waivable list versus Section 11.4 and STEP-03 Section 9.4 | Recommended in the same revision |
| QA4-08 | CR versus RJC discriminator applied inconsistently | Recommended in the same revision |
| QA4-09 | CRC-36 and EKO-04 row lack the "where the record distinguishes" qualifier | Recommended in the same revision |
| QA4-10 | Section 6.3 Note column "none" versus pairing tables | Recommended in the same revision |
| QA4-11 | Level-A entries do not link forward to their UAD4 declaration | Recommended in the same revision |
| QA4-12 | Consequential reliance outside an acceptance; EKO-15 CR/RJC split | Recommended in the same revision |
| QA4-13 | Routing overlaps; DM-05 cross-reference; EKR-41 "Superseded" wording | Recommended in the same revision |
| QA4-14 | Wording near representation vocabulary | Recommended in the same revision |

"Recommended" items are expected to be addressed or answered with a stated reason. The Tech Lead may recommend that any of them not be changed; the Moderator decides.

---

## Constraints on the Revision

- The revision stays narrow. The classification table, boundary definitions, and catalog structure are not reopened except where a finding requires a change.
- Accepted STEP-01, STEP-02, and STEP-03 artifacts are not edited. If a finding (notably QA4-04, PR-04 and GCR-08) appears to be a **direct conflict** with an accepted artifact, it is routed to the Moderator and not resolved inside the artifact (`mod-w/step-04.md`, Out of Scope).
- Every new or changed choice about authority, independence, evidence standing, revalidation, or violation handling is declared under MW-ADAPT-001 in Section 14, with a proposed level.
- No representation, tooling, or state vocabulary is selected. DR, DM, and DP ownership is preserved.
- The revised artifact remains a Draft. The Development Team records no acceptance.

---

## Moderator-Visible Items

| QA item | Moderator disposition |
| --- | --- |
| Promotion of UAD4-13 to UAD4-15 to architecture decisions (TLR4-01, with QA weight from QA4-01 and QA4-04) | **Not decided here.** Remains deferred to final STEP-04 acceptance or a later architecture-maintenance decision, as recorded in `MODERATOR-REVIEW-STEP-04-TECH-LEAD.md`. The Tech Lead should state a recommendation in the revision package. |
| PR-04 and GCR-08 reading (QA4-04): reading or direct conflict | The Tech Lead assesses and reports. If a direct conflict, route to the Moderator. No disposition recorded here. |
| MW-ADAPT-001 evidence: QA sampling found unlisted choices that Tech Lead sampling did not | **Noted.** No observation is proposed or accepted here. The Moderator will decide separately whether to propose one after the revision cycle. |
| Pre-Tech Lead Moderator assessment count discrepancy (OBJ counts; 61 versus 64 rows) | **Noted.** No correction is recorded here. |
| Sequencing of Product Owner sign-off | Product Owner sign-off (3c) is **held** until the revised artifact is ready. It is not waived. |
| Re-review after revision | Default: targeted Tech Lead and QA re-sample of the changed areas (the required findings and any changed classifications), not a full re-review. The Tech Lead may recommend a wider scope if the revision changes more than the findings require. |

---

## Gate State After This Decision

| MOD-W point | Standing |
| --- | --- |
| 2b Development Team work product | Revision required (this decision) |
| 3a Tech Lead review | v0.1 review stands as a record of v0.1. Targeted re-review of the revision pending. |
| 3b QA | v0.1 review complete and approved. Targeted re-sample of the revision pending. |
| 3c Product Owner sign-off | Held. Pending the revised artifact. No waiver recorded. |
| 4a Moderator final acceptance | Pending. **Not recorded here.** |

---

## Conclusion

The QA review is approved. STEP-04 is returned to the Tech Lead for a narrow revision covering QA4-01 to QA4-04 as required, and QA4-05 to QA4-14 as recommended. No waiver is recorded and no acceptance is recorded.
