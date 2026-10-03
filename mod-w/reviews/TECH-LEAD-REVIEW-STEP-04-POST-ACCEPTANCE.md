---
artifact:
  type: tech-lead-review
  from: Tech Lead
  to:
    - MOD-W Moderator
    - Development Team
    - QA
    - Product Owner
  date: 2026-10-03
  review_artifacts:
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md
    - mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-04.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-FOLD-IN.md
    - mod-w/reviews/QA-REVIEW-STEP-04-REVISION.md
    - mod-w/reviews/TECH-LEAD-REVIEW-STEP-04-REVISION.md
    - mod-w/step-04.md
    - mod-w/architecture.md
    - prod-w/rule-judgment-boundary.md
    - prod-w/protocol-semantics.md
    - prod-w/evidence-knowledge-model.md
    - prod-w/gate-challenge-revalidation-semantics.md
  review_status: NON_BLOCKING_FINDINGS
---

# Tech Lead Review: STEP-04 Post-Acceptance Targeted Check

**Reviewer role:** Tech Lead  
**Date:** 2026-10-03  
**Review target:** Targeted late Phase 3a re-review of the v0.3 fold-in, D10, v0.4 PO-condition edits, and v0.5 QA5-04 to QA5-08 text fixes only.  
**Standing:** This is a late, voluntary check after Moderator acceptance. It does not accept STEP-04, waive any gate, reject acceptance, or decide whether a finding reopens D10. The Moderator decides whether to reopen.

---

## Recommendation

**NON_BLOCKING_FINDINGS.**

I found no authority bypass, no D10/artifact contradiction requiring immediate reopen, no stale upstream quotation mismatch in the sampled quotations, and no representation choice introduced by the scoped edits. I found one Recommended finding: the "recovery by new project / carry-over undefined" edit is correctly routed, but it is also a new architecture-significant choice that should be made explicit in Section 14 or in the carry-forward routing so later readers do not treat "new project" as a complete recovery rule.

No gate is accepted or waived by this review.

---

## Findings

### TLR5-01 - Recovery by new project is routed, but the carry-over choice should be declared

**Severity:** Recommended  
**Location:** `prod-w/rule-judgment-boundary.md` Sections 4.11, 10.6, 14.5, 17.7; `mod-w/architecture.md` D10 Consequences

**Text relied on.**

- Section 4.11 defines project as "the body of recorded items and acts governed by one establishing act and one authority chain" and says "A second establishing act therefore begins a different project" (`prod-w/rule-judgment-boundary.md:301-306`).
- D10 says, "Recovery is by a new project. There is no break-glass... What carries into a new project is not defined here" (`mod-w/architecture.md:273-281`).
- The acceptance record says the Product Owner's phrase "acceptances do not carry" was not adopted because it "would be a new rule that no one has reviewed" (`MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md:39`).

**Issue.** The scoped edit correctly prevents re-establishing roots inside the same project, but "recovery by a new project" plus "what carries ... is not defined here" is an architecture-significant product choice. It is mentioned in consequences and routing, but Section 14 does not declare it as its own choice. This is not a contradiction: Section 14.5 leaves open "any root grant, or any establishing-identity self-grant, outside the single establishing act" and GC-OQ-10 (`prod-w/rule-judgment-boundary.md:1501-1505`). The remaining gap is visibility under MW-ADAPT-001.

**Failure scenario.** Project P loses every root grant. A new project P2 is established over copied records. One reader treats prior acceptances as carried because the item history came along; another treats them as historical evidence only because P2 has a new authority chain. Both can point to "recovery by a new project" and "carry-over undefined." This does not grant authority inside P, but it can affect reliance claims in P2.

**Suggested direction.** Do not reopen D10 unless the Moderator wants to settle carry-over now. Prefer a Section 14 / carry-forward clarification: "recovery by new project with carry-over undefined" is an unlisted level A choice or open architecture/methodology item, and any carry-over rule requires later accepted disposition. Keep DM-03/DM-07/STEP-06 routing visible.

### TLR5-02 - UAD4-26 and UAD4-32 level proposals should be confirmed as A, not M

**Severity:** Low  
**Location:** `prod-w/rule-judgment-boundary.md` Section 14.2, UAD4-26 and UAD4-32; acceptance routing QA5-07

**Text relied on.**

