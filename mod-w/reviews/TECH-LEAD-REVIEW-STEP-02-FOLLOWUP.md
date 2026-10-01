---
artifact:
  type: tech-lead-review
  from: Tech Lead
  to: MOD-W Moderator
  date: 2026-10-01
  review_artifacts:
    - prod-w/evidence-knowledge-model.md
    - prod-w/protocol-semantics.md
    - mod-w/reviews/qa.md
    - mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-02.md
    - mod-w/reviews/TECH-LEAD-REVIEW-STEP-02.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-02.md
    - mod-w/domain-language.md
    - research/mod-w-transferability/adaptations.md
    - mod-w/id-glossary.md
  review_status: RECOMMENDATIONS_ONLY
---

# Tech Lead Review: STEP-02 Follow-up

**Reviewer role:** Tech Lead  
**Date:** 2026-10-01  
**Subject:** Targeted review of unresolved STEP-02 authority, revalidation, terminology, and MW-ADAPT-001 questions  
**Status:** Recommendations only; no disposition made

---

## Summary

QA D-05 correctly identifies choices that satisfy the model's own Section 12.1 declaration test but were not declared in Section 12. I do not read them as defects in the model's substance. I recommend confirming D-05a, D-05c, and D-05d as operationalization, and confirming D-05b with a STEP-03 change that separates producer-owned revision from authority over reliance on another actor's item.

I do not recommend reopening STEP-02. I recommend that STEP-03 explicitly resolve EK-OQ-17, EK-OQ-05, and D-08 before defining gate consequences, because all three affect self-approval, challenge handling, or revalidation burden.

---

## D-05 Disposition

### D-05a - AUTH-P or AUTH-A may attach counter-evidence

**Disposition:** Confirm as operationalization.

The model resolves a real tension inside STEP-01, but resolves it in the only reading that preserves both the action table and the authority table. `prod-w/protocol-semantics.md` Section 4.4 gives AUTH-A actors the power to "seek and attach counter-evidence"; Section 5.3 lists ACT-02 as AUTH-P. The model's Section 5.2 limits AUTH-A attachment to the contradicting relationship, while supporting evidence remains ACT-02 under AUTH-P.

This adds no acceptance authority, no validation authority, and no ability to close a challenge. It lowers the barrier to recording dissent, which is aligned with AH-3, WD-2, and the Product Owner's reading. The missed declaration is procedural, not substantive.

**Relied on:** `prod-w/protocol-semantics.md` Sections 4.4 and 5.3; `prod-w/evidence-knowledge-model.md` Sections 5.2 and 7.7; QA D-05a; Product Owner Section 2.4.

### D-05b - Own-item withdrawal/supersession versus another actor's item

**Disposition:** Confirm with change.

The core split is correct: a producer can retract or revise its own item under production authority, but cannot make an authoritative determination that another actor's item may no longer be relied on. That latter act is a reliance/sufficiency judgment and needs the acceptance authority for the item's scope.

The change I recommend is for STEP-03 to state the split more explicitly:

1. Producer withdrawal or supersession of the producer's own item is valid as a recorded revision event, but the prior item remains visible and the event can trigger revalidation.
2. Producer withdrawal of the producer's own counter-evidence is also valid as a recorded revision event, but it must not erase the contradiction from history or hide that a dependent decision considered, or should have considered, that prior counter-evidence.
3. Supersession or invalidation of another actor's item is effective for reliance only through the actor with acceptance authority for that scope, subject to independence rules.
4. A non-authoritative attempt to supersede or invalidate another actor's item is recorded as a challenge, counter-evidence, or advisory finding, not as invalidation.

This does not need promotion to a new architecture decision if STEP-03 resolves EK-OQ-06 and EK-OQ-17 in those terms. It should be declared in the STEP-03 decision list because it touches authority over reliance.

**Relied on:** `prod-w/evidence-knowledge-model.md` Sections 6.7 and 10.5; EKR-09, EKR-10, TRG-1, TRG-4; `prod-w/protocol-semantics.md` PR-10 to PR-16, PR-21, PR-26; QA D-05b; Product Owner R-1 and Section 2.4.

### D-05c - Human closure for dependents tied to consequential decisions

**Disposition:** Confirm as operationalization.

