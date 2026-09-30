---
artifact:
  type: discrepancy-report
  version: 0.1
  created: 2026-09-30
  updated: 2026-09-30
  status: Reported - awaiting MOD-W Moderator disposition
  from: Development Team
  to: MOD-W Moderator
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
  surfaced_during: STEP-01
---

# Development Team Discrepancy Report - Transferability Classification Vocabulary

## Purpose

This report records inconsistencies found in the MOD-W transferability research governance artifacts while executing STEP-01. The Development Team encountered them because it had to select a classification for two proposed observations and found that the authoritative sources disagree about what the available classifications are.

**No corrections have been made.** Every artifact involved is owned by the MOD-W Moderator, the Tech Lead, or the Product Owner, and one of them is the accepted Product Definition. This report proposes resolutions and changes nothing.

---

## Summary

| ID | Defect | Affected artifacts | Severity | Blocking? | Authority required |
| --- | --- | --- | --- | --- | --- |
| DTD-01 | Two competing classification vocabularies exist in accepted artifacts | `research/mod-w-transferability/README.md`, `mod-w/product.md`, `mod-w/step-01.md`, `mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-TECH-LEAD.md` | Medium | No | MOD-W Moderator |
| DTD-02 | `DOMAIN_COUPLED` is absent from the vocabulary given to evidence-producing roles | `mod-w/step-01.md`, `mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-TECH-LEAD.md` | High | Yes, for MW-OBS-008 disposition | MOD-W Moderator |
| DTD-03 | `PARTIALLY_TESTED` is used as a classification but defined nowhere | `research/mod-w-transferability/assessment.md` | Low | No | MOD-W Moderator |
| DTD-04 | `assessment.md` has not been updated since the Product Definition phase and now contradicts the register it synthesizes | `research/mod-w-transferability/assessment.md` | Medium | No | MOD-W Moderator |

---

## DTD-01 - Two Competing Classification Vocabularies

### Evidence

**Vocabulary A** - the accepted Product Definition and the Moderator-owned research governance:

- `research/mod-w-transferability/README.md` lines 132-154 (section headers defining each classification)
- `mod-w/product.md` lines 387-391

Values: `TRANSFERS_UNCHANGED`, `TRANSFERS_WITH_REINTERPRETATION`, `REQUIRES_LOCAL_ADAPTATION`, `DOMAIN_COUPLED`, `NOT_YET_TESTED`

**Vocabulary B** - the step-level instruction to implementing roles:

- `mod-w/step-01.md` line 133
- `mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-TECH-LEAD.md` line 138

Values: `TRANSFERS_UNCHANGED`, `TRANSFERS_WITH_REINTERPRETATION`, `LOCAL_ADAPTATION_PROPOSED`, `NOT_YET_TESTED`

### Effect

Three observations in the register carry `LOCAL_ADAPTATION_PROPOSED`, a value its own governance document does not define:

- MW-OBS-006 (line 373) - **Accepted**
- MW-OBS-007 (line 443) - Proposed
- MW-OBS-008 (line 514) - Proposed

MW-OBS-006 is the sharper case: the *accepted* research record contains a classification string undefined by the research governance that accepted it.

### Interpretation

The rename alone is cosmetic. `LOCAL_ADAPTATION_PROPOSED` is arguably the better name, since it carries the disposition state (proposed, not authorized) that README's Observation-vs-Adaptation rule is careful to preserve. The defect is the divergence, not the wording.

### Proposed resolution (Moderator decides)

Pick one vocabulary and make the other conform. If Vocabulary B's name is preferred, README and the Product Definition need an authorized update, and the Product Definition change is Product Owner work. If Vocabulary A is preferred, the step instruction and the three observations need correcting - and per README's historical-integrity rule, correcting an **accepted** observation (MW-OBS-006) should follow the annotation pattern already established by TLR-007 rather than an in-place rewrite.

---

## DTD-02 - `DOMAIN_COUPLED` Omitted From the Instruction to Evidence-Producing Roles

This is the substantive defect. DTD-01 is a naming divergence; this is a missing option.

### Evidence

`DOMAIN_COUPLED` is defined in `research/mod-w-transferability/README.md` line 146 and listed in `mod-w/product.md` line 390. It is absent from the four-value list in `mod-w/step-01.md` line 133 and in the Tech Lead review feedback line 138.

Across the whole repository, `DOMAIN_COUPLED` appears only in those two definitional locations. **It has never been used to classify an observation.**

### Why this matters

`DOMAIN_COUPLED` is the register's only classification that records a negative finding - that a MOD-W mechanism may not transfer. README's Research Neutrality section requires the research to "actively seek evidence both for and against" and states that mixed evidence must remain mixed. README's own definition of `DOMAIN_COUPLED` includes a safeguard making it safe to use: the classification "does NOT automatically mean canonical MOD-W should change."

The option was designed to be usable without threatening canonical MOD-W, and was then omitted from the instruction handed to the role producing the evidence.

### Demonstrated effect, not hypothetical

MW-OBS-008 records that MOD-W's Phase 2b blocking build gate has no instantiation for a specification deliverable. The finding is that the gate's *defining properties* - mechanical, blocking, reviewer-independent - depend on the deliverable being executable. Under Vocabulary A that is a candidate `DOMAIN_COUPLED` observation.

