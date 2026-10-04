---
artifact:
  type: pilot-trial
  id: PROD-W-POC
  version: 0.1
  created: 2026-10-04
  updated: 2026-10-04
  status: Draft - Development Team work product for STEP-07. Not reviewed. Not accepted.
  produced_by: Development Team
  produced_under: STEP-07
source:
  step: mod-w/step-07.md
  setup_approval: mod-w/reviews/MODERATOR-REVIEW-STEP-07-SETUP.md
  methodology_guidance: prod-w/methodology-guidance.md
  templates: prod-w/templates.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Proof-of-Concept Trial

**Status:** Draft v0.1. Development Team work product for STEP-07. Not reviewed. Not accepted. Final acceptance is pending Tech Lead review (3a), QA (3b), Product Owner sign-off (3c), and MOD-W Moderator acceptance (4a), unless any of 3a to 3c is explicitly waived and recorded.

---

## 1. Purpose and Standing

**This is a pilot.** STEP-07 runs one small, bounded product opportunity through PROD-W to see whether the accepted protocol semantics and the STEP-06 methodology can be followed coherently. It produces pilot evidence.

It is **not**: a protocol revision; a representation selection; tooling or a validator; a lifecycle graph or state vocabulary; a publication package; a proof that PROD-W is effective across product categories; or a disposition of any STEP-08 research hypothesis.

The accepted artifacts STEP-01 to STEP-06 are controlling inputs and were not modified. Where the pilot found friction, it recorded an issue and routed it (`prod-w/proof-of-concept-issues.md`). It did not patch a practice default.

**Package index**

| File | Standing |
| --- | --- |
| `prod-w/proof-of-concept-trial.md` (this file) | Pilot narrative, flow, gates, coverage, burden, limits, traceability. Draft. |
| `prod-w/proof-of-concept-records.md` | The filled pilot records R-001 to R-058, with a simulation-boundary statement and Appendix S (table-top scenarios, not records of the pilot and not evidence). Draft. |
| `prod-w/proof-of-concept-issues.md` | Method issue log, ISS-01 to ISS-22, each routed. Draft. |
| `prod-w/proof-of-concept-findings.md` | Conservative findings mapped to AC-3 and E-1 to E-9. Draft. |
| `research/mod-w-transferability/observations.md` | One proposed observation, MW-OBS-019, added under the research governance route. Proposed, not accepted. |

No other file was added. `prod-w/worked-examples.md` is unchanged and remains a set of scenarios, not evidence.

**Reading rule that governs everything below.** Every record in the pilot was written by one AI session for all actors, including the simulated human positions. Section 3 and the records file §0 state what follows from that. A reader who skips them will over-read the pilot.

---

## 2. Pilot Opportunity Description

**The Standing Card (pilot material).** A one-page, hand-derived reading aid that answers the nine questions of the reader's question card (`prod-w/methodology-guidance.md` §3.2) for one material claim, so that a reader need not open each separate PROD-W record to see the claim's standing.

- **Target user (a pilot persona, not interviewed):** a solo founder or a two-person team running PROD-W who reads their own project's record.
- **Problem claim (CL-01):** a reader cannot read a claim's standing without opening several records and scanning the whole record for absences.
- **Feasibility claims, kept separate from desirability:** a card can be derived at a point (CL-02); a card can be kept consistent over time at tolerable cost (CL-04).
- **Desirability claim, evaluative (CL-03):** the persona would find it worth producing and reading.
- **Why this opportunity.** It is small, bounded, and plausible enough for a build/no-build gate to mean something. Its evidence is **real and verifiable** (the repository at commit 4d6c908, with retrieval markers), so the pilot did not invent testimony, customers, or market data. It has a material uncertainty agent synthesis cannot resolve (whether a non-author reader finds it useful). It allows counter-evidence to be searched for and found (`RO §12.4`, and a staleness test). It has technical feasibility claims separate from commercial desirability.
- **Cost of that choice.** The product is a view of the method under test (ISS-18). Findings about the card are not findings about products in general.

