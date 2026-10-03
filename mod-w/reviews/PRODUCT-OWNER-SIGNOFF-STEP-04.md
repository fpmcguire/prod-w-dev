---
artifact:
  type: product-owner-signoff
  from: Product Owner SubAgent
  to: MOD-W Moderator
  date: 2026-10-03
  review_artifacts:
    - mod-w/step-04.md
    - mod-w/product.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-FOLD-IN.md
    - mod-w/reviews/QA-REVIEW-STEP-04-REVISION.md
    - prod-w/rule-judgment-boundary.md (v0.3: Sections 1 to 14 and 17; Sections 15 and 16 not read)
    - mod-w/architecture.md (decision D10)
  review_status: SIGNED_OFF_WITH_CONDITIONS
---

# Product Owner Sign-off: STEP-04 (Phase 3c)

**Reviewer role:** Product Owner SubAgent (MOD-W Phase 3c)
**Date:** 2026-10-03
**Question answered:** Does `prod-w/rule-judgment-boundary.md` v0.3 and architecture decision D10 do what the product needs, as stated in `mod-w/product.md` v1.1? This is product intent, not drafting detail.

---

## 0. Standing of this document (read first)

- This is a **recommendation about acceptance intent only**. I am not the MOD-W Moderator. It is a sign-off for Phase 3c, not final acceptance. **Moderator final acceptance (4a) is pending and is not recorded here.** No waiver of any gate is recorded here.
- **It does not replace the overridden reviews.** The Tech Lead re-review and QA re-sample of the v0.3 changes and of D10 were overridden by the Moderator and were not performed. My read of those changes is a product-intent read. It is not a substitute for them. I did find one stale sentence in the v0.3 text (Condition C-1) that a re-sample would probably have caught.
- **It does not decide** the PR-04 / GCR-08 reading (Moderator-visible), QA5-04 to QA5-08, or the Moderator's choice in QA5-02 beyond my answer to question 6. My sign-off on Section 10 and D10 **depends on the PR-04 / GCR-08 reading staying a reading**. If the Moderator reads it as a direct conflict, UAD4-13 returns for disposition (Section 3.3 of the artifact) and this sign-off on authority lapses with it.
- **Independence caveat.** I am a Claude-family subagent. The Development Team's declared producing configuration is `claude-sonnet-5-5`. Under PR-27 and PR-28, same-vendor review is not independent corroboration. Weigh this as one reviewer's findings. I was given the QA record and the Moderator fold-in record, so I am not blind to them. The judgments below are mine.
- **What I read.** In full: `mod-w/step-04.md`, `mod-w/product.md`, `MODERATOR-REVIEW-STEP-04-FOLD-IN.md`, `QA-REVIEW-STEP-04-REVISION.md`, decision D10 and the decision index and change log of `mod-w/architecture.md`, and Sections 1 to 14 and 17 of the artifact (including the whole catalog, Sections 6 to 8). **Not read:** Sections 15 and 16 of the artifact (traceability tables), and the upstream STEP-01 to STEP-03 artifacts. I relied on the artifact's and QA's quotations of PR-04, PR-27, GCR-05, GCR-08, GCR-47 and STEP-03 Sections 6.3 and 9.4, and did not check them against the source. I did not re-count the 61-row classification. I ran no git commands and no executable checks. I ran text searches of the artifact for representation terms, for the word "project", and for stale wording on narrowing.

---

## 1. Recommendation

**SIGNED_OFF_WITH_CONDITIONS.**

- **The boundary does what the product needs.** Checks decide what is in the record. Humans decide sufficiency, relevance, warrant, risk, materiality, and substantive independence. The middle pattern (a check may confirm that a judgment was recorded by an authorized actor, never what it decided) holds across the catalog, and no confidence score or weight appears anywhere.
- **I accept the D10 consequences, on the understanding in Section 2.2.** Every one of them fails in the safe direction: authority is lost, never gained illegitimately.
- **I accept the cost of a mistaken finding of invalid acceptance** (Section 2.3). It is bounded, and it errs towards visibility.
- **No representation, tooling or schema is selected** (Section 2.5).
- **I challenge the QA5-02 reading in part** (Section 2.6). I accept it for validity (CRC-62). I do not accept it for flagging (CRC-64) as drafted.
- **Three conditions (C-1 to C-3).** Each is a record action by the Moderator. None needs a rewrite or a new review cycle. Six carry-forward items (F-1 to F-6) bind later steps.

