---
artifact:
  type: qa-review
  from: QA
  to:
    - MOD-W Moderator
    - Tech Lead
    - Development Team
    - Product Owner
  date: 2026-10-03
  review_artifacts:
    - prod-w/rule-judgment-boundary.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-TECH-LEAD-REVISION.md
    - mod-w/reviews/TECH-LEAD-REVIEW-STEP-04-REVISION.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-REVISION.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-REVISION-BRIEF.md
    - mod-w/reviews/TECH-LEAD-STEP-04-REVISION-BRIEF.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-QA.md
    - mod-w/reviews/QA-REVIEW-STEP-04.md
  review_status: APPROVE_FOR_PRODUCT_OWNER_SIGN_OFF_WITH_NON_BLOCKING_FINDINGS
---

# QA Review: STEP-04 v0.2 Targeted Re-Sample (Phase 3b)

**Reviewer role:** QA (MOD-W v5.0.1), read-only
**Date:** 2026-10-03
**Review target:** `prod-w/rule-judgment-boundary.md` v0.2 (Draft), changed areas only
**Standing:** Targeted Phase 3b re-sample. This is a review, not an acceptance. Product Owner sign-off (3c) and Moderator final acceptance (4a) are not performed or recorded here. No product artifact was edited. Line numbers refer to v0.2 as read.

---

## Recommendation

**Approve for Product Owner sign-off.**

- **QA4-01 to QA4-04 are resolved.** Each original failure scenario is closed by the v0.2 text, and each choice is declared at level A and linked from the applying entry.
- **QA4-05 to QA4-14 are addressed.** Four are fully addressed (QA4-06, QA4-09, QA4-13, QA4-14). Six are addressed with small residues (QA4-05, QA4-07, QA4-08, QA4-10, QA4-11, QA4-12), recorded below as non-blocking.
- **No required finding.** I found eight Low findings (QA5-01 to QA5-08). None is a bypass of the self-approval or human-only rules, none changes a classification, and none reopens structure.
- **The revision stayed narrow.** The 61-row classification, the boundary definitions, and the catalog structure were not reopened beyond the approved localized corrections. Evidence is in "Scope discipline" below.
- **I do not recommend a wider re-review.**

**Sequencing.** QA5-01 to QA5-03 are one-sentence clarifications in the authority text that the Moderator asked to keep sampling. QA does not require them. If the Moderator wants any of them made, they should be made before Product Owner sign-off, because a text change after sign-off needs re-confirmation. If the Moderator prefers to sign off on the text as it stands, they can be carried as named soft spots in Section 10.6.

---

## What QA4-01 to QA4-04 now do

| Finding | v0.1 failure | v0.2 result | Status |
| --- | --- | --- | --- |
| **QA4-01** Root minting; CRC-62 collision | A later "establishing act" could mint a root. A team of one was either impossible or exempted without bound | CRC-61 (line 509), 10.2.2, UAD4-27: exactly one establishing act, preceding every other recorded act. Roots are only the grants it records. A later act marked establishing or root is not a root, and its grants are ordinary conferrals. CRC-62 (line 510) exempts only the establishing-act root-grantee case and applies in full to later grants, including a later self-grant by the establishing identity, a role position or collective including it, or a cycle. Scenario A: P holds no AUTH-G or conferral scope, so P's grants fail CRC-61. Scenario B: the founder is a root grantee in the establishing act | **Resolved** (residue: QA5-02) |
| **QA4-02** One-hop laundering; revocation limb; DP-04 | CRC-64 tested only the immediate conferrer and only revocation against an open challenge | CRC-64 (line 512), 10.2.3, UAD4-28: every conferrer along the CRC-61 chain relied on. Revocation or narrowing of a grant held by an actor with standing to challenge, whether or not a challenge is open, and including by cascade. Handling stays F/E. DP-04 (line 653) names evidence, trigger, and STEP-07 as owner, with Tech Lead review as a review need and not a step ownership | **Resolved** (residue: QA5-02, QA5-05) |
| **QA4-03** Cheap finding path | A finding needed no rule or basis, and a non-human AUTH-V finding was unbounded | CRC-59 (line 502), 9.4.3, 9.4.5, 10.3.1, 10.3.4, CRC-15 (line 438), BDR-13, UAD4-29: a finding names the rule(s) violated, the evaluation point, and the record elements examined. A bare assertion is not a finding and does not trigger TRG-6. It is typed by the authority the recorder holds. A non-human finding counts only for rules decidable from the record. CRC-04 (line 417) separates STEP-02 "invalidation" from a finding of invalid acceptance | **Resolved** (residue: QA5-05) |
| **QA4-04** Cascade; PR-04/GCR-08; "assignment" | Two readings of what happens to a revoked conferrer's appointees. PR-04 and GCR-08 not reconciled. One word for two relations | CRC-63 (line 511), 10.2.4, UAD4-30: downstream grants fall prospectively with the chain, acts performed under an effective chain stand (GCR-47), renunciation cascades. Section 3.3 (lines 183-185) adds the PR-04/GCR-08 reading as a Moderator-visible reading tension, not a direct conflict. Work assignment and grant-bearing role-position appointment are separate terms (3.3, 10.2.5, CRC-62, CRC-11). I checked that the GCR-08 description of assignment is faithful to the accepted text | **Resolved** (residue: QA5-01, QA5-02) |