---

## 3. Pilot Boundaries and Non-Claims

**In bounds:** one opportunity; a project establishment act; four actor positions; five registered sources; four claims, one assumption, one hypothesis; two inferences; two gates defined before use (a discovery gate and a build/no-build gate), each attempted; a refusal, an acceptance with residuals, a conditional progression, a revalidation requirement, a commitment, an authority gap, an invalid self-approval and its finding.

**Simulation boundary (summary; full statement in records §0).**

- One AI session (`dev-agent-1`) typed every record, including acts attributed to the human positions H-A and H-B and to `verify-agent-1`. The step file permits simulated product roles as pilot subject matter.
- **No human performed any recorded act.** Gate outcomes are scripted. No gate outcome is a determination about the opportunity by anyone with authority.
- Independence is by recorded identity only. Substantive independence could not occur and was not tested. Actor-kind binding was "none stated" and the weak point it names was not tested.
- Five events were scripted to put pressure on the method (R-033, R-045, R-047, R-048, R-054) and are labeled SCRIPTED where they occur.

**Non-claims.** The pilot does **not** show:

- that PROD-W works for any product category, team, or at any scale;
- that the Standing Card is worth building, or that any reader has the problem;
- that independent humans would behave as scripted;
- that the actor-kind weak point is or is not exploitable;
- that the readiness checklist prevents invalid acceptances;
- how long a human takes to fill the records;
- that agent agreement is evidence (the pilot did not treat it as evidence);
- that any formal-check result is acceptance (none was treated as one).

---

## 4. Role Setup and Authority Model

Established at R-001. Roles are labels that confer nothing. Authority is in grants.

| Position | Identity (kind as designated) | Root grants (R-001) | Standing in the trial |
| --- | --- | --- | --- |
| Founder / Product Owner (pilot subject) | H-A (human, simulated) | RG-1 AUTH-P; RG-2 AUTH-A; RG-3 AUTH-G gate definition (GD-D, GD-B); RG-4 AUTH-G acceptance GD-B; RG-5 AUTH-G conferral for GD-B acceptance | The establishing identity. A producer (adopter) of every claim. Cannot validly accept over its own set. |
| Reviewer / gate authority | H-B (human, simulated) | RG-7 AUTH-A; RG-8 AUTH-G acceptance GD-D and GD-B, conditional progression, exception, validation HY-01 | Independent for GD-D. Became a producer of INF-01 (revised) at R-049, and so is conflicted for GD-B. |
| Production agent | dev-agent-1 (AI) | RG-6 AUTH-P, AUTH-A | Producer of nearly all records, and typist for all simulated acts. |
| Verifier agent | verify-agent-1 (AI) | RG-9 AUTH-V, AUTH-A for FC-1 to FC-3 and invalidity findings | Same session and model as the producer. Distinct by identity only. |

**Notes.**

- The producing configuration for AI actors is at R-007 and R-008 (model `claude-sonnet-5-5`; effort not determinable; harness Claude Code in VS Code; instruction version-binding "not bound").
- Scopes are explicit lists with no containment relation.
- H-A was given an AUTH-G acceptance grant (RG-4) because the root-grant checklist leads a founder to ask for every grant it will need. Holding it is not independence (ISS-15, R-054).
- Independent AUTH-G holder named in the root grants: H-B, with a proxy-limit disclosure. Its independence was a recorded identity and was later lost for GD-B by a recorded act.
- An authority gap for GD-B was **not planned at establishment** and arose from a scripted event. The gap would have been avoidable by naming a third independent human in the establishing act.

---

## 5. Pilot Record Location and Record-Order Practice

