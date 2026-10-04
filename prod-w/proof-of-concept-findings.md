---
artifact:
  type: pilot-findings
  id: PROD-W-POC-FND
  version: 0.1
  created: 2026-10-04
  updated: 2026-10-04
  status: Draft - Development Team work product for STEP-07. Not reviewed. Not accepted.
  produced_by: Development Team
  produced_under: STEP-07
source:
  step: mod-w/step-07.md
  trial: prod-w/proof-of-concept-trial.md
  records: prod-w/proof-of-concept-records.md
  issues: prod-w/proof-of-concept-issues.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Proof-of-Concept Findings

**Status:** Draft v0.1. Development Team work product for STEP-07. Not reviewed. Not accepted.
**Standing:** Pilot findings, stated conservatively. They are Development Team observations until a reviewer adopts them. The "reviewer lens" column says which review point each finding is addressed to. It does not mean that reviewer has made it.

**Read first.** One AI session wrote every record, including the simulated human positions. Gate outcomes and five events were scripted (`prod-w/proof-of-concept-records.md` §0). A finding below that says "demonstrates" means *the records show it in this one case*, which is a statement about record shape and rule application. It is not a statement about how people behave, and it is not a statement about the opportunity.

**Wording used.** *Demonstrates* = shown by records in POC-1 itself. *Suggests* = consistent with the records and not shown. *Not exercised* = stated reason. Scenario observations (records Appendix S) are not evidence and are labeled so.

---

## 1. What the Pilot Demonstrates

| ID | Finding | Evidence | Maps to | Reviewer lens |
| --- | --- | --- | --- | --- |
| D-1 | One bounded opportunity can be taken through project establishment, source registration, claims, evidence, counter-evidence, negative findings, assumption, hypothesis, inference, two defined gates, challenge, formal checks, revalidation, and a stop, using the STEP-06 templates, without needing a rule the templates lack or a change to any accepted artifact. | R-001 to R-058; no accepted artifact modified (see §6 below). | AC-3, E-1 | Tech Lead protocol-conformance |
| D-2 | The kinds of record stayed separable in use. Evidence, counter-evidence, negative finding, inference, assumption, and hypothesis each had a distinct record, and an inference's chain reached evidence. Counter-evidence (EV-03, EV-07) was attached with the same formality as support. | R-014 to R-031, R-026, R-045 | E-6, FR-3 | Tech Lead; QA sample |
| D-3 | A hypothesis could be left visibly unvalidated, with criteria recorded before any test, and a gate that needed it could be refused for exactly that reason. An agent reader was available and was not used as a stand-in. | R-019, R-051, R-057 | E-6, FR-7, E-3 | Tech Lead |
| D-4 | Authority and independence could be read from the record. A grant review found, before the GD-B attempt, that the only independent acceptor had become a producer, and the authority-gap record named why each holder failed. | R-049, R-050, R-052 | E-7, E-5, FR-1 | Tech Lead; QA sample |
| D-5 | Self-approval was visibly invalid. The attempted acceptance by the founder was kept in the record, a finding named three rules it violated, each decidable from the record, and no pilot claim relies on it. | R-054, R-055 | E-3, FR-4 | Tech Lead; QA |
| D-6 | A gate refusal, an acceptance with named residuals, and a visible stop could each be recorded without a lifecycle graph or a state vocabulary. The earlier refusal was cited in the later acceptance with what changed. | R-033, R-044, R-057 | E-8, FR-5 | Tech Lead |
| D-7 | A formal-check result could be recorded with effect claimed and effect not claimed, and it did not become acceptance. A criterion that is not decidable ("the sources are independent") was recorded as unresolved with its checkable part separated. | R-037 to R-039, R-044 | E-9 | Tech Lead; QA |
| D-8 | Conditional progression was recordable for an assumption (ground G1), left the requirement open, and was not inherited by the second gate. | R-043, R-051 | E-8, FR-7 | Tech Lead |
| D-9 | Sourced counter-evidence found after an acceptance produced a Tier 1 requirement on that acceptance, which stayed open and was cited as open in later records. | R-045, R-046, R-047, R-057 | E-8, FR-6 | Tech Lead |
| D-10 | A consequential commitment outside the gates could be recorded with the reliance on unvalidated items stated and the founder's producer status disclosed. | R-047 | E-3, FR-7 | Tech Lead; Product Owner |
| D-11 | Real evidence about a method opportunity can be gathered from the repository without inventing testimony. Two tests and two searches were recorded with retrieval markers and limits. | R-009 to R-013, R-022, R-023, R-028, R-029 | E-6 | QA |