---

## Disposition of QA4-05 to QA4-14

| Finding | Result | Notes |
| --- | --- | --- |
| **QA4-05** Agreement corollary (CRC-52, CRC-09, CRC-45) | CRC-52 and CRC-09 resolved. CRC-45 partly | CRC-52 (line 490) now checks that the closure names each open reason with a disposition. Adequacy stays HJC-16. CRC-09 (line 427) reads direction from a closed list, and an unlisted or unnamed closure kind is unresolved and escalation-eligible (UAD4-31, level A). CRC-45 (line 483) now checks the recorded evaluative designation and the observed-fact or evidence-only form, but "evidence-only form" is not a defined record element (QA5-03) |
| **QA4-06** Derived or view dependencies | Resolved | DR-04 now lists CRC-18, CRC-19, CRC-47, and CRC-52 as needing it, and DR-01 lists CRC-19 (lines 622, 625). B on CRC-18 and CRC-19 is conditional (5.4, 13.1, UAD4-23). CRC-47 is a visibility requirement on any representation (line 485) |
| **QA4-07** CRC-22 waivable list | Resolved | CRC-22 (line 445), 9.6, UAD4-26 use the STEP-03 Section 9.4 boundary. I confirmed in STEP-03 that Section 9.4 item 3 makes a stricter response rule waivable. CRC-39 handling still shows only F (QA5-06) |
| **QA4-08** CR versus RJC | Addressed by explanation, as the brief directed | Sections 4.5, 5.1, and Q5 state the discriminator. GCO-12 and GCO-20 are reconciled (line 337). No row changed. One residue on designation-presence rows (QA5-08) |
| **QA4-09** CRC-36 and EKO-04 qualifier | Resolved | Carried in CRC-36 (line 469), the EKO-04 row (line 543), 10.5, 12.1, INV-11, and the PR-20 row |
| **QA4-10** Note column | Addressed | The named rows now carry their HJC and DR. The column is defined as paired references plus short notes, with Section 8.2 as the complete pairing. A few notes remain partial (GCO-05, GCO-06, GCO-17), which fits that definition |
| **QA4-11** Forward links | Mostly resolved | CRC-15, 35 to 39, 45, 47, 52 to 54, 56, 59 to 64, and others now link. Three entries apply a declared choice without naming it (QA5-06) |
| **QA4-12** Consequential reliance outside acceptance | Resolved by narrowing | CRC-19 (line 442) and CRC-47 are narrowed. The 13.7 profile no longer claims a non-acceptance rule. The EKO-15 row splits CR and RJC parts (line 554). RJ-OQ-12 routes the rest. See QA5-07 on the route |
| **QA4-13** Routing | Resolved | RJ-OQ-03a/03b split. RJ-OQ-09 owned by STEP-07. RJ-OQ-10 aligned with BDR-16. Section 11.3 now routes source comparability to DR-06. EKR-41 reads "restated and enforced through" (lines 612, 1565) |
| **QA4-14** Wording near representation | Resolved | "Successive recorded states" replaced (line 371). BDR-11 and 4.10 cover the outcome set. B rephrased as preventing reliance (lines 399, 778). My grep of v0.2 for the stale wordings found only the negated and upstream-title uses the producer reported |

---

## Declarations sampled