---

## 2. Answers to the six questions

### 2.1 Does the line protect against unjustified confidence without letting checks pretend to judge?

**Yes, with the limits the artifact itself states.** I tested it against the four failure modes in `mod-w/product.md` (lines 23 to 78).

| Failure mode | What the catalog checks | What stays human | My view |
| --- | --- | --- | --- |
| **Plausible ideas** | An item has one recorded class. A hypothesis carries criteria, otherwise it is an assumption (CRC-43). Reliance on an unvalidated hypothesis or assumption is marked and visible (CRC-47). An acceptance that relies under assumption without a prior authorization is invalid (CRC-19). Assumption-rooted basis items are identified (CRC-53) | Whether a proposition is testable, whether criteria are met, whether proceeding is warranted (HJC-10, HJC-11, HJC-14) | Strong. Gap: only an *acceptance* is invalidated. Other consequential commitments are flagged and routed (RJ-OQ-12). See 2.4 item 5 |
| **Weak evidence** | Class-defining elements: an identified source, target and polarity, an attempt record for negative findings. Absence means the item is **not evidence** for that target (CRC-36). Descriptive elements are flagged (CRC-37) | Relevance, sufficiency, persuasion, adequacy of an attempt (HJC-01, HJC-02, HJC-06) | Strong, and honest. A source being *named* is checked. Whether it exists or says what is claimed is not, and the artifact says so (Section 1.4) |
| **Agent agreement** | A concurrence record is not evidence, **where the record distinguishes it from sourced evidence** (CRC-36). Detection results confer no independence (Section 9.4.3). Independence is by recorded identity only (CRC-07) | Substantive independence, including of AI identities (HJC-12) | **Partial.** The strongest rule here is conditional, and AI-identity independence is open. See 2.4 items 2 and 3 |
| **Inherited assumptions** | Every recorded assumption is visible on its dependents (CRC-47). Assumption-rooted items are flagged. Reliance needs authorization (CRC-19) | Which background propositions count as assumptions at all. Unrecorded ones are undetectable (Section 6.5, EKR-22) | Strong within the record. An unrecorded assumption is outside any check, as the artifact says |

**Checks do not pretend to judge.** I looked for the usual leaks.

- Handling **N** reports present or absent and never a verdict (Section 9.7). A present rationale is not "adequate" (Section 4.5, 8.4).
- Non-human findings and verifications are bounded to criteria decidable from the record (CRC-15, CRC-59). The decidability designation is itself a challengeable human judgment (HJC-24).
- CRC-45 is now unresolved where the record has neither an observed-fact designation nor an evidence-only basis statement. This closes QA5-03.
- BDR-02 sends doubtful cases to judgment, which is the right default for this product. BDR-14 forbids scores, grades and weights.

One structural point for the Moderator. A check can be satisfied by a token record: a one-word rationale is "present." The artifact says this plainly (Section 8.4). It is the right limit for a protocol, but the methodology (STEP-06) has to carry the weight of making rationales mean something.

### 2.2 Authority (Section 10, D10): am I willing to live with these consequences?

**Yes, with Conditions C-2 and C-3 and carry-forwards F-1 to F-3.** All five consequences were checked against HA-1, HA-2, FR-4 and the "start minimal" risk mitigation in `mod-w/product.md`.

