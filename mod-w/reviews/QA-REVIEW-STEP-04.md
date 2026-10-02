---
artifact:
  type: qa-review
  from: QA
  to:
    - Development Team
    - MOD-W Moderator
  date: 2026-10-02
  review_artifacts:
    - prod-w/rule-judgment-boundary.md
    - mod-w/reviews/TECH-LEAD-REVIEW-STEP-04.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-TECH-LEAD.md
    - research/mod-w-transferability/observations.md#MW-OBS-016
  review_status: RETURN_FOR_REVISION_NARROW
---

# QA Review: STEP-04 Deliverable (Phase 3b)

**Reviewer role:** QA (MOD-W v5.0.1), read-only
**Date:** 2026-10-02
**Review target:** `prod-w/rule-judgment-boundary.md` v0.1 (Draft); `mod-w/reviews/TECH-LEAD-REVIEW-STEP-04.md`; `mod-w/reviews/MODERATOR-REVIEW-STEP-04-TECH-LEAD.md`; MW-OBS-016 disposition only
**Standing:** Phase 3b review. This is a review, not an acceptance. Final acceptance is the MOD-W Moderator's decision. Nothing here records or implies acceptance. No product artifact was edited.

---

## Recommendation

**Return for revision, narrowly.** Findings QA4-01 to QA4-04 are Medium. They sit in the areas `mod-w/step-04.md` told reviewers to probe hardest (authority, evidence standing, revalidation). Each is fixable with a small, targeted text change. I do not recommend reworking the catalog, the boundary definitions, or the classification table.

- **Required before acceptance:** QA4-01, QA4-02, QA4-03, QA4-04. Each is either a rule change or a new level-A declaration.
- **Recommended in the same revision:** QA4-05 to QA4-14 (Low). Most are one-line corrections or cross-references.
- **Otherwise sound:** classification (61 rows), traceability, representation neutrality, and violation handling held up under sampling. Details below.
- **Alternative if the Moderator prefers not to revise:** accept QA4-01 to QA4-04 as declared soft spots, add them to Section 10.6 and Section 14, and record the choice. QA does not recommend this for QA4-01. It is a path around the artifact's own rule that only humans with a conferral scope may create authority.
- **Sequencing:** Product Owner sign-off (3c) has not occurred. If the Moderator returns the artifact, the Product Owner should sign off on the revised text.

This differs from the Tech Lead's "no unlisted architecture-level choice found." The difference is a sampling-depth difference, not a disagreement about what was sampled. The Tech Lead checked that role-position assignment cannot bypass human-only conferral, and I agree. I probed root grants, chain depth, revocation consequences, and the finding path, which the Tech Lead record does not mention.

---

## Findings

Most severe first. "Location" gives the section or entry and the line in `prod-w/rule-judgment-boundary.md` as read.

### QA4-01 - Root grants can be minted by a later "establishing act"; the root rule also collides with CRC-62

**Severity:** Medium (authority; unlisted choice)
**Location:** CRC-61 (line 493), Section 10.2.2 (lines 937-939), CRC-62 (line 494), UAD4-13 (line 1319), Section 10.6 (lines 1007-1017)

**Issue.** Every non-root grant must chain to a root. A root is "a recorded act by an identified human at project establishment, marked as root, before any act relies on it." Nothing says the project has exactly one establishing act, that the establishing act precedes every other recorded act in the project, or who may perform it. The text only says a root recorded "after acts rely on the chain" is not a root. A new root starts a new chain, and no act yet relies on it, so the test passes.

Separately, CRC-62 makes a grant invalid when "the grantee is the conferring identity." The text does not say whether the establishing identity of a root counts as "the conferring identity." Both readings have a consequence.

**Failure scenario A (minting).**
1. P is a producer of accepted set S and holds no AUTH-G.
2. P records an "establishing act," marked root, that grants AUTH-G for gate G to P2.
3. No act yet relies on that chain, so "before any act relies on it" holds. P2 is not P, so CRC-62 does not apply.
4. P2 accepts S. P2 is not a producer, so CRC-07 passes. CRC-02 passes through the new root.
5. CRC-64 notices that the establishing identity P is a producer of a member of S, but its handling is only F and E.

The result is a favorable acceptance with a flag. The conferral-scope rule (CRC-61) and the human-only rule were both bypassed, and both are headline mechanisms of UAD4-13. The soft-spot list names root *legitimacy* (HJC-22). It does not name root *multiplicity*.

**Failure scenario B (team of one).**
1. A founder establishes the project and grants themselves AUTH-G as root. This is the ordinary small-team case the artifact itself cites (DM-04).
2. Under the literal CRC-62 text this is self-conferral and is invalid, so no valid authority can ever exist.
3. If a root exemption is intended, it is unstated and unbounded.

**Suggested direction.** State semantically: (a) roots arise only from the project's establishing act; (b) that act precedes every other recorded act in the project; (c) whether the establishing identity may be a root grantee, and how CRC-62 treats that. Declare this at level A in Section 14, and add root multiplicity to Section 10.6. No representation needs to be chosen. "Precedes every other recorded act" is a semantic ordering already assumed by CRC-24 and GCR-47.

### QA4-02 - Conflicted-conferral flag can be evaded by one intermediate conferrer; revocation path covers only existing challenges

**Severity:** Medium (independence; the path the Moderator asked QA to sample)
**Location:** CRC-64 (line 496), Section 10.2.3 (lines 941-945), UAD4-14 (line 1320), DP-04 (line 636), HJC-23

**Issue.** CRC-64 flags a case "where the conferrer of a grant relied on for a favorable act is a recorded producer of a member of that act's accepted set." The text tests the *immediate* conferrer. CRC-61 already requires a recorded chain, so the whole chain is available to the check. It is not used. The revocation limb flags only revocation by a producer of an item "against which the revoked holder has an open challenge." It does not reach the prospective case.