| Declaration | Applying entries | Result |
| --- | --- | --- |
| **UAD4-13** (grants, conferral scope, PR-04/GCR-08 reading, terms) | CRC-60 to CRC-62, Section 3.3, 10.2.1, 15.1 | Consistent. The reading is explicit and Moderator-visible. See the Moderator-visible list |
| **UAD4-14** (self-conferral; conflicted conferral) | CRC-62, CRC-64 | Consistent with CRC-62 and UAD4-27 and UAD4-28 |
| **UAD4-15** (effect on recording; revocation) | CRC-63, CRC-60 | Consistent. The cascade is delegated to UAD4-30. CRC-02, where the invalidity lands, does not name it (QA5-06) |
| **UAD4-27** (one establishing act) | CRC-61, CRC-62, 10.2.2, 10.5, 10.6, DR-03, DM-03, HJC-22 | Closes QA4-01. Residue in QA5-02 |
| **UAD4-28** (whole chain; challenger standing) | CRC-64, 10.2.3, DP-04, HJC-23 | Closes QA4-02. Residue in QA5-02, QA5-05 |
| **UAD4-29** (finding content; non-human bound) | CRC-59, CRC-15, CRC-04, 9.4.3, 9.4.5, 10.3.1, BDR-13 | Closes QA4-03. Residue in QA5-04, QA5-05 |
| **UAD4-30** (cascade) | CRC-61, CRC-63, 10.2.4 | Closes QA4-04. Residue in QA5-01, QA5-02 |
| **UAD4-31** (closed direction list) | CRC-09 | Reproducible as written. See QA5-04 |
| **UAD4-32** (record forms for CRC-52, CRC-45) | CRC-52, CRC-45 | CRC-52 clean. CRC-45 see QA5-03 |

**New routing and ownership items.**

- **DM-08** (line 644) gives STEP-06 the guidance-owned part of finding content, and DR-09 keeps recording and attribution with STEP-05. Ownership is clean. I found no representation content in DM-08.
- **RJ-OQ-12** (line 1343) adds no rule, which matches the brief. It names STEP-06 as owner but has no DM item (QA5-07).

---

## Findings

All are **Low** and **non-blocking**. Most severe first.

### QA5-01 - Narrowing is modeled two ways, and the narrowing cascade depends on a judgment it does not pair

**Location:** CRC-63 (line 511), CRC-61 (line 509), 10.2 "Change" row (line 952), 10.2.4 (lines 993-1003), HJC-25 (line 697), DR-08

**Issue.** CRC-63, CRC-61, and 10.2.4 treat narrowing as an act on a grant, with downstream grants falling "to the extent it no longer covers what they confer." The unchanged v0.1 "Change" row says narrowing is "a revocation of the wider grant and a conferral of the narrower." Under that second model, every grant whose chain passes through the revoked wider grant falls entirely, even where the replacement grant still covers it.

Separately, "to the extent it no longer covers" needs scope containment. Where scopes are stated by description, containment is HJC-25 judgment. HJC-25 pairs CRC-02, CRC-60, and CRC-61, but not CRC-63.

**Failure scenario.** H narrows R's grant from scope S1+S2 to S1. R had conferred a grant on T within S1. Under CRC-63's wording T's grant survives. Under the Change row, T's grant falls and needs re-conferral. Two implementers disagree on whether T's next acceptance is valid.

**Suggested direction.** Align the Change row with CRC-63 (narrowing is an in-place act with a partial cascade, or say it is not). Add CRC-63 to the HJC-25 pairing and say the extent of a cascade for a described scope is not decided by the check. No rule change.

### QA5-02 - The establishing identity's role in "conferrer" and "chain" clauses is unspecified, and two consequences of the root and cascade choices are not named

**Location:** CRC-62 (line 510), CRC-64 (line 512), CRC-63 (line 511), 10.2.2 item 4 (line 974), 10.6 (lines 1085-1087), UAD4-27, UAD4-30, DP-04

