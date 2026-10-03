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
    - mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-04.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-FOLD-IN.md
    - mod-w/reviews/QA-REVIEW-STEP-04-REVISION.md
    - prod-w/rule-judgment-boundary.md
    - mod-w/architecture.md
  review_status: ACCEPTED_WITH_RECORDED_CONDITIONS_AND_WAIVERS
---

# MOD-W Moderator Record: STEP-04 Final Acceptance (4a)

**Reviewer role:** MOD-W Moderator
**Date:** 2026-10-03
**Decision:** **Accept with recorded conditions and waivers.** `prod-w/rule-judgment-boundary.md` v0.5 is accepted as the STEP-04 product artifact. Decision D10 in `mod-w/architecture.md` (v0.3) stands as Accepted.

This record states what the Moderator decided. The edits it lists were made by the assistant at the Moderator's direction. No Tech Lead, QA, or Product Owner review of those edits took place.

---

## 1. Decisions on the Product Owner conditions

The Product Owner recommended SIGNED_OFF_WITH_CONDITIONS (`PRODUCT-OWNER-SIGNOFF-STEP-04.md`). Conditions C-1 to C-3 are decided as follows.

| Condition                                  | Decision                                                                                                                                                                                                                                                                                                                                                                                                                              | Where recorded                                                                                                              |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **C-1** Stale sentence in Section 13.2     | Replace the clause with: "widening is a new conferral, narrowing is an act on the grant with a partial downstream cascade (CRC-63)." Checked against CRC-63 and the Section 10.2 Change row. It aligns the clause and adds no rule                                                                                                                                                                                                    | Artifact Section 13.2                                                                                                       |
| **C-2** CRC-64 and root grants             | **Option (ii).** CRC-64 is kept as written. The gap is named. DP-04 evidence is extended with proxy placement through the establishing act. Option (i) is not adopted. It is the route to take if the pilot shows such a proxy                                                                                                                                                                                                        | Artifact Section 10.6 (new bullet "Root grants are not flagged"), Section 10.2.3 (cross-reference), DP-04. D10 Consequences |
| **C-2** "Only from a root grantee" wording | Resolved to the wider reading in CRC-62. A later grant to the establishing identity is valid only if its conferrer holds a covering conferral scope and the conferrer's own authority does not derive, through non-root conferral links, from a grant the establishing identity conferred. The vacuous proviso is removed. The "one root grantee" sentence now says it holds where the establishing identity is the only root grantee | Artifact Section 10.2.2 item 6; Section 10.6 (no self-extension bullet); D10 Consequences                                   |
| **C-3(a)** Recovery                        | Recovery is by a new project. There is no break-glass, because one would be a way to mint a root (QA4-01). What carries into a new project is not defined here. The Product Owner's phrase "acceptances do not carry" is **not** adopted, because it would be a new rule that no one has reviewed                                                                                                                                     | Artifact Section 10.6 (no re-establishment bullet); D10 Consequences. Routed to STEP-06 (DM-07)                             |
| **C-3(b)** GC-OQ-10 and Product OQ-7       | D10 does not settle either. The removal rule narrows the space for an answer and does not give one. GC-OQ-10 remains open                                                                                                                                                                                                                                                                                                             | This record; artifact Section 10.6; D10 Consequences                                                                        |
| **C-3(c)** "Project"                       | Defined in the glossary list as the body of recorded items and acts governed by one establishing act and one authority chain. A second establishing act begins a different project. Boundary practice is DM-03 and DR-03. This definition is what stops "a new project" from being read as re-establishing roots inside the same records                                                                                              | Artifact Section 4.11                                                                                                       |

**The Product Owner's claims, checked against the source.** The stale sentence (Section 13.2) was confirmed. The vacuous proviso in item 6 was confirmed, since a root grantee's authority has no non-root links. A search of `rule-judgment-boundary.md` and `architecture.md` found no other statement of the revoke-plus-confer model of narrowing.

## 2. Waiver

The Moderator **explicitly waives**, before final acceptance and under `mod-w/step-04.md` (Phase 4a and its final-acceptance check):

- the Tech Lead targeted re-review, and
- the QA targeted re-sample,

of the v0.3 changes, of decision D10, and of the v0.4 and v0.5 edits made under this record.

The fold-in record (`MODERATOR-REVIEW-STEP-04-FOLD-IN.md`) recorded overrides and stated that they were not a waiver of final acceptance. That statement stands. This section is the explicit waiver that the final-acceptance check names. The overrides recorded there stand as recorded.