| Consequence | What it means in plain terms | Verdict |
| --- | --- | --- |
| **Human-only conferral from a single establishing act** | Only a human can create authority, and every grant traces to one first recorded act. AI agents cannot expand anyone's authority, including their own | **Accept.** Matches HA-1 and HA-2. The friction (a human act per agent onboarded) is the intended cost. The whole structure rests on an unchecked human assertion (HJC-22, HJC-21). That is the honest limit |
| **No way to re-establish authority if every root grant is revoked or renounced** | Authority can fail closed and stay closed. For a project with one root grantee, one renunciation or one mistaken revocation ends the project's ability to make any valid act | **Accept, with C-3(a).** A break-glass would be a way to mint a root, which is the self-approval route QA4-01 closed. Fail-closed is the safe direction. The product answer is "start a new project," and nothing says what carries into it. A user must see that before relying on it |
| **Removal of a grant holder runs one way** | Revocation comes from the grantee or a human whose conferral scope covers the grant. A descendant who revokes an ancestor cuts their own chain. A covering peer can remove a subtree. A sole root grantee cannot be removed by their appointees without removing the appointees too | **Accept, with C-3(b) and F-3.** It is visible and recorded, and a conflicted removal is flagged (CRC-64). But it effectively answers part of GC-OQ-10 and Product OQ-7 (is top authority reviewable?) as a side effect: inside the protocol, the only removal of a sole root by appointees is mutual destruction. D10 must not be read as having settled that. For two co-roots there is a first-mover property: either can revoke the other if their scope covers it |
| **The establishing identity cannot extend its own authority later** | A founder who omits a grant from the establishing act cannot add it. Only another root grantee can, and only where the chain does not loop through the founder's own conferrals | **Accept.** It closes the "establish, then re-grant" route. In a team of one it means everything the founder needs, including conferral scope, must be in the first act. That is a methodology risk (F-1), not a protocol defect |
| **Conflicted conferral is flagged and escalated, not invalidated** | A producer can confer authority on someone who then accepts the producer's work. The relation is flagged on the grant relied on, over the whole chain, and covers revocation of a challenger's standing (CRC-64). It is not invalid | **Accept.** The artifact is right that invalidation would make authority gaps incurable in a small team (Section 10.2.3). FR-4 requires self-approval to be invalid or detectable as invalid, and a proxy approval is by a different identity. The cost is stated and carries a pilot trigger (DP-04). See F-2 for what the pilot must test. See C-2 for one place where the flag does not fire |

**Is this workable for a team of one or two?** In two parts.

- **The authority machinery is workable.** For two people, both recorded as root grantees in the establishing act, there are no chains and no cascades. Later changes are a conferral by a covering root grantee, or a renunciation. For one person, the project can exist because the founder may be a root grantee of their own establishing act. The chain, cascade and narrowing rules only matter once a project has non-root grants. The risk is operational: the establishing act is unforgiving, and a founder who under-grants is stuck. That is for STEP-06 (F-1).
- **That does not make small teams workable.** Whether a team of one or two can pass any gate validly depends on independence, and D10 does not answer it. A sole human who produced or adopted the work cannot be independent of it (CRC-07). Independence is non-waivable (Section 9.6). The practice for teams of one or two is routed to STEP-06 (DM-04, GC-OQ-07) and the substance test is HJC-12. A solo founder with an outside human advisor, given AUTH-G by conferral, can pass gates, but every such acceptance is flagged under CRC-64, and escalation has no independent target (CRC-32). That is visible and non-blocking, and consistent with WD-2. I do not claim more than that. **Acceptance Criterion 3 (proof of concept) depends on DM-04 being resolved before a pilot** (F-1).

### 2.3 Is the cost of a mistaken finding of invalid acceptance (Section 10.6) acceptable?

**Yes.**

- **What a mistake costs.** A finding that meets CRC-59 is a TRG-6 event. Every dependent of the acceptance gets an open requirement, which closes only by a qualified outcome that names each reason and records a disposition for each (CRC-52). A pending challenge does not suspend it. Withdrawing the finding does not close the requirements either (CRC-58). The effort scales with the number of dependents.
- **Why I accept it.**
  - The error runs towards visibility. A false alarm costs a human some closure work. A false silence costs unjustified confidence, which is the product's whole problem, and WD-6 prefers the former.
  - The cost is bounded at the source. A finding must name the rules violated, the evaluation point and the elements examined. A bare assertion is only a challenge, counter-evidence, an advisory finding or a request. A non-human finding counts only for rules decidable from the record. Only AUTH-V or human AUTH-G holders can record one.
  - Closure stays human (CRC-52), and a correct original acceptance can be reaffirmed by its acceptor.
- **Residue I want measured, not changed** (F-4). In a team of one or two, a single false finding on a central gate acceptance can create many open requirements at once. A non-human AUTH-V holder can do that at machine speed on decidable rules. DP-01 names flag volume and false positives. It should name requirement volume from false findings and closure effort specifically.