**Issue (a), wording.** CRC-61 defines a root grant as one that is not "conferred." CRC-62 invalidates a grant "where its chain returns to the conferrer." CRC-64 flags where "any conferrer along the CRC-61 chain... up to the root" is a producer. The text does not say whether the establishing identity counts as the conferrer of root grants for either clause. Read literally, "chain returns to the conferrer" is satisfied by any non-root conferral, because every conferrer's own authorizing grant is in its chain. The intended meaning is clearly a cycle (10.2.2 item 4, 10.5). Different evaluators get different answers on the same record: whether a root co-grantee may confer a new grant on the establishing identity (CRC-62), and whether a founder who produced the set makes every acceptance by a root grantee flaggable (CRC-64).

**Issue (b), consequences not named.** Together, the single root (UAD4-27) and the cascade (UAD4-30) have three consequences that 10.6 does not state. 10.6 says a conferrer who leaves "strands its appointees until they are re-conferred."

1. **No re-establishment path.** If every root grant is revoked or renounced, no valid chain can exist again. A second establishing act is excluded, and re-conferral needs a holder with a valid chain to a root. For a project with one root grantee this is terminal. The establishing identity's renunciation also takes down any successor it had conferred.
2. **Removal runs one way.** CRC-63 lets any human whose conferral scope covers the grant revoke it, with no requirement that the revoker be in the grant's chain. A descendant can revoke an ancestor only at the price of its own chain falling with it. A covering peer can remove a whole subtree. F/E fires only for a revoker who is a producer (CRC-64).
3. **No self-extension, even through proxies.** If every conferral scope in the project derives from the establishing identity, any later grant to that identity may count as a cycle under CRC-62, depending on (a).

None of these is a bypass. 10.6 names the first-act rule and the root-grantee limit as friction, which covers part of (3). The terminal case and the removal direction bear on the Moderator's pending decision on promoting UAD4-13 to UAD4-15 to architecture, because promotion would carry them.

**Suggested direction.** State that root grants have no conferrer for CRC-62 and CRC-64, or state the opposite, and make "chain returns" say "cycle through the grantee." Add the three consequences to 10.6. DM-03 and DM-07 can carry practice. No new rule is needed.

### QA5-03 - CRC-45 still checks a form that is not a defined record element

**Location:** CRC-45 (line 483), UAD4-32 (line 1427), EKR-28 (`prod-w/evidence-knowledge-model.md` line 648), Section 4.3

**Issue.** CRC-45 now checks the evaluative designation and "whether the record presents the claim under an observed-fact or evidence-only form." EKR-28 says "not established by evidence or inference alone and is not presented as observed fact." STEP-02 defines no recorded "evidence-only form." Whether a claim that cites evidence items is presented as "established by evidence alone" remains an interpretation. The agreement corollary is therefore not fully met. The handling is N (report presence or absence only), which bounds the harm.

**Failure scenario.** Evaluators A and B read a claim with a basis of three evidence items and no inference. A says it is recorded as established by evidence alone. B says it is only supported by evidence. They get different presence results.

**Suggested direction.** Name the record element (for example, a recorded basis type that states "established by evidence alone"), or say the second limb is unresolved where no such element exists. This text follows the brief's wording, so this is an inherited gap and not a drafting departure.

### QA5-04 - UAD4-31 resolves a reading between GCR-05 and STEP-03 that Section 3.3 does not list, and UAD4-29 omits a related inference

**Location:** CRC-09 (line 427), UAD4-31 (line 1426), Section 3.3, Section 10.6, UAD4-29, STEP-03 Section 6.3 (`gate-challenge-revalidation-semantics.md` line 473)

**Issue (a).** UAD4-31 puts challenger resolution on the favorable list, so a producer of any set member cannot validly resolve a challenge against a member. STEP-03 Section 6.3 says challenger resolution is "valid because it is the challenger's own challenge." GCR-05 bars a producer from "closure of a challenge in the set's favor." Reading the two together as UAD4-31 does is defensible and conservative. It is declared at level A. But it is exactly the kind of reading Section 3.3 exists to list. A producer who challenged their own item (GCR-24 permits that) cannot close it, so for a team of one the matter becomes an authority gap (CRC-32). 10.6 and DM-04 do not mention that consequence.

**Issue (b).** CRC-09 now lists "a finding under CRC-59" among the unrestricted conservative acts, so a producer of the set may record one. That follows GCR-05's "invalidation" by extension. UAD4-29 and UAD4-07 do not state it.

**Suggested direction.** Add the GCR-05 and STEP-03 Section 6.3 reading to Section 3.3 (a reading, not a conflict, in my assessment). Add the small-team consequence to 10.6. Add one clause to UAD4-29 on producers recording findings.

