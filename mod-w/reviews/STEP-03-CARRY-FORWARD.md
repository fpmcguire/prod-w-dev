---
artifact:
  type: carry-forward-list
  from: QA (drafted for the MOD-W Moderator)
  to: Tech Lead, MOD-W Moderator
  date: 2026-10-01
  status: DRAFT - consolidated pointer list; no item below is disposed, accepted, or decided by this file
---

# STEP-03 Carry-Forward List

**Purpose:** Gather, in one place, everything STEP-02 left open or routed forward that STEP-03 (and later steps) must inherit, so the Tech Lead writing `step-03.md` does not have to find it across `qa.md`, the Product Owner sign-off, the Moderator addenda, the Tech Lead follow-up, and the model.

**This file is a pointer list.** The sources govern. If this list disagrees with a source, the source is right and this file should be corrected. Nothing here disposes of any item. "Owner" means who would act next, not who has decided.

STEP-03 per `mod-w/roadmap.md`: _Define Gate, Challenge, Disagreement, and Revalidation Semantics_ (FR-2, FR-3, FR-5, FR-7). Per `mod-w/step-02.md` Out of Scope, complete gate mechanics, challenge routing, disagreement resolution, waiver mechanics, and escalation paths belong primarily to STEP-03.

---

## A. Open questions the model routed to STEP-03

Source: `prod-w/evidence-knowledge-model.md` Section 13.1 unless noted.

| ID           | Question (short)                                                                                                                                                                                                                     | Notes                                                                                                                                                            |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| EK-OQ-02     | Who may accept validation of a material hypothesis not tied to a consequential gate? AUTH-G or lesser?                                                                                                                               | Also PS-OQ-09                                                                                                                                                    |
| EK-OQ-03     | May a team, organization or agent fleet be a single actor identity? How is delegation recorded?                                                                                                                                      | Also PS-OQ-06. The evidence-source half was settled by the source/producer distinction (UAD-11).                                                                 |
| EK-OQ-04     | Does an unresolved challenge on an upstream material item itself create a requirement? May reliance continue while a requirement is open or exposure exists? What must respond to an unanswered challenge cited in a decision basis? | Related QA D-08, Product Owner A-2                                                                                                                               |
| EK-OQ-05     | Which set of items is "the accepted item" for independence when a decision cites items produced by others or by the decision-maker?                                                                                                  | **Product Owner A-1: first-priority.** Largest remaining self-approval gap.                                                                                      |
| EK-OQ-06     | How does supersession or invalidation of another actor's item become effective, and by whom?                                                                                                                                         | Also PS-OQ-07. Related QA D-05b.                                                                                                                                 |
| EK-OQ-07     | How is a disputed materiality designation resolved?                                                                                                                                                                                  |                                                                                                                                                                  |
| EK-OQ-08     | Complete form of a conditional-progression authorization; relation to gate waivers                                                                                                                                                   | Also PS-OQ-12, GR-7                                                                                                                                              |
| EK-OQ-10     | Can the passage of time or evidence age itself create a revalidation requirement?                                                                                                                                                    |                                                                                                                                                                  |
| EK-OQ-11     | Are conditions such as contested, validated or open-requirement explicit state or derived from the record? How is "current validity" represented?                                                                                    | Shared with STEP-05; PS-OQ-01                                                                                                                                    |
| EK-OQ-13     | Is unresolved disagreement a named condition, a relationship, or an artifact property?                                                                                                                                               | PS-OQ-03; product OQ-3                                                                                                                                           |
| EK-OQ-16     | Who may reaffirm, revise or retire a dependent that is not a decision when a requirement is open on it?                                                                                                                              | Related QA D-05c                                                                                                                                                 |
| **EK-OQ-17** | **Who designates a post-acceptance change as a correction; may a producer withdraw its own counter-evidence?**                                                                                                                       | **Recorded outside the model**, in `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md` (Addendum 2026-10-01). Roadmap STEP-03 row points to it. Product Owner R-1 / B-1. |
| EK-OQ-01     | Required evidence categories per gate; criteria for "required evidence and challenge criteria"                                                                                                                                       | Shared with STEP-06 and product OQ-2                                                                                                                             |