### 2.4 Is anything a product user would reasonably expect to be required, but is only a flag or a judgment?

Yes. I list the items I consider material. **None blocks sign-off.** Each is a deliberate, declared choice, and the artifact is honest about each. They are listed so the Moderator and later steps see them as product-level exposure, not only as drafting detail.

1. **Conflicted conferral and revocation are flagged, not invalid** (CRC-64). Discussed in 2.2. A user would expect "my approver cannot have been appointed by me." Accepted for the reason given there, with the root-grant gap in C-2.
2. **Substantive independence of AI identities is judgment.** Two recorded AI identities from one model and one operator pass CRC-07, CRC-12 and CRC-13 mechanically. The artifact declines to define AI actor identity because PR-27 and PS-OQ-06 leave it open (Section 10.6). A human acceptor still decides (HJC-12) and configuration is recorded (CRC-39, flag only). This is the largest remaining gap against the product's headline problem, "AI validation through agreement." It is upstream-owned and honestly routed. It must be tested in the pilot (F-2).
3. **PE-2 is enforced as a rule only where the record distinguishes a concurrence record from sourced evidence** (CRC-36, Section 12.1). Elsewhere the remedy is challenge. Same exposure as item 2, same carry-forward.
4. **Human-only authority is human-only *as recorded*.** CRC-03 checks a recorded actor-kind designation. Authentication of identity is not a rule of this catalog (HJC-21, DR-07, RJ-OQ-02). A user would reasonably read "AUTH-G is human-only" as enforced. It is enforced against a designation. STEP-05 must answer DR-07 and not only inherit it. No publication or claim may say the protocol alone guarantees a human acted (F-5).
5. **Reliance under assumption outside an acceptance.** FR-7 says a project may continue while a material hypothesis is unvalidated only when the human role authorizes it. CRC-19 invalidates acceptances. For a consequential commitment that is not an acceptance, the artifact adds no rule (RJ-OQ-12), and CRC-47 only flags. CRC-48 covers decisions. The principal path (the build gate) is covered. The pilot should check whether any real commitment falls outside both gates and decision records (F-6).
6. **Detection is optional, and an invalid acceptance that nobody finds has no TRG-6 effect.** "Blocking-eligible" does not mean "must block" (DP-02). The invalidity itself does not depend on detection (BDR-08), but nothing in the protocol requires that a validity check be run before reliance. For a product whose thesis (`mod-w/product.md`, lines 93 to 94) is that protocol rules beat instructions, a later conformance definition has to require that B-eligible rules are evaluated at or before reliance, by blocking or an equivalent visible refusal. Otherwise E-3 (discipline enforcement) cannot be tested. Carried to STEP-05 and STEP-07 (F-5).
7. **Configuration for AI-produced items is flagged, not required** (CRC-39). The reasoning (honest "not determinable" must not be punished harder than silence, and configuration does not enter authority) is sound and I accept it. A gate may require more.

### 2.5 Does the artifact select any representation, tooling or schema?

**No.**

- A search for named formats and tools (YAML, JSON, Zod, TypeScript, SQL, DSL, MCP, A2A, graph database, ledger, sidecar, front matter) finds only the non-selection statements in Sections 1.3 and 1.2. I found no schema language, storage model, state vocabulary, lifecycle graph, validator, CLI, transport or prompt format.
- New terms ("establishing act," "root grant," "chain," "falls with the chain," "acyclic," "formal-check result," "handling category") are semantic relations over recorded items. D10's consequence that a representation "must be able to reconstruct who held what authority as of a point in time" is a semantic requirement on any representation, which D2 permits. It selects nothing.
- Three things to watch. None is a selection:
  - The one-letter handling codes (I, B, F, E, U, X, N), evaluation kinds (A, S, H) and the outcome set of a formal-check result are expository. BDR-11 says so. STEP-05 should not adopt them as a value set.
  - "Exactly one establishing act, first" needs a total order of recorded acts and a defined start of a project's record. That is DR-03, and it constrains STEP-05 without choosing for it.
  - **"Project" is used as the unit of one authority chain and is not defined** in the artifact or in the upstream artifacts I searched. The unit of the establishing act is a semantic choice, and it is undeclared. See C-3(c).

