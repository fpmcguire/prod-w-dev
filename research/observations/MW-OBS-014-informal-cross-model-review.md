## MW-OBS-014 - Informal Cross-Model Review of a Research Question Caught a Mismatch with Accepted Semantics, and Each Reviewer Failed in a Different Place

**Date:** 2026-10-01 to 2026-10-02 (event); recorded 2026-10-02  
**MOD-W area:** Cross-validation; Product Definition tooling (informal second-model review); Moderator reconciliation  
**Project stage:** Research question raised during STEP-03 implementation, before Tech Lead review of the Development Team's initial work; outside any Step  
**Observed by role:** None. Drafted by the second reviewer (Claude, in a chat session outside MOD-W role assignments) at the Moderator's request  
**Classification (Proposed):** `TRANSFERS_UNCHANGED` for informal cross-model review as a concept  
**Status:** Proposed for Moderator review  
**Significance:** Low to Medium  
**Related:** MW-OBS-002, MW-OBS-007, MW-OBS-009, MW-OBS-010

### Scope caveats, stated first

1. **This may not be a non-software finding.** Like MW-OBS-009, it may be an AI-assistance finding that would arise equally in a software project. The Moderator should decide whether it belongs in this register.
2. **This is a self-report.** The drafter is one of the two reviewers and is describing its own review. It should not be accepted on the strength of this text alone.
3. **No MOD-W Step or gate was involved.** The exchange was a research discussion. No role session, review artifact, or gate ran.

### MOD-W Mechanism or Assumption

`mod-w/templates/MOD-W.md` states that MOD-W "enforces cross-validation between multiple AI agents and models", with the Moderator reconciling all outputs (Cross-validation section).

MOD-W names two forms:

- **Formal:** role-separated review within a Step, with `cross-validation.md` recording the Claude/Codex validation mode and discrepancies going to `validation/`.
- **Informal:** the Product Owner's definition-phase tooling lists more than one chatbot (line 14 of the template), which canonical MOD-W describes as informal cross-validation.

The assumption is that a second model with a different vantage point will catch what the first missed, and that a human decides what the difference means.

MOD-W does not describe informal cross-model review of a research question that arises mid-project, outside Product Definition and outside a Step.

### Observation

The Moderator discussed Agent Skills best practice with ChatGPT. That discussion produced a proposed four-part decomposition for PROD-W (protocol, skills, roles/agents, harness). The Moderator summarized it in a context document and asked Claude for an independent critique, with an explicit instruction not to simply validate it.

**What the second review found.** Reading the accepted `prod-w-dev` artifacts and the canonical MOD-W repository, the second reviewer reported that the proposal:

- illustrated the protocol as named workflow states and role-name approvals, where `prod-w/protocol-semantics.md` Section 10 deliberately defines no state names and PR-01 and PR-03 say a role name never confers authority;
- merged role and actor, which Sections 4.1 and 4.2 separate;
- treated skills as a new layer, where PR-27 already places instructions and tooling in an action's provenance;
- did not account for Section 6.5: runs that share instructions cannot see a defect in those instructions, which bears on a skill shared by a producer and an evaluator.

**What the second review got wrong.** When the `prod-w` repository was made readable, the second reviewer treated its contents as meaningful and reported "drift" between `prod-w` and `prod-w-dev`. The Moderator corrected this: `prod-w` is a placeholder. The reviewer withdrew that finding.

**Who caught what.** The first reviewer lacked the accepted artifacts. The second reviewer lacked the status of `prod-w`, which is not visible in the files. The Moderator held the context that settled both.

**Outcome.** No accepted artifact, roadmap entry, or Step was changed. The question was recorded as competing hypotheses in `research/topics/agent-skills-and-protocol-relationship.md`, and one pointer was added to the EK-OQ-09 row of `mod-w/reviews/STEP-03-CARRY-FORWARD.md`.

**Secondary note.** The second reviewer numbered its recommendations 1 to 4. The Moderator briefly read "step 2" as STEP-02 and was concerned an accepted Step would be reopened. It was resolved by clarification. In a project that identifies work by STEP-NN, plain numbered lists in reviewer output can collide with Step identifiers.

### Evidence

- `research/topics/agent-skills-and-protocol-relationship.md` (the recorded outcome; lists both sources as not archived)
- `mod-w/reviews/STEP-03-CARRY-FORWARD.md`, Section B, EK-OQ-09 row (the pointer)
- `prod-w/protocol-semantics.md` Sections 4.1, 4.2, 6.5, 10; PR-01, PR-03, PR-27
- `mod-w/templates/MOD-W.md` line 3, line 14, and the Cross-validation section
- Canonical MOD-W `docs/role-tooling-matrix.md` (Product Definition Tooling; Cross-Validation Design)
- The Moderator's context document and the Claude review conversation. **Neither is archived in this repository**, by Moderator decision. This weakens the evidence: the findings above cannot be checked against the originals from the repository alone.

### Contradictory Evidence, Preserved

- **The second review was not independent of the first.** It worked from a summary of the first reviewer's analysis. In the terms of canonical `cross-validation.md` this resembles `sequential` mode, where the first output is the baseline. No `parallel` pass was run, in which the second model answers the question cold.
- **There was no ground truth.** Whether the second reviewer's findings are correct has not been checked by any MOD-W role. They are advisory findings.
- **The second reviewer made an error of the same kind it criticized:** reasoning from material without checking its standing.
- **Agreement or disagreement between two models is not evidence** (PR-20). What resolved each point was the Moderator's knowledge, not the exchange.
- **Sample of one**, on a research question with no gate consequence.

### Effect on Work

- A proposed architecture was not adopted into PROD-W on the strength of one model's plausible reasoning.
- The question was preserved as hypotheses and routed to STEP-04, STEP-05, and STEP-08, without touching STEP-03.
- The cost was one review conversation and Moderator attention to correct two misreadings.

### Local Adaptation Required

None. No adaptation is proposed.

Offered for Moderator consideration only, not as an adaptation:

1. When seeking a second-model opinion, give the second model the accepted artifacts, not only a summary of the first model's reasoning.
2. Where the question matters, consider a cold pass before showing the second model the first model's answer.

### Interpretation

The concept appears to transfer without reinterpretation: a second model with different inputs surfaced a mismatch, and the human Moderator reconciled it. This is the pattern MOD-W describes, applied to research work at a point MOD-W does not name.

The mechanism that did the work was **difference in available context plus human reconciliation**, not model difference alone. The second reviewer had read the accepted artifacts; the first had not. The observation cannot separate the effect of a different model from the effect of different inputs.

**Conclusion (deliberately limited):** one exchange, one research question, no gate, reported by a participant. It supports the claim that informal cross-model review is useful in methodology work. It does not show that it is reliable, and it shows that the second reviewer needs correcting too.

### Follow-up

- Moderator determines whether this belongs in this register, given scope caveat 1.
- Moderator determines the classification.
- If the pattern recurs, observe whether supplying accepted artifacts to the second reviewer, or running a cold pass, changes what is caught.
- Observe whether numbered lists in reviewer output collide with Step identifiers again.

### Moderator Disposition

Pending.

---