### QA5-05 - "Decidable from the record" in the CRC-59 bound has no designating authority, and the standing wording is not quite CRC-26's

**Location:** CRC-59 (line 502), CRC-15 (line 438), HJC-24 (line 696), Section 10.2.3 (line 987), CRC-26 (line 454), GCR-24

**Issue (a).** For a verification, CRC-15 (b) has the gate definition designate each criterion as decidable. For a non-human finding under CRC-59, "each rule asserted violated is decidable from the record" borrows the bound without that designation. The asserted rules are protocol rules, not gate criteria. HJC-24 says the gate definer records the designation, which does not fit. The reference should be the catalog's own classification (CR rules and the validity-facet parts of RJC rules) or a recorded designation. As written, a non-human finding's TRG-6 effect rests on an unrecorded decidability judgment. Challenge is available and TRG-6 is not suspended (9.4.3), so this is bounded and declared as a cost in 10.6.

**Issue (b).** 10.2.3 says standing to challenge is "the standing CRC-26 gives: an actor holding AUTH-A covering the target's scope." CRC-26 and GCR-24 do not mention scope, and GCR-24 says raising is "not restricted beyond AUTH-A." The scope qualifier is consistent with CRC-02, but it is attributed to CRC-26. It affects how widely CRC-64's revocation limb fires.

**Suggested direction.** For (a), tie decidability to the catalog classification, or add an HJC-24 exerciser for rules asserted violated. For (b), attribute the scope qualifier to CRC-02 and PR-02, or drop it.

### QA5-06 - A few forward links and one handling cell are missing

**Location:** CRC-02 (line 415), CRC-18 (line 441), CRC-39 (line 472), Section 6.1 (line 390), Section 16 AC4-21, Section 17.5 forward-link row (line 1840)

**Issue.** Section 6.1 and Section 17.5 say every entry that applies a declared choice names it. Three do not:

- **CRC-02** is where an act under a fallen or revoked grant is invalidated (CRC-63, 10.2.4, 9.4.2), but lists no UAD4-15 or UAD4-30. CRC-02 reads "a well-formed grant." The link to CRC-61 validity is carried only by 9.4.2 ("Grant, invalid: acts under it fail CRC-02").
- **CRC-18** applies UAD4-21 (earlier refusals read as recorded attempts) and UAD4-26 (stricter response requirements waivable) without listing either.
- **CRC-39** applies UAD4-26 for gate-required configuration facets (CRC-22, 9.6). Its handling shows only F, while 11.4 shows I, X for the gate-required case.

**Suggested direction.** Add the links, and either add I, X (gate-required case) to CRC-39 or note it. This also corrects the overstatement in AC4-21 and Section 17.5.

### QA5-07 - RJ-OQ-12 names an owner with no register item, and two level proposals look low

**Location:** RJ-OQ-12 (line 1343), Section 6.6, UAD4-32 (line 1427), UAD4-26 (line 1421), Section 14.2 level scale (line 1392)

**Issue.** RJ-OQ-12 routes to STEP-06 "(practice)," but no DM item carries it. Every other STEP-06 route has a DM item. Also, Section 14.2 defines level A as touching "what counts as checkable ... or violation handling." UAD4-32 fixes which record form CRC-52 and CRC-45 check, and UAD4-26 sets which requirements are waivable. Both are proposed M. UAD4-31, a similar choice, is A. The Development Team cannot classify its own levels (14.1), so this is for the Tech Lead and Moderator to confirm.

**Suggested direction.** Add a DM item for RJ-OQ-12 or say the route is to the Moderator with no step owner. Confirm or raise the two levels.

### QA5-08 - Residue on the revised CR/RJC discriminator for designation-presence rows

**Location:** Section 5.1 (lines 331-337), Q5 (line 349), Section 4.2 (line 210), Section 6.3 rows EKO-09, EKO-14

**Issue.** The revised discriminator lists "designation" among content-bearing records of a determination (RJC). Section 4.2 lists "that a proposition carries validation criteria" as a recorded designation. EKO-09 (a hypothesis carries recorded criteria) is CR. EKO-14 (an item has a materiality designation or rationale) is RJC. Both check the presence of a designation. A reviewer applying Q5 gets different answers. Handling does not differ between CR and RJC, and the classification is the conservative-safe side either way, so this is a reproducibility point only. The brief directed an explanatory fix and no reclassification.