## B. Routed to STEP-04, STEP-05, or STEP-08 (listed so STEP-03 does not duplicate them)

| ID / Topic | Question (short) | Routed to |
| --- | --- | --- |
| EK-OQ-09 | Granularity of producing-configuration and lineage recording; does insufficient provenance invalidate or only weaken | STEP-04 (PS-OQ-13). Research input, not a requirement: whether skill name and version belong in the recorded producing configuration; see `research/topics/agent-skills-and-protocol-relationship.md` (Routing). |
| EK-OQ-12 | Realization of item identity across change (representation only, not authority; the authority question is EK-OQ-17) | STEP-05 |
| EK-OQ-14 | Which EKO conditions become machine-checkable rules; handling of detected violations | STEP-04 (PS-OQ-10) |
| EK-OQ-15 | Separating role-specific and machine views of the knowledge model | STEP-05 |
| Agent skills H-C | Whether skills can be generated projections of the protocol | STEP-05. Research input only; do not treat as selecting a representation, prompt format, harness, or runtime integration. |
| Agent skills hypotheses | Disposition of H-A skills beneath protocol, H-B skills as producing configuration, and H-C skills as protocol projections | STEP-08. Incorporated, deferred, or rejected only during research synthesis. |

## C. Points to decide or confirm before or during STEP-03 definition

| Ref               | Item                                                                                                                                                                                      | Source                                                                                  | Owner (next action)                                                   |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| QA D-05a to D-05d | Four authority- and revalidation-touching choices not listed in the model's Section 12                                                                                                    | `qa.md`; `TECH-LEAD-REVIEW-STEP-02-FOLLOWUP.md`; Moderator review final addendum        | Confirmed for STEP-02; D-05b details feed STEP-03                     |
| QA D-08           | Ambiguity between EKR-39 ("challenge takes visible effect immediately") and Section 10.5 ("challenge alone is not a trigger"); a bare contradicting claim triggers revalidation by itself | `qa.md`; Product Owner A-2; Tech Lead follow-up; Moderator review final addendum        | Resolve in STEP-03 by widening EK-OQ-04                               |
| QA D-06           | Accepted terms "Challenge" and "Inference" disagreed with the model's use                                                                                                                 | `qa.md`; Product Owner A-7; Tech Lead follow-up; `mod-w/domain-language.md`             | Resolved for STEP-02 by glossary correction; STEP-03 may revise later |
| QA D-02           | STEP-01 and STEP-02 proposed terms needed disposition                                                                                                                                     | `qa.md`; Product Owner A-7; Moderator review final addendum; `mod-w/domain-language.md` | Resolved for STEP-02; load-bearing terms remain STEP-03-sensitive     |

## D. Product Owner advisory items (3c)

Source: `mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-02.md` Section 3.2. All advisory; none disposed.

| Ref | Advisory (short)                                                                                                                                                                                                        | Applies to                                                               |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| A-1 | Treat EK-OQ-05 as first-priority STEP-03 entry work                                                                                                                                                                     | STEP-03                                                                  |
| A-2 | Resolve D-08: state whether challenge and bare contradicting claims produce exposure, a requirement, or neither; widen EK-OQ-04 to cover contradicting claims                                                           | STEP-03                                                                  |
| A-3 | Consider whether a claim whose support traces entirely to assumptions should be identifiable as assumption-rooted                                                                                                       | STEP-03 / STEP-04                                                        |
| A-4 | Observe in the proof of concept whether product assumption A-5 (background knowledge distinct from material claims) collides with EKR-22 (every relied-on unverified proposition is recorded); record as pilot evidence | Pilot                                                                    |
| A-5 | Plan a burden check (E-2, Acceptance Criterion 3) on the all-dependents revalidation scope and presumed materiality; treat friction as evidence for narrowing, not for dropping intent                                  | STEP-03 / pilot                                                          |
| A-6 | In STEP-05, do not treat EKR-09, EKR-33 or EKR-40 as selecting a ledger or central state model (NG-1, NG-4, Appendix A)                                                                                                 | STEP-05                                                                  |
| A-7 | When disposing of pending terms, reconcile "Inference" and "Challenge"; treat Validation, Invalidation, Material dependency and Revalidation requirement as load-bearing                                                | Resolved for STEP-02 by glossary correction; STEP-03 may revise later    |
| A-8 | Confirm EKR-18 and the Section 10.5 withdraw/supersede/invalidate split as declared choices                                                                                                                             | Resolved for STEP-02 by Tech Lead follow-up and Moderator final addendum |
| A-9 | Record items D-03, D-04, D-07 (stale observation text, missing MW-ADAPT-001 re-evaluation, stale delivery statement)                                                                                                    | Resolved by Moderator final addendum and register updates                |

