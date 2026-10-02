---
artifact:
  type: moderator-review
  from: MOD-W Moderator
  to:
    - Tech Lead
    - Development Team
    - QA
    - Product Owner
  date: 2026-10-03
  review_artifacts:
    - mod-w/reviews/QA-REVIEW-STEP-04-REVISION.md
    - prod-w/rule-judgment-boundary.md
    - mod-w/architecture.md
  review_status: QA_RE_SAMPLE_APPROVED_FOLD_IN_AND_D10_APPROVED_FOR_PRODUCT_OWNER_REVIEW
---

# MOD-W Moderator Record: STEP-04 Fold-In and Architecture Promotion

**Reviewer role:** MOD-W Moderator
**Date:** 2026-10-03
**Status:** QA re-sample approved. QA5-01 to QA5-03 folded into `prod-w/rule-judgment-boundary.md` (v0.3) and approved. UAD4-13 to UAD4-15 promoted to architecture decision D10 and approved. v0.3 released for Product Owner review. STEP-04 is **not accepted**.

---

## Decisions

| # | Decision |
| --- | --- |
| 1 | The QA re-sample (`QA-REVIEW-STEP-04-REVISION.md`) is **approved** as the Phase 3b record for v0.2. Its recommendation is to approve for Product Owner sign-off, with QA5-01 to QA5-08 non-blocking. |
| 2 | **Fold in** QA5-01, QA5-02, and QA5-03 before Product Owner sign-off. QA5-04 to QA5-08 are not folded in and remain non-blocking. |
| 3 | **Promote** UAD4-13, UAD4-14, and UAD4-15 to an architecture decision, with the revised content of UAD4-27, UAD4-28, and UAD4-30 and the QA5-02 consequences carried along. Recorded as **D10** in `mod-w/architecture.md` (v0.2). |
| 4 | The usual edit flow and approvals were **overridden** at the Moderator's direction. The changes below were made without a Development Team revision cycle, a Tech Lead re-review, or a QA re-sample. |
| 5 | The Moderator **approves the edits**: the v0.3 changes to `prod-w/rule-judgment-boundary.md` and decision D10 in `mod-w/architecture.md`. D10 is Accepted on this approval. |
| 6 | v0.3 is **released for Product Owner review (3c)**. |

## What was changed

**`prod-w/rule-judgment-boundary.md` (v0.2 to v0.3).**

- **QA5-01.** Narrowing is an act on the grant with a partial downstream cascade, not a revocation plus a conferral (CRC-63, Section 10.2 Change row, 10.2.4). HJC-25 now pairs CRC-63.
- **QA5-02.**
  - A root grant has no conferrer for CRC-62 and CRC-64. CRC-62's cycle clause is stated as a cycle.
  - A root grantee may confer a later grant on the establishing identity if its chain does not derive from the establishing identity's own conferrals (Section 10.2.2 item 6).
  - Section 10.6 names the consequences: no re-establishment path, removal runs one way, no self-extension through proxies.
  - UAD4-27 and UAD4-30 are extended.
- **QA5-03.** CRC-45 checks for a recorded observed-fact designation or evidence-only basis statement, and is unresolved where neither exists. UAD4-32 and the HJC-18 pairing are aligned.
- Version, status, Section 2.3 gate table, Sections 14.3, 14.5, 17.1, 17.5 (Moderator-visible item 2), and a new Section 17.6 are updated.
- No catalog entry was added or removed, no row was reclassified, and no UAD4 was added. 32 declared, 21 A, 10 M, 1 L.

**`mod-w/architecture.md` (v0.1 to v0.2).** Decision D10 added. The decision index, the FR-1 and FR-4 mapping rows, and the change log are updated. D1 to D9 are unchanged.

## Choice made in QA5-02

QA asked for a statement of whether the establishing identity counts as the conferrer of root grants. The text adopts **no conferrer**. A root grantee with a covering conferral scope can then confer a later grant on the establishing identity, provided its own chain does not derive from the establishing identity's conferrals. This keeps the first-act and root-grantee limits as friction and not as a security boundary, because the establishing identity can already place anything in the establishing act. Challenge of this reading remains open at Product Owner sign-off.

## Overrides recorded

The Moderator overrode the following at the Moderator's own direction. These are Moderator acts, recorded as overrides and not as reviews that took place.

| Override | Effect |
| --- | --- |
| Development Team revision cycle for QA5-01 to QA5-03 | Edits made directly on Moderator direction |
| Tech Lead targeted re-review of the v0.3 changes and of D10 | Not performed. Overridden |
| QA targeted re-sample of the v0.3 changes and of D10 | Not performed. Overridden |
| Architecture promotion after STEP-04 acceptance (the Tech Lead brief's sequence) | D10 recorded before acceptance of STEP-04 |

These overrides apply to the v0.3 changes and D10 only. They are not a waiver of Product Owner sign-off or of final acceptance.

## Not done and not recorded

- Tech Lead re-review and QA re-sample of the v0.3 changes and of D10 (overridden above).
- QA5-04 (UAD4-31 reading and CRC-59 producers), QA5-05, QA5-06, QA5-07, and QA5-08 are not addressed.
- No Product Owner sign-off. No waiver of 3c is recorded.
- **No final acceptance of STEP-04 is recorded here.**
- The PR-04 / GCR-08 reading remains Moderator-visible and is carried into D10 as such. This record does not decide it.
- MW-ADAPT-001 and MW-OBS-016 follow-up evidence: not addressed.

## Gate state

| MOD-W point | Standing |
| --- | --- |
| 2b Development Team work product | v0.3 produced at Moderator direction |
| 3a Tech Lead review | v0.2 re-review approved. v0.3 changes not separately reviewed (overridden) |
| 3b QA | v0.2 re-sample approved by the Moderator. v0.3 changes not separately re-sampled (overridden) |
| 3c Product Owner sign-off | Released for review. Not performed. No waiver recorded |
| 4a Moderator final acceptance | Pending. **Not recorded here.** |