### 2.6 QA5-02 reading: a root grant has no conferrer, so a root grantee may confer a later grant on the establishing identity. Do I accept it?

**In part. I accept it for validity (CRC-62). I do not accept it for flagging (CRC-64) as drafted.**

**For CRC-62, accept.** The Moderator's reasoning holds. The establishing identity can already place anything in the establishing act, so denying it any later grant from a second root grantee would add friction without adding security. The cycle clause keeps the rule bounded. A grant to the establishing identity through a link the establishing identity itself conferred closes a cycle and is invalid. That is the property that matters, and it is what stops self-extension through proxies.

**For CRC-64, challenge.** CRC-61 and CRC-64 say the establishing identity "is not counted as a conferrer by this entry." The consequence is that **authority the establishing identity places in the establishing act is never flagged**, even when that grantee then accepts work the establishing identity produced. The flag exists to make exactly that relation visible, at the one point where the proxy is cheapest to place. A second identity that is really the founder, or a friendly appointee, passes every mechanical check and is not flagged. It is caught only by HJC-21 or HJC-12, both of which need someone to challenge. This is no worse than before D10, because authentication was always open. But D10's own rationale is that "without a bounded root, a chain rule, and an end rule, self-approval can be routed through grants," and root grants remain a route that the flag is blind to by choice.

