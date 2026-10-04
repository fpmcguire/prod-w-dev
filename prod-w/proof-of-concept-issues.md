---
artifact:
  type: pilot-issue-log
  id: PROD-W-POC-ISS
  version: 0.1
  created: 2026-10-04
  updated: 2026-10-04
  status: Draft - Development Team work product for STEP-07. Not reviewed. Not accepted.
  produced_by: Development Team
  produced_under: STEP-07
source:
  step: mod-w/step-07.md
  templates: prod-w/templates.md
  records: prod-w/proof-of-concept-records.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Proof-of-Concept Issue Log

**Status:** Draft v0.1. Development Team work product for STEP-07. Not reviewed. Not accepted.
**Standing:** Method issues, ambiguities, burdens, failed attempts, and open questions found while running the pilot. Each is routed. **None is resolved here.** No accepted STEP-01 to STEP-06 artifact was changed, no practice default was patched, and no routed question is answered. Entries use the wording of template 28.

**How to read the routes.** Each entry has one primary route from the step file's list: STEP-07 pilot evidence; STEP-08 research disposition; MOD-W Moderator protocol question; Product Owner usability follow-up; later architecture or representation work; later methodology correction. "Suggested" means the Development Team's suggestion. The route is for the Tech Lead and the Moderator to confirm.

**Reading the pilot's limit.** Every issue was observed in a pilot written by one AI session for all actors (`prod-w/proof-of-concept-records.md` §0). An issue seen here is a signal. An issue not seen here is not shown absent.

## Summary Table

| ID | Short description | Primary route | Transferability evidence |
| --- | --- | --- | --- |
| ISS-01 | One session wrote every actor's records | STEP-07 pilot evidence | yes |
| ISS-02 | Template 5 forward-reference fields cannot be filled under append-only practice | later methodology correction | no |
| ISS-03 | Card question 6, "recorded as current", has no record element | later methodology correction | no |
| ISS-04 | The eleven-prompt common block invites collapse and repeats | Product Owner usability follow-up | no |
| ISS-05 | Template 9 "testable? yes/no" does not fit "testable in principle, not here" | later methodology correction | no |
| ISS-06 | Template 12 "Requested response" invites supplying wording, which is co-production | later methodology correction | no |
| ISS-07 | A build gate defined with an unobtainable slot is refused by design | STEP-07 pilot evidence | no |
| ISS-08 | The verifier is the same session and model as the producer | MOD-W Moderator protocol question | no |
| ISS-09 | Where a gate's contextual rationale belongs, record or document | later methodology correction | no |
| ISS-10 | Record order rests on the writer's own position numbers | later architecture or representation work | no |
| ISS-11 | Test evidence rests on the pilot's own records, one self-generated source | STEP-07 pilot evidence | no |
| ISS-12 | The readiness checklist's value over its ceremony cannot be separated here | Product Owner usability follow-up | no |
| ISS-13 | A request and a trigger overlap for sourced counter-evidence | later methodology correction | no |
| ISS-14 | After an authority gap the only valid course was to stop | Product Owner usability follow-up | no |
| ISS-15 | The root-grant checklist nudges a solo founder to write a grant that cannot be used | Product Owner usability follow-up | no |
| ISS-16 | Criteria that say "observation time" meet a record with no clock | later architecture or representation work | no |
| ISS-17 | "Consequential" had to be defined by the pilot | STEP-07 pilot evidence | no |
| ISS-18 | The opportunity is a view of the method under test | STEP-07 pilot evidence | yes |
| ISS-19 | Instruction version-binding was not achievable for the task brief | STEP-07 pilot evidence | no |
| ISS-20 | Human time was not measured | Product Owner usability follow-up | no |
| ISS-21 | Treatment words "answered" and "accepted as residual" overlap | later methodology correction | no |
| ISS-22 | The basis-presentation designation was recordable as a stricter condition | STEP-08 research disposition | no |

---

## Entries

### ISS-01

