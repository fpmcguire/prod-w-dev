---
artifact:
  type: pilot-records
  id: PROD-W-POC-REC
  version: 0.1
  created: 2026-10-04
  updated: 2026-10-04
  status: Draft - Development Team work product for STEP-07. Not reviewed. Not accepted.
  produced_by: Development Team
  produced_under: STEP-07
source:
  step: mod-w/step-07.md
  setup_approval: mod-w/reviews/MODERATOR-REVIEW-STEP-07-SETUP.md
  templates: prod-w/templates.md
  methodology_guidance: prod-w/methodology-guidance.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
  pilot_project: POC-1 (a pilot-subject project; not a project of prod-w-dev)
---

# PROD-W Proof-of-Concept Pilot Records

**Status:** Draft v0.1. Development Team work product for STEP-07. Not reviewed. Not accepted.
**Standing:** Pilot evidence only. These are filled records of one bounded trial, written with the STEP-06 template wording as human-readable prompts. They are not a schema, not a serialization, and not a representation choice. Nothing here changes protocol semantics or any accepted artifact.

**Short names.** PS, EK, GC, RJ, RO, G as in `prod-w/templates.md`. T-n = template n in `prod-w/templates.md`. Index, flow, gates, and non-claims are in `prod-w/proof-of-concept-trial.md`. Issues are in `prod-w/proof-of-concept-issues.md`. Findings are in `prod-w/proof-of-concept-findings.md`.

---

## 0. Read This First: The Simulation Boundary

**Every record in this file was typed by one AI session (the Development Team, accountable actor position `dev-agent-1`).** The pilot project POC-1 has four actor identities: two human positions (H-A, H-B), one AI producer position (`dev-agent-1`), and one AI verifier position (`verify-agent-1`). The step file permits the Development Team to simulate or instantiate product roles inside the trial, as pilot subject matter (`mod-w/step-07.md`, Governance Context). So:

- **No human performed any act recorded here as H-A or H-B.** Those acts are scripted pilot-subject acts, typed by `dev-agent-1`. Where this file says "H-B accepts", it means "the script has the H-B position accept". It is not a determination by a person.
- **Independence in POC-1 is by recorded identity only.** One session wrote every record, so substantive independence (who supplied the conclusion) could not occur in fact and cannot be tested. Substance is declared in the script and is not evidence.
- **The actor-kind binding method for H-A and H-B is "none stated"** in the only honest sense: the designation "human" is a pilot-subject designation. The record's weak point (RO §9.5) is not tested by this pilot.
- **`verify-agent-1` is a different accountable position instantiated by the same session** with the same model and no separate context. Its distinctness is a recorded identity, not a reviewer. This is the same-model-family limit (PR-27, PR-28) in its strongest form.
- **Scripted events.** Five events were planned by the Development Team to put pressure on the method. They are labeled SCRIPTED at the point they occur: a premature gate attempt (R-033), a reviewer who supplies wording (R-048), a new counter-evidence result after acceptance (R-045), an external promise by the founder (R-047), and a self-approval attempt (R-054). Events not labeled SCRIPTED were not planned as events, but all content is still produced by one author.

**What follows from this.** The records show whether the STEP-06 templates and defaults can be followed to produce a coherent, traceable record, and how heavy that is. They do not show that independent humans would behave this way, and **no gate outcome below is a determination about the pilot opportunity by anyone with authority**.

**Compact common block.** The common block (T-0.1) has eleven prompts. To keep this file readable, each record carries them on one `CB:` line, in this order: recorded by; actor kind; capacity; grant relied on; position; target; producing configuration; other producers; work assignment. (Record ID and record kind are in the heading.) Collapsing the block this way was a temptation, and the pilot recorded it (ISS-04). Time is not recorded per record. Position in this file is the record position (see R-001 practice statements). The date for every record is 2026-10-04 unless stated.

**Item aliases.** A record carries a record ID (R-nnn, the position) and, where useful, an item alias (CL-01, EV-03). The alias is a convenience reference, not an identifier scheme.

---

## 1. Establishment, Roles, and Configuration (R-001 to R-008)

### R-001 Project Establishment Record (T-1)

```text
CB: H-A; human (designated, simulated - see §0); producer-of-record of this act as establishing identity; grant: none required (establishing act); position 1; target: project POC-1; config: not applicable (a simulated human act; typed by dev-agent-1, R-007 applies to the typing); other producers: dev-agent-1 (typist, simulating); assignment: none.

Marked as: the establishing act of POC-1's authority chain.
Project name: POC-1 "Standing Card" pilot.
Project boundary: the investigation of one small opportunity (the Standing Card, defined at R-014) as pilot material, up to a discovery gate (GD-D) and a build/no-build gate (GD-B). Nothing else.
What this project is NOT: not prod-w-dev; not a project that governs any accepted artifact; not a market study; not a product that will be built; not tooling.
Basis for the establishing identity's standing (an assertion; not checked): H-A is the pilot-subject founder position. The standing is simulated.

ROOT GRANTS recorded by this act:
  RG-1  Grantee H-A. Class AUTH-P. Scope: all POC-1 items. Granting authority: this act.
  RG-2  Grantee H-A. Class AUTH-A. Scope: all POC-1 items.
  RG-3  Grantee H-A. Class AUTH-G. Scope: gate definition for GD-D and GD-B.
  RG-4  Grantee H-A. Class AUTH-G. Scope: acceptance for GD-B only. (See "temptation note" below.)
  RG-5  Grantee H-A. Class AUTH-G. Scope: conferral for the acceptance scope of GD-B only.
  RG-6  Grantee dev-agent-1. Class AUTH-P and AUTH-A. Scope: all POC-1 items.
  RG-7  Grantee H-B. Class AUTH-A. Scope: all POC-1 items.
  RG-8  Grantee H-B. Class AUTH-G. Scope: acceptance for GD-D; acceptance for GD-B; conditional progression and exception for GD-D and GD-B; validation for HY-01.
  RG-9  Grantee verify-agent-1. Class AUTH-V and AUTH-A. Scope: formal checks FC-1, FC-2, FC-3 and any finding that an acceptance of GD-D or GD-B is invalid, for criteria designated decidable in the gate definitions.
  Scopes are stated as explicit lists with no containment relation (G §4.7).
  Granting authority for RG-1 to RG-9: this establishing act.

Everything the establishing identity needs for itself is above: yes.
  Note on RG-4: H-A is a producer of the pilot opportunity and so cannot validly accept GD-B over its own basis. RG-4 exists because the root-grant checklist (G §4.3, first row) asks whether every grant the establishing identity will need for itself is in this act, and a solo founder following it reaches for AUTH-G. Holding the grant is not independence. It is recorded so that the first valid test of self-approval is visible (R-054). Logged as ISS-15.
Independent AUTH-G holder(s) named in root grants for the gates expected soon: yes (H-B, RG-8).
  Why H-B is claimed independent (the proxy-limit disclosure, G §4.3): H-B is a distinct pilot-subject human position, appointed to review and accept, and is not an author of any item at establishment. In the pilot this claim is only a recorded identity, because one session writes both (see §0). It can be challenged.

Initial role-position appointments: R-003 to R-006.

PRACTICE STATEMENTS (project-level practice, not protocol):
  What counts as "recorded": an entry placed by an identified actor in this file at the next position. A private draft is not recorded.
  Where records are kept: `prod-w/proof-of-concept-records.md` (this file), appended in order.
  Who can write, and who can edit whose records: only the Development Team session can write to this file, for every actor including the simulated humans. No actor edits another's record. A change to an earlier record is a new record. Weak point stated: the writer controls the whole record location.
  How record order is established, and by whom: by position number in this file, assigned by the writer. This is the recorder's own assertion alone, which G §4.5 advises against. No second order source exists in the pilot. The file is not committed during the pilot, so git history gives no independent order. Logged as ISS-10.
  How backdating or out-of-order entries are handled: none occurred. Any would be a new visible record.
  How actor identity is recorded: by the identities H-A, H-B, dev-agent-1, verify-agent-1. Role labels confer nothing.
  How actor kind is designated and what binding is recorded: designated here. T-25 note at R-002 for H-A and at R-041 for H-B. Binding is none stated and simulated.
  Source-identity convention: T-4 entries R-009 to R-013 with project-local references SRC-nn, reused. "Unclear" comparability is treated as one source.
  Producing-configuration convention: T-11 statements R-007 and R-008. Each AI-produced record cites one by position.
  Commitment routing practice: consequential commitments go through a gate acceptance or a decision record. A commitment outside the gates uses T-24. "Consequential" for POC-1 means an external promise, a resource commitment beyond one working session, or a direction change.
  Grant review practice: T-27 before any gate attempt. One review in the trial (R-050).
  How carried-over work is treated: not applicable. No earlier project exists.

Known authority gaps and limitations at establishment: (1) Simulation boundary (§0). (2) No independent AUTH-G holder for GD-B exists beyond H-B, whose independence is not yet tested. (3) No human reader is available to the pilot, so reader-facing evidence cannot be obtained.
Imported prior work: none.
```

### R-002 Actor-Kind Binding Note (T-25), H-A

```text
CB: H-A; human (designated); producer-of-record; grant: none required; position 2; target: R-001; config: not applicable (simulated, typed by dev-agent-1); other producers: dev-agent-1 typist; assignment: none.

Actor identity: H-A.
Kind as designated, who designated it, when, under what grant: human; designated by H-A in R-001 (the establishing act, no grant).
Binding method recorded: [x] None stated. (The designation is a pilot-subject designation. No access control, credential, out-of-band confirmation, or attestation applies. The writer of the record is an AI session.)
Known limits of this method: the whole method is absent. Anyone, or any agent, can write "H-A" here.
Claim made: "The record designates this actor as human and states the method above, which is none."
Claim NOT made: that anything guarantees a human acted. In this pilot a human did not act.
```

### R-003 Role-Position Entry (T-2), Founder / Producer

```text
CB: H-A; human; producer; grant RG-1..RG-5; position 3; target: role position; config: n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

Role position (label, confers nothing): Founder / Product Owner (pilot subject).
Actor(s) assigned: H-A, human (designated).
Grants relied on: RG-1 AUTH-P; RG-2 AUTH-A; RG-3 AUTH-G gate definition (GD-D, GD-B); RG-4 AUTH-G acceptance GD-B; RG-5 AUTH-G conferral for GD-B acceptance. All conferred by R-001.
Is the appointment itself grant-bearing? Yes. The grants are conferred in R-001 (root grants), so no separate T-3 is needed.
Capacities expected: producer; challenger-reviewer; gate-definition author.
Items this actor has produced or materially influenced: adopts the opportunity framing (R-014 to R-017); authors GD-D and GD-B (R-020, R-021).
Independence limits and known conflicts: H-A is a producer of all claims in POC-1. H-A cannot validly accept, authorize, waive, reaffirm, or close in its own favor. RG-4 and RG-5 cannot be used favorably over the GD-B accepted set while H-A is a producer of it.
Combined with another position? No.
Escalation route: AUTH-G for the GD-B acceptance scope; holders now: H-A (conflicted), H-B (see R-050, R-052).
Fallback actor and grant needed: a third independent human with AUTH-G for GD-B acceptance (none exists).
Date or event for review of this entry: before each gate attempt (T-27, R-050).
```

