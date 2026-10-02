---
artifact:
  type: tech-lead-revision-brief
  from: Tech Lead
  to:
    - Development Team
    - MOD-W Moderator
    - QA
  date: 2026-10-02
  review_artifacts:
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-QA.md
    - mod-w/reviews/QA-REVIEW-STEP-04.md
    - prod-w/rule-judgment-boundary.md
    - mod-w/step-04.md
    - mod-w/reviews/TECH-LEAD-REVIEW-STEP-04.md
    - prod-w/protocol-semantics.md
    - prod-w/gate-challenge-revalidation-semantics.md
    - research/mod-w-transferability/adaptations.md
  review_status: RETURNED_TO_DEVELOPMENT_TEAM_FOR_NARROW_REVISION
---

# Tech Lead STEP-04 Revision Brief

**Reviewer role:** Tech Lead  
**Date:** 2026-10-02  
**Subject:** Narrow revision instructions for `prod-w/rule-judgment-boundary.md` v0.1 after approved QA Phase 3b review  
**Standing:** This is a revision work package. It is not acceptance. Final acceptance remains the MOD-W Moderator's decision. Product Owner sign-off remains held until the revised artifact is ready.

---

## Direction to the Development Team

Revise `prod-w/rule-judgment-boundary.md` narrowly. Do not reopen the 61-row classification, the boundary definitions, or the catalog structure except where a finding below requires a localized correction. Do not edit accepted STEP-01, STEP-02, or STEP-03 artifacts.

Every new or changed choice about authority, independence, evidence standing, revalidation, or violation handling must be declared in Section 14 under MW-ADAPT-001 with a proposed level, and linked forward from the catalog entry that applies it. The revised artifact remains a Draft and must record no acceptance.

I agree with QA that QA4-01 through QA4-04 require revision before acceptance. I also direct the recommended QA4-05 through QA4-14 fixes in the same revision because they are narrow and reduce ambiguity without changing the artifact's architecture.

---

## Required Findings

### QA4-01 - Root grants, establishing act, and CRC-62

**Disposition:** Direct revision with a specific semantic direction.

Revise CRC-61, Section 10.2.2, UAD4-13, Section 10.6, and any affected routing/traceability text to establish:

1. A PROD-W project has exactly one protocol-establishing act for the project authority chain.
2. That establishing act must precede every other recorded project act. A later act cannot become a second root merely because no later act has yet relied on it.
3. Root grants arise only from that establishing act. Non-root grants must chain acyclically to a root grant that arises from it.
4. The establishing identity may be a root grantee only for grants recorded by the establishing act itself.
5. CRC-62 does not treat that limited root-grantee case as self-conferral. CRC-62 does apply to any later grant, including a later grant by the establishing identity to itself, a role position including itself, a collective including itself, or a cycle returning to itself.
6. Root legitimacy remains HJC-22: the artifact checks that the recorded project-root form exists; it does not decide whether the establishing identity had real-world standing.

Declare this as a level-A authority choice in Section 14, either by revising UAD4-13 or adding a new UAD4 entry if that is clearer. Add root multiplicity and establishing-act uniqueness to Section 10.6 as known soft spots or bounded choices. Link the revised CRC-61 and any root text to the Section 14 declaration.

Reasoning: QA is right that the current wording allows root minting and is unclear for teams of one. The selected direction preserves the small-team case without allowing arbitrary later roots.

### QA4-02 - Conflicted conferral chain depth, revocation limb, and DP-04

**Disposition:** Direct revision with a specific semantic direction.

Revise CRC-64, Section 10.2.3, UAD4-14, DP-04, RJ-OQ-09, and affected Section 13 text to establish:

1. CRC-64 evaluates every link in the CRC-61 chain relied on by a favorable act, not only the immediate conferrer. A grant is flagged and escalation-eligible if any ancestor conferrer in the chain is a recorded producer of a member of the act's accepted set.
2. CRC-64 also covers revocation or narrowing of a grant held by any actor with standing to challenge the relevant item or set, not only a holder with an already open challenge at the moment of revocation.
3. The handling remains F/E, not I, for this STEP-04 revision. The purpose of the conferral or revocation remains HJC-23.
4. DP-04 must name evidence and a trigger: pilot evidence should include adversarial or near-adversarial cases of proxy conferral, ancestor-chain conflict, and challenger-standing suppression. The trigger for reconsidering F/E versus I is observed use or plausible rehearsal showing that flagged conflicted conferral or revocation can materially enable favorable acceptance or suppress challenge standing before review.
5. DP-04 should name the pilot owner as STEP-07, with targeted Tech Lead review of the pilot evidence before any later strengthening is proposed. Do not make the Tech Lead a step owner.