**Failure scenario (laundering).**
1. P, a producer of S, holds a conferral scope. P confers a conferral scope on Q, who is not a producer of anything in S. P's grant to Q is not itself "relied on for a favorable act."
2. Q confers AUTH-G for the gate on R.
3. R accepts S. The conferrer of R's grant is Q, so CRC-64 does not fire. P is two links upstream and unflagged.

This is the proxy path the Tech Lead named (TLR4-02), with one extra hop. The artifact's own argument for flag-not-invalid ("calling it unrestricted would reopen the self-approval path through a proxy," line 943) applies equally to the second hop.

**Failure scenario (opposition suppression).**
1. A conflicted producer holding a conferral scope revokes a challenger's AUTH-A before the challenger records a challenge.
2. The challenger's later challenge is "invalid and visible" under CRC-26, so no contestation arises.
3. CRC-64 does not fire, because no open challenge existed when the revocation was made.

BDR-10 is respected, since the challenge is recorded. The effect is still prevented by a conferral-layer act that carries only a flag at best.

**Suggested direction.**
- Evaluate CRC-64 over every link of the CRC-61 chain, or say explicitly that ancestors count as "the conferrer."
- State whether revocation of a grant held by anyone with standing to challenge is covered, not only an existing open challenge.
- DP-04 defers the *strength* of handling to pilot evidence. A burden-focused pilot is unlikely to observe adversarial conferral. The Moderator may want to name what evidence, owner, or trigger would move CRC-64 from F/E to I. This was already Moderator-visible in TLR4-02, and QA agrees it should be high priority.

### QA4-03 - A finding that an acceptance is invalid (CRC-59, UAD4-07) needs no cited rule or basis, and non-human AUTH-V on this path is unbounded

**Severity:** Medium (detection standing; revalidation)
**Location:** CRC-59 (line 486), Section 9.4.3 (lines 811-819), Section 9.4.5 (lines 829-831), Section 10.3.1 (lines 949-958), CRC-15 (line 422), CRC-30 (line 442), CRC-04 (line 401)

**Issue.** CRC-59 lets an AUTH-V holder or a human AUTH-G holder record a finding that an acceptance is invalid. That finding is the TRG-6 event and creates a requirement on every dependent that relied on the acceptance. Three gaps:

1. CRC-59 does not require the finding to be a formal-check result as Section 4.10 defines one (rule applied, evaluation point, record elements examined). The requirement exists only in prose in 4.10.
2. A revalidation *request* (CRC-30) must carry "a stated basis." A *finding*, which has the stronger effect, need not carry any. A finding is cheaper than a request.
3. The "bounded" non-human AUTH-V rule (CRC-15 (b), (c); Section 10.3.1) is scoped to "satisfies a gate-required formal check." A non-human AUTH-V holder recording an invalidity finding under CRC-59 is not caught by that bound. It need not rely on any criterion designated decidable from the record.

**Failure scenario.**
1. An AI actor holding AUTH-V for a gate class records "acceptance A is invalid," with no rule cited and no evaluation point.
2. TRG-6 fires. Every dependent of A gets an open requirement. Section 9.4.3 says a pending challenge does not suspend TRG-6.
3. Closing each requirement needs Tier-1 reaffirmation: a fresh independent human acceptance (CRC-52, GCR-60).
4. The cost asymmetry is large: one unreasoned, non-human record against a human re-acceptance per dependent. Section 10.6 acknowledges the cost ("a mistaken finding costs dependents a requirement that a human must close"), but the mitigating conditions are not in the rule.

CRC-04 lists "invalidation" among acts recorded only under AUTH-G. The context is STEP-02 hypothesis invalidation (EKO-12), so I do not read this as a conflict. The word appears in both places with different meanings and a reader can conflate them.

**Suggested direction.** Require a CRC-59 finding to be a formal-check result: it names the violated rule(s), the evaluation point, and the record elements examined. A finding that is a bare assertion is typed as a challenge or request, not as TRG-6. State that the CRC-15 decidability bound also governs non-human findings under CRC-59, or declare why it does not. Distinguish "finding of invalid acceptance" from STEP-02 "invalidation" in CRC-04.

### QA4-04 - Revocation cascade is undeclared, and conferral is not reconciled with PR-04 and GCR-08

**Severity:** Medium (authority; unlisted choice)
**Location:** CRC-61 (line 493, Eval "A, S"), CRC-63 (line 495), UAD4-15 (line 1321), Section 3.3 (lines 166-177), Section 15.1 (PR-04 row, line 1405)

**Issue 1: cascade.** CRC-63 says revocation "does not reach acts performed while the grant was effective" and that "acts under the grant after revocation are invalid." It does not say what happens to grants the revoked holder conferred. Reading A: those grants survive, so a revoked rogue conferrer's appointees keep authority. Reading B: they fall with the chain, since CRC-61 requires a chain to root and carries evaluation kind S, so acts under them after revocation become invalid. Both are defensible and they produce different outcomes. UAD4-15 declares prospectivity but not the cascade.

**Issue 2: PR-04 and GCR-08.** PR-04: "Authority is neither transitive nor inheritable. One authority class does not confer another." GCR-08: "Delegation never conveys authority." The artifact cites PR-04 as a source for CRC-61 and UAD4-13 (line 1405: PR-04 maps to CRC-02, CRC-60, CRC-61). Section 10.2.1 compares three ways to fill the conferral gap but never addresses these sentences. CRC-61 has an AUTH-G holder, through a conferral scope, confer other classes (for example AUTH-V on a non-human actor) and AUTH-G itself. Section 3.3 lists six reading tensions and this is not among them. I cannot tell from the text whether this is a reading (conferral by explicit conferral-scope grant is not class-confers-class or transitivity) or a direct conflict that `mod-w/step-04.md` says must be routed to the Moderator. The artifact should say which.