### R-004 Role-Position Entry (T-2), Reviewer / Gate Authority

```text
CB: H-B; human (designated, simulated); capacity: n/a (appointment record written by H-A as recorder of R-001 content); grant: n/a; position 4; target: role position; config: n/a; other producers: dev-agent-1 typist; assignment: none.

Role position: Reviewer and gate authority (pilot subject).
Actor(s) assigned: H-B, human (designated).
Grants relied on: RG-7 AUTH-A; RG-8 AUTH-G (acceptance GD-D and GD-B; conditional progression and exception GD-D and GD-B; validation HY-01). Conferred by R-001.
Is the appointment itself grant-bearing? Yes (root grants in R-001).
Capacities expected: challenger-reviewer; acceptor.
Items this actor has produced or materially influenced: none at establishment.
Independence limits and known conflicts: H-B must not edit items or supply conclusions or wording. H-B may challenge and then accept (G §6.1). H-B performs no verification it later relies on.
Combined with another position? No.
Escalation route: another AUTH-G holder for the gate; none exists besides H-A.
Fallback actor and grant needed: none designated.
Date or event for review: before each gate attempt.
```

### R-005 Role-Position Entry (T-2), Producer Agent

```text
CB: dev-agent-1; AI; producer; grant RG-6; position 5; target: role position; config: R-007; other producers: none; assignment: none.

Role position: Production agent.
Actor(s) assigned: dev-agent-1, AI.
Grants relied on: RG-6 AUTH-P and AUTH-A, conferred by R-001.
Is the appointment itself grant-bearing? Yes (root grant).
Capacities expected: producer of claims, evidence, attempts, inferences, assumptions; challenger (non-independent as to its own items).
Items produced or materially influenced: all POC-1 items other than gate definitions and decisions and challenges authored by H-B.
Independence limits and known conflicts: a producer. Holds no AUTH-G or AUTH-V. Agreement with itself is not corroboration (EKR-17).
Combined with another position? No.
Escalation route: H-A for gate definition matters; H-B for acceptance matters.
Fallback actor: none.
Review event: before each gate attempt.
```

### R-006 Role-Position Entry (T-2), Verifier Agent

```text
CB: verify-agent-1; AI; verifier; grant RG-9; position 6; target: role position; config: R-008; other producers: none; assignment: none.

Role position: Formal-check verifier.
Actor(s) assigned: verify-agent-1, AI.
Grants relied on: RG-9 AUTH-V (FC-1, FC-2, FC-3 and invalidity findings for criteria designated decidable) and AUTH-A. Conferred by R-001.
Is the appointment itself grant-bearing? Yes.
Capacities expected: verifier; producer of advisory formal-check results.
Items produced or materially influenced: none of the items it verifies. Stated limit: it is the same session as dev-agent-1 (§0). Distinctness is by identity only.
Independence limits and known conflicts: must produce nothing it verifies (GCR-10). Same-model-family and same-session limit recorded in R-008.
Combined with another position? No.
Escalation route: H-A (gate definition) for criteria questions.
Fallback actor: none.
Review event: before each gate attempt.
```

### R-007 Producing-Configuration Statement (T-11), dev-agent-1

```text
Item or act produced: all records attributed to dev-agent-1, and (as typist-simulator) all records attributed to H-A and H-B.
Actor identity (position): dev-agent-1.
Model: Claude Sonnet 5.5 (identifier `claude-sonnet-5-5`, as stated in the session environment).
Reasoning effort: not determinable. The session carried an effort setting whose scale is not exposed to the actor.
Harness or runtime: Claude Code (VS Code extension), single session.
Tooling: file read, write, edit, search (Grep, Glob), and shell commands in the working repository. No web access was used.
Instructions in force at the act:
  Content or reference: the Development Team task brief for STEP-07 (pasted by the user), `mod-w/step-07.md`, `mod-w/reviews/MODERATOR-REVIEW-STEP-07-SETUP.md`, and the session's standing system instructions.
  Version-binding method used: not bound. The brief text is not copied into this record, and the standing instructions cannot be recovered by the actor. Repository files read are bound only by the repository head at 2026-10-04: commit 4d6c908.
  Includes: system or standing instructions; task brief; templates given (`prod-w/templates.md`); role charters read (`prod-w/role-charters.md` headings only).
Source inputs supplied: SRC-01 to SRC-05 (R-009 to R-013).
Human role in the output: generated unaltered (no human edited the records before this handoff).
Reviewer limitation: any reviewer that is a Claude-family model shares this producer's blind spots. verify-agent-1 is the same session.
```

### R-008 Producing-Configuration Statement (T-11), verify-agent-1

```text
Item or act produced: R-037, R-038, R-039, R-055, and any other verifier act.
Actor identity (position): verify-agent-1.
Model: same as R-007.
Reasoning effort: not determinable (as R-007).
Harness or runtime: same session as R-007. It is not a separate run.
Tooling: same as R-007.
Instructions in force at the act: the role-position entry R-006, the gate definitions R-020 and R-021, and the criteria text FC-1 to FC-3 in those definitions. Version-binding: the gate-definition records are at fixed positions in this file, so the text is recoverable as it stood at the check, provided the file is not edited. Edits are not detectable from inside the file (ISS-10).
Source inputs supplied: the records examined, named in each result.
Human role in the output: generated unaltered.
Reviewer limitation: the same model, the same session, and the same author as the records it verifies. Its verification satisfies GCR-10 only by recorded identity.
```

---

## 2. Source Register (R-009 to R-013)

### R-009 Source Register Entry (T-4), SRC-01

```text
CB: dev-agent-1; AI; producer; AUTH-P (RG-6); position 9; target: evidence slots; config R-007; other producers: none; assignment: H-A to dev-agent-1, "register sources", no conclusions specified.

Source reference: SRC-01.
Description: the "reader's question card" (nine questions) and its stated status as non-normative orientation, and the statement that its usefulness is evidence for STEP-07 to gather.
Origin or owner: Development Team, STEP-06 work product, accepted by the Moderator for STEP-06.
Location: `prod-w/methodology-guidance.md` §3.2, §18.1 (RQ-10 row), §20.1 table (RQ-10 row).
Version or retrieval marker: repository head 4d6c908, read 2026-10-04.
Date observed: 2026-10-04.
Kind: artifact or data set.
Derived from other sources: none known.
Related sources that may be the same source: none. (SRC-02 is a different artifact that the guidance cites; the guidance's wording is the Development Team's own.)
Comparability: distinct from SRC-02, SRC-03, SRC-05. Reason: different files and authors-by-position.
Limits: it is the producing team's own prior work. It records a question, not a finding.
```

### R-010 Source Register Entry (T-4), SRC-02

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 10; target: evidence slots; config R-007; other producers: none; assignment: as R-009.

Source reference: SRC-02.
Description: the accepted STEP-05 position on views, the eight visibility invariants VI-1 to VI-8, and the reasons a single-valued status and a hand-authored view are risky.
Origin or owner: Development Team, STEP-05 work product, accepted.
Location: `prod-w/representation-options.md` §12.4 and §12.5.
Version or retrieval marker: repository head 4d6c908, read 2026-10-04.
Date observed: 2026-10-04.
Kind: artifact or data set.
Derived from: none known.
Related sources: SRC-01 cites SRC-02 for RQ-10. Treated as related, not the same.
Comparability: distinct from SRC-01 (different text, different date of authorship); related by citation.
Limits: it argues from the semantics. It reports no reader or user observation.
```

### R-011 Source Register Entry (T-4), SRC-03

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 11; target: evidence slots; config R-007; other producers: none; assignment: as R-009.

Source reference: SRC-03.
Description: the Product Owner's STEP-06 sign-off, including its "Suggested STEP-07 Pilot Focus" and its note that the templates are "usable but heavy".
Origin or owner: the prod-w-dev Product Owner (a MOD-W role position).
Location: `mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-06.md`.
Version or retrieval marker: repository head 4d6c908, read 2026-10-04.
Date observed: 2026-10-04.
Kind: testimony (recorded as testimony).
Derived from: none known.
Related sources: none.
Comparability: distinct.
Limits: the author is a MOD-W reviewer of the method, not a target user of a Standing Card. It says nothing about readers of a pilot project's records.
```

### R-012 Source Register Entry (T-4), SRC-04

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 12; target: AT-01, AT-02; config R-007; other producers: none; assignment: as R-009.

Source reference: SRC-04.
Description: the results of text searches of the repository, run by dev-agent-1 for the attempts AT-01 and AT-02.
Origin or owner: dev-agent-1 (the searcher). The underlying files are the repository's.
Location: searches over `prod-w/*.md`, `mod-w/*.md`, `mod-w/reviews/*.md`, `research/mod-w-transferability/*.md`. Terms are in R-022 and R-023.
Version or retrieval marker: repository head 4d6c908, run 2026-10-04.
Date observed: 2026-10-04.
Kind: search result.
Derived from: the repository files searched.
Related sources: may be the same as SRC-01 to SRC-03 where a hit lies in those files. Comparability: unclear relative to SRC-01, SRC-02, SRC-03. Reason: a search hit is a pointer into those files. Treated as one source with them for independence expectations (G §8.3).
Limits: text matching only. It cannot find a synonym or a thing not written down.
```

### R-013 Source Register Entry (T-4), SRC-05

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 13; target: EV-05, EV-06, EV-07; config R-007; other producers: none; assignment: as R-009.

Source reference: SRC-05.
Description: this pilot's own records, at stated evaluation points.
Origin or owner: dev-agent-1 and the simulated actors, all typed by one session.
Location: this file.
Version or retrieval marker: evaluation point by record position (EP-1 = after R-031; EP-2 = after R-044). The file is not bound by hash.
Date observed: 2026-10-04.
Kind: artifact or data set.
Derived from: none (primary, within the pilot).
Related sources: none.
Comparability: distinct from SRC-01 to SRC-04, but EV-05, EV-06, and EV-07 all rest on SRC-05 and are therefore one source. Self-generated: the producer of the tested records is the producer of the test.
Limits: cannot show how an independent reader reads the records. Logged as ISS-11.
```

---

## 3. Claims, Assumption, Hypothesis (R-014 to R-019)

### R-014 Claim Record (T-5), CL-01 (problem)

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 14; target: GD-D; config R-007; other producers: H-A (adopted the opportunity framing; a producer); assignment: H-A to dev-agent-1, "propose one small opportunity", H-A did not specify the conclusion.