- **Location:** `prod-w/proof-of-concept-records.md`, one file, appended in order.
- **Order:** by position number (R-001 to R-058) assigned by the writer. No second source of order exists. The file was not committed during the pilot, so git history gives no independent order. This is the recorder's own assertion alone, which the guidance advises against (G §4.5). It was stated at R-001 and logged as ISS-10.
- **Who writes:** one session, for every actor. Weak point stated at R-001.
- **Edits:** none to earlier records. Changes are new records (R-049 supersedes R-030 and leaves it visible).
- **Evaluation points:** EP-1 (after R-031) and EP-2 (after R-044), named by position.
- **Record versus document.** In the records file: common-block facts, source references, evidence items, designations, validation criteria, gate definitions, treatments, determinations, rationale text. In this file and the findings: analysis, flow, burden, limits, and mapping. Issue entries are kept in the issue log, and the records carry references to them (R-058). Assessed in section 8 and ISS-09.

---

## 6. Trial Flow Summary

| Phase | Records | What happened |
| --- | --- | --- |
| Establish | R-001 to R-008 | Project establishment with root grants and practice statements; an actor-kind binding note; four role-position entries; two producing-configuration statements. |
| Register sources | R-009 to R-013 | Five source entries. SRC-05 is the pilot's own record. |
| Frame the opportunity | R-014 to R-019 | Four claims (problem, feasibility at a point, feasibility over time, evaluative desirability), one assumption, one hypothesis with validation criteria recorded before any test. |
| Define gates before use | R-020, R-021 | GD-D (discovery) and GD-B (build/no-build), each with slots, challenge criteria, formal checks, contextual judgments, non-waivable list. Written after the claims, before any evidence. |
| Search and evidence | R-022 to R-029 | Two attempts (one partial, one finding nothing on the target), evidence items with relationships (supports, qualifies, and counter-evidence recorded in the same sitting it was found), and two producer-run tests (T-1 reading burden, T-2 two derived cards). |
| Infer | R-030, R-031 | Two inferences, separate from the evidence. |
| First gate attempt | R-032, R-033 | Readiness walk-through, then a scripted premature attempt; **refused**. |
| Challenge and check | R-034 to R-039 | An independent challenge (CH-01), a response that did not close it, a non-independent self-challenge (CH-02), two verified formal checks (FC-1, FC-2), and one advisory "unresolved" result for a criterion that is not decidable. |
| Second gate attempt | R-040 to R-044 | Readiness again, a binding note, an independence declaration, a conditional progression authorization for the assumption, and an **acceptance with named residuals** for exploration scope only. Simulated determination. |
| Post-acceptance pressure | R-045 to R-049 | A scripted staleness test produced counter-evidence (EV-07), a revalidation requirement (REQ-1, Tier 1, left open), a scripted external commitment by the founder (T-24), a scripted reviewer challenge that supplied wording, and its adoption, which made the reviewer a producer. |
| Gap, self-approval, refusal | R-050 to R-057 | Grant review found the gap before the attempt; readiness for GD-B; authority-gap record; escalation (unanswered); a scripted self-approval attempt by the founder (invalid on its face and kept visible); a finding that it is invalid; an independence declaration disclosing the reviewer's contribution; and a **refusal** of GD-B. |
| Log | R-058 | References to the 22 issues in the issue log. |

Table-top sub-scenarios (solo founder, exception, conferral cure, two-human co-production avoidance, three humans plus agent) are in records Appendix S and are not pilot evidence.

---

## 7. Gates Attempted and Outcomes

| Gate | Type | Defined | Attempts | Outcome | Basis for the outcome |
| --- | --- | --- | --- | --- | --- |
| GD-D | Discovery-style: problem framing to card-content exploration | R-020, before use | 1: R-032 and R-033 (premature, scripted). 2: R-040 to R-044. | Attempt 1 refused (R-033). Attempt 2 **accepted with unresolved CH-01, CH-02, EV-03** for exploration scope only (R-044), with CPA-1 covering assumption AS-01. **Simulated determination.** | Readiness items all "yes" at R-040. FC-1 and FC-2 satisfied (R-037, R-038). The earlier refusal was cited with what changed since. |
| GD-B | Build/no-build: authorize prototype cards for a reader test | R-021, before use | 1: R-051 and R-054 (invalid self-approval, scripted), R-055 (finding), R-057 (refusal). | **Refused (R-057).** The self-approval attempt (R-054) is invalid on its face and kept visible. | Items 4 to 9 of the readiness checklist were "no". The authority gap AG-1 had no cure in the pilot. Slot B1 (reader evidence) is empty by design. HY-01 unvalidated and relied on. REQ-1 open. |