Declare the chain-depth and standing-to-challenge choices at level A in Section 14 and link CRC-64 to that declaration.

Reasoning: I agree with QA that immediate-conferrer-only language leaves an avoidable laundering path. I am not directing invalidation now because the current artifact deliberately leaves handling strength to pilot evidence; strengthening to chain-wide flag/escalation is the narrowest safe revision.

### QA4-03 - CRC-59 findings and non-human bounds

**Disposition:** Direct revision with a specific semantic direction.

Revise CRC-59, Section 9.4.3, Section 10.3.1, CRC-15 or a cross-reference from CRC-15, BDR-13, CRC-04 wording, UAD4-07, and affected Section 13/15/16 text to establish:

1. A CRC-59 finding that an acceptance is invalid must be a formal-check result that names the violated rule or rules, states the evaluation point, and identifies the record elements examined.
2. A bare assertion that an acceptance is invalid is not a CRC-59 finding and does not trigger TRG-6. It is typed as a challenge, counter-evidence, advisory finding, or revalidation request according to the authority the recorder actually holds.
3. The CRC-15 decidability bound governs non-human CRC-59 findings. A non-human AUTH-V holder may record a CRC-59 finding only when the violated rule is decidable from the record and the finding states the elements examined and evaluation point. If the asserted invalidity depends on interpretation, the non-human output remains advisory or request-like and does not itself trigger TRG-6.
4. Human AUTH-G findings under CRC-59 must still state rule(s), evaluation point, and record elements examined, but they are not limited to non-human decidability criteria where the human is exercising authorized judgment.
5. CRC-04 must distinguish STEP-02 hypothesis or content invalidation from a STEP-03/STEP-04 finding that an acceptance is invalid. Replace or qualify the bare word "invalidation" where it could be read as the latter.

Declare the changed CRC-59 finding-content and non-human-finding bound as level A in Section 14, or revise UAD4-07 at level A if that is the cleaner route. Link CRC-59 and CRC-15/BDR-13 to the declaration.

Reasoning: QA is right that the current finding path is too cheap relative to its TRG-6 effect. This revision preserves detection standing but requires reproducible basis.

### QA4-04 - Revocation cascade, assignment terms, and PR-04 / GCR-08

**Disposition:** Direct revision with a different approach than QA suggested in one respect: I decide the PR-04/GCR-08 issue is a reading tension, not a direct conflict.

Revise CRC-61, CRC-63, Section 3.3, Section 10.2, UAD4-15, Section 15.1, and affected traceability to establish:

1. Grants downstream of a revoked or narrowed grant fall prospectively with the chain. They do not validate acts after the upstream link is revoked or narrowed unless independently re-conferred through a valid chain to root.
2. Acts already performed while the whole chain was effective are not retroactively invalidated merely by later revocation, preserving GCR-47.
3. Use two distinct terms:
   - work assignment or production assignment for provenance/producer relationships under GCR-08 and PR-27;
   - role-position appointment, role-position assignment, or grant-bearing role appointment for assignment to a role position that carries grants and is treated as conferral under CRC-62.
4. Add a Section 3.3 reading note: PR-04 and GCR-08 prohibit authority by mere transitivity, inheritance, delegation, role label, or work assignment. CRC-61 is not delegation and not class-confers-class; it creates a new explicit grant by a human AUTH-G holder whose conferral scope authorizes the grant. This is a STEP-04 operationalization of GC-OQ-02, not a direct conflict with PR-04 or GCR-08.
5. The note must also acknowledge the tension and route it as Moderator-visible because the accepted upstream text did not name conferral scope. Do not edit upstream artifacts.

Declare the revocation cascade choice at level A in Section 14 and link CRC-63 to it. If the PR-04/GCR-08 reading is added to an existing authority UAD4 entry, make the reading explicit there.

Reasoning: QA is right that two implementers could read the cascade differently. I choose prospective cascade failure because CRC-61 makes an effective chain to root part of grant validity. I do not treat PR-04/GCR-08 as a direct conflict because explicit conferral by an authorized human is materially different from delegation, inheritance, or one authority class automatically conferring another.