```text
Issue ID: ISS-01
Observed during: whole pilot (records §0).
Description: One AI session typed every record, including every act attributed to the human positions H-A and H-B and to verify-agent-1. Independence was by recorded identity only. Substance could not be tested. Declarations (R-042, R-056) cannot be false in any detectable way. The actor-kind binding note (R-002, R-041) had nothing to bind.
Protocol area affected: PR-17, PR-27, GCR-09, RO §9.5.
Methodology area affected: G §6.2, §9; templates 16, 25.
Impact: the pilot cannot show that independent humans would behave as scripted, that the weak point of actor-kind binding is exploitable, or that the independence declaration is honest in use. Gate outcomes are scripted and are not determinations by anyone.
Temporary handling: labeled SIMULATED and SCRIPTED at each point; findings are limited to record shape and rule application.
Suggested route: STEP-07 pilot evidence. A pilot with real human actors would be needed for these questions, and the Product Owner can judge whether to ask for one later.
Is concrete evidence about MOD-W transferability involved? Yes. The step's allowance for simulated product roles held in writing but made the product-role acts weak evidence. Proposed as MW-OBS-019.
```

### ISS-02

```text
Issue ID: ISS-02
Observed during: R-014 (claim records), R-028 (test T-1).
Description: Template 5 asks the claim record to list "items that rely on this claim", "challenges against this claim", and "gate or decision this claim bears on". Practice says to edit only your own records and never rewrite history. So a claim record can only say "none at recording", and later links live in later records. Reading a claim's standing then means scanning the whole record. In EV-05, five of nine questions could only be answered by scanning all 31 records for the absence of items.
Protocol area affected: none known (EK §6.4 requires dependency links in both directions, derivable from history).
Methodology area affected: template 5; G §4.6, §17.
Impact: the forward fields look like they will be maintained and cannot be. A reader may trust "none" in a claim record.
Temporary handling: "none at recording" was written in each claim record.
Suggested route: later methodology correction (state that those fields are as-of-recording), and later architecture or representation work (derived views are the only reliable reader of later links).
Transferability evidence: no.
```

### ISS-03

```text
Issue ID: ISS-03
Observed during: R-029 (test T-2).
Description: Question 6 of the reader's question card (G §3.2) asks whether the item carries an open requirement and is "recorded as current". No record element states "current". VI-6 only says a dependent with an open requirement is not shown as current. So the answer to "recorded as current?" is the absence of a requirement, which is not a statement.
Protocol area affected: CRC-51; RO §12.4 VI-6.
Methodology area affected: G §3.2 question 6.
Impact: one question of nine was answerable only in part, for both derived cards.
Temporary handling: card said "no open requirement recorded" and "recorded as current is not answerable".
Suggested route: later methodology correction (reword the question). If a "current" statement is wanted as a record element, that is a protocol question for the Moderator, and the Development Team makes no suggestion.
Transferability evidence: no.
```

### ISS-04

```text
Issue ID: ISS-04
Observed during: all records (the common block, T-0.1).
Description: The common block has eleven prompts. Across 58 records the same facts repeat: the producing-configuration reference repeats in 32 of 58 records (R-007) and 4 more (R-008), the grant is the same, the work assignment is the same. The pilot compressed the block to one line per record. That was a temptation to collapse a distinction, taken knowingly. A reviewer must trust that nothing was lost. The "other producers" and "work assignment" prompts did their job (R-049 shows H-B as a producer), but only because someone was watching them.
Protocol area affected: PR-06, PR-08 (one record, one actor, one capacity).
Methodology area affected: template 0.1.
Impact: burden; risk that a compressed block hides a producer.
Temporary handling: a compact `CB:` line with all prompts in a fixed order, and a statement of that practice at the top of the records file.
Suggested route: Product Owner usability follow-up (the Product Owner's note on "usable but heavy" in SRC-03 predicted this), then later methodology correction (a quick-start form that keeps all prompts).
Transferability evidence: no.
```

### ISS-05

```text
Issue ID: ISS-05
Observed during: R-018 (AS-01).
Description: Template 9 asks "Is it testable? yes (then record it as a hypothesis) / no". AS-01 is testable in principle, and not in this trial, because no reader is reachable. Answering "yes" would require a hypothesis with criteria that no one can run. Answering "no" would be untrue.
Protocol area affected: EKR-21 (a hypothesis needs recorded criteria).
Methodology area affected: template 9; G §7.3.
Impact: a false binary. The pilot wrote a longer answer.
Temporary handling: "testable in principle, not here" in the field.
Suggested route: later methodology correction.
Transferability evidence: no.
```

### ISS-06