- QA flagged that both levels looked low and left them for Tech Lead/Moderator confirmation (`QA-REVIEW-STEP-04-REVISION.md:169-175`).
- The artifact records UAD4-26 as visible exception semantics and waivability of gate requirements (`prod-w/rule-judgment-boundary.md:1439`).
- The artifact records UAD4-32 as the record forms checked by CRC-52 and CRC-45 (`prod-w/rule-judgment-boundary.md:1445`).
- The acceptance record says the proposed levels "remain proposals for Tech Lead and Moderator confirmation" (`MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md:89-92`).

**Issue.** My view is that both are level A. UAD4-26 decides violation handling and waiver coverage. UAD4-32 decides what record form counts as checkable for CRC-45/CRC-52. Neither creates a blocking defect, but leaving them proposed at M understates their architectural relevance.

**Failure scenario.** A later step treats UAD4-26 as a methodology-level cleanup and changes exception coverage without architecture review, or treats UAD4-32 as mere drafting and changes the record element that CRC-45 checks. Either would change rule boundary behavior.

**Suggested direction.** Moderator or a later Tech Lead checkpoint should confirm both as level A or record why M is intended. No artifact rewrite is required for STEP-04 acceptance unless the Moderator wants the level table amended.

---

## Check-by-Check Table

| Check | Status | Result |
| --- | --- | --- |
| 1. MW-ADAPT-001 sampling | finding | One unlisted/significant choice found: new-project recovery with carry-over undefined. Other candidates are declared or routed: project definition is in 4.11 and tied to DM-03/DR-03; CRC-59 decidability is in UAD4-29; wider CRC-62 reading is in UAD4-27/D10. |
| 2. Authority and independence | clean | I did not find a permitted route for the establishing identity or a producer to gain valid authority or perform a favorable act beyond the text's stated F/E exposures. Root proxy remains intentionally unflagged and routed to DP-04/F-2, not hidden. |
| 3. D10 against artifact | clean | D10 is faithful to Sections 10.2 and 10.6, CRC-60 to CRC-64, and UAD4-13/14/15/27/28/30. I found no D10 claim absent from the artifact. |
| 4. CRC-59 re-anchoring | clean | The bound is now anchored in catalog classification: CR or validity-facet RJC. Derived-condition availability is handled by DR-01/DR-04 and conditional B wording, not by the non-human finding bound itself. HJC-24 is not stale if read as classification/designation judgment. |
| 5. Section 3.3 UAD4-31 row | clean | The row is a conservative reading, not a direct conflict. GCR-05 bars favorable closure by a producer; STEP-03 6.3 explains challenger resolution validity but does not address producer status. The CRC-32 authority-gap consequence for a team of one is correct. |
| 6. Consistency and traceability | clean with low finding | Counts and stale-wording searches are consistent. Sections 15 and 16 include the changed entries I sampled. TLR5-02 records my view on UAD4-26/UAD4-32 levels. |
| 7. Upstream quotations | clean | Sampled quotations for PR-04, PR-27, GCR-05, GCR-08, GCR-47, STEP-03 6.3, and STEP-03 9.4 matched source substance. |
| 8. Representation neutrality | clean | "Project," "establishing act precedes every other recorded act," and as-of reconstruction are semantic. I found no schema, storage model, serialization, validator, lifecycle graph, or state vocabulary selected by A to C. |
| 9. Open items | clean with low finding | F-1 to F-6, QA5-03, QA5-07, GC-OQ-10, and Product OQ-7 are not lost. TLR5-02 gives my requested view that UAD4-26 and UAD4-32 should be A. |

---

## Answers to Directed Items

### 1. MW-ADAPT-001 sampling

**Finding:** TLR5-01.

Candidate dispositions:

| Candidate | Unlisted choice? | Level | Needs UAD4? | Reason |
| --- | --- | --- | --- | --- |
| Definition of "project" | Partly declared/routed | A | Already tied to UAD4-27/D10; consider explicit carry-forward note | It defines the unit of one establishing act and authority chain (`prod-w/rule-judgment-boundary.md:301-306`). |
| CRC-59 decidability anchored in catalog classification | Declared | A | No new UAD4 needed | UAD4-29 states the CR/RJC validity-facet bound (`prod-w/rule-judgment-boundary.md:1442`). |
| Wider CRC-62 reading for later grants to establishing identity | Declared | A | No new UAD4 needed | UAD4-27 and CRC-62 state the later-grant rule and cycle reading (`prod-w/rule-judgment-boundary.md:517,1440`). |
| Recovery by new project with carry-over undefined | Yes, or insufficiently visible | A | Yes or equivalent Section 14/carry-forward declaration | D10 and 10.6 rely on it, while carry-over is explicitly undefined. |