The model tightens STEP-01 rather than weakening it. PR-26 says a requirement remains until an authorized actor reaffirms, revises, or retires the dependent. ACT-07 and ACT-05 require human AUTH-G and independence for consequential decisions. If a non-decision dependent is cited by a consequential decision, closing the requirement on that dependent can effectively restore the decision's basis. Requiring a human, independent actor for that closure is a sound operationalization of the consequential-decision authority boundary.

The model appropriately leaves non-decision dependents outside consequential-decision support as EK-OQ-16. I do not recommend promotion to architecture unless STEP-03 chooses a broader rule that all revalidation closure must use AUTH-G.

**Relied on:** `prod-w/evidence-knowledge-model.md` Sections 10.4 and 10.8; EKR-37, EKR-38; `prod-w/protocol-semantics.md` ACT-05, ACT-07, PR-13, PR-16 to PR-21, PR-26; QA D-05c.

### D-05d - Duty to record contradicting information

**Disposition:** Confirm as operationalization.

The affirmative duty in EKR-18 is a product-level normative duty, and it should have been declared because it touches what counts as complete evidence conduct. Substantively, I confirm it. Without it, the model would preserve counter-evidence only once someone voluntarily records it, while the product failure pattern is that negative evidence disappears before becoming visible.

The model is honest about its enforcement limit: unrecorded information cannot be detected by the semantic model. That limit does not make the duty invalid; it makes breach detectable only through later challenge, lineage, disclosure, or inconsistency. STEP-03 should carry this forward as a conformance duty, not as a machine-checkable guarantee.

**Relied on:** `prod-w/evidence-knowledge-model.md` Sections 1.4 and 7.7; EKR-18, EKR-30; `prod-w/protocol-semantics.md` ACT-02 and ACT-03; QA D-05d; Product Owner Section 2.4.

---

## Open-Question Recommendations

### EK-OQ-17 - Correction designation and withdrawal of own counter-evidence

**Recommendation:** STEP-03 should require independent review for any post-acceptance producer designation that a change is a correction rather than a supersession, unless the original acceptor or another independent actor with the same acceptance authority confirms that meaning is unchanged.

Minimum recommended rule:

- A producer may propose and record a correction designation.
- If the item has never been accepted and is not cited by a consequential decision, that designation may stand unless challenged.
- If the item has been accepted, or is cited directly or indirectly by a consequential decision, the correction designation must be notified to the original acceptor where available and confirmed by an independent actor with authority for the affected scope.
- If independent confirmation is absent, the change is treated conservatively as a supersession for reliance purposes and can trigger revalidation.
- Withdrawal of own counter-evidence is allowed only as a visible historical event; it must not remove the prior contradiction from decision history, dependency exposure, or auditability.

Reason: otherwise PR-16 can be bypassed through item identity. A producer could make a meaning-changing edit, call it a correction, and keep another actor's past acceptance attached to new content.

### EK-OQ-05 - What counts as "the accepted item" for independence

**Recommendation:** STEP-03 should define "the accepted item" for consequential gate acceptance and consequential decisions as the decision record plus every material item that the decision relies on as basis, including cited claims, evidence, assumptions, hypotheses, inferences, dependency/materiality designations, and recorded responses to challenges that are necessary to the sufficiency determination.

This is stricter than item-text-only independence, but it matches the product risk. A gate acceptor who produced the demand claim, the crucial inference, or the non-materiality designation is not independent of the basis they are accepting, even if someone else authored the final decision record.

I recommend allowing STEP-03 to distinguish two cases:

- **Acceptance of the decision/gate:** independence should be evaluated over the material basis set.
- **Routine citation of background or non-material items:** independence should not be expanded automatically; the materiality mechanism should decide whether those items enter the basis set.

This should be first-priority STEP-03 work because it is the largest remaining self-approval gap.

### D-08 / EK-OQ-04 - Challenge, bare contradiction, exposure, and requirements

**Recommendation:** Confirm the model's intended split, but revise STEP-03 inputs so EK-OQ-04 covers both challenges and bare contradicting claims/inferences.

Recommended semantics:

- A challenge without counter-evidence produces visible contestation and exposure, not an automatic revalidation requirement.
- Counter-evidence produces a revalidation requirement on direct dependents with material dependency, as TRG-2 states.
- A bare contradicting claim or inference should not automatically create the same requirement as source-identified counter-evidence unless STEP-03 defines a threshold, because it is nearly as cheap as a challenge.
- A contradicting claim or inference should at minimum produce visible contestation and exposure, and it should permit any AUTH-A, AUTH-V, or AUTH-G actor to request revalidation through ACT-06.
- If STEP-03 wants bare contradicting claims/inferences to be triggers, it should state why they are treated differently from challenges and whether any authority, provenance, materiality, or sufficiency threshold applies.

I read EKR-39's phrase "Contradiction and challenge take visible effect immediately" as true but under-specified: the visible effect for a challenge should be exposure/contestation, not necessarily a requirement. STEP-03 should remove that ambiguity.

---

## Terms

### QA D-06 - Challenge and Inference

**Recommendation:** Revise the domain terms, not the model.

The model's expanded uses are justified and already declared in UAD-03 and UAD-10. The accepted glossary is now narrower than the accepted model:

- **Challenge** should be revised from targeting "a claim, inference, or decision" to targeting an item, relationship, or decision, with examples including evidence quality and support/dependency relationships.
- **Inference** should be revised from "drawn from evidence" to a reasoned interpretation derived from cited evidence, assumptions, or other inferences, with the constraint that citation chains must ground in evidence or assumptions and never become evidence themselves.

When the Moderator disposes of pending STEP-02 terms, I recommend treating Validation, Invalidation, Material dependency, Revalidation trigger, Revalidation requirement, Correction, Supersession, Withdrawal, and Exposure as load-bearing terms that should be accepted only with any STEP-03 changes reflected.

---

## MW-ADAPT-001 Re-evaluation

MW-ADAPT-001 asks two questions at the STEP-02 gate.

### Did the declaration produce findings?

**Yes.** Section 12 produced 16 declared choices. In my 2026-09-30 review, I confirmed UAD-01 to UAD-16 as valid STEP-02 operationalization after revision, with UAD-04 to UAD-07 identified as architecture-adjacent but not requiring promotion before STEP-02 acceptance.

### Did architecture-level content still slip past it?

**Yes, partially.** QA D-05 is evidence that the declaration did not catch every authority-, evidence-, and revalidation-touching choice. I classify the misses as follows:

| Ref | Slipped-past level | Recommendation |
| --- | --- | --- |
| D-05a | Model-level authority operationalization | Confirm; should have been declared |
| D-05b | Architecture-adjacent authority over reliance | Confirm with STEP-03 change; declare in STEP-03 |
| D-05c | Revalidation/authority operationalization | Confirm; should have been declared |
| D-05d | Product-level normative duty over evidence conduct | Confirm; should have been declared |
| EK-OQ-17 / Product Owner R-1 | Architecture-adjacent self-approval risk | Resolve in STEP-03 before gate mechanics harden |

This does not mean MW-ADAPT-001 failed uselessly. It produced findings and also revealed that a self-audit pass alone is incomplete. My recommendation is to keep MW-ADAPT-001 active for STEP-03, but strengthen it: after the Development Team declaration, the Tech Lead or QA should sample for unlisted choices in authority, independence, evidence standing, and revalidation before acceptance.

---

## Additional Findings

I found no additional substantive issue beyond QA D-05, D-06, D-08, Product Owner R-1/R-2, and the existing carry-forward list.

One carry-forward emphasis: STEP-03 should treat the all-dependents revalidation scope as a burden risk to test, not as a reason to weaken the model prematurely. The mechanism is product-intent aligned, but if every cheap contradiction or challenge creates requirements, teams may learn to ignore requirements. D-08 is therefore the pressure point that determines whether UAD-06 remains usable.

---

## Recommendation Summary

1. Confirm D-05a, D-05c, and D-05d as valid STEP-02 operationalization, while recording that they should have been declared.
2. Confirm D-05b with the STEP-03 changes above for correction, supersession, invalidation, and withdrawal of counter-evidence.
3. Resolve EK-OQ-17 and EK-OQ-05 early in STEP-03 because both are self-approval paths.
4. Expand EK-OQ-04/D-08 to cover bare contradicting claims and inferences, not only challenges.
5. Revise the accepted domain terms for Challenge and Inference to match the model.
6. Record MW-ADAPT-001 re-evaluation as: the declaration produced findings; architecture-adjacent content still slipped past it; keep the adaptation and add independent sampling.
