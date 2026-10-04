---
type: qa-review
from: QA
to: MOD-W Moderator, Tech Lead, and Development Team
date: 2026-10-04
review_artifacts:
  - mod-w/step-06.md
  - mod-w/reviews/MODERATOR-REVIEW-STEP-06-SETUP.md
  - mod-w/reviews/DEVELOPMENT-TEAM-HANDOFF-STEP-06.md
  - mod-w/reviews/TECH-LEAD-REVIEW-STEP-06.md
  - mod-w/reviews/DEVELOPMENT-TEAM-REWORK-STEP-06.md
  - mod-w/reviews/TECH-LEAD-REVIEW-STEP-06-REWORK.md
  - mod-w/reviews/MODERATOR-REVIEW-STEP-06-TECH-LEAD-REWORK.md
  - prod-w/methodology-guidance.md
  - prod-w/role-charters.md
  - prod-w/templates.md
  - prod-w/worked-examples.md
review_status: PASS_WITH_NOTES
---

# QA Review: STEP-06 (Phase 3b)

## Recommendation

I recommend **PASS_WITH_NOTES**.

I found no blocking defect. The four deliverables stay guidance, templates, and hypothetical examples. I found no representation, tooling, numeric sufficiency, human-acted claim, or pilot-evidence claim. The TLR6-01 re-work is present and limited to metadata. I found no revision of accepted STEP-01 to STEP-05 artifacts, and no final acceptance or waiver is recorded.

The four notes below (QAR6-01 to QAR6-04) are non-blocking. I am not asking for a re-work cycle on them. The Development Team may fix QAR6-01 and QAR6-02 as part of any later edit. The Moderator may accept all four as harmless.

This review does not record STEP-06 final acceptance. It does not waive Product Owner sign-off.

## Review Method / Coverage

QA review is by sampling. It is independent of the producer's self-checks in guidance §20.2, which I did not rely on.

**Read in full**
- `mod-w/step-06.md`
- All six review and handoff records listed in the front matter.
- `prod-w/worked-examples.md` (WE-1 to WE-8).
- `mod-w/reviews/MODERATOR-REVIEW-STEP-06-PRE-TECH-LEAD.md`. It is not in the assigned list but is referenced by the handoff.

**Read in part**
- `prod-w/methodology-guidance.md`: §§12.5 to 12.8, 15, 16, 20.2 to 20.6 in full. Section structure and headings for all of §§4 to 14 and 17 to 20.
- `prod-w/role-charters.md`: §2 (five distinctions) and the section index.
- `prod-w/templates.md`: the section index, §0 disclaimers, and the numbering of Templates 1 to 28.

**Checked by search or command**
- Numeric sufficiency, scoring, and weighting terms.
- Schema, tooling, and format terms.
- "pilot" in the worked examples.
- Status and version lines in all four files.
- `git diff` of the re-work against the submission commit `4eb09a4`.
- `git diff --name-only` since the STEP-05 completion commit `ee85cf7`.
- Roadmap and review records for acceptance or waiver text.
- Existence and wording of 37 cited rule IDs in the accepted artifacts.

**Not done**
- I did not read `methodology-guidance.md` (1117 lines), `role-charters.md`, or `templates.md` end to end. Findings about unread passages are limited to structure, search, and the Tech Lead's targeted reads.
- I did not exercise the templates by filling them for a real case. STEP-07 owns that.

## Acceptance-Check Results