**Suggested direction.** One sentence in 5.1: why EKO-09 (a criteria element of the item) is CR while EKO-14 (a designation with a rationale on a cited item) is RJC. Or accept as is.

---

## Scope discipline

I compared the 61 rows of Section 6.3 between v0.1 (commit 8436bb9) and v0.2 (commit be78ea2) on four columns: ID, disposition, entry, and handling. All 61 are identical. Condition text and notes changed on some rows, as the brief allowed.

| Check | Result |
| --- | --- |
| Row count and dispositions | 61 rows: 48 CR, 12 RJC, 1 DR. OBJ 12 CR + 1 RJC. EKO 16 CR + 4 RJC. GCO 20 CR + 7 RJC + 1 DR. Matches Sections 1.5, 13.1, 13.7 |
| Catalog structure | 64 CRC entries, same IDs, same families. Only the last column header changed ("Pair / deferral / declared") |
| Document structure | Only headings added: 10.2.4, 10.2.5, 17.5. One renamed: 9.3. No heading removed |
| Boundary definitions | 4.1 to 4.3 and 4.6 to 4.9 unchanged in substance. 4.4 gained one clarifying sentence (a finding of invalid acceptance is a CRC-59 formal-check result). 4.5 gained a paragraph. 4.10 gained two sentences. 4.11 gained terms. 5.1 and Q5 were rewritten under the brief's QA4-08 direction (see QA5-08) |
| Declared choices | 32 declared. Levels 21 A, 10 M, 1 L. Matches Sections 14.6 and 17.5 |
| Identifiers | CRC 64, HJC 26, DR 10, DM 8, DP 6, UAD4 32, BDR 18, RJ-OQ 13, AC4 26 all defined. No undefined identifier cited. The only unqualified RJ-OQ-03 hits are in the change record |
| Sections 1.5, 13, 15, 16, 17.5 | Consistent with each other on the establishing act, cascade, chain evaluation, CRC-59 content, the 61-row counts, and the 32 declarations. Two overstatements ("each is linked," QA5-06). Section 2.3 still shows Tech Lead re-review and QA re-sample as pending, which is accurate for v0.2 as submitted and out of date against the gate record. It needs refreshing at the next text change or at acceptance bookkeeping |
| Representation neutrality | No schema, storage, serialization, validator, lifecycle graph, state vocabulary, transport, CLI, or prompt format is selected. New terms ("marked as the establishing act," "falls with the chain," "acyclic," "chain to root") are semantic. The probe table in 14.4 covers them. The establishing-act ordering is a semantic requirement on DR-03 and constrains STEP-05, but selects nothing |
| Draft status | Front matter and Section 17.5 say Draft and not accepted. No acceptance, sign-off, or waiver is recorded anywhere in the artifact |

---

## MW-ADAPT-001 sampling note

I sampled the changed areas for unlisted choices in authority, independence, evidence standing, revalidation, violation handling, and representation leakage.

- **Authority and independence:** CRC-60 to CRC-64, CRC-09, CRC-62's cycle clause, Sections 3.3, 10.2.1 to 10.2.5, 10.5, 10.6, UAD4-13 to 15, 27, 28, 30, 31.
- **Evidence standing:** CRC-36, CRC-45, CRC-47, UAD4-09, UAD4-32.
- **Revalidation:** CRC-52, CRC-59, Sections 9.4.3 and 9.4.5, UAD4-07, UAD4-29.
- **Violation handling:** CRC-22, CRC-09, CRC-64, Section 9.2, Section 9.6, UAD4-26.
- **Representation ownership:** DR-03, DR-08, DR-09, DM-03, DM-07, DM-08, DP-04.