## E. Model passages near gate mechanics that STEP-03 should revisit

Flagged in `mod-w/reviews/qa.md` Notes. Not defects.

- Section 9.4 / EKR-30 / UAD-13: decision records must cite challenges and contradicting items recorded against their basis. Stated as record content only; STEP-03 owns the gate consequences.
- EKR-41: rule constraining implementations ("may block or flag; must not decide"). Declared and hedged; STEP-03/STEP-04 should confirm the boundary.
- Section 10.2 / EKR-35 / UAD-05: presumed materiality for items cited by a consequential decision or gate acceptance.
- Section 10.4 / EKR-37 / UAD-06: revalidation requirements applied to every dependent item, not decisions only (extends PR-26 and WD-6).
- UAD-04 to UAD-07: architecture-adjacent choices the Tech Lead ruled need no promotion. `mod-w/architecture.md` is unchanged, so these rules live only in the model.

## F. Process items from STEP-02 that affect STEP-03 working

| Item                                                                       | Source                                                                               | Note                                                                                    |
| -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------- |
| MW-ADAPT-001 re-evaluation recorded                                        | `qa.md` D-04; `adaptations.md`; Tech Lead follow-up; Moderator review final addendum | Declaration remains required for STEP-03; add independent sampling for unlisted choices |
| Plan gate (2a) and build gate (2b) not instantiated for specification work | MW-OBS-012 (accepted); MW-OBS-008 (accepted)                                         | Observe again at STEP-03                                                                |
| MW-OBS-011, MW-OBS-012, and MW-OBS-013 dispositions recorded               | `observations.md`; Moderator review final addendum                                   | Bodies preserve historical text; dispositions govern current status                     |
| Agent-skills carry-forward experiment                                      | `research/topics/agent-skills-and-protocol-relationship.md`                          | At STEP-03 close-out, consider the planned MOD-W-level experiment on carry-forward consolidation as a proposed transferability observation; this adds no PROD-W requirement. |
| 3b/3c ran after acceptance (sequence deviation)                            | Moderator review, Addendum 2026-10-01                                                | Hold 3a/3b/3c before acceptance at STEP-03, or record any waiver beforehand             |
| `step-02-complete` tag                                                     | MOD-W 4a                                                                             | Create after final STEP-02 closure commit                                               |

## G. STEP-01 questions still open

STEP-01's open questions (`prod-w/protocol-semantics.md`, Section 11) were partly addressed by STEP-02 (PS-OQ-04, PS-OQ-06, PS-OQ-13: see model Section 13.2). Others, such as PS-OQ-01, 02, 03, 07, 09, 10, 12, were not resolved by STEP-02 and appear above only where the model cross-referenced them. This list does not reproduce the full STEP-01 set; check Section 11 of that file when writing `step-03.md`.

## H. Moderator Research Topic Additions

`research/topics/agent-skills-and-protocol-relationship.md` was added as a Moderator-derived research note. It is explicitly non-normative: it does not create a PROD-W requirement, change MOD-W, select an agent harness, select a prompt/skill format, or reopen STEP-01 or STEP-02.

STEP-03 should treat it only as background research where it intersects carry-forward routing:

- producing-configuration granularity belongs with EK-OQ-09 / STEP-04;
- skills-as-generated-projections belongs with STEP-05 representation work;
- hypothesis disposition belongs with STEP-08 research synthesis;
- the planned carry-forward-consolidation skill experiment belongs, if run, in the MOD-W transferability record, not in the STEP-03 product artifact.