**What these do not show.** None of D-1 to D-11 shows that people would do the same, that independent actors would find the same defects, or that the same cost would hold at larger size.

---

## 2. What the Pilot Suggests but Does Not Demonstrate

| ID | Finding | Why only suggested | Maps to | Reviewer lens |
| --- | --- | --- | --- | --- |
| S-1 | The common block and the templates are heavy: 58 records, about 14,000 words, with the producing-configuration reference repeated in 32 of 58 records, for one small opportunity. | Counts are the AI's own output. No human filled any record, no human time was measured. Consistent with the Product Owner's note ("usable but heavy"). | E-1, E-2 | Product Owner usability |
| S-2 | The readiness checklist makes unmet conditions listable in one place and gave each refusal its reasons. | The script already knew the answers and one actor wrote both. Whether it prevents invalid acceptances is not separable (ISS-12). | E-3, E-2 | Product Owner; QA |
| S-3 | A two-human team can lose its only independent acceptor to a helpful reviewer, because the challenge template invites supplying wording. | The event was scripted, and the template wording made it easy (ISS-06). A real reviewer's behavior is not tested. | E-5, E-7, FR-4 | Product Owner; Tech Lead |
| S-4 | The root-grant checklist's first row nudges a solo founder toward an acceptance grant that cannot validly be used, which is a false-authority risk at the start. | Seen in the establishing act and in the scripted attempt. No real founder. Scenario S-1 agrees but is not evidence (ISS-15). | E-2, E-7, FR-4 | Product Owner |
| S-5 | A hand-derived Standing Card goes stale: four of nine answers were wrong after 13 later records. A card derived by hand cannot be relied on without a check against the record. | One card, one interval, one producer, self-generated (ISS-11). Consistent with the project's own position in `RO §12.4`. Says nothing about whether readers want a card. | E-6 (about the opportunity only) | Development Team observation |
| S-6 | Claim records cannot carry later links under append-only practice, so reading standing means scanning. | Counted at 31 records. A larger record was not tried (ISS-02). | E-1, E-2 | Tech Lead; Product Owner |
| S-7 | The record-versus-document distinction works for sources, evidence, and designations and is unclear for rationale text and issue entries. | One writer decided where to put them (ISS-09). | E-2 | Product Owner |
| S-8 | The weak points the guidance names for record order and instruction binding are real in a one-writer file. | The pilot cannot show whether they are exploitable (ISS-10, ISS-19). | E-9, E-1 | Tech Lead |
| S-9 | Two honest results about the opportunity itself, offered only as pilot content: the repository contains no reader statement that standing is hard to read (AT-02), and a card exists only as prompts (AT-01). | Repository-only reach. Absence of a statement is not absence of a need. **Neither result is a market finding.** | AC-3 | Development Team observation |

---

## 3. What the Pilot Failed to Exercise

| ID | Not exercised | Reason | Route |
| --- | --- | --- | --- |
| N-1 | Independent human behavior at any step | One AI session wrote everything. | ISS-01 |
| N-2 | Actor-kind binding as a real weak point | No human act; the note says "none stated". | ISS-01 |
| N-3 | Real disagreement | One writer. Positions were scripted. The pilot proves only that disagreement stays visible when recorded. | ISS-01 |
| N-4 | An exception (T-18) | Nothing waivable was unsatisfied. Scenario only (S-2). | Appendix S |
| N-5 | A grant act after establishment (T-3), and any cure of the authority gap | No cure was pursued. The conferral scenario (S-3) is not evidence. | Appendix S |
| N-6 | Closure of the revalidation requirement | A Tier 1 closure needs an independent human with authority, and AG-1 shows none for the GD-B set. A fresh GD-D acceptance was not attempted. | R-046, R-052 |
| N-7 | Acceptance of a build/no-build gate on real reader evidence | The reader-evidence slot is empty by design. | ISS-07 |
| N-8 | Validation of any hypothesis | HY-01 had no test and no human reader. | R-019 |
| N-9 | Recognition of an unforeseen consequential commitment | The commitment was scripted and matched a pre-stated definition. | ISS-17 |
| N-10 | Imported prior work (T-26) | No earlier project. | R-058 |
| N-11 | Human time and burden | No human filled any record. | ISS-20 |
| N-12 | Three-human plus agent execution in a working cadence; two-human accidental co-production beyond the scripted case; solo-founder use by a real founder | Scenarios only (S-1, S-4, S-5). | Appendix S |
| N-13 | Same-day counter-evidence recording as a team habit | One writer in one sitting makes it trivial. | R-026 |
| N-14 | Source-based corroboration across independent sources | Real sources were repository text; none external. | ISS-11 |