### 2. Authority and independence

I found no hidden valid route for authority gain:

- **Root grantee as proxy:** Root grants have no conferrer, so CRC-64 does not flag a founder placing authority in a proxy through the establishing act (`prod-w/rule-judgment-boundary.md:516,519`). The artifact names this: "Root grants are not flagged" and routes proxy placement evidence to DP-04/F-2 (`prod-w/rule-judgment-boundary.md:1103`; `MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md:77-79`). This is an exposure, not a hidden bypass.
- **Non-root chains:** CRC-64 evaluates "any conferrer along the CRC-61 chain" (`prod-w/rule-judgment-boundary.md:519`), closing one-hop laundering.
- **Narrowing to strip a challenger:** CRC-64 covers revocation or narrowing, including cascade, of a grant held by an actor with standing to challenge (`prod-w/rule-judgment-boundary.md:519`). Handling is F/E, intentionally not I.
- **Second establishing act:** CRC-61 says a later act marked establishing or root is ordinary conferral, not a second root (`prod-w/rule-judgment-boundary.md:516`).
- **Circular project definition:** The definition uses one establishing act and one authority chain; boundary drawing is DM-03/DR-03 (`prod-w/rule-judgment-boundary.md:305`). I do not see circularity that changes rule outcomes.

### 3. D10 against the artifact

D10 decision bullets match the artifact:

- Conferral scope and PR-04/GCR-08 reading: D10 lines 265 and artifact Section 3.3/CRC-61/UAD4-13 (`mod-w/architecture.md:265`; `prod-w/rule-judgment-boundary.md:184,516,1427`).
- One establishing act/root grants/no conferrer: D10 line 266 and CRC-61/UAD4-27 (`mod-w/architecture.md:266`; `prod-w/rule-judgment-boundary.md:516,1440`).
- Self-conferral invalid for later grants: D10 line 267 and CRC-62 (`mod-w/architecture.md:267`; `prod-w/rule-judgment-boundary.md:517`).
- Prospective revocation/narrowing cascade: D10 line 268 and CRC-63/UAD4-30 (`mod-w/architecture.md:268`; `prod-w/rule-judgment-boundary.md:518,1443`).
- Conflicted conferral/revocation F/E: D10 line 269 and CRC-64/UAD4-28 (`mod-w/architecture.md:269`; `prod-w/rule-judgment-boundary.md:519,1441`).

I found no omission that D10 relies on silently. Consequences in D10 lines 275-282 are present in Section 10.6 and acceptance routing.

### 4. CRC-59 re-anchoring

Clean. CRC-59 now requires a formal-check result naming rules, evaluation point, and elements examined; a non-human AUTH-V holder is bounded to rules classified CR or validity-facet RJC (`prod-w/rule-judgment-boundary.md:509`). CRC-15 echoes the same bound (`prod-w/rule-judgment-boundary.md:445`). This is decidable from the record at the level of accepted catalog classification.

Derived conditions DR-01 and DR-04 affect blocking eligibility for CRC-18/CRC-19 (`prod-w/rule-judgment-boundary.md:379,448,449`), not whether the asserted rule is in the catalog. A non-human finding still must state elements examined and evaluation point. HJC-24 remains usable as the paired judgment for classification/designation of decidability; it is not stale after the re-anchor.

Searches for "decidab" and "CRC-15 bound" found no inconsistent remaining wording in the scoped files.

### 5. Section 3.3 UAD4-31 row

Clean. GCR-05 says a producer may not perform favorable acts, including "closure of a challenge in the set's favor" (`prod-w/gate-challenge-revalidation-semantics.md:258`). STEP-03 Section 6.3 says challenger resolution is by the challenger and "ends that challenge's contribution only" (`prod-w/gate-challenge-revalidation-semantics.md:640-643`). Reading challenger resolution of a challenge against a set member as favorable is conservative and compatible: STEP-03 explains who can perform that closure form, while GCR-05 limits producers performing favorable acts.

The team-of-one consequence is correct. If the only producer challenges its own item, GCR-24 permits the challenge, but GCR-05/CRC-09 prevent favorable closure by that producer. That creates an authority gap routed through CRC-32/DM-04, not a conflict.