| # | Acceptance check (`mod-w/step-06.md`) | Result | Basis |
| --- | --- | --- | --- |
| 1 | Guidance under `prod-w/`, states it is guidance, not protocol revision | Met | Guidance §§1.3 and 1.4 (lines 37 to 61). Templates §0 says "not a schema" and that semantics do not change |
| 2 | Role charters distinguish identity, role labels, grants, capacity, work assignment | Met | Role-charters §2 is a five-row table with "is / is not / where recorded". It adds the appointment-versus-assignment rule and "configuration is not identity" |
| 3 | Project establishment and root-grant practice, without modifying D10 | Met | Guidance §4 (§§4.1 to 4.7). §16.1 and §16.2 restate D10 and CRC-63 as given facts |
| 4 | Independence practice for small teams, including authority gaps | Met | Guidance §6 (§6.4 teams by size, §6.5 agents). WE-4 shows an authority gap and flagged cures |
| 5 | Evidence guidance distinguishes evidence, counter-evidence, negative findings, assumptions, hypotheses, inferences, decisions | Met | Guidance §7.1 to §7.4. Templates 5 to 10 give separate records |
| 6 | Category and threshold practice without universal scores | Met | Guidance §7.5. Line 373 says categories "are not a taxonomy and not scores". Line 401 permits a count only as a presence condition |
| 7 | Gate slots, acceptance, refusal, deferral, exception, conditional progression, escalation | Met | Guidance §12.1 to §12.7 and §14. Templates 13 to 20 |
| 8 | Templates preserve producer, reviewer/challenger, verifier, acceptor, authority, provenance, standing-record distinctions | Met | 28 templates present, numbered 1 to 28 with a Common Block. The index matches the handoff's count |
| 9 | One valid progression and one visible non-progression or unresolved disagreement | Met | WE-1 (valid progression), WE-2 (refusal and authority gap), WE-3 (unresolved disagreement) |
| 10 | Formal-check guidance records findings without making checks gate acceptance | Met | Guidance §11.5 "Checks must not become gate acceptance". §11.3 and §11.4. WE-5 and Template 22 and 23 |
| 11 | Actor-kind binding without claiming the protocol proves a human acted | Met | Guidance §9 and Template 25 (the Tech Lead also read them closely) |
| 12 | Source comparability and producing-configuration version binding at practice level | Met | Guidance §8.1 to §8.3. Mechanisms are listed as options and none is selected. WE-1 step 2 shows a comparability note |
| 13 | Recovery by new project stays visible. Carry-over not defined as accepted unless marked project practice | Met | Guidance §16.2 says "This guide does not define carry-over as accepted protocol". Step 10 keeps the question open. Template 26 and WE-8 Part B follow it |
| 14 | Pilot questions routed to STEP-07 and research/hypotheses to STEP-08 | Met | Guidance §18.1 (pilot questions) and §19. Line 483 routes publication wording to STEP-09 |
| 15 | No representation, schema, validator, lifecycle graph, state vocabulary, tool, or publication package | Met | Search found tooling and format words only in sentences that disclaim them (guidance lines 58, 622; templates line 36). Nothing was added outside `prod-w/` guidance files and a research observation |
| 16 | Transferability evidence proposed under research governance | Met | MW-OBS-018 appended as proposed and non-blocking. It adds 60 lines to the research register and edits no existing entry |
| 17 | Final acceptance not recorded before 3a, 3b, 3c occur or are waived | Met | See "Governance-Record Checks" below |

## Scope Confirmations

| QA scope item | Result |
| --- | --- |
| Artifacts remain guidance, templates, and worked examples, not protocol revisions | Confirmed. All four files carry "Draft v0.2 ... Not reviewed. Not accepted." The accepted semantics files are cited, not edited |
| No representation, schema, validator, lifecycle graph, state vocabulary, tool, runtime integration, or publication package is selected or implemented | Confirmed by search and by the commit stat. The only new files are the four `prod-w/` files, review records, and the research entry |
| No numeric sufficiency score, weight, confidence percentage, or artificial precision | Confirmed. Every match for "score", "weight", "%", or "confidence" is a prohibition (guidance lines 61, 373, 401, 1033 to 1066; templates line 40). "40 sample threads" in WE-3 is an invented fact, not a threshold |
| Worked examples are hypothetical and not pilot evidence | Confirmed. WE §0 says the facts are invented, the STEP-07 pilot has not been run, and the examples should not be cited as findings. WE-6 ends by routing workability to STEP-07 |
| TLR6-01 re-work present and does not alter WE-1 to WE-8 | Confirmed. See below |
| No accepted STEP-01 to STEP-05 artifacts revised | Confirmed. See below |
| No final acceptance, QA waiver, or Product Owner waiver recorded | Confirmed. See below |

### TLR6-01 re-work

`git diff 4eb09a4 HEAD -- prod-w/worked-examples.md` shows exactly three changes:
1. Front matter `version: 0.1` to `0.2`.
2. The status line "Draft v0.1" to "Draft v0.2".
3. One added Change Notes row (v0.2), with the v0.1 row kept.

The diff has no hunk inside WE-1 to WE-8. The re-work note and the Tech Lead's re-work review describe the change accurately. The "Not reviewed. Not accepted." wording is unchanged and still correct.

### Accepted-artifact boundary

`git diff --name-only ee85cf7 HEAD` lists only:
- STEP-06 review records.
- `mod-w/step-06.md` and `mod-w/roadmap.md`. These are STEP-06 work-package and status files, set during Moderator setup.
- The four STEP-06 `prod-w/` files.
- `research/mod-w-transferability/observations.md`.