**Exposure left by the waiver.**

- The v0.3 text changes were never reviewed by the Tech Lead or by QA. These are CRC-45, the "root grant has no conferrer" wording in CRC-61, CRC-62 and CRC-64, the Section 10.6 additions, and the HJC-25 pairing. D10 as a promotion, and the v0.4 and v0.5 edits, were not reviewed either.
- The Product Owner found the stale sentence and the vacuous proviso. That is evidence that a re-sample would probably have found defects.
- Sections 15 and 16 (traceability tables) were not read by the Product Owner. The quotations of PR-04, PR-27, GCR-05, GCR-08, GCR-47 and STEP-03 Sections 6.3 and 9.4 were not checked against source. The 61-row classification was not recounted. QA's v0.2 re-sample is the last check of the row counts.
- No reviewer is independent of the Development Team's producing configuration. Every review was by a Claude-family model, and under PR-27 and PR-28 same-vendor review is not independent corroboration. The Product Owner said this in the sign-off.
- D10 became Accepted before STEP-04 acceptance, outside the Tech Lead's sequence. A return for revision of the authority sections would have to reopen it.

## 3. Readings accepted as Moderator-visible

Both are accepted as **readings, not conflicts**.

1. **PR-04 and GCR-08 against conferral** (Section 3.3, UAD4-13, D10). A conferral under CRC-61 is not delegation and not class-confers-class. The Product Owner's sign-off on the authority sections depends on this staying a reading. If a pilot or a later step shows a direct conflict, UAD4-13 and D10 return to the Moderator for disposition, and the sign-off on authority lapses with them.
2. **Challenger resolution (UAD4-31) against GCR-05 and STEP-03 Section 6.3** (QA5-04). UAD4-31 puts challenger resolution of a challenge against a set member on the favorable list, so a producer of a set member cannot validly resolve it. This is a conservative reading and is declared at level A. It is listed in Section 3.3 of the artifact from v0.5, and this record is the Moderator's acceptance of it as a reading. The small-team consequence (a producer who challenged its own item cannot close it, which makes an authority gap) is routed to STEP-06 under DM-04.

## 4. Routing of carry-forward items

Items not marked Closed remain open. Each has an owner.

| Item       | Owner                                           | What is owed                                                                                                                                                                                                                                                                                            |
| ---------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **F-1**    | STEP-06, before any pilot establishes a project | DM-03 (establishment practice: every needed grant, including conferral scope, in the establishing act; at least two root grantees where a second person exists), DM-02, DM-07, and **DM-04** (independence practice for teams of one or two). DM-04 is a hard dependency for Acceptance Criterion 3     |
| **F-2**    | STEP-07                                         | Pilot evidence: two AI identities from one model and one operator acting as independent challenger and verifier; proxy conferral at each link; **proxy placement through the establishing act**; two co-roots revoking each other; whether a team of one or two can pass any gate validly, and the cost |
| **F-3**    | STEP-06 and the Moderator                       | Carry GC-OQ-10 and Product OQ-7 as open. D10 is not an answer                                                                                                                                                                                                                                           |
| **F-4**    | STEP-07                                         | Extend DP-01 to measure requirement volume and closure effort from false CRC-59 findings, and the volume of always-firing flags in small teams                                                                                                                                                          |
| **F-5**    | STEP-05, STEP-07, publication                   | STEP-05 answers DR-07 (authentication of actor kind). Any conformance definition requires B-eligible rules to be evaluated at or before reliance. No claim may say the protocol alone guarantees that a human acted                                                                                     |
| **F-6**    | STEP-07                                         | Check whether any consequential commitment falls outside both a gate acceptance and a decision record (RJ-OQ-12)                                                                                                                                                                                        |
| **QA5-01** | Closed                                          | Folded into v0.3. C-1 removed the last remnant                                                                                                                                                                                                                                                          |
| **QA5-02** | Closed                                          | Decided in v0.3 and C-2. The residue is DP-04 and F-2                                                                                                                                                                                                                                                   |
| **QA5-03** | STEP-05                                         | Define the record element that "evidence-only form" refers to. CRC-45 is unresolved where none exists                                                                                                                                                                                                   |
| **QA5-04** | Closed (v0.5); practice to STEP-06              | Closed in v0.5 as text: the reading is in Section 3.3, the UAD4-29 clause is added, and the consequence is in Section 10.6. Accepted as a reading (Section 3 above). The small-team practice goes to STEP-06 (DM-04)                                                                                    |
| **QA5-05** | Closed (v0.5); STEP-07 for pilot                | Closed in v0.5: the non-human CRC-59 decidability bound is anchored in the catalog classification (CR, or the validity-facet part of an RJC condition), and the scope qualifier is attributed to CRC-02. Adoption and effect of non-human verification stay with STEP-07 (DP-06)                        |
| **QA5-06** | Closed (v0.5)                                   | Closed in v0.5: links added to CRC-02, CRC-18 and CRC-39, and the gate-required case noted on CRC-39. The CRC-39 handling cell is unchanged, so the handling profiles are unchanged                                                                                                                     |
| **QA5-07** | STEP-06; Moderator and Tech Lead                | DM-09 was added in v0.5 for RJ-OQ-12, owned by STEP-06. The proposed levels of UAD4-26 and UAD4-32 are not confirmed here. They remain proposals for Tech Lead and Moderator confirmation                                                                                                               |
| **QA5-08** | Closed (v0.5)                                   | Closed in v0.5: designation-presence paragraph added to Section 5.1                                                                                                                                                                                                                                     |