### 6. Consistency and traceability

Clean with TLR5-02.

- Counts: Section 17.8/acceptance record say 64 entries, 61 rows, 32 declared choices, 21 A, 10 M, 1 L, and nine DM items (`MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md:101`; `prod-w/rule-judgment-boundary.md:1912`). My identifier scan did not contradict this.
- Section 2.3 gate table records waiver status for v0.3, D10, v0.4, and v0.5 (`prod-w/rule-judgment-boundary.md:127-135`).
- Sections 17.6, 17.7, and 17.8 record the scoped changes and non-review status (`prod-w/rule-judgment-boundary.md:1876-1912`).
- Sections 15 and 16: sampled changed entries CRC-02, CRC-18, CRC-39, CRC-45, CRC-59, CRC-61 to CRC-64 and AC4 rows; I found no loss of traceability.
- Stale wording searches for "revocation plus conferral," "only from a root grantee," "same decidability bound," "CRC-15 bound," "Draft," and "not accepted" found no stale scoped wording. Remaining "Draft" and "not accepted" hits were outside the accepted-product status issue or in historical notes.

### 7. Upstream quotations

Clean. Sampled source checks:

- PR-04: authority is neither transitive nor inheritable, and one class/scope does not confer another (`prod-w/protocol-semantics.md:351-355`).
- PR-27/PR-28: producing configuration is provenance, not identity; re-execution confers no independence (`prod-w/protocol-semantics.md:392-393`).
- GCR-05: favorable acts barred for producers; conservative acts permitted (`prod-w/gate-challenge-revalidation-semantics.md:258`).
- GCR-08: delegation never conveys authority; assignment is provenance and only sometimes makes the assigner a producer (`prod-w/gate-challenge-revalidation-semantics.md:273-278`).
- GCR-47: authorizations and exceptions do not act retroactively (`prod-w/gate-challenge-revalidation-semantics.md:359` and conditional progression line 765).
- STEP-03 Section 6.3: challenger resolution and authority closure forms (`prod-w/gate-challenge-revalidation-semantics.md:640-645`).
- STEP-03 Section 9.4: non-retroactivity and required authorization before acceptance (`prod-w/gate-challenge-revalidation-semantics.md:354-359,760-766`).

### 8. Representation neutrality

Clean. The scoped edits stay semantic:

- "Project" is a semantic body governed by one establishing act and one authority chain, with boundary drawing deferred (`prod-w/rule-judgment-boundary.md:305`).
- "Establishing act precedes every other recorded act" is semantic ordering; Section 14.4 treats order as representation-deferred (`prod-w/rule-judgment-boundary.md:1479-1484`).
- As-of reconstruction is a consequence of D10, not a selected storage model (`mod-w/architecture.md:275,281`).

I found no selected schema, storage model, serialization, validator, lifecycle graph, state vocabulary, UI, or tooling.

### 9. Open items

Clean with TLR5-02.

- F-1 to F-6 are preserved in acceptance routing (`MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md:75-82`).
- QA5-03 remains STEP-05 (`MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md:85`).
- QA5-07 is routed to STEP-06 / Moderator / Tech Lead, with UAD4-26 and UAD4-32 levels unconfirmed (`MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md:89`).
- GC-OQ-10 and Product OQ-7 remain open; D10 says it does not settle them (`mod-w/architecture.md:280`; `prod-w/rule-judgment-boundary.md:1103`).
- My level view: UAD4-26 and UAD4-32 should be A, not M, because they touch violation handling and what counts as checkable.

---

## Not Done

- I did not reopen the 61-row classification, catalog structure, or boundary definitions beyond the scoped A to C changes.
- I did not perform a full line-by-line re-review of Sections 15 and 16; I sampled the changed entries and AC4 rows relevant to the request.
- I did not run executable tests; this is a document review.
- I did not edit `prod-w/rule-judgment-boundary.md`, `mod-w/architecture.md`, any other review record, the Product Owner record, or any research register.

---

## Producing Configuration and Independence

Produced by Codex in ChatGPT/Codex, GPT-5-based coding agent, using local shell text inspection (`Get-Content`, `rg`) and manual review. The Development Team used `claude-sonnet-5-5`. This is a different vendor/model family from the Development Team's producing configuration. Under PR-27 and PR-28, this review records a separate review action and findings; it is still a late voluntary check and does not itself satisfy or waive any MOD-W gate.

MOD-W v5.0.1