**Issue 3: terminology.** "Assignment" is used for work assignment (CRC-11, HJC-12, GCR-08) and for assignment to a role position (CRC-62). CRC-62 turns the second into a conferral. A reader can apply it to the first. Both usages are inherited from STEP-01/STEP-03, so this is wording care, not a defect in the sources.

**Failure scenario.** H revokes conferrer P for misconduct. P had conferred AUTH-G on R before the revocation. Under Reading A, R keeps accepting. Under Reading B, R's later acceptances are invalid, but nothing in the text says so. Two implementers of the same artifact would disagree on the same record.

**Suggested direction.** Declare the cascade choice at level A. Add a Section 3.3 reading, or a Moderator-routed conflict note, for PR-04 and GCR-08. Use two distinct terms for the two kinds of assignment.

### QA4-05 - Three catalogued conditions fail the agreement corollary as worded

**Severity:** Low (classification; Section 4.3)
**Location:** CRC-52 (line 474) / GCO-20; CRC-09 (line 411) / GCO-03; CRC-45 (line 467)

**Issue.** Section 4.3 says that if two competent evaluators could reach different answers on the same record, the condition is not objectively checkable as stated. Three catalogued conditions still contain a clause where they could:

- **CRC-52, "addresses every reason present."** The closure record could be read as *naming each reason with a disposition* (record-checkable), or as *adequately addressing* each reason (judgment). The HJC-16 pair in Section 8.2 says the check confirms "a closure meets authority conditions," not that each reason is named. The pair does not settle which reading applies.
- **CRC-09, "closure of a challenge in the set's favor," with "direction is read from the closed list, not interpreted."** The accepted list (GCR-05) uses the phrase, but the closed list does not say which closure kinds are favorable. Whether a given closure favors the set can depend on interpretation.
- **CRC-45, "not presented as observed fact or as established by evidence alone."** "Presented" is a property of how content reads, unless a recorded designation carries it. The catalog says the designation is checked and content is not. The condition as worded reaches past the designation.

**Failure scenario.** Evaluators A and B read CRC-52 differently. A treats a closure that names two of three reasons as invalid. B treats a closure that names all three, but is perfunctory, as valid, or invalid on adequacy grounds. The same record gets opposite results under handling I.

**Suggested direction.** In each entry, state the record form being checked (closure names each reason with its disposition; a closed list of favorable closure kinds; the evaluative designation field) and pair the residue to the HJC entry.

### QA4-06 - Several CR rows depend on derived or view conditions without a DR link, and the blocking-eligible claim overstates them

**Severity:** Low (hidden dependency on a representation choice)
**Location:** CRC-18 (line 425), CRC-19 (line 426), CRC-47 (line 469), CRC-52 (line 474), DR-01 and DR-04 (lines 606, 609), Section 5.4 (line 357)

**Issue.**
- CRC-18 requires citing "exposure" and "open requirements" in the standing record. Exposure is a derived condition, and its derivation is deferred (GCO-22, DR-04).
- CRC-19 depends on "assumption-rooted basis items" and "open requirement on a basis item" (DR-01, DR-04).
- CRC-47 requires that the item "is surfaced with unresolved assumptions." "Surfaced" is a property of views (EK-OQ-15, STEP-05), not a record element.
- CRC-52 depends on "open requirement."

DR-01 and DR-04 list "Needed by" as CRC-06, CRC-44, CRC-53 and CRC-29, CRC-51, CRC-54. They omit CRC-18, CRC-19, CRC-47, CRC-52. These rows are tagged B (blocking-eligible), which Section 5.4 defines as "every input it needs is available in the record as of the act." Where exposure is derived-only, that precondition depends on STEP-05.

Section 9.5 (last row) says a representation that cannot compute an answer leaves the condition unsatisfied and falls to human review. That protects against reading absence as satisfaction, but a STEP-05 reader will not see the dependency from the DR register.

**Failure scenario.** STEP-05 evaluates a representation that stores explicit conditions but does not derive exposure. CRC-18 is still tagged B. An acceptance omits an exposure citation and passes a check that was never able to see exposure.

**Suggested direction.** Add CRC-18, CRC-19, CRC-47, and CRC-52 to the "Needed by" columns of DR-01 and DR-04. Qualify the B tag on CRC-18 and CRC-19. Restate the "surfaced" clause in CRC-47 as a visibility requirement on any representation, as 1.6 already does for "visible."

### QA4-07 - CRC-22's closed list of waivable requirements omits two the artifact says are waivable

**Severity:** Low (internal inconsistency)
**Location:** CRC-22 (line 429), Section 11.4 (line 1057), Section 9.6 (lines 846-855), STEP-03 Sections 5.5 and 9.4 (non-waivable item 3, second sentence)

**Issue.** CRC-22 says an acceptance is valid only if the listed entries hold, "or, for a waivable gate requirement (CRC-12, CRC-13, CRC-16 amendment, CRC-17), the shortfall is covered by an exception." Two other requirements are said to be waivable elsewhere:
- Section 11.4 says a gate definition that requires named configuration facets makes a shortfall an unsatisfied gate requirement, handling "I, X." CRC-39 (configuration) is not among the entries CRC-22 lists, so there is no CRC-22 hook for that gate requirement at all.
- STEP-03 Section 5.5 and 9.4 item 3 say a gate-defined stricter treatment (response) rule may be waived. CRC-18 requires "a recorded treatment from the recognised list" but does not state the stricter-response variant, and CRC-22 does not list it.

**Failure scenario.** A gate requires configuration facets for items it relies on. An acceptance omits them and carries a valid exception. By CRC-22's closed list, the exception covers nothing, so the acceptance is invalid. By Section 11.4 it is valid under exception. The two parts of the same artifact disagree.