**What the outcomes mean.** The pilot shows a discovery gate reaching a recorded acceptance with residuals only after a refusal, an independent challenge, verification, and a conditional progression authorization, and a build/no-build gate failing to progress for reasons the record states. Because the determinations are scripted, they show the *shape* of a recorded gate sequence and not that any opportunity passed or failed on its merits. **No claim relies on R-054 being valid.**

---

## 8. What Was Exercised and What Was Not Exercised

**Evidence strength key:** *Full pilot* = recorded in POC-1 (one writer, scripted). *Scripted event* = a planned pressure within POC-1. *Scenario* = table-top, Appendix S, not evidence. *Not exercised* = stated reason.

| Item the step asks for | Status | Where | Strength and note |
| --- | --- | --- | --- |
| Establishment and root grants | Exercised | R-001 | Full pilot. Simulated human. |
| Role-position and grant records | Exercised | R-003 to R-006 | Full pilot. |
| Source register, same reference reused | Exercised | R-009 to R-013 | Full pilot. Comparability judgments recorded, including "one source" for three self-generated tests. |
| Material claim, evidence, counter-evidence, negative finding | Exercised | R-014 to R-029 | Full pilot. Evidence is real and repository-based, producer-run where tests. |
| Assumption, hypothesis, inference separated | Exercised | R-018, R-019, R-030, R-031 | Full pilot. Criteria recorded before tests. HY-01 has no test and no validation. |
| Agent agreement not treated as evidence | Exercised | R-019 (agent reader set aside), R-008 | Full pilot. No agreement item exists. |
| Challenge with visible standing | Exercised | R-034 to R-036, R-048 | Full pilot. CH-01 independent and unresolved; CH-02 self, not independent; CH-03 carried. |
| Discovery-style gate | Exercised | R-020, R-032 to R-044 | Full pilot; scripted acceptance. |
| Build/no-build gate | Exercised | R-021, R-051 to R-057 | Full pilot; scripted refusal. |
| Gate readiness and decision records with accepted set, standing-record treatments, formal-check result, contextual rationale, independence declaration | Exercised | R-032, R-033, R-040, R-044, R-051, R-057 | Full pilot. |
| Formal-check result without becoming acceptance | Exercised | R-037 to R-039, R-055 | Full pilot. Effect claimed and not claimed stated each time. |
| Self-approval prevention and invalidity | Exercised | R-054, R-055 | Scripted event. Invalid on its face and kept visible. |
| Independence declaration | Exercised | R-042, R-056 | Full pilot. Cannot be false in a detectable way (ISS-01). |
| Authority-gap handling | Exercised | R-050 to R-053 | Scripted event leading to the gap. Gap found before the attempt. |
| Unresolved disagreement or non-progression | Exercised | CH-01, CH-02, CH-03, R-057 | Full pilot. **No real disagreement occurred**: one writer produced all positions. Recorded as a limit. Non-progression by refusal and residual acceptance were shown by script. |
| Conditional progression | Exercised | R-043 | Full pilot, G1 only. G2 not issuable for GD-B (AG-1). |
| Exception handling | **Not exercised** | Records Appendix S, S-2 | Nothing waivable was unsatisfied. Scenario only. |
| Revalidation trigger or request | Exercised | R-045, R-046 | Scripted event. Requirement left **open**; closure **not exercised**. A Tier 1 closure needs a fresh acceptance by an independent AUTH-G holder, and AG-1 shows none for the GD-B set. A fresh GD-D reaffirmation was not attempted to keep the pilot bounded. |
| Consequential-commitment recording (T-24) | Exercised | R-047 | Scripted event. Recognition of an unforeseen commitment not tested (ISS-17). |
| Record-versus-document distinction | Exercised and assessed | §5; ISS-09 | Full pilot. Workable for sources, designations, evidence; unclear for rationale and issue entries. |
| Grant Act Record (T-3) | **Not produced** | Records Appendix S, S-3 | No grant changed. Cure by conferral was not pursued. Scenario only. |
| Imported prior work (T-26) | **Not applicable** | Records R-058 | No earlier project. |
| Actor-kind binding (T-25) | Exercised formally | R-002, R-041 | Vacuous: the binding method is "none stated" because no human acted. |
| Producing configuration (T-11) | Exercised | R-007, R-008 | Version-binding "not bound" (ISS-19). |
| Grant review (T-27) | Exercised | R-050 | Scripted prompt; found the gap before the attempt. |
| Same-day counter-evidence recording | Exercised, weakly | R-026, R-045 | Recorded in the same sitting it was found. One writer in one sitting makes this near-trivial. A real team's habit was not tested. |
| Three-human plus agent, two-human, solo founder | Scenarios only | Appendix S, S-1, S-4, S-5 | Scenario. Not evidence. |
| Worked examples remain scenarios | Maintained | Records Appendix S header | No worked example is cited as evidence. |

