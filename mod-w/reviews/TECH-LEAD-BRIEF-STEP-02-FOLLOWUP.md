---
artifact:
  type: tech-lead-brief
  from: MOD-W Moderator (drafted by QA, for Moderator edit before sending)
  to: Tech Lead
  date: 2026-10-01
  status: DRAFT - not yet sent; not yet confirmed by the Moderator
---

# Tech Lead Brief: STEP-02 Follow-up Review

**Purpose:** Ask the Tech Lead for a targeted review of items STEP-02 left unresolved, before `step-03.md` is written. This is a request for your findings and recommendations. It does not pre-decide any answer.

**Standing:** STEP-02 is recorded as complete with exceptions (`mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`, Addendum 2026-10-01). Nothing in this brief reopens that, and nothing here is a Moderator disposition. The Moderator decides every outcome.

**Please read the model fresh.** `prod-w/evidence-knowledge-model.md` is the subject. The QA and Product Owner reports below are inputs, not conclusions you must adopt. Where you disagree with them, say so.

---

## 1. Why you are being asked

Your 2026-09-30 review (`mod-w/reviews/TECH-LEAD-REVIEW-STEP-02.md`) confirmed the 16 choices the model declared in its Section 12 (UAD-01 to UAD-16). Later review found choices that bear on authority and revalidation but were **not** in that list, so they were not put to you. QA recorded them as defect D-05 in `mod-w/reviews/qa.md`. The Product Owner sign-off (`mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-02.md`) gave a product-intent view of each.

These choices become inputs to STEP-03 (gates, challenge, disagreement, revalidation). They are cheaper to settle before STEP-03 is defined.

## 2. Requests

For items 2.1 to 2.4, for each choice state one of: **confirm as operationalization**, **confirm with change** (say what), **promote to an architecture decision**, or **return for revision**. Give your reasoning and the artifacts you relied on.

### 2.1 Choices not declared in Section 12 (QA D-05)

| Ref | Choice | Where in the model | Tension with STEP-01 |
| --- | --- | --- | --- |
| D-05a | Counter-evidence may be attached by an actor holding AUTH-P **or** AUTH-A | Section 5.2 ("contradicts" row); Section 7.7 | STEP-01's action table lists ACT-02 as AUTH-P only (`prod-w/protocol-semantics.md` ACT-02 row), while its authority table lets AUTH-A "seek and attach counter-evidence" (line 138). The model resolves the split without declaring it. |
| D-05b | A producer may withdraw or supersede its own item without acceptance; supersession or invalidation of **another actor's** item needs the acceptance authority for that scope | Section 10.5 (supporting definitions); routed only as EK-OQ-06 | Not addressed by STEP-01 beyond PR-26's "authorized actor". |
| D-05c | A revalidation requirement on a dependent that is a consequential decision, or is cited by one, must be closed by a **human** subject to independence rules | Section 10.8; EKR-38 | PR-26 says "an authorized actor"; the human requirement is derived from ACT-07. Who may close a requirement on a non-decision dependent is EK-OQ-16. |
| D-05d | An actor holding information that contradicts an item it produced or relies on **must record it** as counter-evidence | Section 7.7; EKR-18 | A new affirmative duty. The model states it cannot be enforced when the information is never recorded (Section 1.4). |

The model's own declaration test (Section 12.1) is: declare a choice if a reasonable alternative reading would produce a materially different model, or if it touches authority, actor identity, independence, revalidation semantics, or what counts as evidence.

### 2.2 Open questions the Moderator wants a recommendation on

You may supply recommendations. A recommendation does not close a question; closure comes only from an accepted STEP-03 artifact.

- **EK-OQ-17** (new; recorded in `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`, Addendum 2026-10-01): who may designate a post-acceptance change as a *correction* (acceptance retained, no trigger) rather than a *supersession*; whether the original acceptor must be told; whether a producer's own correction designation retains acceptance without independent review; and whether a producer may withdraw its own counter-evidence without independent review. Basis: model Section 6.7, EKR-10, EKJ-09, UAD-04; Product Owner risk R-1.
- **EK-OQ-05**: which set of items counts as "the accepted item" for independence when a decision cites items produced by others or by the decision-maker (model Section 9.5). The Product Owner ranks this as the largest remaining self-approval gap.
- **D-08 / EK-OQ-04**: what a *challenge* and a *bare contradicting claim* produce on dependents: exposure, a revalidation requirement, or nothing. The model says both "Contradiction and challenge take visible effect immediately" (EKR-39) and "A challenge alone is not a trigger" (Section 10.5), and TRG-2 lets a contradicting claim create a requirement by the event itself.

### 2.3 Terms (QA D-02, D-06)

`mod-w/domain-language.md` has 16 pending STEP-02 terms awaiting Moderator disposition, and two accepted terms that the model now stretches: **Challenge** (accepted definition targets claim, inference or decision; UAD-03 extends targets to evidence items and relationships) and **Inference** (accepted definition "drawn from evidence"; the model allows inference from assumptions and from other inferences). Please say whether you recommend revising the terms, the model, or neither.

### 2.4 MW-ADAPT-001 re-evaluation (QA D-04)

`research/mod-w-transferability/adaptations.md` requires, at the STEP-02 gate: *did the declaration section produce findings, and did any architecture-level content still slip past it?* Your review answered the first half implicitly. Please answer both from your own reading. QA's D-05 and the Product Owner's R-1 are candidate evidence for the second half, and you may judge them differently.

## 3. Out of scope for this brief

- Do **not** edit the accepted model, `mod-w/domain-language.md`, or any accepted artifact. If you recommend a change, state it in your review. Edits need a separate Moderator authorization.
- Do **not** write `step-03.md` as part of this review. A carry-forward list for STEP-03 is at `mod-w/reviews/STEP-03-CARRY-FORWARD.md`.
- Do **not** dispose of QA defects, observations, or terms. Recommend only.

## 4. Deliverable

A review file, for example `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02-FOLLOWUP.md`, in the format of your 2026-09-30 review, containing:

1. A disposition and reasoning for each of D-05a to D-05d.
2. Recommendations for EK-OQ-17, EK-OQ-05, and D-08.
3. Your view on D-06 (terms).
4. Your answer to the D-04 re-evaluation question.
5. Anything you found that neither QA nor the Product Owner raised.

## 5. Inputs

- `prod-w/evidence-knowledge-model.md` (Sections 3.3, 5.2, 6.7, 7.7, 9.5, 10.5, 10.8, 12, 13; EKR-10, EKR-18, EKR-37 to EKR-39)
- `prod-w/protocol-semantics.md` (authority table, ACT-01 to ACT-07, PR-16 to PR-21, PR-26)
- `mod-w/reviews/qa.md`
- `mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-02.md`
- `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02.md`
- `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md` (including both 2026-10-01 addenda)
- `mod-w/domain-language.md`
- `research/mod-w-transferability/adaptations.md`
- `mod-w/id-glossary.md` (reference for the ID prefixes used above)

Caveat on the Product Owner sign-off: its author was a Claude-family subagent with limited independence from the Development Team, and it did not read `domain-language.md`, `observations.md`, `adaptations.md` or `roadmap.md`.