`git log ee85cf7..HEAD` over `protocol-semantics.md`, `evidence-knowledge-model.md`, `gate-challenge-revalidation-semantics.md`, `rule-judgment-boundary.md`, `representation-options.md`, `mod-w/architecture.md`, and `mod-w/step-01.md` to `step-05.md` returns no commits. The working tree is clean.

### Governance-Record Checks

- `mod-w/roadmap.md` line 43 shows STEP-06 as "In Progress". It does not show it as Complete or Accepted.
- Every STEP-06 review record states that final acceptance, the QA waiver, and the Product Owner waiver are not recorded. The Moderator's re-work approval (`MODERATOR-REVIEW-STEP-06-TECH-LEAD-REWORK.md`) lists 3b and 3c as expected, "No waiver recorded", and 4a as "Pending. Not recorded."
- The step file's acceptance checklist is still unchecked.
- A text search found no STEP-06 acceptance or waiver language outside those records.

## Traceability Sample Results

I looked up 37 rule identifiers cited in the guidance and worked examples. Each exists in the accepted artifacts: PR-05, 11, 13, 16, 17, 18, 19, 20, 25, 27, 28; INV-02, 04, 16; ACT-06, 07; GCR-03, 05, 06, 07, 13, 19, 28, 30, 36, 38, 39, 58, 67; CRC-48, 59, 63, 64; EKR-17, 18, 19; HJC-12; BDR-14.

Existence is the weaker check. The Development Team's own handoff warns that it cannot find meaning errors. So I read the rule text for the ones the examples lean on most.

| Methodology claim | Accepted source | Result |
| --- | --- | --- |
| AUTH-G is human only. Agent suggestion cannot approve (WE-2 step 6) | PR-05 | Matches |
| Self-review, re-execution, and agent review give advisory findings and never independence or acceptance (WE-1, WE-4) | PR-27, PR-28 | Matches. PR-27 also says configuration is provenance, not identity, as role-charters §2 states |
| An acceptor who is a recorded producer of any member of the set is invalid, however small the edit (WE-5) | PR-16, GCR-03 | Matches |
| An invalid action has no intended effect and stays visible (WE-5) | PR-11 | Matches |
| No waiver or relabeling validates an acceptance that independence invalidates (WE-4, WE-5) | GCR-06 | Matches |
| A gate amended after a refusal on the same basis applies only as a recorded exception (WE-2, WE-3) | GCR-13 | Matches |
| Earlier refusals and deferrals are cited with a treatment. No override hierarchy among holders (WE-1, WE-3) | GCR-39 | Matches the two quoted sentences |
| Agent agreement is not corroboration (WE-1, WE-2) | EKR-17, PR-20 | Matches |
| A finding that an acceptance is invalid must name the rule, the evaluation point, and the record elements examined. A bare assertion is not a finding (WE-5) | CRC-59 | Matches |
| A flagged, escalation-eligible conferral from a conflicted holder is not invalid (WE-4 cure B) | CRC-64 | Matches |
| A renunciation cascades prospectively down the chain (WE-8 Part A) | CRC-63 | Matches |
| Sourced counter-evidence creates a requirement on direct material dependents. A challenge, a bare claim, or a bare inference gives only contestation and exposure (WE-7) | GCR-30, GCR-31 | Matches |
| One requirement per dependent, with one reason per trigger (WE-7) | GCR-58 | Matches |
| A request by an AUTH-A, AUTH-V, or AUTH-G holder creates the requirement and needs no independence (WE-5, WE-7) | GC §7.5 P3, GCR-31, ACT-06 | Matches |
| Age and time never create or close a requirement but can be the stated basis of a request (WE-7) | GCR-67 | Matches |
| Detection results are advisory. A challenge to a finding does not suspend the requirement it created (WE-5) | RJ §9.4.3, BDR-13 | Matches |
| A decision that is consequential needs AUTH-G, or it is a recommendation (WE-2, WE-6) | ACT-07 | Matches |
| Substantive independence is a judgment, not decidable from the record (WE-5 external evaluator) | HJC-12 | Matches |
| Pilot-workability and DM-09 default status are open (guidance §15.2; WE-6) | RJ §6.6 (DM-09), CRC-19, CRC-48 | Framed as practice, not as a new rule |
| DM-07 has two readings (guidance §16) | RJ §6.6, §10.6, D10 | Consistent with the Tech Lead's TLR6-08 |

I did not find a methodology statement that contradicts the accepted text in the passages I sampled. The Tech Lead's separate sample (guidance §§4.5 to 4.7, 6.4, 7.3 to 7.6, 8.1, 9, 11 to 13, 15 to 18) found none either. The two samples overlap on WE-1, WE-5, and WE-7, and differ on the other passages, so together they cover more than either alone.