```text
Issue ID: ISS-06
Observed during: R-048, R-049 (scripted).
Description: Template 12's "Requested response" field makes no distinction between asking the producer to reconsider and supplying the replacement conclusion. The natural reviewer remedy is better wording. A producer who adopts it makes the reviewer a producer of the revised item (GCR-03; G §6.4 B), and the reviewer cannot then accept. In the pilot this created the authority gap AG-1. The event was scripted, but the template wording made the script easy to write.
Protocol area affected: GCR-03, GCR-08.
Methodology area affected: template 12; G §6.4 B.
Impact: a two-human team can lose its only independent acceptor with one helpful sentence. Nothing in the template warns at the point of writing.
Temporary handling: recorded in the challenge's own note and in the revised inference's producer note.
Suggested route: later methodology correction (a prompt at the field), and Product Owner usability follow-up (does a real reviewer feel this pull).
Transferability evidence: no.
```

### ISS-07

```text
Issue ID: ISS-07
Observed during: R-021 (GD-B), R-051.
Description: GD-B defines a required reader-value slot (B1) that no one in the pilot can fill, and deliberately makes it non-waivable. That ensures the gate is refused. It also means the build/no-build gate shows non-progression and does not show an acceptance path. Gate definitions were also written after the claims and before the evidence, by the same actor who wrote the claims. Tailoring a gate to the available evidence cannot be detected from the record.
Protocol area affected: GCR-12, GCR-13.
Methodology area affected: G §12.1; template 13.
Impact: the pilot demonstrates refusal of a build gate and does not demonstrate acceptance of one on real reader evidence.
Temporary handling: stated in the trial file as a limit.
Suggested route: STEP-07 pilot evidence.
Transferability evidence: no.
```

### ISS-08

```text
Issue ID: ISS-08
Observed during: R-006, R-008, R-037, R-038, R-055.
Description: verify-agent-1 is a different accountable position and the same session and model as the producer. It satisfies GCR-10 by identity and shares every blind spot of the producer. It also recorded a finding that an acceptance is invalid (R-055), which an AI AUTH-V holder may do only for criteria decidable from the record. The three rules there were decidable. Whether a same-session verifier should carry weight is the question RQ-16 already routes.
Protocol area affected: GCR-10, PR-27, PR-28, CRC-59; RQ-16.
Methodology area affected: G §11.7; templates 22, 23.
Impact: the pilot shows that the check can be run and recorded. It does not show that it adds independent assurance.
Temporary handling: limit stated in R-008 and in each result.
Suggested route: MOD-W Moderator protocol question (existing RQ-16). The pilot adds a data point and decides nothing.
Transferability evidence: no.
```

### ISS-09

```text
Issue ID: ISS-09
Observed during: R-044, R-057 (T-15), the trial file.
Description: G §17 puts "rationale text (presence checked, adequacy a judgment)" with the record and "narrative explanation of why the team believes something" in the document. The gate decision record's contextual sufficiency judgment is both. The pilot put it in the record, as template 15 asks, and then repeated the reasoning in the trial file. Whether the pilot should also have put the issue log and the burden notes in the record (as T-28 entries) or only in documents was unclear. The pilot treated T-28 as a document with references from the record (R-058).
Protocol area affected: none.
Methodology area affected: G §17; templates 15, 28.
Impact: some duplication. The distinction was usable for sources, evidence, and designations, and unclear for rationale text and issue entries.
Temporary handling: rationale in the record; narrative and analysis in the trial and findings files; issue entries in this file with references.
Suggested route: later methodology correction.
Transferability evidence: no.
```

### ISS-10

```text
Issue ID: ISS-10
Observed during: R-001 practice statements; R-008; R-037.
Description: Record order is the position number assigned by the writer, who is also the author of every record, in a file that is not committed during the pilot. G §4.5 advises order not rest on the recorder's own assertion. A change to an earlier record is not detectable from inside the file, so instruction version-binding of gate definitions (R-008) relies on no one editing. No second order source was available.
Protocol area affected: RQ-04, RQ-17; RO §10.4.
Methodology area affected: G §4.5, §4.6.
Impact: backdating, if done, could not be detected by this record.
Temporary handling: stated as a known weak point in R-001.
Suggested route: later architecture or representation work (RQ-04). Pilot evidence: the weak point is real in a one-writer file.
Transferability evidence: no.
```

### ISS-11

```text
Issue ID: ISS-11
Observed during: R-013, R-028, R-029, R-045.
Description: Three evidence items (EV-05, EV-06, EV-07) are test results whose only source is the pilot's own records, written and tested by one producer. The source register treats them as one source, correctly. The gate's source-independence slot expectation cannot see that they are all self-generated. That is a different weakness from one shared source: it is a source that is the claim's own producer.
Protocol area affected: EKR-11, EKR-17.
Methodology area affected: templates 4, 6; G §8.3.
Impact: a gate slot could be filled by self-generated test results and look sourced.
Temporary handling: "self-generated" in limitations and comparability notes.
Suggested route: STEP-07 pilot evidence.
Transferability evidence: no.
```