---

## 4. STEP-06 Practice Defaults: Workable, Burdensome, Unclear, Not Tested

| Practice default | Assessment | Evidence and note |
| --- | --- | --- |
| G §4: establishing act and root grants, with a proxy-limit disclosure | **Workable; one unclear nudge.** | R-001. The checklist row on self-grants invites a grant that cannot be used (ISS-15). The proxy-limit disclosure was easy to write and cannot be tested by one writer. |
| G §4.5, §4.6: what "recorded" means, order, write control | **Workable on paper; weak point real.** | R-001. Order by writer's position number (ISS-10). Whether people could behave better is not tested. |
| G §5, role-charters: roles, grants, capacities | **Workable.** | R-003 to R-006. Role labels, grants, and capacities stayed separate. |
| G §6: independence practice (substance test, work-assignment disclosure, small teams) | **Workable and unclear, not tested for substance.** | R-042, R-049, R-056. The distinction between challenging and supplying wording is thin (ISS-06). Substantive independence untestable (ISS-01). |
| G §7: evidence guidance, source register, attempt records, negative findings | **Workable, burdensome.** | R-009 to R-031. Same-day recording was easy for one writer. Each evidence item needed about fourteen prompts. Self-generated sources are not visible to the slot's independence expectation (ISS-11). |
| G §8: producing configuration | **Workable; version-binding not achievable.** | R-007, R-008. "Not bound" is allowed and was honest (ISS-19). |
| G §9: actor-kind binding | **Not tested.** | R-002, R-041 are vacuous. |
| G §10: challenge practice | **Workable; one unclear field.** | R-034 to R-036, R-048. A response did not close a challenge. "Requested response" invites wording (ISS-06). |
| G §11: formal checks, decidability, invalid-acceptance findings | **Workable.** | R-037 to R-039, R-055. Effect claimed/not claimed prevented the check from reading as acceptance. A decidable criterion written for a time stamp met a record with none (ISS-16). |
| G §12: gate definition, readiness, decisions, residual acceptance, conditional progression | **Workable, burdensome, partly unclear.** | R-020, R-021, R-032, R-040, R-044. Treatments vocabulary overlaps (ISS-21). Definition-before-evidence is workable and tailoring undetectable (ISS-07). |
| G §12.6: exceptions | **Not tested.** | Scenario S-2 only. |
| G §13: revalidation | **Workable; one overlap.** | R-045, R-046. A request and TRG-2 overlap (ISS-13). Closure not exercised. |
| G §14: escalation and authority gaps | **Workable and clear; offers little to a stuck team.** | R-052, R-053. Gap understood before the crisis in the script (ISS-14). |
| G §15: consequential commitments (T-24) | **Workable once recognized; recognition not tested.** | R-047 (ISS-17). |
| G §16: grant review; recovery by new project | **Grant review workable. Recovery not tested.** | R-050. T-26 not applicable. |
| G §17: record versus document | **Mostly workable; unclear for rationale and issue entries.** | ISS-09. |
| G §3: reader's question card | **Usable; one question unanswerable.** | R-029. Q6 "recorded as current" has no record element (ISS-03). Card goes stale (EV-07). |

---

## 5. STEP-06 Carried-Forward Pilot Focus