**Suggested direction.** Replace the closed parenthetical in CRC-22 with a statement that a gate requirement waivable under STEP-03 Section 9.4 is covered by CRC-20, and add the gate-required configuration and stricter-treatment cases.

### QA4-08 - The CR versus RJC discriminator is not applied consistently

**Severity:** Low (classification scheme)
**Location:** Section 4.5 (lines 236-249), Section 5.1 (lines 313-321), Section 6.3 (lines 502-576), notably OBJ-03, OBJ-04, GCO-02, GCO-03, GCO-12, GCO-19, GCO-20

**Issue.** Section 5.1 says a condition is RJC where the thing checked is a determination act, and gives "closure" and "acceptance" as examples. Section 4.5 uses CRC-02, CRC-03, CRC-07, and CRC-09 as examples of recorded-judgment facets (authority, recorder identity, independence, direction), yet those rows (OBJ-03, OBJ-04, GCO-02, GCO-03) are classified CR in Section 6.3. GCO-12 checks "a closure is of a recognized kind and a closer meets its authority conditions" and is CR. GCO-20 also checks a closure and is RJC. GCO-19 checks supersession or invalidation by an authorized human and is CR.

The handling does not differ between CR and RJC, so no rule is wrong. The reproducibility of the Q5 test is. Two reviewers applying Q5 to GCO-12 and GCO-20 get different answers for the same kind of thing.

**Suggested direction.** State how Q5 treats a check of the facets of Section 4.5 on a determination act (identity, authority, independence, timing). Either those are RJC, or they are CR and the Section 4.5 examples are reworded. Reconcile GCO-12 with GCO-20.

### QA4-09 - CRC-36 and the EKO-04 row do not carry the "where the record distinguishes" qualifier

**Severity:** Low
**Location:** CRC-36 (line 453), Section 6.3 EKO-04 row (line 527), Section 10.5 (line 996), Section 15.4 INV-11 (line 1601), STEP-02 line 435

**Issue.** STEP-02 says detection of agreement-presented-as-evidence is objective only where the record distinguishes sourced evidence from a concurrence record. Section 10.5 and the INV-11 row carry that qualifier. CRC-36 states "an identified source that is not solely a concurrence or agreement record" without it, and the Section 6.3 row for EKO-04 shows "I, B" without it. Section 3.3 does say the residue is judgment. A reader of CRC-36 alone sees an unconditional check.

**Suggested direction.** Carry the qualifier into CRC-36 and the EKO-04 row.

### QA4-10 - Note column in Section 6.3 says "none" where the pairing tables name a judgment

**Severity:** Low (traceability consistency)
**Location:** Section 6.3 rows OBJ-01, OBJ-02, OBJ-04, OBJ-09, OBJ-13, EKO-12, EKO-20, GCO-02, GCO-07, GCO-27; Section 6.2 pair column; Section 8.2

**Issue.** Rows say "none" or name only a DR where the catalog entry pairs a judgment:
- GCO-02 says "none"; CRC-02 pairs HJC-25 and CRC-03 pairs HJC-21.
- GCO-07 and OBJ-13 say "none"; CRC-13 pairs HJC-12 and CRC-15 pairs HJC-24.
- OBJ-09, EKO-12, EKO-20, GCO-27 say "none"; CRC-04 pairs HJC-17.
- OBJ-01, OBJ-02, OBJ-04 name only DR-07 or DR-08, with no HJC-21 or HJC-25.

Section 8.3 says no judgment is unpaired, which stays true. A reader of Section 6.3 alone would conclude these rows have no judgment residue and might assume a stronger check than the catalog gives.

**Suggested direction.** Fill in the HJC in the Note column, or define the column as "primary note only."

### QA4-11 - Level-A catalog entries do not link forward to their UAD4 declaration, contrary to Section 6.1

**Severity:** Low (MW-ADAPT-001 navigation)
**Location:** Section 6.1 (line 374); entries CRC-15, CRC-35, CRC-36, CRC-39, CRC-59, CRC-60 to CRC-64; Section 14.2

**Issue.** Section 6.1 says no entry adds a requirement beyond accepted rules "except where Section 14 declares a choice and the entry says so." In Section 6.2 only CRC-04 cites a UAD4 entry (UAD4-22). CRC-24, CRC-56, and CRC-59 cite UAD3 entries. None of the level-A entries lists its UAD4. This is the defect class that MW-OBS-016 item 3b describes: declared choices not linked from where they apply. The seven identifiers corrected in Section 17.2 were back-links. The forward direction was not checked.

**Failure scenario.** A reader of CRC-64 or CRC-59 has no signal that the entry applies a level-A declared choice. The Tech Lead review and this one both had to find them from Section 14.

**Suggested direction.** Add a UAD4 reference to each entry that applies a declared choice, or relax the Section 6.1 sentence.

### QA4-12 - Consequential reliance outside an acceptance is claimed as invalidating, but CRC-19 covers acceptances only

**Severity:** Low
**Location:** CRC-19 (line 426), CRC-47 (line 469), Section 13.7 (line 1226), Section 6.3 EKO-15 row (line 538), Section 3.3 EKO-15 reading (line 173); STEP-03 Sections 9.2 and 9.3

**Issue.** Section 13.7 profiles EKO-15 as "invalidating a currency mark or consequential reliance (F, I)." CRC-19 requires the authorization "recorded at or before the acceptance," and CRC-47 sends consequential reliance to CRC-19. STEP-03 Section 9.2 reads "progression" in FR-7 as "progression through a gate, or any consequential commitment," but ties the invalidity condition to Section 5.4 condition 8, which is an acceptance condition. So a consequential commitment that is not an acceptance has no catalogued invalidating rule, though the digest claims one.