### ISS-12

```text
Issue ID: ISS-12
Observed during: R-032, R-040, R-051.
Description: The readiness checklist caught five of nine conditions on the premature GD-D attempt (R-032 items 5 to 9 "no") and six on GD-B (R-051 items 4 to 9). It also gave the refusals their stated reasons. The pilot cannot say whether it prevented an invalid acceptance, because the script already knew the answers and one actor wrote both. R-054 (self-approval) was written without a checklist, and INV-1 found three violated rules after the fact. The checklist did make the missing conditions listable in one place.
Protocol area affected: PR-13; GC §5.4.
Methodology area affected: G §12.4; template 14.
Impact: usefulness against ceremony is not separable in this pilot.
Temporary handling: recorded as an observation only.
Suggested route: Product Owner usability follow-up. A real team's use is needed.
Transferability evidence: no.
```

### ISS-13

```text
Issue ID: ISS-13
Observed during: R-045, R-046.
Description: Sourced counter-evidence on a material dependency already creates a requirement on direct material dependents (TRG-2). Template 21 opens with a request that "creates a requirement". The pilot filed a request that restated the trigger. It was unclear whether the request was required, harmless, or a double count.
Protocol area affected: TRG-2, ACT-06, GCR-58 (one requirement per dependent).
Methodology area affected: template 21; G §13.2.
Impact: minor ambiguity and some duplication.
Temporary handling: the request cites the trigger, and the requirement carries one reason (EV-07).
Suggested route: later methodology correction.
Transferability evidence: no.
```

### ISS-14

```text
Issue ID: ISS-14
Observed during: R-050 to R-057.
Description: The grant review (R-050) found the GD-B gap before the attempt, so the gap was understandable before a crisis in this script. Once found, the only valid course was to stop: no cure was available in the pilot, the conferrer was conflicted, no third human existed, and the refusal could not be followed by a progression. The opportunity ended at GD-B with no way forward. Stopping is permitted by the protocol, but a real team's reaction is unknown.
Protocol area affected: GC §8.6.
Methodology area affected: G §14.3, §16.1; templates 20, 27.
Impact: the method is clear about what is not a cure. It offers little to a two-human team that is stuck, beyond "name a third human in the establishing act".
Temporary handling: recorded; table-top S-3 explores the flagged conferral cure.
Suggested route: Product Owner usability follow-up.
Transferability evidence: no.
```

### ISS-15

```text
Issue ID: ISS-15
Observed during: R-001 (RG-4), R-054.
Description: The root-grant checklist's first row asks whether every grant the establishing identity will need for itself is in the establishing act, because it cannot be added later. A founder who follows it will include AUTH-G for acceptance. Having that grant looks like authority and cannot validly be used over the founder's own set. The guidance elsewhere says so, but the checklist row nudges the other way. This is the Product Owner's first pilot-focus item (solo-founder usability without false self-approval), seen from the establishing act and not from the gate.
Protocol area affected: CRC-62, GCR-05.
Methodology area affected: G §4.3; template 1.
Impact: a risk of a false sense of authority at the start. The pilot recorded the grant, wrote the attempt, and showed it invalid. Whether a real founder is misled is not tested.
Temporary handling: noted in R-001.
Suggested route: Product Owner usability follow-up, then later methodology correction.
Transferability evidence: no.
```

### ISS-16

```text
Issue ID: ISS-16
Observed during: R-037 (FC-1).
Description: FC-1 asks that each evidence item record an "observation time". The records have a date and a position, and no clock. The verifier treated position as satisfying it. That is a reading of the criterion, not a fact.
Protocol area affected: none known.
Methodology area affected: template 6, 13, 22; G §7.2.
Impact: a decidable criterion written for a time stamp was satisfied by a different thing.
Temporary handling: stated in R-037.
Suggested route: later architecture or representation work.
Transferability evidence: no.
```

### ISS-17