| Focus item (Product Owner, STEP-06 sign-off) | What the pilot shows | Strength |
| --- | --- | --- |
| Solo-founder usability without false self-approval | A solo-founder path reaches refusal, deferral, escalation, or an authority gap, never a valid acceptance. The establishing checklist nudges a founder to take a grant that looks like authority (ISS-15). | Scenario S-1 and R-001, R-054. Not a real founder. |
| Three-human plus agent: common block, source/evidence, independence declarations, decision records | The record counts for a discovery gate split mostly toward the producer. The reviewer's load is small in count. Whether people complete them in a normal cadence is not tested. | Scenario S-5. |
| Two-human avoidance of accidental co-production | Accidental co-production happened in one scripted step and removed the only independent acceptor. An avoidance path exists (S-4). The template field makes the wrong path easy (ISS-06). | Scripted (R-048, R-049) and scenario. |
| Gate readiness checklist usefulness | Lists unmet conditions in one place; value over ceremony not separable. | ISS-12. Suggests only. |
| Time and burden of the minimum set for discovery and build/no-build gates | 36 records for the discovery path, 14 for the build/no-build refusal path; about 12 minutes of timed AI authoring time (plus untimed reading); no human time. | Counts only (ISS-20). |
| Same-day counter-evidence recording | Recorded in the same sitting, trivially for one writer. | Weak (N-13). |
| Consequential commitments via template 24 | Recordable and visible with a warning; recognition untested. | Scripted (R-047). |
| Grant review and authority-gap handling before a crisis | The grant review caught the gap before the attempt, in the script. Whether a real team would run the review is untested. | R-050; scripted. |
| Record-versus-document usability | Workable for most kinds, unclear for rationale and issue entries. | ISS-09. |
| Worked examples remain scenarios, not evidence | The pilot cited none as evidence and kept its own scenarios in a labeled appendix. | Maintained. |

---

## 6. Compliance With the Step's Own Boundaries

- No accepted STEP-01 to STEP-06 artifact was modified. Files created: the four required, plus one proposed observation appended to `research/mod-w-transferability/observations.md` under the research governance route. (QA can confirm from `git status`; the working tree shows only these changes.)
- No schema, serialization, state vocabulary, lifecycle graph, storage model, validator, CLI, database, transport, prompt format, harness, runtime integration, API, or publication package was selected or built. The `CB:` line and the position numbers are pilot practice and not a format. Do not write a parser against them.
- No STEP-08 hypothesis was disposed of. ISS-22 is routed to STEP-08.
- No accepted-protocol question was answered. Routed ones: RQ-16 (ISS-08), RQ-04 (ISS-10), RQ-02 (ISS-22).
- Transferability evidence is proposed as MW-OBS-019 and is not accepted.

---

## 7. Findings Mapped to AC-3 and E-1 to E-9

| Requirement | Demonstrated | Suggested | Not exercised |
| --- | --- | --- | --- |
| AC-3 One small opportunity through PROD-W workflow | D-1, D-11 | S-9 (content of the pilot opportunity only) | N-7 (build accepted), N-8 |
| E-1 Protocol feasibility | D-1, D-6 | S-1, S-6, S-8 | N-1 |
| E-2 User applicability | none | S-1, S-2, S-4, S-6, S-7 | N-1, N-11, N-12 |
| E-3 Discipline enforcement | D-3, D-5, D-10 | S-2 | N-1, N-3 |
| E-4 MOD-W transferability | none | MW-OBS-019 (proposed) | none |
| E-5 Role model coherence | D-4 | S-3 | N-3 |
| E-6 Evidence quality | D-2, D-3, D-11 | S-5 (about the opportunity) | N-14 |
| E-7 Authority clarity | D-4, D-5 | S-3, S-4 | N-2, N-5 |
| E-8 Workflow progression semantics | D-6, D-8, D-9 | S-6 | N-6, N-7 |
| E-9 Automated enforceability boundary | D-7 | S-8 | N-2 |

**Net statement.** The pilot supports a narrow claim: PROD-W's records and rules can be followed to a coherent, traceable, and visibly non-progressing result in one bounded, simulated case. It does not support any claim about users, effectiveness, burden for people, independence in practice, or commercial value.

---

## 8. Findings by Owner

| Owner lens | Findings |
| --- | --- |
| **Tech Lead protocol-conformance** | D-1, D-2, D-3, D-4, D-5, D-6, D-7, D-8, D-9; S-3, S-8; the reading-coverage limit (trial §10.10) and the unchecked rule citations. |
| **QA verification** | D-5, D-7, D-11; sampling targets: R-014 to R-031 (record kinds separate), R-037 to R-039 and R-055 (effect claimed/not claimed), R-044 and R-057 (standing record cited with treatments), R-049 and R-050 (producer attribution), the counts in trial §9. |
| **Product Owner usability** | S-1, S-2, S-4, S-7; ISS-04, ISS-12, ISS-14, ISS-15, ISS-20; whether a human-run pilot should follow. |
| **Development Team observations** | S-5, S-9; ISS-11, ISS-18. |

---

MOD-W v5.0.1