The EKO-15 row also carries one primary disposition (RJC) but mixes a CR check (the marks on dependency links) and an RJC check (the authorization).

**Suggested direction.** Either add the non-acceptance commitment case to CRC-19, or narrow the Section 13.7 profile text. Say which part of EKO-15 is CR and which is RJC.

### QA4-13 - Open-question routing has small ownership overlaps and one mislabeled cross-reference

**Severity:** Low (AC4-23)
**Location:** RJ-OQ-03 (line 1248), RJ-OQ-09 (line 1254), RJ-OQ-10 (line 1255), DM-05 (line 626), Section 11.3 (line 1047), DP-04 (line 636), Section 6.5 EKR-41 row (line 596)

**Issue.**
- **RJ-OQ-03** routes to "STEP-05; STEP-06 guidance." It does not say which part belongs to which.
- **RJ-OQ-09** routes to "STEP-07; Tech Lead." The Tech Lead is not a step owner.
- **RJ-OQ-10** sends "should skill name and version be a separate configuration element?" to STEP-08. UAD4-11 already decided that skills are instructions and the catalog adds no separate element. Routing the question to research re-opens a declared choice. BDR-16 says reclassification needs an accepted revision, so the route should be named as that.
- **Section 11.3** says source comparability is "a practice question (DM-05)." DM-05 is defined as conventions for stating producing configuration. Section 13.6 uses DM-05 correctly. The 11.3 reference overlaps DR-06 with a practice owner the register does not define.
- **Section 6.5, EKR-41** says "Superseded here by BDR-14 and BDR-05." Section 3.1 says no accepted rule is changed, and Section 13.7 says "EKR-41 stands." "Superseded" is the wrong word for a rule the artifact preserves.

**Suggested direction.** Split RJ-OQ-03 into its representation and practice parts, name a step owner for RJ-OQ-09, align RJ-OQ-10 with BDR-16, correct the DM-05 reference in 11.3, and replace "Superseded" with "restated and enforced through."

### QA4-14 - Wording near representation vocabulary (advisory)

**Severity:** Low (advisory; no selection found)
**Location:** Section 5.4 H row (line 355), Section 4.10 (line 287), Section 9.2 B row (line 761), Section 9.1 (line 750)

**Issue.** None of these selects a representation. Each is worded close to one:
- The H kind is defined as "comparing successive recorded states." "States" leans toward snapshot-based representations. The artifact says elsewhere that A, S, and H describe the question asked and not storage (lines 1371, 1277).
- Section 4.10 gives a four-value outcome set for a formal-check result (satisfied, violated, satisfied under exception, unresolved). BDR-11 says handling categories are not values, but does not say the same of this outcome set.
- Section 9.2 B says blocking can "prevent the act from taking effect," while 9.1 says an invalid act never has effect. The intended meaning is preventing *reliance*. The wording can be read as invalid acts having effect unless blocked.

**Suggested direction.** Replace "states" with "recorded history," extend BDR-11 to the outcome set, and rephrase B as preventing reliance on the act.

---

## Sampling performed

I read `prod-w/rule-judgment-boundary.md` in full (1,694 lines), `mod-w/step-04.md`, the Step-04 setup review, the Tech Lead review, the Moderator's Tech Lead review, the Moderator pre-Tech Lead assessment, and MW-OBS-016 including its disposition. I read the upstream rule rows that the sampled entries cite (STEP-01 PR/OBJ/HJ; STEP-02 EKR/EKO/EKJ/TRG; STEP-03 GCR/GCO and Sections 3.3, 4.7, 5.4, 5.5, 8.6, 9.2, 9.4, 16).

### Section 6.3 rows tested against the three-part test (T1, T2, T3)

Required rows are in bold.

| Row | Disposition | QA assessment |
| --- | --- | --- |
| OBJ-02 | CR | Agree. Grant lookup over recorded grants. |
| OBJ-03 | CR | Agree on outcome. See QA4-08 on Q5. |
| OBJ-04 | CR | Agree. Depends on recorded actor-kind designation (HJC-21 residue). Note column incomplete (QA4-10). |
| **OBJ-12** | RJC | Agree. A waiver is a determination act. The check confirms presence of authorized human, grant, rationale, named requirement, and marker. None decides whether the waiver is warranted (HJC-15). |
| OBJ-13 | CR | Agree. Presence of named criteria. |
| **EKO-04** | CR, composite split | Agree with the split (UAD4-09). The concurrence limb is objective only where the record distinguishes concurrence (QA4-09). |
| **EKO-05** | CR, composite split | Agree. Class-defining versus descriptive is a declared reading. Presence of each element is T2-clean. |
| **EKO-11** | RJC | Agree. Authority, independence, and human identity are facets. Whether the criteria are met stays HJC-11. |
| EKO-12 | CR | Agree. Typing rule. |
| EKO-14 | RJC | Agree. Presence of a materiality designation or rationale; warrant is HJC-03. |
| **EKO-15** | RJC | Partly agree. Mixed CR and RJC under one disposition; "surfaced" and non-acceptance consequential reliance are not covered (QA4-06, QA4-12). The STEP-03 Section 9.2 reading is correctly cited and I verified it. |
| EKO-17 | RJC | Agree. Citation with a treatment. |
| **EKO-19** | CR | Agree. The TRG-2 narrowing matches STEP-03 Section 3.3. Depends on whether the requirement is derived or recorded (DR-04). |
| GCO-02 | CR | Agree. Note column incomplete (QA4-10). |
| **GCO-03** | CR | Agree. "Closure of a challenge in the set's favor" in CRC-09 fails the corollary (QA4-05). |
| **GCO-07** | CR | Agree. The two-part waivability split in 9.6 is faithful to GCR-10 and GCR-46. Note column incomplete (QA4-10). |
| **GCO-08** | RJC | Agree on class. The B tag depends on derived exposure (QA4-06). Treatment table matches STEP-03 Section 5.5. |
| GCO-09 | RJC | Agree. Depends on assumption-rooted items (QA4-06). |
| GCO-10 | RJC | Agree. The six non-waivable conditions match STEP-03 Section 9.4. |
| GCO-12 | CR | Agree on outcome. Inconsistent with GCO-20 (QA4-08). |
| **GCO-17** | RJC | Agree. "Receipt is not checkable" is stated. "Pending objection" is read as an open challenge, an assumption the text does not state. |
| **GCO-20** | RJC | Agree on class. "Addresses every reason" fails the corollary (QA4-05). |
| **GCO-22** | DR | Agree. Derivability is a conformance property of a representation (GCR-35: "a conforming representation must make it enumerable..."). It is not a failure to classify. The derived-condition users of it are the issue (QA4-06). |
| **GCO-28** | CR | Agree. "Trigger of any kind" is read with the narrowed TRG-2 and with TRG-6 from GCR-62. |