Artifact text fixes for QA5-04 to QA5-08 were made in v0.5 at the Moderator's direction (artifact Section 17.8). QA5-03 stays with STEP-05, and the proposed levels of UAD4-26 and UAD4-32 stay unconfirmed.

## 5. Edits made at the Moderator's direction

| File                                              | Change                                                                                                                                                                                                                                                                                                  |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `prod-w/rule-judgment-boundary.md` (v0.3 to v0.4) | C-1 wording in Section 13.2. Section 10.2.2 item 6, Section 10.2.3 cross-reference, Section 10.6 (no re-establishment, no self-extension, two new bullets). DP-04 evidence. Section 4.11 definition of "project". Front matter, status line, Section 2.3 gate table, Section 17.1 row, new Section 17.7 |
| `mod-w/architecture.md` (v0.2 to v0.3)            | D10 Consequences extended (recovery, root grants not flagged, GC-OQ-10 and Product OQ-7 not settled). D10 decision text unchanged. Change log row                                                                                                                                                       |

No catalog entry, classification row, or UAD4 was added or reclassified. The v0.5 text fixes (QA5-04 to QA5-08; artifact Section 17.8) were made later the same day under the same direction: a new Moderator-visible row in Section 3.3, a Section 10.6 bullet, the CRC-59 decidability anchor and its echoes, UAD4 links on CRC-02, CRC-18 and CRC-39, DM-09, and one Section 5.1 paragraph. They add no catalog entry, row, UAD4 or level. The counts in Sections 1.5, 13.1 and 14.6 are unchanged (64 entries; 61 rows; 32 declared, 21 A, 10 M, 1 L); the DM register now has nine items.

## 6. Not done and not recorded

- Tech Lead re-review and QA re-sample of the v0.3 changes, D10, and the v0.4 and v0.5 edits (waived above).
- No edit to the Product Owner record, to any research register, or to `mod-w/step-04.md`, `mod-w/roadmap.md`, `mod-w/domain-language.md`, or any other review record.
- MW-ADAPT-001 and MW-OBS-016 follow-up evidence: not addressed here. The Development Team proposes no observation (Section 14.6), and the Moderator decides separately.
- Glossary disposition of the terms in Section 4.11 (including "project") into `mod-w/domain-language.md`: not done.
- No representation, tooling, or schema is selected by anything in this record.

## Gate state

| MOD-W point                      | Standing                                                                                                   |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| 2b Development Team work product | v0.5 produced at Moderator direction                                                                       |
| 3a Tech Lead review              | v0.2 re-review approved. v0.3 changes, D10, and v0.4 and v0.5 edits not reviewed. **Waived** (Section 2)   |
| 3b QA                            | v0.2 re-sample approved. v0.3 changes, D10, and v0.4 and v0.5 edits not re-sampled. **Waived** (Section 2) |
| 3c Product Owner sign-off        | Performed. SIGNED_OFF_WITH_CONDITIONS. Conditions C-1 to C-3 applied in v0.4                               |
| 4a Moderator final acceptance    | **Accepted with recorded conditions and waivers**, by this record                                          |

MOD-W v5.0.1