## Usability for STEP-07

The package is usable as input to the pilot design. The examples show short-form records that point to templates by number. Template 0.2 indexes all 28. Guidance §19 and the routing lists in §18 state what the pilot should test. The examples are written so that STEP-07 can reuse the cases without citing them as results.

## Findings

All findings are non-blocking.

### QAR6-01: WE-2 is unclear about whether the authority gap follows from Marcus's grants

- **Location:** `prod-w/worked-examples.md` WE-2 Setting and Record 8.
- **Severity:** Note.
- **Finding:** The Setting says Marcus holds AUTH-G for the gate and is the only holder. It does not say whether Marcus also holds a conferral scope. Record 8 lists "a conferral by Marcus" as an option. The same record calls the situation an authority gap in which no independent identity can fill the role. The reader has to infer that Marcus has a conferral scope but that no independent human currently holds a grant.
- **Why it matters little:** The semantics are not wrong. An authority gap is where no valid holder currently exists, and the example still shows a stop. A reader modelling a similar case could misread whether the gap is closed by re-conferral.
- **Suggested change if edited later:** Add one clause to the Setting stating whether Marcus holds a conferral scope.

### QAR6-02: WE-7 closure table contains a garbled phrase

- **Location:** `prod-w/worked-examples.md` WE-7, closure table row "I-4's successor (optional)", Who column: "Marcus (AUTH-G; a producer of neither I-4 nor its material basis closure)".
- **Severity:** Note.
- **Finding:** "its material basis closure" is not a defined term. The intended meaning appears to be that Marcus produced neither I-4 nor its material basis. The Tech Lead's sample did not flag it.
- **Suggested change if edited later:** Reword as "a producer of neither I-4 nor any member of its material basis". Do this only with a version note, since the Development Team's re-work scope was limited to metadata.

### QAR6-03: A Moderator record was drafted by the Development Team and its wording confirmation is not recorded

- **Location:** `mod-w/reviews/MODERATOR-REVIEW-STEP-06-PRE-TECH-LEAD.md`, Recording note.
- **Severity:** Note (process).
- **Finding:** The record says it "was drafted by the Development Team from the Moderator's stated decision" and is "pending the Moderator's confirmation of wording". I found no later record that the Moderator confirmed it. The handoff's status line points to it as the basis for routing to the Tech Lead. The Tech Lead and Moderator re-work reviews proceeded without mentioning it. This file is also not in the review list assigned to QA.
- **Why it matters little:** The record adds no conditions, directions, or waivers, and the routing decision it records is consistent with later Moderator records. The open point is whether the record's wording is the Moderator's own.
- **For the Moderator:** Confirm or amend the wording of that record before final acceptance, or record that it is harmless.

### QAR6-04: Guidance §20.2 and §20.3 are point-in-time producer statements

- **Location:** `prod-w/methodology-guidance.md` §20.2.1 (line 1073, "git status shows only new untracked files ... and the pre-existing modification to `mod-w/roadmap.md`") and §20.3.
- **Severity:** Note.
- **Finding:** These sections describe the working tree before the package was committed and are now historical. They are also producer-run. This review replaces the git-boundary check with a check over the commit range (above) and finds the same result. §20.3 states that part of the accepted base was not read in full, so the guidance's own self-checks do not establish full coverage.
- **Suggested change if edited later:** Add a one-line note that §20.2 and §20.3 describe the state at submission and are superseded by the review records.

## Items Left to the Moderator (not resolved here)

These were routed by the Development Team and the Tech Lead. I did not resolve them and did not expect STEP-06 to:
- RQ-02: whether basis-presentation designation becomes a protocol requirement.
- RQ-03: who may record scope vocabulary and containment relations.
- RQ-14: the record-versus-document allocation, pending Product Owner input.
- MG-N1: the DM-07 label difference between the step file and the accepted register.
- MG-N2 and MG-N3: provenance of the v0.1 drafts, and the practice-versus-rule status of the consequential-commitment default.
- MW-OBS-018 disposition.

Product Owner sign-off (3c) is still needed to confirm that intended product teams can use the guidance. QA did not test that.

## Confirmation: Final Acceptance Remains Moderator-Owned

STEP-06 final acceptance (MOD-W point 4a) belongs to the MOD-W Moderator. This QA review is Phase 3b only. It records no acceptance. It records no waiver of Product Owner sign-off (3c), and no waiver of QA. It does not edit any deliverable. Product Owner sign-off remains expected before final acceptance unless the Moderator explicitly waives it and records the waiver.

MOD-W v5.0.1