**Not tested individually:** the remaining OBJ, EKO, and GCO rows. I read them against Section 5.2 and found no misplacement, but I did not apply T1-T3 to each in turn. The row counts I verified mechanically: 61 rows; 12 CR + 1 RJC (OBJ), 16 CR + 4 RJC (EKO), 20 CR + 7 RJC + 1 DR (GCO), matching Sections 1.5, 13.1, and 13.7.

### CR rows tested for evaluator disagreement

Tested CRC-09, CRC-17, CRC-32, CRC-33, CRC-36, CRC-45, CRC-52, CRC-55. Results are in QA4-05 and QA4-09. CRC-17 (recency against recorded times), CRC-32 (authority gap), CRC-33 (clearing acts), and CRC-55 (confirmation conditions) passed.

### RJC rows tested for "checks the act, not the substance"

OBJ-12, EKO-11, EKO-14, EKO-17, GCO-08, GCO-09, GCO-10, GCO-11, GCO-17, GCO-21. Each checks facets from Section 4.5 only and decides no judgment content. GCO-21's rationale element is checked as present, not adequate. No RJC row reached substance.

### DR rows tested for "representation-owned, not a hidden failure to classify"

DR-01 to DR-10 read. DR-02 (identity across change), DR-03 (order), DR-04 (derived conditions), DR-05, DR-06, DR-07, DR-08, DR-09, DR-10 are representation questions. None hides an unclassified condition. The issue is the incomplete "Needed by" lists (QA4-06). DR-07 routes partly to "later implementation work," which is not a step owner but is not an ownership leak.

### Other sections sampled

CRC-01 to CRC-64 read in full. Section 9 (all subsections). Sections 10.2 to 10.6. Section 11. Section 12.7 and 12.8. Section 13. Section 14. Section 15.1 to 15.4.

---

## Traceability results