```text
Issue ID: ISS-17
Observed during: R-001, R-047.
Description: The practice default asks a project to say in advance what counts as consequential. The pilot defined it in R-001 (an external promise, effort beyond one session, a direction change) and then wrote a commitment that fit that definition by design. Whether T-24 catches commitments a team did not think of as consequential is untested. This is MG-N3.
Protocol area affected: RJ-OQ-12; CRC-19, CRC-47.
Methodology area affected: G §15; template 24.
Impact: T-24 was workable once the commitment was recognized. Recognition is the part not tested.
Temporary handling: recorded.
Suggested route: STEP-07 pilot evidence (informs MG-N3; the Tech Lead confirms the practice-versus-rule line).
Transferability evidence: no.
```

### ISS-18

```text
Issue ID: ISS-18
Observed during: R-014 and after.
Description: The opportunity is a reading aid for PROD-W records, so the product under pilot and the method under test overlap. Evidence about the product (EV-05 to EV-07) is also evidence about the template set's reading burden. That helped the pilot (real, verifiable evidence without invented testimony) and weakens it (the product is reflexive).
Protocol area affected: none.
Methodology area affected: G §19.
Impact: findings about the Standing Card should not be read as findings about products in general.
Temporary handling: stated in the trial file's non-claims.
Suggested route: STEP-07 pilot evidence.
Transferability evidence: yes. A methodology developing a method for developing methods shows the same reflexivity at the product level. Proposed as MW-OBS-019.
```

### ISS-19

```text
Issue ID: ISS-19
Observed during: R-007, R-008.
Description: Template 11 asks for a version-binding method for the instructions in force. The task brief and system instructions could not be copied or hashed by the actor. The statement says "not bound", which the template allows. Reasoning effort was not determinable. Repository inputs were bound only by the head commit.
Protocol area affected: CRC-39; RQ-08.
Methodology area affected: G §8.1; template 11.
Impact: an honest "not bound" was easy to write, and the template did not punish it. No claim of reproducibility can be made.
Temporary handling: recorded as not bound with the reason.
Suggested route: STEP-07 pilot evidence.
Transferability evidence: no.
```

### ISS-20

```text
Issue ID: ISS-20
Observed during: the pilot as a whole.
Description: The step asks for time and burden to complete the minimum artifact set. Only the AI session's elapsed time and record counts were measured. A human estimate would be speculation, because no human filled any record.
Protocol area affected: none.
Methodology area affected: G §18.1 (DP-01, RQ-13).
Impact: the Product Owner's burden question is answered only in counts (trial file §9).
Temporary handling: counts and the elapsed session time are reported with their limits.
Suggested route: Product Owner usability follow-up.
Transferability evidence: no.
```

### ISS-21

```text
Issue ID: ISS-21
Observed during: R-040, R-044.
Description: The available treatments of a challenge in the standing record are "answered", "conceded or withdrawn by the challenger", "moot", "accepted as residual", "covered by exception". CH-01 was answered by a response that conceded the gap and offered no new evidence. "Answered" is not true in the sense that the challenger is satisfied, and "accepted as residual" is the honest one. The pilot used "accepted as residual". A response never closes a challenge, so it is unclear when "answered" is the right treatment.
Protocol area affected: GC §5.5; GCR-17, GCR-25.
Methodology area affected: G §12.4; template 15.
Impact: ambiguity in the treatment vocabulary at the point an acceptor chooses one.
Temporary handling: "accepted as residual", with the reason.
Suggested route: later methodology correction.
Transferability evidence: no.
```

### ISS-22

```text
Issue ID: ISS-22
Observed during: R-017, R-021.
Description: CL-03 carries a basis-presentation designation ("presented as a value judgment"), and GD-B makes it a stricter condition, as G §7.6 suggests. It was easy to record and easy to check. The pilot shows only that it can be recorded. It does not show whether it protects against hiding a judgment, because no one tried to present CL-03 otherwise.
Protocol area affected: RQ-01, RQ-02, CRC-45.
Methodology area affected: G §7.6.
Impact: pilot evidence on burden only.
Temporary handling: none needed.
Suggested route: STEP-08 research disposition (and RQ-02 stays with the Moderator).
Transferability evidence: no.
```

---

## Open Questions Not Resolved by the Pilot

- Whether independent humans, given the same templates, would reach the same refusals (ISS-01).
- Whether the actor-kind weak point is exploitable (ISS-01, RQ-05).
- Whether a team recognizes a consequential commitment before making it (ISS-17).
- How long it takes a human to fill the minimum set (ISS-20).
- Whether the readiness checklist prevents invalid acceptances (ISS-12).

---

MOD-W v5.0.1