OPPORTUNITY (pilot material, not a real-market claim): the "Standing Card". A one-page, hand-derived reading aid that answers the nine questions of G §3.2 for one material claim, so a reader need not open each separate record. Target user (a pilot persona, not interviewed): a solo founder or two-person team running PROD-W who reads their own project's record. It is a document-form aid, not tooling and not a generated view.

Claim text: A reader of a PROD-W record cannot read the standing of one material claim without opening several separate records and scanning the whole record for the absence of others.
Claim kind: material.
Materiality designation and basis: material. A change in its standing would plausibly change the discovery gate decision (GD-D).
Basis-presentation designation: not applicable (not evaluative).
Evidence attached: EV-01 (qualifies), EV-02 (supports), EV-05 (supports, producer-run test).
Counter-evidence attached: none found beyond the qualifications. Attempt records AT-01 and AT-02.
Assumptions relied on: AS-01.
Inferences relied on: INF-02.
Items that rely on this claim: GD-D basis (material); INF-02.
Challenges against this claim: none at recording. (Under append-only practice this field cannot be filled for later challenges; see ISS-02.)
Gate or decision this claim bears on: GD-D.
```

### R-015 Claim Record (T-5), CL-02 (technical feasibility, at a point)

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 15; target: GD-D; config R-007; other producers: H-A (adopted); assignment: as R-014.

Claim text: At a stated evaluation point, a Standing Card for one material claim can be derived by hand from the records so that each of the nine questions is answered from the record alone, or is stated as not answerable from the record.
Claim kind: material.
Materiality designation and basis: material. A change in its standing would plausibly change GD-D, as it is the technical-feasibility slot. It is kept separate from commercial desirability (CL-03).
Evidence attached: EV-06 (supports; producer-run test). EV-03 (qualifies).
Counter-evidence attached: EV-03 is attached as qualifying. Attempts: AT-01.
Assumptions relied on: none recorded at creation.
Inferences relied on: none.
Items that rely on this claim: GD-D basis; INF-01.
Challenges against this claim: none at recording.
Gate or decision this claim bears on: GD-D.
```

### R-016 Claim Record (T-5), CL-04 (technical or operational feasibility, over time)

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 16; target: GD-D, GD-B; config R-007; other producers: H-A (adopted); assignment: as R-014.

Claim text: A hand-derived Standing Card can be kept consistent with the record as the record grows, at a cost small enough that a solo founder or two-person team would keep doing it.
Claim kind: material.
Materiality designation and basis: material. Operational feasibility is separate from CL-02 (a card at one point) and from CL-03 (desirability). A change in its standing would plausibly change both gates.
Evidence attached: none at recording ("none exists").
Counter-evidence attached: EV-03 (contradicts; recorded at R-026). The producer had already read SRC-02 §12.4 when recording this claim, so it states here that counter-evidence exists and is attached at R-026.
Assumptions relied on: none recorded. (Cost is not estimated anywhere in the pilot.)
Inferences relied on: none.
Items that rely on this claim: GD-D basis (as an included claim); GD-B basis.
Challenges against this claim: none at recording.
Gate or decision this claim bears on: GD-D, GD-B.
```

### R-017 Claim Record (T-5), CL-03 (evaluative; commercial desirability)

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 17; target: GD-B; config R-007; other producers: H-A (adopted); assignment: as R-014.

Claim text: A solo founder or two-person team would find a Standing Card worth producing and reading, relative to reading the records or using the question card alone.
Claim kind: evaluative and material.
Materiality designation and basis: material. This is the build/no-build question.
Basis-presentation designation: presented as a value judgment. Not presented as observed fact or as established by evidence alone.
Evidence attached: none exists. EV-04 qualifies (a burden concern from a non-user).
Counter-evidence attached: none found. No attempt could reach target users (AT-02 reach).
Assumptions relied on: AS-01.
Inferences relied on: none.
Items that rely on this claim: GD-B basis.
Challenges against this claim: none at recording.
Gate or decision this claim bears on: GD-B.
```

### R-018 Assumption Record (T-9), AS-01

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 18; target: CL-01, CL-03; config R-007; other producers: H-A (adopted); assignment: as R-014.