**Mechanical (my own script, independent of the Development Team's):**
- All 266 upstream identifiers appear: PR, ACT, HJ, INV, EKR, EKJ, GCR, GCJ in the Section 15 tables; OBJ, EKO, GCO in Section 6.3 (61 rows); TRG-1 to TRG-6 in Section 15.1. Zero missing.
- 64 CRC identifiers defined. No undefined CRC is cited. Every CRC is cited at least twice.
- HJC (26), DR (10), DM (7), DP (6), UAD4 (26), BDR (18), RJ-OQ (11): defined and each cited at least twice. BDR numbering is continuous 01-18.
- UAD4 level count 16 A, 9 M, 1 L matches Section 17.2. Handling profiles in 13.1 (28 GCO) and 13.7 (20 EKO) each cover every condition once.

**Content trace sampled:** CRC-05, 07, 09, 13, 15, 18, 20, 22, 27, 29, 33, 36, 51, 52, 55, 56, 57, 59 trace to the cited accepted IDs and say what those IDs say, except as noted in QA4-05 and QA4-09. HJC-01 to HJC-26: HJC-01 to HJC-20 trace to HJ/EKJ/GCJ rows as shown in 15.2, which I spot-checked. HJC-21 to HJC-26 are declared derived entries (UAD4-24); each names the CRC whose limit it marks, which is an adequate trace for a derived grouping.

**Weak anchors, not defects:** CRC-60 to CRC-64 rest on PR-01/02/04/05, GCR-40, GCR-47, and the open question GC-OQ-02. They are new rules, not restatements. They are declared (UAD4-13 to UAD4-15), but the entries themselves do not say so (QA4-11), and the PR-04 mapping is the tension in QA4-04.

**Out-of-catalog entries (Section 6.5):** PR-12, GCR-20 (first sentence), PR-24, PR-25/EKR-02/EKR-19, EKR-06, EKR-18, EKR-22 (first part), EKR-41, GCR-27, GCR-67. Each has a stated reason and a "where its force lies" pointer. None is a silently dropped requirement. EKR-18 (duty to record contradicting information) has no handling because breach is not detectable from a record lacking the information. BDR-07 and Section 1.4 correctly say that does not make it optional. The EKR-41 wording is QA4-13.

---

## Representation-neutrality results

I searched for: schema, storage/store, workflow engine, validator, lifecycle, graph, serialization, transport, CLI, prompt, runtime, database, API, JSON, YAML, ledger, state machine, state vocabulary, rules engine, harness, sidecar, DSL, MCP, A2A, index, query, hash, signature, authentication, timestamp, log, append-only, enum, field, column.

**Every hit is one of:** a non-selection statement (Sections 1.2, 1.3, 9 intro, 14.5), a semantic definition (Sections 4.1, 4.9, 5.4), an upstream term used as a semantic condition ("append-only," GCO-23), or STEP-05/06/07 routing (DR/DM/DP, Section 13.9-13.10). I found no selected representation.

Specific terms, per the Moderator's list:

| Term | Result |
| --- | --- |
| record, evaluation point | Defined semantically (4.1); realization deferred (DR-03, DR-10). Clean. |
| chain to root | A relation over recorded grants (CRC-61). Computation deferred (DR-08). Clean. The semantic content has gaps (QA4-01, QA4-04). |
| formal-check result | Semantic notion (4.10). Recording deferred (DR-09). Four-value outcome set is worded near a value set (QA4-14). |
| actor kind | A recorded designation. Authentication deferred (DR-07). Clean. |
| conferral scope | A scope of AUTH-G. No vocabulary. Clean. |
| A/S/H evaluation kinds | Describe the question asked. "Successive recorded states" is worded near snapshots (QA4-14). |
| handling categories | Semantic effects (BDR-11). Clean. Letter codes are declared expository (1.2). |

No finding of a selected representation. QA4-14 is wording only.

---

## Violation-handling results

- **"Blocking-eligible" cannot be read as "must block."** Confirmed. Sections 5.4, 9.2 (B row, "May: prevent the effect"), and 9.4.4 ("not a mechanism and not a requirement"), and DP-02 all keep blocking optional. The one wording hazard is QA4-14.
- **No handling prevents recording a challenge, counter-evidence, withdrawal, retirement, request, escalation, refusal, or deferral.** Confirmed. BDR-09, BDR-10, Section 9.2 B "Must not," and 9.3 all say so. Defective acts become "ineffective" or "invalid and visible," which is a consequence of the source rule (PR-10), not a prevention of recording. One related effect I note without finding: a defective withdrawal (CRC-58) leaves the item not withdrawn. That follows GCO-16 and PR-10 and is consistent with BDR-10.
- **Mechanical detection does not decide sufficiency, persuasion, adequacy, risk, materiality, acceptability, or substantive independence.** Confirmed in Sections 9.7, 9.8, BDR-14, and by the N handling on every residue entry. I found no entry that reports a verdict on a residue. The exceptions are the corollary failures in QA4-05, which are wording, not handling.
- **Detection standing.** The two-layer model is sound. The weak point is who may record a finding and what it must contain (QA4-03).

---

## Tech Lead flagged areas

| Area | QA result |
| --- | --- |
| Conflicted conferral: CRC-64, 10.2.3, UAD4-14, DP-04 | Sampled. The flagged-not-invalid choice is declared and bounded as the Tech Lead said. The one-hop laundering path and the revocation limb are not covered (QA4-02). DP-04 should carry an owner and a trigger. |
| Grant conferral and self-conferral: CRC-60 to CRC-64 | Role-position assignment is correctly treated as conferral (CRC-62), as the Tech Lead found. Root grants, revocation cascade, and the PR-04/GCR-08 reading are not handled (QA4-01, QA4-04). |
| Non-human AUTH-V: CRC-15, Section 10.3 | CRC-15's four conditions bound a non-human verification used to satisfy a gate-required check. Verification never becomes acceptance (10.3.3). The bound does not reach a non-human finding under CRC-59 (QA4-03). |
| Detection standing and revalidation: CRC-51, 52, 59, UAD4-07 | CRC-51 and CRC-52 trace correctly to GCR-58 to GCR-63 and EKR-37 to EKR-39. CRC-59 is the finding path in QA4-03. A false finding can create a requirement cheaply because a finding needs no stated basis. |
| Evidence standing: UAD4-09, 10, 11 | The class-defining versus descriptive split is placed correctly on the elements I checked (source identified, not concurrence, target, polarity, attempt record on one side; category, basis, limitations, times on the other). The timing split for presumed materiality (UAD4-10) and the flag-not-invalidate choice for configuration (UAD4-11) follow accepted semantics. One qualifier is missing from CRC-36 (QA4-09). |

---

## Open-question routing

| Check | Result |
| --- | --- |
| STEP-05 owns representation choices | Confirmed. DR-01 to DR-10; Section 13.10; Section 1.3. Item identity, derived conditions, closure computation, state vocabulary, lifecycle, and machine views are all left to STEP-05. |
| STEP-06 owns methodology, templates, thresholds, guidance | Confirmed. DM-01 to DM-07; Section 13.10. No template, charter, example, or threshold appears. |
| STEP-07 owns pilot and burden evidence | Confirmed. DP-01 to DP-06. DP-04 asks pilot to settle a security-adjacent semantics question; see QA4-02. |
| STEP-08 or later receives only research or publication items | Confirmed with one exception: the skills-as-configuration question in RJ-OQ-10 (QA4-13). Other STEP-08 items (GC-OQ-12, H-A/B/C) are research dispositions. |
| No ownership leakage through DR/DM/DP/RJ-OQ | Minor overlaps only (QA4-13). |
| All routed questions disposed | GC-OQ-01, 02, 03, 09, 11; EK-OQ-09, 14; PS-OQ-02, 05, 08, 10, 13 each have a disposition in Section 13. GC-OQ-09 is routed to pilot only, where STEP-03 listed "STEP-04 / STEP-05 / pilot"; the artifact says why it is not a representation question. |

---

## Acceptance-check status AC4-01 to AC4-26

My independent assessment. "Met" means the check's text is satisfied. Notes mark where my findings touch the check.

| Check | Status | Note |
| --- | --- | --- |
| AC4-01 | Met | Representation-neutral on every search. See QA4-14 (wording). |
| AC4-02 | Met | Section 4.3 and BDR-01. See QA4-05 on three entries that fail the corollary as worded. |
| AC4-03 | Met | Section 4.4. |
| AC4-04 | Met | Section 4.5, BDR-05, Section 8.4. See QA4-08. |
| AC4-05 | Met | Sections 4.5 to 4.9, 4.10. |
| AC4-06 | Met | Every entry has sources. Weak anchors for CRC-60 to CRC-64 (QA4-04, QA4-11). |
| AC4-07 | Met | 61 rows classified. See QA4-05, QA4-08. |
| AC4-08 | Met | GC-OQ-01 disposed with rule membership and handling categories. |
| AC4-09 | Partly Met | Creation, scope, change, revocation, audit, and self-conferral are each disposed. The creation disposition has an unaddressed path (QA4-01), the conflicted path has a gap (QA4-02), and revocation consequences are incomplete (QA4-04). |
| AC4-10 | Met | AI-held AUTH-V and verifier independence are disposed; verification never becomes acceptance. See QA4-03 on the adjacent CRC-59 path. |
| AC4-11 | Met | GC-OQ-09 disposed as not adopted, with reasons. |
| AC4-12 | Met | GC-OQ-11 disposed; both candidates adopted as rules. |
| AC4-13 | Met | EK-OQ-09 disposed with facet-level configuration and flag-not-invalidate. |
| AC4-14 | Met | EK-OQ-14 disposed; EKO membership and handling profile verified. |
| AC4-15 | Met | STEP-05 ownership preserved. See QA4-06 on missing DR links. |
| AC4-16 | Met | STEP-06 ownership preserved. |
| AC4-17 | Met | Section 9.4.3 and BDR-13, BDR-17. See QA4-03 on the standing of a finding. |
| AC4-18 | Met | Sections 9.2, 9.8, BDR-14. |
| AC4-19 | Met | BDR-07 and Section 1.4. |
| AC4-20 | Met | No score, weight, or numeric sufficiency measure introduced. |
| AC4-21 | Met (form) | Declaration present and covers the required categories. Completeness is not established: QA4-01 and QA4-04 are choices a reasonable alternative reading would have decided differently, and neither is in Section 14. |
| AC4-22 | Met | The Tech Lead sampling note exists. This record is also a sampling note: Sampling performed, Tech Lead flagged areas, and findings QA4-01 to QA4-04 are unlisted choices. |
| AC4-23 | Partly Met | Routing is sound except the minor overlaps in QA4-13. |
| AC4-24 | Met | No selected representation or tooling. |
| AC4-25 | Met | MW-OBS-016 was proposed under the research governance process and dispositioned by the Moderator (record consistent; see below). |
| AC4-26 | Not QA-owned / pending | Product Owner sign-off (3c) is not recorded and no waiver is recorded. Moderator final acceptance is not recorded. I have no evidence that all later gates or waivers are complete. |

---

## MW-OBS-016 disposition check

The disposition in `research/mod-w-transferability/observations.md` lines 1212-1222 matches `mod-w/reviews/MODERATOR-REVIEW-STEP-04-TECH-LEAD.md`: accepted as evidence, three classifications as stated, no local adaptation authorized. The observation text still says the sampling "has not occurred" and lists open follow-ups. That is correct for an observation preserved in original form. I did not review the body for accuracy beyond consistency with the artifact.

---

## Moderator-visible

1. **QA4-01 to QA4-04 need a Moderator decision** on whether to return for a narrow revision (QA's recommendation) or accept them as declared soft spots. QA4-01 and QA4-04 are unlisted level-A choices.
2. **UAD4-13 to UAD4-15 promotion (TLR4-01).** QA4-01 and QA4-04 add weight to the case for promoting them to an architecture decision. They define how authority is created, ended, and chained, which the architecture is silent on. QA does not decide this.
3. **PR-04 / GCR-08 reading (QA4-04).** Whether this is a reading or a direct conflict under `mod-w/step-04.md` Out of Scope is a Moderator-visible routing question.
4. **MW-ADAPT-001 re-evaluation evidence.** The Tech Lead sampling found no unlisted choice. Independent QA sampling found four (QA4-01, QA4-04, the QA4-02 path, and QA4-03). That is relevant to MW-OBS-016 follow-up item 2 ("whether the Tech Lead or QA sampling finds unlisted choices") and to the adaptation's standing. QA does not edit the register. The Moderator may wish to propose an observation.
5. **Sequencing.** If the Moderator returns the artifact, Product Owner sign-off (3c) should follow the revision. Product Owner sign-off on the current version would need re-confirmation.
6. **Record discrepancy outside my target.** `mod-w/reviews/MODERATOR-PRE-TECH-LEAD-REVIEW-STEP-04.md` lines 47 and 136 say "OBJ: 12 catalogued, 1 deferred" and "the full classification table (64 rows)." The deliverable has OBJ 12 CR + 1 RJC (OBJ-12), nothing deferred in OBJ, and 61 rows; 64 is the CRC count. I read that file only for context and did not review it. The Moderator may want to correct it.
7. **No waiver of 3b or 3c is recorded.** QA performed 3b. 3c remains pending.

---

## What I did not review

- I did not apply T1-T3 individually to every row of Section 6.3, or to every CRC entry. I read all entries and tested those listed under Sampling performed.
- I did not verify the content of every Section 15.1 mapping row against upstream text. I verified presence mechanically for all 266 identifiers and checked content for the entries listed under Traceability results.
- I did not review STEP-01, STEP-02, or STEP-03 for correctness. They are accepted inputs. I read their text only to test the artifact's use of them.
- I did not review `mod-w/architecture.md` decisions beyond D1 to D9 as the artifact cites them.
- I did not review MW-OBS-016's body for accuracy. I checked only its disposition.
- I did not review the Moderator pre-Tech-Lead assessment except for the discrepancy in item 6.
- I did not run any executable validation. None exists for this repository.
- I did not perform Product Owner sign-off. I did not accept the artifact. I did not edit any product artifact, review record other than this one, or research register.
- I did not run an adversarial review beyond the paths listed. The absence of other findings does not show that no unlisted choice remains.
