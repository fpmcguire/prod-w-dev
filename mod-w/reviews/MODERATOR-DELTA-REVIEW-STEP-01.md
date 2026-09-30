---
artifact:
  type: moderator-review-feedback
  kind: delta-review
  from: MOD-W Moderator
  to: Development Team
  date: 2026-09-30
  supersedes: none
  amends: mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-DEV-TEAM.md (Section 5 only; verdict in that review's Section 1 stands)
  review_artifacts:
    - mod-w/validation/dev-team-step-01-discrepancy-report.md
    - research/mod-w-transferability/observations.md (MW-OBS-008 post-proposal note, MW-OBS-009, MW-OBS-010)
    - research/mod-w-transferability/README.md
    - research/mod-w-transferability/assessment.md
    - mod-w/step-01.md
    - mod-w/product.md
    - prod-w/protocol-semantics.md
  review_status: ACCEPTED
---

# Moderator Delta Review: STEP-01 Discrepancy Report and New Observations

**Reviewer role:** MOD-W Moderator
**Date:** 2026-09-30
**Status of this document:** Analysis and recommended verdict only. Per PR-05 and PR-16, no AI-executed role — including this one — can accept a gate on its own authority. Every disposition below is a recommendation. A human holding MOD-W Moderator authority must confirm it before any status changes, any file is edited, or any adaptation is authorized.

**What this document does not do:** it does not treat MW-OBS-010 as verified (it is a self-report; PR-19, PR-28), it does not resolve the vocabulary question by frequency, it does not edit `mod-w/product.md` or `mod-w/templates/*`, and it does not rewrite any accepted observation in place.

---

## 0. Independent Verification (done before ruling on anything that depends on it)

Decisions 2 and 4 both turn on whether `prod-w/protocol-semantics.md` actually contains architecture-level content that entered without Tech Lead review. MW-OBS-010 is a self-report by the role that produced the artifact. Per the constraint, that report is not independent verification. I read Section 4 of the artifact myself, against `mod-w/architecture.md` D4, before relying on anything below.

**Finding: the report holds up under independent reading, in one place clearly and one place mildly, matching the distinction MW-OBS-010 itself draws.**

- **PR-27** ("producing configuration is provenance, not identity," §4.1) resolves a question D4 leaves open. D4's text: "Architecture separates actor identity, role assignment, artifact authorship, review/challenge participation, and authority grants." D4 does not say whether a change of AI model or reasoning configuration constitutes a new actor identity. PR-27 answers that question, with a stated rationale (preventing manufactured independence via configuration-switching) that is exactly the kind of consequence D4/D6 exist to police. This is a decision about the identity model, not a restatement of one already accepted. The Section 13 change note shows the Moderator confirmed the underlying _fact_ — controlled re-execution is deliberate practice — but the specific normative rule and its rationale read as authored during the implementation step, not pre-authorized as an architecture decision. **I concur this is architecture-level content.**
- **The AUTH-P/A/V/G taxonomy** (§4.4) is traceable to `mod-w/product.md`'s "Authority Types" section (verified above), which already distinguishes production, assessment/challenge, verification, and consequential-gate authority in prose. The four-class table with explicit may/may-not columns is new structuring of already-accepted product content, not a new decision. D4 doesn't enumerate it, but D4 also doesn't need to — this is downstream operationalization, squarely inside STEP-01's stated job (D4, FR-1). **I concur this is the milder instance MW-OBS-010 itself describes, and it does not independently warrant a Tech Lead review.**

This independent finding is what makes Decision 4 below a "commission" rather than a "waive."

---

## 1. Disposition of DTD-01 to DTD-04

### DTD-01 — Two competing classification vocabularies

**Ruling: Vocabulary A is authoritative** (`TRANSFERS_UNCHANGED`, `TRANSFERS_WITH_REINTERPRETATION`, `REQUIRES_LOCAL_ADAPTATION`, `DOMAIN_COUPLED`, `NOT_YET_TESTED`), as defined in `research/mod-w-transferability/README.md` and matched in the accepted `mod-w/product.md` (lines 387-391).

**Rationale, stated rather than defaulted to frequency:**

- `observations.md` itself designates README as the single source of truth for classification semantics: "See `README.md` for governance rules and classification definitions" (top of file). `mod-w/step-01.md` is downstream of that designation — its own closing line reads "See `research/mod-w-transferability/README.md` for full research governance rules" — so it presents itself as a summary, not a competing authority.
- `mod-w/product.md` is the accepted Product Definition, higher in the artifact hierarchy than a step-level instruction file, and it matches README exactly. Two accepted, higher-authority artifacts agree; one step-level restatement disagrees. That is a description of authority order, not a vote count — the discrepancy report's four value-vs-five value split is not being used as the deciding factor here.
- The case for Vocabulary B is not frivolous — `LOCAL_ADAPTATION_PROPOSED` does encode a disposition state (proposed vs. authorized) that README's Observation-vs-Adaptation distinction cares about, and the discrepancy report is right to flag that this is the stronger of Vocabulary B's two divergences. But that concern is already handled elsewhere: every observation carries an independent `Status` field (`Proposed for Moderator review` / `Accepted`) that records exactly this distinction. The classification value does not need to also encode it. This removes the only substantive argument for Vocabulary B's naming and leaves its omission of `DOMAIN_COUPLED` as a plain defect.

**Correction required (Moderator-authorized, not self-applied by any AI role):**

- `mod-w/step-01.md` line 133 and `mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-TECH-LEAD.md` line 138: replace the four-value list with README's five values, using README's names (`REQUIRES_LOCAL_ADAPTATION`, not `LOCAL_ADAPTATION_PROPOSED`).
- **MW-OBS-006 is Accepted and carries the non-canonical value.** Per Historical Integrity, it is not rewritten. Recommended annotation, to be appended by whoever the human Moderator designates (following the TLR-007 pattern — append, don't rewrite):

  > **Vocabulary normalization note (2026-09-30, appended per DTD-01 disposition):** This observation's recorded classification `LOCAL_ADAPTATION_PROPOSED` is drawn from `mod-w/step-01.md`'s vocabulary, since superseded. `research/mod-w-transferability/README.md` and the accepted `mod-w/product.md` are the authoritative vocabulary and use `REQUIRES_LOCAL_ADAPTATION` for the same disposition state. The original text and classification label are preserved unchanged per Historical Integrity. Treat this observation as `REQUIRES_LOCAL_ADAPTATION` going forward.

- MW-OBS-007 is still **Proposed**, not accepted — no annotation needed; its classification is simply normalized to `REQUIRES_LOCAL_ADAPTATION` if and when it is accepted.
- MW-OBS-008's build-gate component is Proposed, not accepted — see Section 3 below; it is reclassified directly, not annotated.

### DTD-02 — `DOMAIN_COUPLED` omitted from the role-facing instruction

**Ruling: confirmed as the substantive defect the discrepancy report describes.** `DOMAIN_COUPLED` is defined in two accepted, higher-authority artifacts and was never made available to the role producing evidence. Resolved by the DTD-01 correction above. The consequence for MW-OBS-008 is decided in Section 3.

### DTD-03 — Undefined `PARTIALLY_TESTED`

**Ruling: define it, do not remove it, and scope it to the synthesis layer only.**

`assessment.md`'s Summary Table operates at a coarser grain than an individual observation — a named area (e.g., "Review/approval processes") can legitimately have some sub-parts with accepted evidence and others untested. That is a genuinely different kind of statement than an observation classification, and collapsing it into `NOT_YET_TESTED` would be inaccurate (README already warns against using `NOT_YET_TESTED` as a default). Recommended addition to README, in the Observation Classifications section, marked as synthesis-only:

> **`PARTIALLY_TESTED`** _(synthesis-level status; do not use as an observation classification)_ — Used only in `assessment.md`'s Summary Table, for a named area where some sub-parts have accepted supporting observations and others remain untested. Never applied to an individual `MW-OBS-XXX` entry.

### DTD-04 — `assessment.md` is stale

**Ruling: the synthesis pass happens now, at this gate — not deferred to STEP-02.**

README requires the update "at each major gate (e.g., after Product Definition acceptance, after architecture, after implementation...)." Both the architecture gate and this implementation gate have passed without one, and the discrepancy report already documents five concrete contradictions between `assessment.md` and the current register. Deferring compounds a known inaccuracy for another full step with no offsetting benefit — this is Moderator-owned synthesis work, not Development Team work, so there is no boundary-crossing cost to doing it promptly (that risk is precisely what DTD-04's own closing note flags and avoids by not having the Development Team touch it).

Recommended corrections for the human Moderator (or delegate) to apply directly to `assessment.md`, not performed here:

- Project stage: STEP-01 delivered, pending this delta disposition — not "Product Definition phase, pre-acceptance."
- Transfers With Reinterpretation: add MW-OBS-004 (Accepted).
- Requires Local Adaptation: add MW-OBS-006 (Accepted, value normalized per DTD-01).
- Transfers Unchanged: correct count to 3, including MW-OBS-005.
- Summary Table: replace `PARTIALLY_TESTED` per DTD-03's scoped definition, or drop it if the areas are re-split more precisely; add rows/evidence for architecture concepts (MW-OBS-004) and implementation semantics (MW-OBS-008, pending this review's disposition).
- Apparent Domain Coupling: no longer "None yet" once MW-OBS-008's build-gate component is accepted as `DOMAIN_COUPLED` (Section 3).

---

## 2. Confirmation of Independent Verification Basis

Already performed in Section 0 above, ahead of the decisions that depend on it, per the requirement not to treat the self-report as verified.

---

## 3. Revised Disposition of MW-OBS-008

**Recommendation changed from the original review.** The original review's Section 5 item 2 recommended accepting the observation as originally classified. With the vocabulary gap resolved (DTD-02), that recommendation is withdrawn for the build-gate component only.

- **Implementation semantics component:** unaffected. **Recommend: Accept as `TRANSFERS_WITH_REINTERPRETATION`.**
- **Build-gate component:** **Recommend: Accept as `DOMAIN_COUPLED`, not `LOCAL_ADAPTATION_PROPOSED`/`REQUIRES_LOCAL_ADAPTATION`.**

**Rationale:** README's definition of `DOMAIN_COUPLED` — "the MOD-W mechanism is materially tied to software development and may not transfer meaningfully to this non-software domain in its current form" — matches the evidence exactly: the gate's defining properties (mechanical, blocking, reviewer-independent) depend on the deliverable being executable, and for this deliverable there was nothing to instantiate. That is a different and stronger claim than "the mechanism just needs a substitute" (`REQUIRES_LOCAL_ADAPTATION`), and README's own safeguard — a `DOMAIN_COUPLED` finding "does NOT automatically mean canonical MOD-W should change" — means accepting this classification carries no implied threat to canonical MOD-W.

**This does not foreclose a local adaptation.** `DOMAIN_COUPLED` records what happened to the canonical mechanism; a local adaptation (Option A or B, still open) can still be authorized separately as a substitute for this project's practical continuity. Per the original review, Option A (declare the gate not applicable for specification steps, use the acceptance-check traceability table as the documentary handoff condition) remains the standing recommendation; Option B is deferred pending recurrence evidence from STEP-02/03. Neither is decided today — only the classification is in scope for this ruling.

No split into new observation IDs is needed; the single-observation, per-component classification the Development Team already used is adequate and the header already marks it "mixed."

---

## 4. Disposition of MW-OBS-009 and MW-OBS-010

### MW-OBS-009 — unaffected, disposition confirmed

**Recommend: Accept as `TRANSFERS_WITH_REINTERPRETATION`.** Keep in this register with the scope caveat text intact (whether this is non-software transferability evidence at all, versus a general AI-assistance finding, remains an open question the Moderator — not this document — should resolve if it matters to later synthesis). No adaptation needed: PR-27/PR-28 already state the substantive rule this observation asked for, and the existing disposition pattern (revise/escalate, never self-accept) already matches it.

### MW-OBS-010 — new, recommend Accept

**Recommend: Accept as `REQUIRES_LOCAL_ADAPTATION`** (the observation already used README's vocabulary correctly and flagged the DTD-01 conflict itself — no normalization needed), **Significance: High**, on the strength of the independent verification in Section 0, not on the strength of the self-report alone.

**On whether MW-OBS-009 and MW-OBS-010 warrant a single disposition:** **recommend keeping them separate**, cross-referenced (as they already are). They share a root cause — MOD-W's independence model is under-specified for AI-assisted, same-medium execution — but they are evidence about different mechanisms with different proposed remedies: MW-OBS-009 is about configuration variance within a role and proposes documentation only; MW-OBS-010 is about role-boundary enforcement collapsing when both sides of the boundary produce prose, and proposes an active mechanism (Option C). Merging them would obscure that one needs no adaptation and the other does.

**On Option C authorization** ("every Development Team deliverable declares the decisions it had to make that the accepted architecture did not decide, routed to Tech Lead"): **recommend authorizing**, contingent on human sign-off. Draft `adaptations.md` entry:

> ## MW-ADAPT-001 — Development Team Undecided-Architecture Declaration
>
> **Date:** 2026-09-30
> **Source observation:** MW-OBS-010
> **Affected MOD-W area:** Tech Lead to Development Team boundary (Phase 1 to Phase 2)
> **Proposed by:** Development Team (as Option C for MW-OBS-008); recommended by MOD-W Moderator delta review
> **Authorized by:** _(pending human Moderator sign-off)_
> **Status:** Proposed
>
> ### Canonical MOD-W Behavior
>
> `mod-w/templates/MOD-W.md` line 40 relies on role separation alone (Codex plans and reviews; a different role implements) to keep planning and implementation independent. It assumes the two outputs are in different media (prose vs. code), which is not true in `prod-w-dev`.
>
> ### Local Adaptation
>
> Every Development Team deliverable in `prod-w-dev` must include a declaration section listing the decisions it had to make that the accepted architecture (or other accepted upstream artifact) did not already decide, with the reasoning and the input each was derived from. This section routes to the Tech Lead, in addition to whatever Moderator review already occurs.
>
> ### Reason
>
> Role separation alone does not surface an architecture-level decision made inside an implementation artifact when both are prose in the same repository. MW-OBS-010 demonstrated this concretely (PR-27), and independent verification (this review, Section 0) confirmed it. A mechanical acceptance-check-to-location check (MW-OBS-008 Option B) would not have caught it, because the decision was well-traced to a location — the defect was in the _level_ of the decision, not its documentation.
>
> ### Scope and Reversibility
>
> Applies to all Development Team deliverables in `prod-w-dev` from this point forward. Temporary/experimental: reconsider if it produces no findings for two consecutive steps (may be unnecessary overhead) or if it fails to catch a recurrence (may need strengthening, e.g. combined with Option B).
>
> ### Effect on Canonical MOD-W
>
> This is a local experimental adaptation. Canonical MOD-W v5.0.1 is unchanged.
>
> ### Interaction with Other Adaptations
>
> Complements, does not replace, any adaptation later authorized for MW-OBS-008 (Option A/B address the vanished build gate; this addresses the boundary-enforcement gap that took its place). No conflict.
>
> ### Re-evaluation Condition
>
> Re-evaluate at the STEP-02 gate: did the declaration section produce any findings, and did any architecture-level content still slip past it?
>
> ### Moderator Rationale
>
> _(pending human Moderator sign-off)_

---

## 5. Decision 4 — Tech Lead Review Gate

**Recommend: commission, do not waive.**

The original review's Decision 4 was procedural housekeeping because nothing at the time indicated architecture-level content had actually entered the artifact. Section 0's independent verification changes that: PR-27 is architecture-level content, and it passed Moderator review unflagged (the original review's own Section 2 check 3 cites §4.1 — exactly where PR-27 sits — without recognizing it settled a new question). Waiving the gate now, immediately after independent evidence confirms the exact failure mode the gate exists to catch, would formalize the boundary collapse rather than remedy it. A benign outcome (PR-27 is judged sound) does not retroactively validate skipping the check — MW-OBS-010's own point stands: "a boundary that only fails visibly when the output is also wrong is not a boundary."

**Recommended scope for the commissioned review** (deliberately narrow, not a full re-review):

1. PR-27 and the §4.1 identity-model resolution, against `mod-w/architecture.md` D4 and D6.
2. The AUTH-P/A/V/G taxonomy (§4.4), against `mod-w/product.md` "Authority Types" and D4 — lower priority per Section 0's finding, but worth a confirming look since it is new structuring even if grounded.
3. Any other Section 13 change-log entries showing mid-step additions not present in the original briefing.

**If the human Moderator instead chooses to waive** (not recommended here, but the option must remain visible per GR-7/OBJ-12 rather than defaulted away by this document): the waiver record must identify the authorized human, the rationale, the unsatisfied requirement (Tech Lead review of architecture-level content in a Development Team deliverable), and be marked explicitly as an exception, not silent conformance.

STEP-02 planning need not block on this review completing; `prod-w/protocol-semantics.md`'s status should remain conditional (not "Accepted by Moderator" outright) until the scoped review completes or an explicit, recorded waiver is chosen.

---

## 6. What Must Change in `prod-w/protocol-semantics.md` Before Acceptance

**Recommend: no textual change to the normative content.** Section 0 found PR-27 sound on its merits; the defect identified is procedural (which reviewer, at which gate) not substantive (what the rule says).

**One additive note recommended**, to be applied by the Tech Lead or Moderator (not the Development Team, to avoid repeating the exact boundary question under review): a Section 13 change-log entry recording that PR-27 (§4.1) and the AUTH-P/A/V/G taxonomy (§4.4) are pending the scoped Tech Lead review commissioned in Section 5, so a future reader does not mistake current Moderator-review-only status for completed boundary conformance.

---

## 7. Confirmation

`mod-w/product.md` and `mod-w/templates/*` were read for cross-reference only and were not modified by this review. Verified against `git status` (Section 9).

---

## 8. Recommended Next Steps

1. Human Moderator confirms or amends every ruling in Sections 1, 3, 4, 5, 6.
2. On confirmation: apply the DTD-01 correction to `mod-w/step-01.md` and `MODERATOR-REVIEW-FEEDBACK-TECH-LEAD.md`; append the MW-OBS-006 annotation; update `research/mod-w-transferability/README.md` with the `PARTIALLY_TESTED` synthesis-status definition; update `assessment.md` per DTD-04; update MW-OBS-008's build-gate classification to `DOMAIN_COUPLED`; accept MW-OBS-010 and add MW-ADAPT-001 to `adaptations.md` if authorized.
3. Commission the scoped Tech Lead review per Section 5, or record an explicit waiver.
4. Add the Section 13 provenance note to `prod-w/protocol-semantics.md` per Section 6 (Tech Lead or Moderator only).
5. Proceed to STEP-02 planning; `protocol-semantics.md` status remains conditional until item 3 resolves.

---

## Moderator Sign-off

- **Status:** Approved
- **Moderator:** Frank McGuire (MOD-W Moderator)
- **Date:** 2026-09-30
- **Conditions:**
  - DTD-01 to DTD-04: dispositions in Section 1 confirmed as written.
  - MW-OBS-008: accepted, split classification per Section 3 (`TRANSFERS_WITH_REINTERPRETATION` / `DOMAIN_COUPLED`).
  - MW-OBS-009: accepted as `TRANSFERS_WITH_REINTERPRETATION`, no adaptation.
  - MW-OBS-010: accepted as `REQUIRES_LOCAL_ADAPTATION`, Significance High.
  - MW-ADAPT-001 (Option C, undecided-architecture declaration): authorized.
  - Decision 4: **the scoped Tech Lead review recommended in Section 5 was not commissioned.** Approval of STEP-01 proceeds without it. This is recorded as an explicit, visible waiver of that review, per GR-7 and OBJ-12 — identified requirement: Tech Lead review of architecture-level content (PR-27 §4.1; AUTH-P/A/V/G taxonomy §4.4) in a Development Team deliverable. Rationale: the Moderator judged the content sound on its own independent reading (Section 0) and elected to proceed rather than block STEP-02 on a further review. This is a deviation from this document's own recommendation, made explicitly and visibly rather than silently.
  - `prod-w/protocol-semantics.md` status updated to Accepted, conditional on the above; see its Section 13 for the corresponding change note.