Assumption: The reader of a PROD-W record is a person who did not write it (a founder reading a teammate's records, or a returning author), and that reader matches the Standing Card's pilot persona.
What relies on it: CL-01 and CL-03, under assumption (reliance marks on those dependency links).
Why it is being relied on now: no non-author reader is available to the pilot, and the claims cannot be framed without a reader.
What would follow if it is false: CL-01 may be about the author's own convenience only, and CL-03 may have no buyer.
Is it testable? In principle yes, in this trial no (no reach to any reader). Kept as an assumption because no validation criteria exist. Logged as ISS-05 (the template's yes/no does not fit "testable in principle, not here").
Material? yes.
Path to resolution: remains open.
Consequential reliance (inside a gate acceptance)? yes, at GD-D. T-17 reference: CPA-1 (R-043). Without it the GD-D acceptance would be invalid (CRC-19).
```

### R-019 Hypothesis Record (T-10), HY-01

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 19; target: CL-03, GD-B; config R-007; other producers: H-A (adopted); assignment: as R-014.

Hypothesis: A reader who did not write a project's records, given only a Standing Card for one claim, states that claim's standing as the same reader would state it from the full records.
Validation criteria (recorded before any test):
  What would support it: for one claim, the reader's stated answers to the nine questions match answers derived from the full records at the card's evaluation point, with each non-answerable question stated as non-answerable.
  What would weaken it: a mismatch on any of questions 3 to 7 (contested, exposed, reliance, open requirement, acceptance).
  What would refute it: the reader states a claim as accepted or current when the records show an open requirement or an unresolved challenge.
Scope it would be validated for: one claim, one reader, one evaluation point.
Tests run and results: none. No human reader is available. (An agent reader was considered and not run. An agent's result would be agent agreement and would not stand in for a human reader. It was set aside to avoid laundering it as validation.)
Evidence attached: none. Counter-evidence attached: none.
Challenges: none at recording.
Relied on by (dependents) before validation: yes (GD-B basis). Consequential: yes, at GD-B. T-17 reference: none exists. This is a defect to resolve before any GD-B acceptance.
Validation: none recorded.
Criteria amended after results recorded: no.
```

---

## 4. Gate Definitions, Recorded Before Use (R-020 to R-021)

### R-020 Gate Definition (T-13), GD-D

```text
CB: H-A; human (simulated); gate-definition author; grant RG-3; position 20; target: gate GD-D; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

Gate name: GD-D "Discovery to card-content exploration".
PROGRESSION AND SCOPE
  What may cross: movement of the pilot opportunity from problem framing to exploring what a Standing Card should contain.
  For what scope: exploration of content only. Not a build, not a reader test, not tooling, not generated views.
  Why this scope (judgment): the scope is low-cost and reversible and does not rely on HY-01.
ACCEPTOR GRANTS AND ACCEPTANCE RULE
  AUTH-G grants that may accept: RG-8 (H-B).
  Number of valid independent acceptances required: one.
  Role-conflict resolver for this gate: none designated.
GATE BASIS
  Subject: the Standing Card opportunity as framed in CL-01, CL-02, CL-04.
  Basis items expected in the accepted set: CL-01, CL-02, CL-04; EV-01, EV-02, EV-03, EV-05, EV-06; AT-01, AT-02; INF-02; AS-01; the materiality designations on these.
REQUIRED EVIDENCE
  Slot S1 "Problem": target CL-01; dimension problem; kinds: artifact, search result, experiment or test result; source-independence: no more than one item per source reference; recency: none; counter-evidence search required: yes, reach: the repository, text search for existing aids (stated in the attempt record).
  Slot S2 "Feasibility at a point": target CL-02; dimension technical feasibility; kinds: experiment or test result; source-independence: not applicable (one test is expected); counter-evidence search required: yes, EV-03 must be attached and treated.
REQUIRED CHALLENGE CRITERIA
  Targets that must have been challenged: CL-01.
  Challenger independence required: yes (an actor who produced none of CL-01's basis).
  Response rule stricter than default: none.
FORMAL CHECKS
  FC-1: each evidence item in the basis records a source reference, producer, observation time, target, relationship, and a limitations statement. Designated decidable by H-A. Independent verification required: yes.
  FC-2: the acceptor is a producer of no member of the accepted set. Designated decidable by H-A. Independent verification required: yes.
STRICTER CONDITIONS
  Every evaluative claim in the basis carries a basis-presentation designation. (No evaluative claim is in GD-D's basis. Recorded so the condition is in force.)
CONTEXTUAL JUDGMENTS THE ACCEPTOR MUST MAKE
  Relevance and sufficiency of evidence for S1 and S2; adequacy of challenge responses; whether residual disagreement is acceptable; whether the scope is right.
WAIVABLE REQUIREMENTS: recency (none defined here, so nothing is waivable in practice).
NOT WAIVABLE (always): the six items of G §12.6.
Escalation route: none beyond H-B. Authority gap if H-B is conflicted.
Review practice (visible prompt only): re-read before any attempt.
```

### R-021 Gate Definition (T-13), GD-B

```text
CB: H-A; human (simulated); gate-definition author; grant RG-3; position 21; target: gate GD-B; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

Gate name: GD-B "Build/no-build: prototype Standing Cards for a reader test".
PROGRESSION AND SCOPE
  What may cross: authorization to produce hand-made Standing Cards for the pilot record and put them to at least one human non-author reader. Not tooling, not generated views, not publication.
  For what scope: the pilot opportunity only.
  Why this scope (judgment): the smallest step that can produce reader evidence.
ACCEPTOR GRANTS AND ACCEPTANCE RULE
  AUTH-G grants that may accept: RG-8 (H-B) and RG-4 (H-A, which the independence rule will not let count over H-A's own set).
  Number of valid independent acceptances required: one.
  Role-conflict resolver: none designated.
GATE BASIS
  Subject: producing the prototype set.
  Basis items expected: CL-01 to CL-04; HY-01; AS-01; INF-01 (current revision); EV-01 to EV-07; the GDR-D2 acceptance as an upstream act (its accepted-set items count; the act does not).
REQUIRED EVIDENCE
  Slot B1 "Reader value": target CL-03 and HY-01; dimension customer; kinds: experiment or test result with a human non-author reader, or testimony recorded as testimony from such a reader; counter-evidence search required: yes.
  Slot B2 "Feasibility over time": target CL-04; dimension technical feasibility; kinds: experiment or test result; source-independence: not more than one item per source reference; counter-evidence search required: yes, EV-03 and EV-07 must be treated.
REQUIRED CHALLENGE CRITERIA
  Targets that must have been challenged: INF-01 and CL-04, by an actor who produced none of the challenged item. Challenger independence required: yes.
FORMAL CHECKS
  FC-1 as in GD-D. FC-2 as in GD-D.
  FC-3: every relied-on unvalidated material hypothesis or assumption has a recorded T-17 authorization (decidable from the record). Independent verification required: yes.
STRICTER CONDITIONS
  Every evaluative claim in the basis carries a basis-presentation designation (CL-03 does).
CONTEXTUAL JUDGMENTS THE ACCEPTOR MUST MAKE: relevance and sufficiency for B1 and B2; adequacy of responses; whether residual disagreement is acceptable; whether the scope is right.
WAIVABLE REQUIREMENTS: none designated. (Slot B1 is deliberately not waivable: a build gate with no reader evidence is the case the pilot wants to see refused.)
NOT WAIVABLE (always): the six items of G §12.6.
Escalation route: another AUTH-G holder for GD-B; none besides H-A and H-B exists.
Review practice: re-read before any attempt.
```

---

## 5. Attempts and Negative Findings (R-022 to R-023)

### R-022 Attempt and Negative-Finding Record (T-7), AT-01

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 22; target: CL-01, CL-02; config R-007; other producers: none; assignment: H-A to dev-agent-1, "search for existing aids", no conclusions specified.

What was looked for: an existing reader aid, filled card, or summary view of a claim's standing in the project's artifacts.
Target item: CL-01, CL-02.
What was searched: case-insensitive text search for "question card", "reader's question", "card of questions", and for "view" combined with "standing", over `prod-w/*.md` and `mod-w/*.md`, run 2026-10-04 at repository head 4d6c908. Source: SRC-04.
Method: grep with the quoted terms. Recorded before results were read.
When: 2026-10-04.
What it could have found and could not: it could find any file that names such an aid. It could not find an aid described in other words, an aid outside the repository, or practice by anyone outside the project.
Result: found something partial. The prompts (the nine-question card) exist in `prod-w/methodology-guidance.md` §3.2 and are referenced at §18.1 and in the RQ-10 rows. No filled card for any claim exists. Nothing else matched.
Limits: repository only. No external search. No user asked.
Follow-up still open: none within the pilot.
Inference drawn: INF-02 (R-031).
```

### R-023 Attempt and Negative-Finding Record (T-7), AT-02

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 23; target: CL-01, CL-03; config R-007; other producers: none; assignment: as R-022.

What was looked for: any recorded reader, reviewer, or user statement that reading a record's standing was hard, or that a summary aid was wanted.
Target item: CL-01, CL-03.
What was searched: case-insensitive text search for "quick-start", "quick start", "abbreviated practice", "hard to read", "summary", "dashboard" over `prod-w/*.md`, `mod-w/reviews/*.md`, and `research/mod-w-transferability/*.md`, run 2026-10-04 at 4d6c908. Source: SRC-04. Hits in the review files were then read in context.
Method: grep, then reading each hit's paragraph.
When: 2026-10-04.
What it could have found and could not: any written reader complaint or request. It could not find unwritten opinion or the view of anyone outside the project.
Result: found something partial, and found nothing on the target. The only related hit is the Product Owner's note that the templates are "usable but heavy" and that STEP-07 should identify which need quick-start examples (SRC-03). That is about the burden of filling templates, not about reading standing. **No recorded statement from any reader that standing is hard to read exists.**
Limits: out of reach: every person outside the repository, and any person inside it who has not written it down.
Follow-up still open: a human reader test (GD-B slot B1).
Inference drawn: none recorded separately. The result itself bears on CL-01 and CL-03 and is cited in EV-04.
```

---

## 6. Evidence, Counter-Evidence, and Tests (R-024 to R-029)

### R-024 Evidence Record (T-6), EV-01

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 24; target: CL-01; config R-007; other producers: none; assignment: as R-009.

Source reference: SRC-01.
What the source says: the card is "non-normative"; "Whether readers actually find the card helpful ... is evidence for STEP-07 to gather" (faithful summary of G §3.2, quoted fragment marked).
How obtained: retrieved (read).
Observation time: the file as of 4d6c908.
Evidence basis kind: artifact or data set.
Evaluation dimension: problem.
Target item: CL-01.
Relationship to the target: qualifies. It shows the question is open and that the card was written as a prompt set. It does not show that a reader has a problem.
Derived from: none.
Limitations: the project's own prior statement. A statement that something is untested is not evidence that it is a problem.
Source-comparability note: related by citation to SRC-02 (EV-02). Different text.
Sourced or agreement record: sourced.
Presentation: evidence only.
```

### R-025 Evidence Record (T-6), EV-02

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 25; target: CL-01; config R-007; other producers: none; assignment: as R-009.

Source reference: SRC-02.
What the source says: one item can be "accepted, contested, exposed, carry an open requirement, and be superseded all at once", so a single-valued status hides combinations (faithful summary of RO §12.5, point 1).
How obtained: retrieved (read).
Observation time: the file as of 4d6c908.
Evidence basis kind: artifact or data set.
Evaluation dimension: problem.
Target item: CL-01.
Relationship: supports. If an item has several simultaneous conditions held in separate records, a reader needs several records to read them.
Derived from: none.
Limitations: an argument from the semantics, not an observation of a reader. It shows why standing is multi-part, not that it is hard for a reader.
Source-comparability note: related to SRC-01. Different text.
Sourced or agreement record: sourced.
Presentation: contains evaluation ("hides combinations"). The interpretation is separated as INF-01.
```

### R-026 Evidence Record (T-6), EV-03 (counter-evidence)

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 26; target: CL-04, CL-02; config R-007; other producers: none; assignment: as R-009.

(Recorded in the same sitting in which it was found, immediately after R-025, from the adjacent paragraph of the same source. See §8 of the trial file: same-day recording.)
Source reference: SRC-02.
What the source says: "A hybrid that generates human views from the record can preserve the invariants in one place, and a hybrid that hand-authors them cannot." The view "may not omit what accepted semantics require to be visible"; "If a view disagrees with the record, the view is wrong" (quotes from RO §12.4).
How obtained: retrieved (read).
Observation time: the file as of 4d6c908.
Evidence basis kind: artifact or data set.
Evaluation dimension: technical feasibility.
Target item: CL-04.
Relationship: contradicts CL-04. Qualifies CL-02 (it does not say a card cannot be derived at a point, only that hand authoring cannot preserve the invariants).
Derived from: none.
Limitations: it is the project's own position, given before any trial, and is about generated versus hand-authored views in general, not about one-page cards.
Source-comparability note: same source reference (SRC-02) as EV-02. Both are one source for independence expectations.
Sourced or agreement record: sourced.
Presentation: evidence only.
```

### R-027 Evidence Record (T-6), EV-04

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 27; target: CL-03, CL-01; config R-007; other producers: none; assignment: as R-009.

Source reference: SRC-03.
What the source says: the templates are "usable but heavy"; STEP-07 "should measure fill-in burden and identify which templates need quick-start examples or abbreviated practice" (quote from the Product Owner's non-blocking notes).
How obtained: retrieved (read). Recorded as testimony.
Observation time: the sign-off as of 4d6c908, dated 2026-10-04.
Evidence basis kind: testimony recorded as testimony.
Evaluation dimension: customer.
Target item: CL-03.
Relationship: qualifies. It shows that burden is a concern for a reviewer of the method, which bears on whether a further hand-made artifact is welcome. It does not show desire for a card.
Also bears on CL-01: qualifies. Not about reading standing. See AT-02.
Derived from: none.
Limitations: the author is a reviewer of PROD-W, not a target user, and the remark is about template burden.
Source-comparability note: distinct.
Sourced or agreement record: sourced.
Presentation: evidence only.
```

### R-028 Evidence Record (T-6), EV-05 (test T-1: reading burden)

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 28; target: CL-01; config R-007; other producers: none; assignment: none (self-initiated within the trial plan).

Source reference: SRC-05, at evaluation point EP-1 (after R-031).
What the source shows: test T-1. The Development Team tried to read the standing of CL-01 from the records at EP-1, by the nine questions.
How obtained: computed and observed by reading.
Observation period: EP-1. The 31 records existed.
Evidence basis kind: experiment or test result (producer-run).
Evaluation dimension: problem.
Target: CL-01.
Relationship: supports.
Result:
  Records that had to be opened by reference: 13 of 31 (R-014 claim; R-007 configuration; R-024, R-025, R-028 evidence; R-022, R-023 attempts; R-030, R-031 inferences; R-018 assumption; R-009, R-010, R-013 sources).
  Questions 3, 4, 6, 7, 8 (contested, exposed, open requirement, accepted, superseded) can only be answered by scanning all 31 records and finding none. A claim record cannot state later challenges or acceptances, because records are not edited (ISS-02). The answer "none" depends on the scan being complete. Nothing in the record says the scan was complete.
  Question 9 was answerable: the evaluation point is a position number.
Derived from: SRC-05 records at EP-1.
Limitations: the tester is the author of the records, who knew where to look. A newcomer would need longer. At 31 records the cost is small. No test at greater size. The persona reader is assumed (AS-01).
Source-comparability note: same source (SRC-05) as EV-06 and EV-07.
Sourced or agreement record: sourced (a test result), self-generated.
Presentation: evidence only.
```

### R-029 Evidence Record (T-6), EV-06 (test T-2: derive two cards)

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 29; target: CL-02; config R-007; other producers: none; assignment: none.

Source reference: SRC-05, at EP-1.
What the source shows: test T-2. Two Standing Cards were derived by hand at EP-1.
How obtained: computed (hand derivation), then each answer was marked answerable from the record alone, or not.
Evidence basis kind: experiment or test result (producer-run).
Evaluation dimension: technical feasibility.
Target: CL-02.
Relationship: supports.

CARD-1 (claim CL-01, evaluation point EP-1):
  Q1 Who produced it, configuration: dev-agent-1; adopted by H-A; config R-007.
  Q2 Rests on: EV-01 (qualifies), EV-02 (supports), EV-05 (supports); AS-01 (assumption); chain grounds in evidence.
  Q3 Contested: no challenge or contradicting item recorded against it.
  Q4 Exposed: no.
  Q5 Reliance under assumption: yes, AS-01 (not yet covered by any authorization).
  Q6 Open requirement / recorded as current: no open requirement recorded. "Recorded as current" is not answerable from the record: no record element states it.
  Q7 Accepted: no.
  Q8 Superseded or withdrawn: no.
  Q9 View: names this file and EP-1.
CARD-2 (claim CL-02, evaluation point EP-1):
  Q1 dev-agent-1; adopted by H-A. Q2 EV-06 (supports), EV-03 (qualifies). Q3 contradicting item EV-03 recorded (qualifies). Q4 not determinable without scanning dependents; INF-01 depends on it. Q5 none. Q6 as above. Q7 no. Q8 no. Q9 names this file and EP-1.
Result: for each card, eight of nine questions were answerable from the record alone. Question 6 was answerable only in part ("recorded as current" has no record element). Logged as ISS-03.
Derived from: SRC-05.
Limitations: the deriver wrote the records. EP-1 is early. Both claims are in the pilot's own record, which is shorter than a real project's.
Source-comparability note: same source (SRC-05) as EV-05 and EV-07.
Sourced or agreement record: sourced, self-generated.
Presentation: evidence only.
```

---

## 7. Inferences (R-030 to R-031)

### R-030 Inference Record (T-8), INF-01

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 30; target: GD-B; config R-007 (T-11 reference); other producers: H-A (adopted); assignment: none.

Inference: A Standing Card is feasible only as a clearly non-normative view that names its record and evaluation point, and it carries a staleness risk that no check in the pilot can detect.
Cites: EV-03, EV-05, EV-06.
Chain grounds in: evidence.
Alternative interpretations considered: (a) a card is not worth producing at all; (b) the staleness risk is small because projects are short; (c) a generated view avoids the risk (outside the pilot's scope).
Limits: the evidence is the project's own position (EV-03) and the producer's own tests (EV-05, EV-06).
Support given to the dependent is: derived (inference).
Items that rely on this inference: GD-B basis.
Challenges: none at recording.
```

### R-031 Inference Record (T-8), INF-02

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 31; target: CL-01; config R-007; other producers: H-A (adopted); assignment: none.

Inference: The absence of any filled card (AT-01) implies the card has not been produced. It does not imply that readers do not need one, and it does not imply that a need exists.
Cites: AT-01, AT-02.
Chain grounds in: evidence (the attempt records).
Alternative interpretations considered: absence of requests (AT-02) means no need; absence of requests means no reader has yet read the records at scale.
Limits: reach limited to the repository (AT-01, AT-02).
Support given to the dependent is: derived (inference).
Items that rely on this inference: CL-01.
Challenges: none at recording.
```

**EP-1 = the record as it stands after R-031.**

---

## 8. First Gate Attempt: Refusal (R-032 to R-033)

### R-032 Gate Readiness Checklist (T-14), GD-D, first walk-through

```text
CB: dev-agent-1; AI; producer of the checklist (practice aid; not a check); AUTH-P; position 32; target: GD-D; config R-007; other producers: none; assignment: H-A to dev-agent-1, "prepare readiness for GD-D".

Gate: GD-D (R-020).
Prepared by: dev-agent-1. Acceptor-to-be: H-B.

1. Acceptor is a human holding AUTH-G covering the scope: yes (RG-8).
2. A gate definition was recorded before this act and the progression is within it: yes (R-020).
3. Accepted set listable and every member's producers recorded: yes. Members: CL-01, CL-02, CL-04; EV-01, EV-02, EV-03, EV-05, EV-06; AT-01, AT-02; INF-02; AS-01; designations (all "material"). Producers: dev-agent-1; H-A adopted.
4. Acceptor is a producer of no member: yes by recorded identity. The independence declaration is not yet made.
5. Each required formal check satisfied by an independent verification: no. None recorded.
6. Each required evidence slot and challenge criterion satisfied or covered: no. S1 and S2 have items. The challenge criterion (CL-01 challenged by a non-producer) is unmet.
7. Every standing-record item listed with a treatment: no. EV-03 is a contradicting item and has no treatment.
8. Every relied-on unvalidated hypothesis or assumption has a conditional progression authorization: no. AS-01 is relied on, none recorded.
9. The act will be explicit, attributable, and carry an independence declaration: no. None prepared.

If anything is "no": refusal, deferral, escalation, or a corrected basis. Not acceptance with a note.
Standing-record items and proposed treatments:
  Item 1: EV-03 (contradicts CL-04; qualifies CL-02): proposed treatment, to be decided by the acceptor.
  Item 2: none other recorded.
```

### R-033 Gate Decision Record (T-15), GD-D, refusal (SCRIPTED: premature attempt)

```text
CB: H-B; human (simulated); capacity: gate authority holder (refusal is conservative); grant RG-8; position 33; target: GD-D; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

(SCRIPTED: the Development Team presented the gate before the challenge, verification, and authorization existed, to exercise the refusal path and to put a refusal into the standing record of the later acceptance.)

Gate and gate definition: GD-D, R-020.
Determination: refused.
Progression authorized: none.
Subject as it stood: CL-01, CL-02, CL-04 with evidence at EP-1.
Accepted set: as R-032 item 3.
Standing record reviewed: EV-03 (contradicting item), no challenges, AS-01 reliance. No earlier refusals. No exceptions.
Formal-check status: unresolved. No Template 22 result exists.
Contextual sufficiency judgment: not made. Sufficiency was not found for the basis as it stood.
FOR A REFUSAL: unsatisfied: R-032 items 5, 6 (challenge criterion), 7, 8, 9. What would change the determination: a challenge to CL-01 by an actor who produced none of its basis; independent verification of FC-1 and FC-2; a recorded treatment for EV-03; a conditional progression authorization for AS-01; an independence declaration.
Independence declaration: not required of a refusal. H-B is a producer of nothing in the set.
This refusal is not final and erases nothing. It stays in the standing record of any later act on this gate and basis (GCR-39).
```

---

## 9. Challenges and Formal Checks (R-034 to R-039)

### R-034 Challenge Record (T-12), CH-01

```text
CB: H-B; human (simulated); capacity: challenger-reviewer; grant RG-7 (AUTH-A); position 34; target: CL-01; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

Target: item CL-01.
Target scope: sufficiency of a basis for a stated scope.
Basis: identified gap, and a request to seek counter-evidence not yet found. The problem claim rests on the project's own artifacts and a producer-run test. No reader says that reading standing is hard. EV-02 argues from the semantics. EV-05 was run by the author.
Counter-evidence cited: none. This challenge has a stated basis only.
Is the challenger a producer of the challenged item? No (recorded, independent as to CL-01).
Requested response: state the limits of CL-01's evidence.
Contributes to: contestation of CL-01; exposure for direct material dependents; a requirement only by P1, P2, or P3.
```

### R-035 Challenge Response (T-12), RESP-01

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 35; target: CH-01; config R-007; other producers: none; assignment: none.

Response kind: explanation (with a concession of the stated gap; no revision or withdrawal).
Response by: dev-agent-1.
Content: the gap is real. AT-02 found no reader statement. EV-05 is producer-run. CL-01 stays recorded as it is, with its limits in EV-01, EV-02, EV-05 and in INF-02's alternatives. No new evidence is offered.
Closure: none. A response never closes a challenge (GCR-25). CH-01 stands unresolved, and its condition is "answered, not resolved".
```

### R-036 Challenge Record (T-12), CH-02 (self-challenge, not independent)

```text
CB: dev-agent-1; AI; capacity: challenger-reviewer; grant RG-6 (AUTH-A); position 36; target: CL-02; config R-007; other producers: none; assignment: none.

Target: item CL-02.
Target scope: independence or attribution; sufficiency.
Basis: identified gap. EV-06 was produced by the same actor that wrote the records the cards were derived from. The test does not show that anyone else could derive the card.
Counter-evidence cited: none.
Is the challenger a producer of the challenged item? Yes (recorded, not independent).
Requested response: none.
Contributes to: contestation and exposure. It does not satisfy any independent-challenge requirement (PR-19). A self-challenge is useful as a visible limit.
```

### R-037 Formal-Check Result (T-22), FC-1

```text
CB: verify-agent-1; AI; capacity: verifier; grant RG-9 (AUTH-V); position 37; target: GD-D formal check FC-1; config R-008; other producers: none; assignment: none.

Check applied: FC-1 (R-020): each evidence item in the basis records a source reference, producer, observation time, target, relationship, and a limitations statement.
Version of the criteria: R-020 as recorded at position 20.
Evaluation point: after R-036.
Record elements examined: R-024 (EV-01), R-025 (EV-02), R-026 (EV-03), R-028 (EV-05), R-029 (EV-06).
What the result says: satisfied. All five carry each of the six elements. (The observation time of EV-05 and EV-06 is an evaluation point by position, not a clock time. The criterion asks for "observation time". Treated as satisfied by position because the file has no clock. See ISS-10.)
Producing actor and standing: AUTH-V holder (RG-9) for FC-1. It produced none of the elements examined (by recorded identity; same session, R-008).
Limits: relative to the record at the evaluation point. It does not say the records are complete or accurate.
EFFECT CLAIMED: satisfies the gate's formal-check slot for FC-1.
EFFECT NOT CLAIMED: acceptance; sufficiency; validation; progression; independence; corroboration; truth.
```

### R-038 Formal-Check Result (T-22), FC-2

```text
CB: verify-agent-1; AI; capacity: verifier; grant RG-9; position 38; target: GD-D formal check FC-2; config R-008; other producers: none; assignment: none.

Check applied: FC-2 (R-020): the acceptor is a producer of no member of the accepted set.
Version of the criteria: R-020 at position 20.
Evaluation point: after R-036.
Record elements examined: the producers recorded in R-009 to R-031 and R-034 to R-036 (the accepted set's members and the opposition); the acceptor-to-be H-B.
What the result says: satisfied. H-B appears as a producer of none of the members. H-B appears as the producer of R-034 (a challenge). A challenge is not a member of the accepted set (G §6.1).
Producing actor and standing: AUTH-V holder (RG-9).
Limits: identity only. Substance is a separate judgment and is left to the independence declaration (R-042). The same session wrote every record, so the check cannot detect substantive co-production.
EFFECT CLAIMED: satisfies the formal-check slot for FC-2.
EFFECT NOT CLAIMED: acceptance; sufficiency; independence in substance; truth.
```

### R-039 Formal-Check Result (T-22), advisory, "sources are independent"

```text
CB: verify-agent-1; AI; capacity: producer of an advisory formal-check result; grant RG-9 (not applicable, see below); position 39; target: GD-D slot S1; config R-008; other producers: none; assignment: none.

Check applied: the sentence "the sources are independent" (a phrase from G §11.6's examples, not a gate criterion in R-020).
Version of the criteria: none. It is not in R-020.
Evaluation point: after R-036.
Record elements examined: R-024, R-025, R-026, R-028, R-029 and R-009, R-010, R-013.
What the result says: unresolved. The phrase is not decidable (G §11.6). Only its checkable part is decidable: no more than one item per source reference in slot S1. S1 items are EV-01 (SRC-01), EV-02 (SRC-02), EV-05 (SRC-05): distinct, so the checkable part is satisfied. Substantive independence is a judgment left to the acceptor. EV-02 and EV-03 share SRC-02. EV-03 is not in slot S1. EV-05 and EV-06 share SRC-05.
Producing actor and standing: advisory only (not a gate-required check, so RG-9 is not relied on).
Limits: as above.
EFFECT CLAIMED: informs the acceptor about the shared-source facts.
EFFECT NOT CLAIMED: satisfaction of any slot; acceptance; corroboration.
```

---

## 10. Second Gate Attempt: Acceptance with Residuals (R-040 to R-044)

### R-040 Gate Readiness Checklist (T-14), GD-D, second walk-through

```text
CB: dev-agent-1; AI; producer of the checklist; AUTH-P; position 40; target: GD-D; config R-007; other producers: none; assignment: H-A to dev-agent-1, "re-walk readiness".

Gate: GD-D. Prepared by dev-agent-1. Acceptor-to-be: H-B.

1. Human holding AUTH-G for the scope: yes (RG-8).
2. Gate definition recorded before this act: yes (R-020).
3. Accepted set listable and producers recorded: yes. Unchanged from R-032, plus nothing new. Opposition (not in the set): CH-01, RESP-01, CH-02.
4. Acceptor a producer of no member: yes by identity (R-038); the declaration is at R-042.
5. Required formal checks satisfied by independent verification: yes (R-037, R-038).
6. Slots and challenge criterion satisfied: yes. S1 has EV-01, EV-02, EV-05 and AT-01, AT-02. S2 has EV-06 and EV-03 attached. The challenge criterion is met by CH-01 (H-B, a non-producer). CH-02 does not count toward it.
7. Standing-record items each have a treatment: yes, proposed below.
8. Relied-on assumptions covered by conditional progression: yes, AS-01 by CPA-1 (R-043). HY-01 is not relied on within GD-D's scope.
9. Act explicit and attributable with an independence declaration: yes (R-042). The binding note is at R-041.

Standing-record items and proposed treatments:
  CH-01 (unanswered gap; answered by RESP-01 without new evidence): accepted as residual.
  CH-02 (self-challenge, not independent): accepted as residual.
  EV-03 (contradicting item against CL-04; qualifies CL-02): accepted as residual.
  Exposure of INF-02 and of CL-01's direct material dependents arising from CH-01: accepted as residual.
  Reliance under assumption: AS-01 (CPA-1).
  Earlier refusal GDR-D1 (R-033): what changed is listed in the decision.
  Exceptions: none.
```

### R-041 Actor-Kind Binding Note (T-25), H-B

```text
CB: H-B; human (designated, simulated); capacity: acceptor; grant RG-8; position 41; target: R-044; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

Actor identity: H-B.
Kind as designated, who, when, under what grant: human; designated by H-A in R-001; no grant required for the designation.
Binding method: [x] None stated. (A real project would choose among access-control placement, a credential, out-of-band confirmation, or attestation. None applies because the act is a script.)
Known limits: the writer of the record is an AI session. The weak point named in G §9 is not exercised by this pilot.
Claim made: "The record designates this actor as human and states the method above, which is none."
Claim NOT made: that a human acted. None did.
```

### R-042 Independence Declaration (T-16), H-B, for GDR-D2

```text
Acceptor: H-B.
Act this declaration accompanies: GDR-D2 (R-044) and CPA-1 (R-043).

I, or any identity I control, have:
  [ ] created, edited, restated, summarized, renamed, or adopted a member of the accepted set: no.
  [ ] supplied the substance of a member: no.
  [ ] assigned production of a member to another actor: no.
  [ ] recorded a materiality designation, dependency link, or non-material designation shaping the basis: no.
  [ ] performed a verification relied on: no.
  [ ] conferred a grant that a favorable act relies on: no.
  [ ] a relationship with a producer or the matter a reviewer would want to know: no.
"I know of no undisclosed production, assignment, or substantive contribution by me, or by an identity I control, to any member of the accepted set."
Work assignments I know of in this accepted set: H-A assigned drafting and searching to dev-agent-1 (R-009 to R-031); none specified conclusions.
Disclosure: I recorded CH-01 (a challenge, not a member of the accepted set).
This declaration is an assertion. It can be challenged. It is not proof of independence.
(Scripted: written by dev-agent-1 for H-B. In this pilot the declaration cannot be false in any detectable way, because the declarant and the producer are one writer.)
```

### R-043 Conditional Progression Authorization (T-17), CPA-1

```text
CB: H-B; human (simulated); capacity: acceptor; grant RG-8 (AUTH-G, conditional progression for GD-D); position 43; target: AS-01; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none. The recorder is independent of the accepted set (R-042).

Authorization ID: CPA-1.
Ground: G1 (relied-on assumption).
Progression and scope covered: GD-D's progression only (exploring card content).
Items relied on while unresolved: AS-01 (G1).
For AS-01: what would resolve it: a non-author human reader is identified and the persona match is recorded as evidence or refuted. Position expected to resolve: H-B (validation scope covers HY-01, not AS-01; AS-01 would first be recorded as a hypothesis with criteria).
Rationale (judgment): exploring content is cheap, reversible, and does not itself depend on the reader's existence.
Reliance bound: CL-01 and CL-03 may rely on AS-01 within GD-D's scope only. CL-03 is not in GD-D's basis.
Statement: the unmet requirement (AS-01 validated or retired) remains UNSATISFIED and OPEN.
Marks produced: reliance under assumption on the dependency links CL-01 to AS-01.
Review event: none.
Independence declaration: R-042.
Ends when: validated, refuted, retired, or revoked. Never by time.
Not inherited: GD-B needs its own authorization. None exists.
```

### R-044 Gate Decision Record (T-15), GD-D, acceptance with residuals (SCRIPTED outcome by simulated H-B)

```text
CB: H-B; human (simulated); capacity: acceptor; grant RG-8; position 44; target: GD-D; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

SIMULATED JUDGMENT. No human made this determination (§0). It is recorded so that the record's shape and treatments can be checked.

Gate and gate definition: GD-D, R-020.
Determination: accepted (accepted with unresolved matters, not an exception).
Progression authorized and scope: exploration of what a Standing Card should contain. Not a build, not a reader test, not tooling, not inherited by GD-B.
Subject as it stood: the opportunity as framed in CL-01, CL-02, CL-04 at EP-2-minus (record position 43).
Accepted set reference: R-032 item 3 (CL-01, CL-02, CL-04; EV-01, EV-02, EV-03, EV-05, EV-06; AT-01, AT-02; INF-02; AS-01; designations).
Standing record reviewed, each item with a treatment:
  CH-01: condition unresolved, answered by RESP-01 with no new evidence. Treatment: accepted as residual.
  CH-02: unresolved, not independent. Treatment: accepted as residual.
  EV-03: contradicts CL-04, qualifies CL-02. Treatment: accepted as residual.
  Exposure of INF-02 and CL-01's direct material dependents (via CH-01): accepted as residual.
  Open requirements: none. Reliance under assumption: AS-01, covered by CPA-1. Reliance while open: none.
  Earlier refusal GDR-D1 (R-033): what changed since: R-034 (independent challenge recorded), R-037 and R-038 (verification), R-043 (authorization), R-042 (declaration), R-041 (binding note). The refusal's unsatisfied items are addressed.
  Exceptions already applying: none.
Unresolved matters accepted as residual: "accepted with unresolved CH-01, CH-02, EV-03 (against CL-04)". Rationale: the scope is exploration only and is reversible.
Formal-check status: satisfied (R-037, R-038). The advisory result R-039 is unresolved and not a gate criterion.
Conditional progression authorizations covering this act: CPA-1.
Exceptions covering this act: none.
Contextual sufficiency judgment (a judgment, recorded as one): the basis shows that the nine-question card exists only as prompts, that deriving a card at a point is workable at pilot size, and that hand-authoring carries an acknowledged risk. That is sufficient to explore card content, and insufficient for any build or reader test. No claim is made that the problem is real for any reader.
Independence declaration: R-042.
This acceptance is a determination of sufficiency for the stated scope. It is not a finding of truth and it validates no hypothesis.
```

**EP-2 = the record as it stands after R-044.**

---

## 11. Post-Acceptance Events: Revalidation, Commitment, Co-Production (R-045 to R-049)

### R-045 Evidence Record (T-6), EV-07 (test T-3: staleness) (SCRIPTED)

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 45; target: CL-04; config R-007; other producers: none; assignment: none.

(SCRIPTED: the Development Team re-derived CARD-1 at EP-2 to see whether a hand card made earlier stays right. Counter-evidence was recorded at once, whether or not it helped.)

Source reference: SRC-05, comparing EP-1 and EP-2.
What the source shows: CARD-1 (R-029, derived at EP-1) compared with the answers derivable from the record at EP-2 (after R-044).
How obtained: computed.
Evidence basis kind: experiment or test result (producer-run).
Evaluation dimension: technical feasibility.
Target: CL-04.
Relationship: contradicts.
Result: of nine answers on CARD-1, four were wrong at EP-2 across 13 later records (R-032 to R-044): Q3 (a challenge, CH-01, now exists), Q4 (exposure now exists), Q5 (reliance under assumption is now covered by CPA-1, which the card did not show), Q7 (CL-01 is now in the accepted set of GDR-D2, "accepted with unresolved" CH-01, CH-02, EV-03). Q1, Q2, Q6 (no open requirement at EP-2), Q8, Q9 unchanged or still right. A reader using CARD-1 in place of the record would have mis-stated CL-01's standing on four questions. CARD-2 changed on Q3 (CH-02) and Q7.
Derived from: SRC-05 at EP-1 and EP-2.
Limitations: the producer ran its own test. One card, one interval. No test at greater size or with more than one reviser.
Source-comparability note: same source (SRC-05) as EV-05 and EV-06.
Sourced or agreement record: sourced (a test result), self-generated.
Presentation: evidence only.
Trigger: source-identified counter-evidence on a material dependency of CL-04 (TRG-2). See R-046.
```

### R-046 Revalidation Request and Requirement (T-21), REQ-1

```text
REQUEST
CB: dev-agent-1; AI; producer; AUTH-A (RG-6); position 46; target: GDR-D2; config R-007; other producers: none; assignment: none.

Dependent item: the GDR-D2 acceptance (R-044), whose accepted set includes CL-04.
Changed, contested, or withdrawn item: CL-04 (EV-07, R-045).
Stated basis: new sourced counter-evidence on a material dependency of CL-04 (TRG-2). The request restates the trigger. (ISS-13: whether a request is needed when the trigger already creates the requirement.)
Effect: creates a requirement on the dependent. It concludes nothing.

REQUIREMENT
Reasons present now: EV-07 (against CL-04). EV-03 (against CL-04) was already accepted as residual at GDR-D2 and is not a new reason.
Tier: 1 (the dependent is a consequential decision, a gate acceptance).
Also: INF-01 (cites EV-03, EV-05, EV-06) carries exposure through CL-04 and CL-02. Not a requirement.
Standing: OPEN. No closure was attempted in the trial (see the trial file, §8). A Tier 1 closure by reaffirmation would be a fresh acceptance by an independent human AUTH-G holder over the accepted set computed on the current basis. Revision would carry the requirement. Time, silence, and completion of downstream work do not close it.
Effect on later reliance: GDR-D2 is not shown as current (VI-6). New reliance on it, including GD-B's basis items CL-04 and CL-02, needs a closure or a reliance-while-open authorization (T-17, G2).
```

### R-047 Consequential Commitment That Is Not an Acceptance (T-24), COM-1 (SCRIPTED)

```text
CB: H-A; human (simulated); capacity: n/a (the committing party); grant: none (organizational basis, not a PROD-W grant); position 47; target: HY-01, AS-01, CL-04; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

(SCRIPTED: the founder position makes a promise before GD-B is attempted, to test whether T-24 catches it.)

Commitment: H-A tells a pilot-subject outside reader (an unnamed, hypothetical person, pilot material only) that a hand-made Standing Card for one claim will be ready for their review within the week.
Why it is consequential: an external promise, made before GD-B. It commits H-A and dev-agent-1 effort.
Routing decision: [x] Neither: a commitment by the founder outside the project's gates. It was not routed through a gate acceptance (GD-B is unmet) or a decision record (H-A holds no AUTH-G that could validly make it, because H-A is a producer of the basis).
Who made the commitment and on what authority: H-A, as founder. An organizational basis. It is not a PROD-W grant.
Unvalidated hypotheses relied on: HY-01.
Assumptions relied on: AS-01 (CPA-1 covers GD-D's scope only and is not inherited).
Open requirements relied on: REQ-1 on GDR-D2, and through it CL-04.
Reliance marks on the dependency links: present, stated here.
Visible warning, to be stated wherever the commitment is cited: "This commitment relies on HY-01, which is unvalidated, on AS-01, an assumption, and on CL-04, which carries an open revalidation requirement (REQ-1). It is not a PROD-W acceptance and does not validate anything."
Later gate that would test the reliance, and who runs it: GD-B, run by H-B (if independent).
Independence: H-A is a producer of the basis on which this relies. This is stated. Calling it a commitment does not make it independent of that basis.
```

### R-048 Challenge Record (T-12), CH-03 (SCRIPTED: reviewer supplies wording)

```text
CB: H-B; human (simulated); capacity: challenger-reviewer; grant RG-7 (AUTH-A); position 48; target: INF-01; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

(SCRIPTED: placed to see whether a reviewer's natural remedy, offering better wording, makes the reviewer a producer. See ISS-06.)

Target: item INF-01.
Target scope: content.
Basis: disputed interpretation. INF-01 says a card is "feasible only as" a non-normative view. H-B disputes "only as", and also finds the staleness risk stated without a remedy.
Counter-evidence cited: none. This challenge has a stated basis only.
Is the challenger a producer of the challenged item? No at recording.
Requested response: replace the conclusion with the following wording: "A Standing Card is feasible as a non-normative view that names its record and evaluation point, and any use of it must be checked against the record at a stated evaluation point before it is relied on."
Contributes to: contestation of INF-01; exposure for direct material dependents; no requirement.
Note (recorded at the time): the field "Requested response" has no way to tell a request to reconsider from a supply of the replacement conclusion. This text supplies the conclusion.
```

### R-049 Inference Record (T-8), INF-01 revised, supersedes R-030 (adoption)

```text
CB: dev-agent-1; AI; producer; AUTH-P; position 49; target: GD-B; config R-007; other producers: H-A (adopted, carried from R-030); H-B (the conclusion's wording was supplied in CH-03 and adopted here: a producer); assignment: none.

Inference: A Standing Card is feasible as a non-normative view that names its record and evaluation point, and any use of it must be checked against the record at a stated evaluation point before it is relied on.
Cites: EV-03, EV-05, EV-06, EV-07.
Chain grounds in: evidence.
Alternative interpretations considered: as R-030.
Limits: as R-030, plus: EV-07 shows a card goes stale. The wording was supplied by H-B.
Support given to the dependent is: derived (inference).
Items that rely on this inference: GD-B basis.
Challenges: CH-03 carries to this successor, visibly as carried. It is not closed. The producer's revision is a concession by revision; the challenge is neither resolved nor closed (GCR-25). Closing requires the challenger's resolution or an independent AUTH-G authority closure.
Supersession: this record supersedes R-030. R-030 stays recorded and visible.
Producer note: **H-B is now a producer of INF-01 (revised)**. Under GCR-03, no contribution is too small, and supplying the conclusion counts even where another actor typed it. This is the co-production the method warns against (G §6.4 B).
```

---

## 12. Grant Review, Authority Gap, Self-Approval, Second Gate Attempt (R-050 to R-057)

### R-050 Grant Review Record (T-27), GRV-1

```text
CB: H-A; human (simulated); capacity: reviewer; grant: none required (a visible prompt, no automatic effect); position 50; target: grants RG-1 to RG-9; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

Review prompted by: a scheduled review event (before the GD-B attempt) and the concern raised by R-049.
Grants reviewed (grantee, class, scope, conferring act): RG-4 H-A AUTH-G acceptance GD-B (R-001); RG-5 H-A conferral (R-001); RG-8 H-B AUTH-G acceptance GD-B, conditional progression, exception, validation HY-01 (R-001); RG-9 verify-agent-1 (R-001).
For each:
  RG-4: still wanted? no (cannot validly be used over H-A's own set). Chain effective: yes. Downstream: none. Holder independent of the sets it acts on: no (H-A is a producer of every GD-B basis member).
  RG-5: still wanted? narrower (only if a third independent human is found). Chain effective: yes. Holder independent for conferral purposes: no. A conferral by H-A for GD-B acceptance would be flagged (CRC-64) because H-A is a producer of the set.
  RG-8: still wanted? yes. Chain effective: yes. Holder independent of the GD-B accepted set: **no**. H-B supplied the conclusion of INF-01 (revised) (R-049).
  RG-9: independent by identity over the GD-B set; same-session limit stands (R-008).
Departures expected: none.
Re-conferral plan: none possible now. A grant to a third human would be needed. The only conferrer with a covering scope is H-A (RG-5), who is conflicted.
Acts relying on a fallen grant after its fall: none. No grant fell.
Authority gaps that follow: for the GD-B acceptance scope, and for any G1 or G2 conditional progression over the GD-B set.
Outcome: no grant changed. Escalation (R-053). Stop at the gap (R-052).
```

### R-051 Gate Readiness Checklist (T-14), GD-B

```text
CB: dev-agent-1; AI; producer of the checklist; AUTH-P; position 51; target: GD-B; config R-007; other producers: none; assignment: H-A to dev-agent-1, "prepare readiness for GD-B".

Gate: GD-B (R-021). Prepared by dev-agent-1. Acceptor-to-be: H-B.

1. Acceptor is a human holding AUTH-G covering the scope: yes (RG-8).
2. Gate definition recorded before this act and the progression is within it: yes (R-021).
3. Accepted set listable and producers recorded: yes. Members: CL-01 to CL-04; HY-01; AS-01; INF-01 (revised, R-049); EV-01 to EV-07; AT-01, AT-02; INF-02; designations; formal-check records relied on (none for FC-3 yet).
4. The acceptor is a producer of no member: **no**. H-B is a producer of INF-01 (revised) (R-049).
5. Each required formal check satisfied by an independent verification: no. FC-3 not run. FC-1 and FC-2 not run for this basis.
6. Slots and challenge criteria satisfied: no. B1 has no evidence at all. B2 has EV-03 and EV-07, both against. The challenge criterion for INF-01 and CL-04 is unmet: CH-03 was by H-B before H-B became a producer, and CL-04 has no challenge by a non-producer.
7. Standing-record items listed with a treatment: no. CH-01, CH-02, CH-03, REQ-1 (open), EV-03, EV-07, GDR-D1, and COM-1's reliance are untreated for this gate.
8. Relied-on unvalidated hypotheses or assumptions have a T-17 authorization, and open requirements are closed or covered: no. HY-01 and AS-01 have none for GD-B. REQ-1 is open, with no G2 authorization.
9. Act explicit, attributable, with an independence declaration: no. H-B's declaration would have to disclose R-049.

Anything "no": refusal, deferral, escalation, or a corrected basis. Not acceptance with a note.
Items 4 and 8 cannot be cured by any act H-B or H-A can validly perform.
```

### R-052 Authority-Gap Record (T-20), AG-1

```text
CB: dev-agent-1; AI; capacity: producer (a record against a matter; no authority is needed to record the gap); AUTH-P; position 52; target: GD-B acceptance and any T-17 authorization over its set; config R-007; other producers: none; assignment: none.

Matter: acceptance of GD-B; conditional progression (G1 on HY-01 and AS-01, G2 on REQ-1's dependents); validation of HY-01.
Resolving authority needed: AUTH-G for GD-B, held by an identity that is a producer of no member of the GD-B accepted set.
Why no identity qualifies: H-A holds RG-4 and is a producer of every basis member (adopted CL-01 to CL-04, AS-01, HY-01, INF-01, INF-02; authored GD-B). H-B holds RG-8 and is a producer of INF-01 (revised) (R-049). No third human holds AUTH-G for GD-B.
What a conflicted holder may still do: conservative acts only: refuse, defer, escalate, request revalidation, challenge, withdraw or retire own items. H-B records a refusal (R-057).
Options (record which is pursued):
  [ ] Grant to an independent human by a valid conferrer: not pursued. The only conferrer (H-A, RG-5) is conflicted, so the grant would be flagged and escalation-eligible (CRC-64). Tabletop in Appendix S, S-3.
  [ ] Re-basing on independent items: not pursued. INF-01 (revised) is H-B's wording; reverting to R-030 would withdraw the successor, and CH-03 would be moot only if the producer withdrew with no successor. Tabletop considered, not run.
  [ ] Substitution of the acceptor: none available.
  [x] Stop at this gate. The protocol permits it.
Not cures: acceptance by the conflicted holder; a second role label; a collective identity; an agent or evaluator; a waiver; time; a self-conferred grant.
Progression that depends on this matter: none until cured.
```

### R-053 Escalation Record (T-19), ESC-1

```text
CB: dev-agent-1; AI; capacity: producer (holds AUTH-A, RG-6); AUTH-A; position 53; target: GD-B; config R-007; other producers: none; assignment: none.

Matter: the GD-B acceptance gap (AG-1) and the open REQ-1.
Reason: authority gap; conflict of interest.
Resolving authority sought: AUTH-G for GD-B, independent of the accepted set.
Identities holding that authority now: H-A (conflicted), H-B (conflicted).
Determination asked for: other. Cure by grant to an independent human, or stop at the gate.
What is unaffected while this is open: progression continues only through valid acts by other holders. None exist for GD-B. GD-D's exploration scope, already accepted, is unaffected, but GDR-D2 is not shown as current while REQ-1 is open.
Addressee's determination: none recorded. The escalation remains visible. Time does not act. The addressee position (an independent AUTH-G holder) is vacant.
```

### R-054 Gate Decision Record (T-15), GD-B, attempted self-approval by H-A (SCRIPTED: INVALID ON ITS FACE)

```text
CB: H-A; human (simulated); capacity: acceptor (attempted); grant RG-4 (held; cannot validly be relied on here); position 54; target: GD-B; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

(SCRIPTED: the founder position, holding a root AUTH-G grant, records an acceptance to see whether the record shows it as invalid. This record is not erased. It stays recorded as an invalid act (PR-11). No later record relies on it, and no pilot claim depends on it.)

Gate and gate definition: GD-B, R-021.
Determination: accepted. (As written by H-A.)
Progression authorized: the production of prototype Standing Cards for a reader test. (None authorized in fact: the act is invalid.)
Subject as it stood: as R-051.
Accepted set: as R-051 item 3.
Standing record reviewed: not cited. None of CH-01, CH-02, CH-03, REQ-1, EV-03, EV-07, GDR-D1 is treated.
Formal-check status: none recorded.
Conditional progression authorizations covering this act: none. HY-01, AS-01, and REQ-1 are relied on.
Contextual sufficiency judgment: "the basis is good enough to build".
Independence declaration: H-A ticks: adopted members of the accepted set; authored GD-B; supplied the substance of members. H-A cannot truthfully make the "I know of no undisclosed production" statement. The declaration discloses H-A's own producer status.
Not a finding of truth and validates no hypothesis.
```

### R-055 Finding That an Acceptance Is Invalid (T-23), INV-1

```text
CB: verify-agent-1; AI; capacity: verifier; grant RG-9 (AUTH-V, invalidity findings for GD-B criteria designated decidable); position 55; target: R-054; config R-008; other producers: none; assignment: none.

Acceptance found invalid: R-054.
Rule or rules violated:
  (1) The acceptor must be a producer of no member of the accepted set (GC §5.4 condition 4; FC-2). H-A is recorded as a producer of CL-01 to CL-04, AS-01, HY-01, INF-01, INF-02 (R-014 to R-019, R-030, R-031) and as author of GD-B (R-021). Decidable from the record.
  (2) Every relied-on unvalidated hypothesis or assumption has a T-17 authorization recorded at or before the act (CRC-19; FC-3). HY-01 and AS-01 are relied on. No T-17 for GD-B exists. Decidable from the record.
  (3) The standing record is cited with treatments (GCR-17). R-054 cites none. Decidable from the record.
  (4) An independence declaration is present: it is present (the declaration discloses producer status), so this condition is not violated. Independence over the set is a separate non-waivable condition and is the one violated at (1).
Evaluation point: after R-054.
Record elements examined: R-014 to R-019, R-021, R-030, R-031, R-049, R-051, R-054.
Is each rule asserted violated decidable from the record? yes.
Dependents that relied on the acceptance: none. No record cites R-054 as a basis.
Requirement created on each dependent: none (no dependent).
This finding is challengeable. It writes nothing into any item's condition. R-054 stays visible as an invalid act.
(Limit: recorded by an AI AUTH-V holder, permitted only because each rule is decidable from the record. Same session as the producer. See R-008.)
```

### R-056 Independence Declaration (T-16), H-B, for the GD-B refusal

```text
Acceptor: H-B (acting as gate authority holder; a refusal is a conservative act that a producer may perform).
Act this declaration accompanies: GDR-B1 (R-057).

I, or any identity I control, have:
  [x] supplied the substance (the conclusion or key content) of a member, even where another actor typed it: yes. The conclusion of INF-01 (revised), supplied in CH-03 (R-048) and adopted at R-049.
  [ ] created, edited, or adopted a member: no.
  [ ] assigned production: no.
  [ ] recorded a designation: no.
  [ ] performed a verification relied on: no.
  [ ] conferred a grant relied on: no.
  [ ] a relationship a reviewer would want to know: no.
Work assignments I know of in this accepted set: H-A to dev-agent-1 (as in R-042).
This declaration is an assertion. It can be challenged. It is not proof of independence.
It shows H-B cannot give a favorable act over this set. A refusal is not favorable.
```

### R-057 Gate Decision Record (T-15), GD-B, refusal (SCRIPTED outcome by simulated H-B)

```text
CB: H-B; human (simulated); capacity: gate authority holder (conservative act); grant RG-8; position 57; target: GD-B; config n/a (simulated); other producers: dev-agent-1 typist; assignment: none.

SIMULATED DETERMINATION. No human made it (§0).

Gate and gate definition: GD-B, R-021.
Determination: refused. This is a refusal that stops progression, with no build authorized. It is a visible non-progression.
Progression authorized: none.
Subject as it stood: producing prototype Standing Cards, with the basis as at R-051.
Accepted set: R-051 item 3.
Standing record reviewed:
  CH-01, CH-02: unresolved. CH-03: unresolved, carried to INF-01 (revised). EV-03, EV-07: contradicting items. REQ-1: an open Tier 1 requirement on GDR-D2, on which basis items CL-04 and CL-02 rest. GDR-D1: an earlier refusal on GD-D, not on this gate. R-054: an invalid attempted acceptance of this gate (INV-1). COM-1: a commitment relying on unvalidated HY-01, assumption AS-01, and open REQ-1.
  Treatments: none is accepted as residual. A refusal does not accept anything.
Formal-check status: unresolved (FC-3 not run; FC-1 and FC-2 not run for this basis).
Conditional progression authorizations: none. None can be given validly (AG-1).
Exceptions: none.
Contextual sufficiency judgment: sufficiency is not found. Slot B1 has no evidence. Slot B2 has only evidence against. HY-01 is unvalidated and relied on.
Independence declaration: R-056 (discloses H-B's contribution to INF-01 (revised)).
FOR A REFUSAL: unsatisfied: R-051 items 4, 5, 6, 7, 8, 9. What would change the determination: a human non-author reader test (slot B1); a treatment or closure of REQ-1; validation of HY-01 or a T-17 authorization by an independent AUTH-G holder; an independent AUTH-G holder for this gate (a cure for AG-1); an independent challenge of INF-01 and CL-04.
This refusal is not final and erases nothing.
```

---

## 13. Method Issue Log Entries (T-28) and Record Kinds Not Produced

### R-058 Method Issue Log Entry references

The issue log is `prod-w/proof-of-concept-issues.md`. Entries ISS-01 to ISS-22 were recorded there as friction appeared. Entries tied to specific records here: ISS-02 (R-014, R-028), ISS-03 (R-029), ISS-04 (the compact common block), ISS-05 (R-018), ISS-06 (R-048, R-049), ISS-10 (R-001, R-037), ISS-11 (R-013, R-028), ISS-13 (R-046), ISS-15 (R-001, R-054), ISS-19 (R-007).

### Record kinds required by the step file and not produced

| Template | Why not produced |
| --- | --- |
| 3 Grant Act Record | No grant changed after establishment. The cure for AG-1 would be a conferral, and was not pursued (R-052). A scenario record is in Appendix S (S-3). It is not a record of POC-1. |
| 17 Conditional Progression Authorization | Produced once (CPA-1, R-043). Not produced for GD-B: no valid issuer exists (AG-1). |
| 18 Exception Record | Not exercised. Nothing waivable was unsatisfied. GD-D defines only recency as waivable, and no recency criterion was set. GD-B designates nothing waivable. Every unsatisfied GD-B requirement is non-waivable or deliberately non-waivable. A scenario is in Appendix S (S-2). |
| 26 Imported Prior Work | Not applicable. POC-1 has no earlier project. |
| 21 closure half | Not exercised. REQ-1 was left open. Closure needs an independent AUTH-G holder, which AG-1 shows is not available for the GD-B set, and a fresh GD-D acceptance was not attempted in the pilot. |

---

## Appendix S. Table-Top Scenarios (Not Records of POC-1; Not Evidence)

These are scenarios run by the Development Team on paper to cover cases the full pilot could not. **They are not records of POC-1, are not pilot evidence, and no finding relies on them as evidence.** Observations from them are labeled "scenario" in `prod-w/proof-of-concept-findings.md`. They are separate from `prod-w/worked-examples.md`, which remains a set of methodology scenarios, not evidence.

### S-1 Solo founder, no H-B

H-A is the only human. H-A holds RG-1 to RG-5. The establishing checklist row ("every grant the establishing identity needs for itself") nudges H-A to include AUTH-G acceptance. In the walk-through: H-A's GD-D readiness item 4 is "no" (H-A is a producer of every member). The only valid acts are refusal, deferral, escalation, and recording the authority gap (T-20). Cure options 1 to 3 need another human; option 4 is stop. The scenario record set to reach this point: R-001, R-003, T-9 and T-5 records, T-13, T-14, T-20, T-15 as a refusal. No independence declaration, T-17, or T-22 result is reachable in this scenario. Observation (scenario): the method gives a solo founder a complete honest record and no valid acceptance. It does not provide a way to feel authorized. The risk is the other direction: RG-4 lets a founder write a grant that looks like authority (ISS-15).

### S-2 Exception, tabletop

If GD-D had defined recency (for example, "SRC-03 dated within the last review point") and SRC-03 failed it, H-B could record an exception (T-18) with an acceptance: marker EXCEPTION; waived requirement "recency"; not one of the six non-waivable items; risk accepted; visible wherever cited; recorded at or before the acceptance; with an independence declaration. The distinguishing test (GCR-48): after the progression the unmet requirement does not stay open, so it is an exception and not a conditional progression. Observation (scenario): the template wording makes this distinction answerable. Not exercised in the pilot.

### S-3 Conferral to cure the gap, tabletop

H-A (RG-5) confers AUTH-G for GD-B acceptance to a third human H-C. T-3 would read: Act conferral; grantee H-C; class AUTH-G; scope acceptance for GD-B; conferral scope relied on: RG-5; chain: R-001 (root); recorder a producer of items a favorable act under this grant could concern: **yes**; any conferrer along the chain such a producer (CRC-64): **yes (H-A)**; rationale: cure for AG-1; effective when recorded, not retroactive. The conferral is **flagged and escalation-eligible**, not invalid, and the flag travels with every favorable act by H-C that relies on it. H-C must also not edit items or supply conclusions. Observation (scenario): the cure exists and is weaker than a root grant. Naming H-C in R-001 would have avoided the flag, and the proxy-limit disclosure would then be the only exposure.

### S-4 Two humans, accidental co-production

R-048 and R-049 are the pilot's version (a real sequence in the pilot, but scripted). The scenario adds the avoidance path: H-B, wanting to help, records the disputed point as a challenge with "Requested response: reconsider the 'only as'" and **no wording**; dev-agent-1 revises in its own words; H-B remains independent of INF-01 (revised) *by identity*. Substance is then a matter of H-B's declaration. Observation (scenario): the avoidance path is available. The template field "Requested response" does not discourage the wording path (ISS-06). In this pilot the path that led to the gap is the one that was walked, by design.

### S-5 Three humans plus an agent

H-A producer; H-B reviewer and accepter; H-C verifier with AUTH-V and AUTH-A; dev-agent-1 producing. Fill the common block, source and evidence records, independence declarations, and a gate decision record in a normal working day: the pilot's record set for GD-D is R-009 to R-044, which is 36 records. By recorded actor they are dev-agent-1 26, H-B 6, verify-agent-1 3, H-A 1. A three-human split would move the verify-agent-1 records to H-C. Observation (scenario): the load falls mostly on the producer side. The reviewer side is small: one challenge, one binding note, one independence declaration, one conditional progression, one decision. Whether people complete these in a working cadence is not tested (no people). This is a count by position, not a time.

---

MOD-W v5.0.1