---

## 9. Burden and Usability Notes

**Measured or counted (all from the Development Team's own work):**

- **Records:** 58 in 13 record groups, of which 53 carry a compact common-block line (one line carrying the eleven prompts) and 5 do not (two configuration statements, two independence declarations, and the issue reference record).
- **Record kinds used (by template):** T-6 evidence 7, T-4 source 5, T-5 claim 4, T-2 role position 4, T-15 gate decision 4, T-12 challenge 4, T-8 inference 3, T-22 formal check 3, T-14 readiness 3, and T-7, T-25, T-16, T-13, T-11 two each; T-9, T-10, T-27, T-24, T-23, T-21, T-20, T-19, T-17, T-1 once each.
- **Repeated fields:** the producing-configuration reference repeats in 32 of 58 records (R-007) and 4 more (R-008). The same grant, work assignment, and "other producers" lines repeat across the producer records. The eleven-prompt block was compressed to one line (ISS-04).
- **Volume:** the records file is about 14,000 words. The issue log is about 3,800 words.
- **Minimum artifact set for one discovery gate** (the pilot's GD-D path, R-009 to R-044): 36 records, of which about 26 are the producer agent's, 6 are the reviewer's, 3 are the verifier's, and 1 is the founder's (the gate definition). This is a count by position and not a time.
- **Minimum artifact set for one build/no-build gate that ends in refusal** (R-045 to R-057 plus the gate definition at R-021): 14 records, mostly produced by the pressure events (a staleness test, a request, a commitment, a challenge, a revision, a review, readiness, gap, escalation, attempt, finding, declaration, refusal).
- **Time:** the shell clock read 07:26 at the first command after the inputs were read and 07:38 after the last pilot file was written, so about 12 minutes of timed authoring for all four files and the evidence searches, plus untimed reading of the inputs before 07:26. That is the AI's authoring time in one session. It is not a human estimate, and no human estimate is offered because none is supportable (ISS-20).

**Temptations and friction recorded (each is a candidate burden signal):**

- To compress the common block (ISS-04): taken, knowingly.
- To leave forward fields in claim records (ISS-02): "none at recording" had to be written in every claim.
- To skip the gate definition until after the evidence: not taken. The definitions were written first, and the pilot recorded that tailoring cannot be detected (ISS-07).
- To write the self-approval attempt as quietly as possible: not taken. It was recorded in full, with a declaration that discloses the founder's producer status, and the finding names three violated rules.
- To label a reviewer's helpful wording as ordinary comment: not taken, but the template made the other path easy (ISS-06).
- To treat the verifier's result as "the gate passed": not taken. Effect claimed and not claimed stated each time.
- To treat the agent reader as a stand-in for the missing human reader: considered and set aside at R-019.

**Unclear prompts:** template 9 "testable?" (ISS-05); card question 6 "current" (ISS-03); template 21 request versus trigger (ISS-13); treatment wording "answered" (ISS-21).

**Heaviness.** The Product Owner's remark that the templates are "usable but heavy" (SRC-03) is consistent with the pilot's counts. Whether a human would find them too heavy is not tested.

---

## 10. Limits of the Evidence

1. **One writer.** Every record was typed by one AI session. This is the largest limit. It removes real disagreement, real independence, and real human behavior (ISS-01).
2. **Scripted outcomes.** Five events and both gate outcomes were planned. The pilot shows that the method can record them, and cannot show that they would occur.
3. **One opportunity.** A reading aid for the method under test (ISS-18). Not representative.
4. **Self-generated evidence.** Tests T-1, T-2, T-3 were run by the producer on the producer's own records (ISS-11). Real sources are repository text only. No external source, no user, no market evidence was used.
5. **Same-session verifier.** `verify-agent-1` is the same model and session as the producer (ISS-08).
6. **No clock, no independent order.** Record order is by position (ISS-10, ISS-16).
7. **Instructions not bound** (ISS-19).
8. **No time measurement for humans** (ISS-20).
9. **The records are not committed.** Git history contributes nothing to order or tamper-evidence.
10. **Reading coverage.** The templates, guidance (lines 1 to 1000), and the parts of the semantics cited were read. The `rule-judgment-boundary.md`, `evidence-knowledge-model.md`, `gate-challenge-revalidation-semantics.md`, and `protocol-semantics.md` files were **not read in full**. Rule IDs cited in the records were taken from the methodology guidance's citations of them and not checked against the originals. A reviewer should check the cited rules (GCR-03, GCR-05, GCR-09, GCR-10, GCR-17, GCR-25, GCR-39, GCR-48, CRC-19, CRC-59, CRC-64, TRG-2, PR-11, PR-17, PR-19, PR-27) against the accepted text. A misstated rule would be a defect in the records.

---

## 11. Traceability to AC-3 and E-1 to E-9

Findings are in `prod-w/proof-of-concept-findings.md`. This table says where each requirement is addressed in the pilot.

| Requirement | Addressed by | Pilot result in one line |
| --- | --- | --- |
| AC-3 One small opportunity taken through PROD-W workflow | Sections 2, 6, 7; records R-001 to R-058 | One bounded opportunity was run through establishment, evidence, challenge, two gates, and revalidation, in a simulated and scripted pilot. |
| E-1 Protocol feasibility | Sections 6 to 8; ISS-04, ISS-02 | The protocol's acts and records could be followed in one case without a rule conflict. Not tested with independent actors. |
| E-2 User applicability | Sections 8, 9; ISS-04, ISS-12, ISS-15, ISS-20 | Not demonstrated. No user took part. Burden counts only. |
| E-3 Discipline enforcement | R-033, R-054, R-055, R-057 | The record made invalid and non-progressing acts visible. Enforcement by people is not tested. |
| E-4 MOD-W transferability | MW-OBS-019 (proposed); ISS-01, ISS-18 | Two concrete observations are proposed. None accepted. |
| E-5 Role model coherence | Section 4; R-003 to R-006, R-050 | Role labels, grants, capacities, and work assignments stayed separable. The role model gave a clear reason for each refusal. |
| E-6 Evidence quality | R-014 to R-031 | Claim, evidence, counter-evidence, negative finding, assumption, hypothesis, inference were kept apart. Evidence quality itself is limited (ISS-11). |
| E-7 Authority clarity | R-001, R-050 to R-055 | Grants and chains were readable. A gap and a self-approval were identified from the record. |
| E-8 Workflow progression semantics | Section 7; R-033, R-044, R-057 | Refusal, residual acceptance, conditional progression, revalidation requirement, and stop were recordable without a lifecycle graph. |
| E-9 Automated enforceability boundary | R-037 to R-039, R-055 | The decidable checks were separable from judgments. Formal results did not become acceptance. No tool exists or was built. |

---

MOD-W v5.0.1