**Result.** I found no unlisted choice that changes the boundary or requires a revision. I found a few points the text leaves unspecified or undeclared. They are QA5-02 (the establishing identity in "conferrer" clauses), QA5-04 (a reading and a producer's finding), and QA5-05 (decidability reference and the standing scope). This bears on MW-OBS-016 follow-up item 2: the v0.1 independent sampling found four Medium areas, and the v0.2 re-sample found Low-level points only. That is evidence, not a certification that nothing remains.

---

## Acceptance-check status for the changed areas

| Check | Status | Note |
| --- | --- | --- |
| AC4-01, AC4-24 | Met | No representation, tooling, or state vocabulary selected |
| AC4-02 to AC4-07 | Met | Definitions, classification, and traceability intact. Residues in QA5-03 and QA5-08 |
| AC4-09 | Met | Creation, scope, change, revocation, audit, and self-conferral each disposed. Residue in QA5-01 and QA5-02 |
| AC4-10 | Met | Non-human verifier and non-human finding both bounded. Residue in QA5-05 |
| AC4-15, AC4-16 | Met | STEP-05 and STEP-06 ownership preserved. RJ-OQ-12 route noted (QA5-07) |
| AC4-17, AC4-18 | Met | Standing of detection and its limits stated. Finding content required |
| AC4-21 | Met | 32 choices declared, including level-A authority and revalidation choices. Three forward links missing (QA5-06) |
| AC4-22 | Met for this re-sample | The Tech Lead record and this record are the sampling notes |
| AC4-23 | Met | Routing corrections made. QA5-07 residue |
| AC4-25 | No action | The revision proposes no observation. Disposition of MW-OBS-016 is the Moderator's |
| AC4-26 | Pending, not QA-owned | Product Owner sign-off and Moderator final acceptance are not recorded and no waiver is recorded |

---

## Moderator-visible

1. **Decision on the recommendation.** The Moderator decides whether to proceed to Product Owner sign-off on the text as it stands, or to fold QA5-01 to QA5-03 in first (see Sequencing).
2. **PR-04 and GCR-08 reading.** QA concurs that this is a reading tension and not a direct conflict, as the Tech Lead assessed. The reading depends on the conferral scope being a scope of AUTH-G, which is itself a STEP-04 choice (UAD4-13). If the Moderator reads it as a direct conflict, UAD4-13 returns for disposition, as Section 3.3 says. Routing it as Moderator-visible is appropriate.
3. **Promotion of UAD4-13 to UAD4-15.** QA does not decide it. If promoted, UAD4-27, UAD4-28, and UAD4-30 should travel with them, as Section 14.3 says. QA adds that the QA5-02 consequences (no re-establishment path, one-way removal) would travel as well. Naming them in 10.6 first would make the promotion decision better informed.
4. **GCR-05 and STEP-03 Section 6.3 reading (QA5-04).** A reading that Section 3.3 does not list. QA's assessment is that it is a reading, not a conflict. The Moderator may want it visible beside the PR-04 reading.
5. **MW-ADAPT-001 evidence.** See the sampling note. No observation is proposed here.
6. **Level proposals.** UAD4-26 and UAD4-32 for the Tech Lead and Moderator to confirm (QA5-07).
7. **Section 2.3 gate table** is stale against the gate record (see Scope discipline).
8. **Earlier record discrepancy.** The pre-Tech Lead Moderator assessment count discrepancy that QA noted in `QA-REVIEW-STEP-04.md` item 6 is unchanged by this review. I did not re-check it.
9. **No waiver of 3c is recorded.** QA has performed 3b for v0.2.

---

## What I did not review

- I read the whole of v0.2 once and the changed areas closely. I read unchanged areas for consistency, not line by line.
- I did not re-apply T1 to T3 to every Section 6.3 row. I compared the classification mechanically against v0.1 and tested the rows that bear on QA4-05 and QA4-08.
- I did not review STEP-01, STEP-02, or STEP-03 for correctness. I read these upstream rows to test the revision: GCR-05, GCR-08, GCR-16, GCR-24, GCR-26, GCR-40, GCR-46, GCR-47, GCR-57, GCR-60, STEP-03 Sections 6.3, 9.4, 9.6, PR-01, PR-02, PR-04, PR-05, PR-27, EKR-04, EKR-13, EKR-28.
- I did not review `mod-w/architecture.md`, MW-OBS-016's body, or the research registers.
- I did not run any executable validation. None exists for this repository. My checks were comparisons of the two committed versions, identifier-resolution and count scripts, and text searches. They are QA's own and independent of the Development Team's self-checks.
- I did not run an adversarial review beyond the paths listed above. The absence of other findings does not show that no unlisted choice remains.
- I did not perform Product Owner sign-off, accept the artifact, or waive any gate. I edited no product artifact, no other review record, and no research register.