---

## Recommended Findings

### QA4-05 - CRC-52, CRC-09, CRC-45 agreement corollary

**Disposition:** Direct revision.

Revise the three entries to state the record form being checked:

- CRC-52: objective check is that the closure names each open reason and records a disposition for each; adequacy remains HJC-16.
- CRC-09: objective direction is read from a closed list of favorable and conservative act kinds; if a closure kind is not on the list, direction is unresolved or escalated rather than interpreted.
- CRC-45: objective check is the recorded evaluative designation and whether the record presents it under an observed-fact/evidence-only form; whether the content is evaluative or warranted remains HJC-18.

Update paired HJC references where needed.

### QA4-06 - Derived/view dependencies and B tags

**Disposition:** Direct revision.

Add CRC-18, CRC-19, CRC-47, and CRC-52 to the relevant DR-01 and DR-04 "Needed by" columns. Qualify blocking eligibility for CRC-18 and CRC-19 as dependent on the representation making the required derived condition available at the evaluation point. Reword CRC-47 so "surfaced" is a semantic visibility requirement on any conforming representation, not a selected view mechanism.

### QA4-07 - CRC-22 waivable list

**Disposition:** Direct revision.

Replace the closed parenthetical in CRC-22 with a rule that any gate requirement waivable under STEP-03 Section 9.4 can be covered by a valid CRC-20 exception, while non-waivable conditions cannot. Explicitly include gate-required configuration facets and gate-defined stricter treatment/response requirements.

### QA4-08 - CR versus RJC discriminator

**Disposition:** Direct revision with a different approach than QA suggested.

Do not reopen row classifications wholesale. Instead revise the Q5/RJC explanation so checks of authority, identity, independence, timing, and direction facets on a determination act may remain CR when the rule decides protocol validity from record facts and does not evaluate the determination's substance. Keep the existing row classifications unless a specific wording fix above requires a local row note. Reconcile GCO-12 and GCO-20 by explaining why GCO-12 checks closure kind/authority as validity facts while GCO-20 reaches a closure's reason-addressing record and is treated as RJC with HJC-16 residue.

Reason for differing from QA: QA identified a real reproducibility problem in the discriminator, but the safer narrow fix is explanatory. Reclassifying rows would reopen the catalog more than this revision requires.

### QA4-09 - CRC-36 and EKO-04 qualifier

**Disposition:** Direct revision.

Carry "where the record distinguishes sourced evidence from concurrence/agreement" into CRC-36 and the EKO-04 row. Keep the existing Section 10.5 and INV-11 treatment consistent.

### QA4-10 - Section 6.3 note column

**Disposition:** Direct revision.

Fill the HJC references in the Note column for rows QA named, or explicitly define the column as "primary note only" and add cross-reference to Section 8.2 for complete pairings. Prefer filling the references; it is clearer and narrow.

### QA4-11 - UAD4 forward links

**Disposition:** Direct revision.

Add UAD4 references to every catalog entry that applies a declared choice, especially CRC-15, CRC-35, CRC-36, CRC-39, CRC-59, and CRC-60 through CRC-64. This applies to the new or revised choices from QA4-01 through QA4-04 as well. Keep Section 6.1's promise rather than weakening it.

### QA4-12 - Consequential reliance outside acceptance

**Disposition:** Direct revision with a different approach than QA suggested.

Narrow the Section 13.7 profile text rather than adding a new non-acceptance invalidating rule to CRC-19. State that CRC-19 invalidates acceptance that relies under assumption without the required authorization. For consequential commitments outside an acceptance, STEP-04 records the accepted STEP-03 reading and routes any non-acceptance enforcement detail to later semantics or methodology unless already covered by an accepted rule.

Also split the EKO-15 row note to identify the CR portions and RJC portions. Do not create a new rule for non-acceptance consequential commitments in this narrow revision.

Reason for differing from QA: adding the non-acceptance commitment case to CRC-19 would expand rule surface beyond the accepted acceptance-condition source. Narrowing the overclaim is safer.

### QA4-13 - Routing overlaps and wording

**Disposition:** Direct revision.

Make the routing corrections QA identified:

- Split RJ-OQ-03 into representation-owned and guidance-owned parts.
- Replace "STEP-07; Tech Lead" for RJ-OQ-09 with STEP-07 as owner and targeted Tech Lead review of evidence as a governance/review need.
- Align RJ-OQ-10 with BDR-16: a separate skill-name/version configuration element would require an accepted revision, not an open STEP-08 research route that silently reopens UAD4-11.
- Correct the Section 11.3 DM-05 cross-reference so source comparability remains DR-06 unless a practice convention is truly meant.
- Replace "Superseded" for EKR-41 with "restated and enforced through" or equivalent preservation language.

### QA4-14 - Representation-adjacent wording

**Disposition:** Direct revision.

Replace "successive recorded states" with "recorded history" or equivalent representation-neutral wording. Extend BDR-11 or adjacent text so the formal-check outcome set is semantic, not a selected serialized value set. Rephrase the B handling row so blocking may prevent reliance on the act, not imply that invalid acts otherwise have effect.

---

## Section Consistency Updates Required

The revision will require consistency updates beyond the immediately edited entries:

- **Section 1.5:** update only if summary counts or digest claims mention exact UAD4 level counts, authority root semantics, chain evaluation, or handling profiles affected by the revision. Do not change the 61-row classification count unless the Development Team makes an expressly directed local row-note update that changes no row membership.
- **Section 13:** update GC-OQ-02, GC-OQ-03, EK-OQ-14/EKO-15, RJ-OQ routing, and DP-04 text for the revised authority, CRC-59, consequential-reliance, and routing choices.
- **Section 15:** update PR-04/GCR-08 trace notes, CRC-59/GCR-57 to GCR-63 traces, CRC-60 to CRC-64 traces, and any wording that now overstates or understates the revised choices.
- **Section 16:** update AC4-09, AC4-10, AC4-21, AC4-23, and AC4-26 if their traceability text needs to reference the revised sections. Keep acceptance pending.

The Development Team should also update change notes to describe a narrow revision after QA return, without recording acceptance.

---

## MW-ADAPT-001 and Architecture Recommendation

I recommend promoting UAD4-13, UAD4-14, and UAD4-15, as revised, to architecture decisions or architecture decision records after STEP-04 acceptance. They define core authority-chain semantics: grant creation, root establishment, self-conferral, conflicted conferral handling, and revocation cascade. They are too central to leave only as buried STEP-04 operationalization over the long term.

The Moderator decides promotion. The Development Team should not edit `mod-w/architecture.md` in this revision.

---

## Re-review Scope

Recommend targeted re-review, not a full STEP-04 re-review.

After Development revises the artifact, Tech Lead and QA should re-sample:

- CRC-15, CRC-22, CRC-36, CRC-45, CRC-52, CRC-59, CRC-60 through CRC-64;
- Sections 3.3, 6.1 to 6.3, 9.2, 9.4.3, 10.2 to 10.6, 13, 14, 15, 16, and change notes;
- all new or changed UAD4 links and DP/DR/DM routing text.

Wider review is not needed unless the Development Team changes row membership, boundary definitions, catalog structure, or accepted-source interpretations beyond the instructions in this brief.

---

## Additional Tech Lead Sampling

I re-sampled authority, independence, evidence standing, and revalidation while preparing this brief.

I found no additional required finding beyond QA4-01 to QA4-14. I did find two small instructions to fold into the revision:

1. Where CRC-59 findings become formal-check results, ensure DR-09 still owns how they are recorded and attributed. The artifact may require content semantically but must not choose a representation.
2. Where root grants are limited to the single establishing act, keep DM-03 as practice for project establishment. STEP-04 decides protocol effect; STEP-06 still owns establishment practice.

No gate is accepted or waived by this brief.

---

## What I Did Not Review

- I did not perform Product Owner sign-off.
- I did not accept STEP-04 or waive any gate.
- I did not edit `prod-w/rule-judgment-boundary.md`, accepted STEP-01/02/03 artifacts, or the research registers.
- I did not re-run a full row-by-row classification review of all 61 rows.
- I did not review the full bodies of STEP-01, STEP-02, or STEP-03 for correctness; they remain accepted inputs.
- I did not dispose of MW-OBS-016 or any transferability observation.
- I did not select any representation, tooling, schema, state vocabulary, or validator behavior.

---

## Deliverable Instruction

Development Team should produce a narrow revised draft of `prod-w/rule-judgment-boundary.md` implementing this brief, then return it for targeted Tech Lead and QA re-sample. Phase 3c remains held until the revised artifact is ready.