The flag does not prevent anything, so treating it as friction (Moderator's note) is right for CRC-62. For CRC-64 the cost of counting the establishing identity as the conferrer is only flag volume in small teams, and the flag is true. The Moderator should decide this, so it is Condition C-2 and not a unilateral change.

**Drafting inconsistency, for the Moderator.** Section 10.2.2 item 6 and Section 10.6 say the establishing identity can receive a later grant "only from a root grantee." CRC-62 as written permits any conferrer whose chain does not pass through a grant the establishing identity conferred, including a non-root holder under a different root grantee. The proviso in item 6 ("provided the conferring root grantee's own authority does not derive...") is vacuous for a root grantee, because a root grant has no non-root links. I do not think the wider reading is harmful. Choose one.

---

## 3. Conditions

All three are record actions for the Moderator. None needs the Development Team to rewrite anything, or a new review cycle. Under the override pattern already in use, they can be made by the Moderator directly.

- **C-1. Correct a stale sentence in the GC-OQ-02 disposition.** Section 13.2 (line 1263 of v0.3) still reads "**Change:** widening is a new conferral, narrowing is revocation plus conferral (CRC-63)." That is the exact two-model ambiguity QA5-01 asked to remove, and CRC-63 and Section 10.2 now say the opposite. Section 13.2 is where the work package's GC-OQ-02 acceptance check (AC4-09) is answered, so the wrong model sits in the answer itself. Align it with CRC-63 and Section 10.2 (narrowing is an act on the grant with a partial cascade). **I pre-confirm any edit that only does that**, so it needs no further Product Owner review. My text search found no other stale statement of the old model.
- **C-2. Decide how CRC-64 treats root grants, and record it.** Either:
  - **(i)** count the establishing identity as the conferrer of root grants **for the CRC-64 flag only** (leaving CRC-62 and the Moderator's QA5-02 reading unchanged), or
  - **(ii)** keep CRC-64 as written, **name the gap** in Section 10.6 and in D10's consequences ("authority placed in the establishing act is not flagged"), and add **proxy placement through the establishing act** to the evidence DP-04 seeks.
  - Whichever is chosen, resolve the "only from a root grantee" wording against CRC-62 (Section 2.6). I accept either choice. I do not accept leaving the gap unnamed.
- **C-3. Record three product consequences that D10 and Section 10.6 leave implicit.** In D10 and Section 10.6, or in the Moderator's acceptance record, at the Moderator's choice. (a) and (c) belong in the artifact or D10.
  - **(a)** Total loss of root grants is **recovered by a new project**. The protocol has no break-glass. What carries into a new project (items, provenance, acceptance) is not defined, and acceptances do not carry.
  - **(b)** D10 does **not** settle GC-OQ-10 or Product OQ-7 (whether top authority is reviewable or overridable). Its removal rule narrows the space for that answer.
  - **(c)** "Project" is the **unit of one authority chain**. List it in Section 4.11 for glossary disposition, since it is load-bearing for the establishing-act rule.

---

## 4. Carry-forward items (advisory, binding on later steps)

These are not edits to this artifact. They keep the exposures in Sections 2.2 and 2.4 from being lost.

- **F-1. STEP-06, before any pilot establishes a project.** Deliver DM-03 (establishment practice: put every needed grant, including conferral scope, in the establishing act, and keep at least two root grantees where a second person exists), DM-02, DM-07, and **DM-04 (independence practice for teams of one or two)**. The last is a hard dependency for Acceptance Criterion 3.
- **F-2. STEP-07, pilot evidence to collect** (extends DP-04 and DP-06):
  - an adversarial case of two AI identities from one model and one operator acting as independent challenger and verifier;
  - proxy conferral at each link of a chain, and proxy placement through the establishing act (see C-2);
  - the first-mover case of two co-roots revoking each other;
  - whether a team of one or two can pass any gate validly, and what it costs.
- **F-3. STEP-06 and the Moderator.** Carry GC-OQ-10 explicitly as open, and do not treat D10 as having answered it.
- **F-4. STEP-07.** Extend DP-01 to measure requirement volume and closure effort from false CRC-59 findings, and the volume of always-firing flags in small teams.
- **F-5. STEP-05, STEP-07 and publication.**
  - STEP-05 must answer DR-07 (authentication of actor kind), not only inherit it.
  - Any conformance definition must require B-eligible rules to be evaluated at or before reliance. DP-02 must not conclude that detect-and-flag alone is enough without a product decision.
  - No claim may say that human-only authority is guaranteed by the protocol alone.
- **F-6. STEP-07.** Check whether any consequential commitment falls outside both a gate acceptance and a decision record (RJ-OQ-12). If one does, FR-7 is only flag-enforced for it, and that is a candidate semantics revision.

**Burden, untested.** The artifact is large: 64 catalog entries, 26 judgments, 32 declared choices (21 at level A), and, in D10, a conferral, chain, cascade and narrowing model. `mod-w/product.md` lists "protocol design becomes too complex to be practical" as the first known risk, with "start minimal" as the mitigation. I did not test whether a team can follow it, and no step has. It is Evidence Expectation E-2. The dormant-for-small-teams observation in Section 2.2 is the best answer I have, and it is an argument, not evidence.

---

## 5. Summary decision table

| Question | Answer |
| --- | --- |
| 1. Line between checks and judgment protects against unjustified confidence without checks pretending to judge | Yes. Honest limits. Weakest on AI-identity independence and conditional PE-2 (2.4 items 2 and 3) |
| 2. Authority consequences (Section 10, D10) acceptable | Yes, with C-2, C-3, and F-1 to F-3. Workable for two co-roots and for the existence of a team of one. Small-team gate passage depends on DM-04, which D10 does not answer |
| 3. Cost of a mistaken finding of invalid acceptance | Acceptable. Bounded, conservative. Measure it (F-4) |
| 4. Expected as required but only a flag or judgment | Seven items (2.4). None blocks. Items 2, 4 and 6 are the material ones |
| 5. Representation, tooling or schema selected | No. "Project" is undefined (C-3(c)) |
| 6. QA5-02 reading | Accept for validity (CRC-62). Challenge for flagging (CRC-64): C-2 |
| Status | **SIGNED_OFF_WITH_CONDITIONS (C-1 to C-3)** |

If C-2 is declined outright, my status would drop to returned for revision on the authority sections only. C-1 and C-3 are record actions and do not change the status.

---

## 6. Not done and not recorded

- **No final acceptance of STEP-04 is recorded here.** No waiver is recorded.
- No Tech Lead re-review and no QA re-sample of the v0.3 changes or D10 was performed. This record does not stand in for them.
- QA5-04 to QA5-08 and the PR-04 / GCR-08 reading are not decided here.
- I did not edit `prod-w/rule-judgment-boundary.md`, `mod-w/architecture.md`, any accepted artifact, any other review record, or any research register. This file is the only file I wrote.
- The artifact's Section 2.3 gate table still shows 3c as "Held." That is correct as of v0.3. Whether and when to update it is the Moderator's bookkeeping.

MOD-W v5.0.1