Working from Vocabulary B, the Development Team had no such option and classified the component `LOCAL_ADAPTATION_PROPOSED`, which frames a possible domain-coupling finding as a procedural gap that a local fix resolves.

`mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-DEV-TEAM.md` Section 5 item 2 recommends accepting that classification. If accepted as proposed, the accepted record will carry the softened framing.

### Pattern worth checking

Nine observations are on record. Their classifications are three `TRANSFERS_UNCHANGED`, one `NOT_YET_TESTED`, two `TRANSFERS_WITH_REINTERPRETATION` plus one mixed, and three `LOCAL_ADAPTATION_PROPOSED`. None is `DOMAIN_COUPLED`.

`assessment.md` lines 64-70 reports that absence as a finding: "No observations have yet classified any MOD-W mechanism as systematically domain-coupled to software."

**This is not evidence that the record is distorted.** It may simply be true that no domain coupling has been found. The point is narrower and it is about method: the absence is currently being reported as a research result, while the instruction given to evidence-producing roles omitted the option that would record it. Until the vocabularies agree, that particular absence cannot be relied on as a finding.

### Proposed resolution (Moderator decides)

1. Restore the negative classification to every instruction given to evidence-producing roles.
2. Before disposing of MW-OBS-008, decide whether the build-gate component is `DOMAIN_COUPLED` rather than a local-adaptation case. The Development Team has flagged MW-OBS-008 accordingly and has not changed its proposed classification.
3. Consider whether MW-OBS-003's registered open questions should be re-examined against the full vocabulary, since they were registered as `NOT_YET_TESTED` and two of them are now partly answered.

---

## DTD-03 - Undefined Classification `PARTIALLY_TESTED`

`research/mod-w-transferability/assessment.md` line 254 classifies "Review/approval processes" as `PARTIALLY_TESTED`. That value appears in no vocabulary - not README, not the Product Definition, not the step instruction.

This is a third vocabulary, of one value, in the synthesis layer.

**Proposed resolution:** either define it in README as a legitimate synthesis-level status distinct from observation classifications, or replace it. If the intent was "some evidence, insufficient to classify," README's `NOT_YET_TESTED` explicitly warns against using that as a default, so a defined synthesis-level status may genuinely be the better answer.

---

## DTD-04 - `assessment.md` Is Stale and Now Contradicts the Register

README's Assessment and Review Cadence requires the Moderator to update `assessment.md` per stage gate. It has not been updated since the Product Definition phase, and the register has moved past it.

Contradictions between `assessment.md` and the current contents of `observations.md`:

| `assessment.md` states | Register actually contains |
| --- | --- |
| Line 18: "Project stage: Product Definition phase, pre-acceptance" | Product Definition accepted 2026-09-30; architecture accepted; STEP-01 delivered |
| Line 50: "Transfers With Reinterpretation - Accepted observations: None yet" | MW-OBS-004, Accepted, `TRANSFERS_WITH_REINTERPRETATION` |
| Line 58: "Requires Local Adaptation - Accepted observations: None yet" | MW-OBS-006, Accepted, `LOCAL_ADAPTATION_PROPOSED` |
| Line 40: "Accepted observations: 2 (MW-OBS-001, MW-OBS-002)" under Transfers Unchanged | MW-OBS-005 is also Accepted and `TRANSFERS_UNCHANGED` |
| Lines 251-253: Architecture concepts, Tech Lead role, Implementation semantics all `NOT_YET_TESTED` | MW-OBS-004 addresses architecture; MW-OBS-008 addresses implementation semantics |

The synthesis layer currently **understates** the project's own findings in both the reinterpretation and local-adaptation categories, and reports as untested three areas the register has since produced evidence on.

**Proposed resolution:** a Moderator synthesis pass at the STEP-01 gate, which README already requires. Noted here rather than corrected, because `assessment.md` is a Moderator-owned synthesis and a Development Team rewrite of it would be exactly the kind of boundary crossing reported in MW-OBS-010.

---

## Self-Authorized Corrections

None. No artifact named in this report has been modified.

The only change the Development Team made in response to these findings is an appended, dated note on its own proposed MW-OBS-008 flagging that the classification is under question pending DTD-02. The proposed classification itself was left as originally recorded so that the Moderator review referencing it remains accurate.

---

## MOD-W Moderator Decisions Required

1. Which classification vocabulary is authoritative (DTD-01), and how are the three affected observations reconciled given that one is accepted.
2. Whether `DOMAIN_COUPLED` is restored to role-facing instructions (DTD-02).
3. Whether MW-OBS-008's build-gate component should be reclassified before disposition (DTD-02). **This is the one item that blocks a pending decision.**
4. Whether `PARTIALLY_TESTED` is defined or removed (DTD-03).
5. When the `assessment.md` synthesis pass occurs (DTD-04).

---

## Provenance

Surfaced during STEP-01 execution by the Development Team while selecting classifications for MW-OBS-008 and MW-OBS-009. Producing configuration recorded per the provenance principle the same step defined (`prod-w/protocol-semantics.md` PR-27): Claude Opus 5, executing the Development Team role under `mod-w/step-01.md`.
