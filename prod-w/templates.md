---
artifact:
  type: methodology-templates
  id: PROD-W-TPL
  version: 0.2
  created: 2026-10-04
  updated: 2026-10-04
  status: Draft - Development Team work product for STEP-06. Not reviewed. Not accepted.
  produced_by: Development Team
  produced_under: STEP-06
source:
  step: mod-w/step-06.md
  methodology_guidance: prod-w/methodology-guidance.md
  role_charters: prod-w/role-charters.md
  protocol_semantics: prod-w/protocol-semantics.md
  evidence_knowledge_model: prod-w/evidence-knowledge-model.md
  gate_challenge_revalidation_semantics: prod-w/gate-challenge-revalidation-semantics.md
  rule_judgment_boundary: prod-w/rule-judgment-boundary.md
  representation_options: prod-w/representation-options.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Templates

**Status:** Draft v0.2. Development Team work product for STEP-06. Not reviewed. Not accepted.
**Standing:** Methodology aids, subordinate to the accepted protocol artifacts. They add no protocol rule.

**Short names.** PS = `prod-w/protocol-semantics.md`. EK = `prod-w/evidence-knowledge-model.md`. GC = `prod-w/gate-challenge-revalidation-semantics.md`. RJ = `prod-w/rule-judgment-boundary.md`. RO = `prod-w/representation-options.md`. G = `prod-w/methodology-guidance.md`.

---

## 0. How to Use These Templates

**They are not a schema.** The templates are human-readable prompts. Field labels are prompts for a person to answer, not field names, keys, or an input format. Nothing here selects a schema, serialization, state vocabulary, storage model, validator, tool, or prompt format. Do not write a parser against them. If a later accepted step selects a representation, these templates are re-expressed in it, and the semantics they prompt for do not change.

**Wording lists are prompts, not value sets.** Where a template offers wording such as "accepted / refused / deferred", the words are what the record may *say*. They are not a status vocabulary. No template defines an item "status" field. An item's conditions (contested, exposed, relied on under assumption, with an open requirement) are read from the record, not set on it (EKR-02; RO §12.6).

**No numbers.** No template has a score, weight, grade, rank, or confidence percentage, and none should be added (EKR-19; BDR-14). Uncertainty goes in the *limitations* entry and in the visible presence of challenges and counter-evidence.

**Examples are not pilot results.** Filled examples elsewhere in this method are hypothetical methodology examples (`prod-w/worked-examples.md`). Nothing in these templates records a pilot.

**Blank means blank.** An unfilled required entry is a visible gap. Write "none exists" or "not determinable" where that is true, so the gap is stated rather than silent. A statement of absence makes the absence visible. It does not satisfy a requirement that something be present (GC §5.2).

### 0.1 Common Block

Begin **every** record with this block. It carries the distinctions the protocol keeps apart (producer, challenger, verifier, acceptor, authority, provenance).

```text
Record ID:
Record kind (use the template name):
Recorded by (actor identity - not a role label):
Actor kind as designated (human / AI / evaluator / automated):
Capacity on this record (producer / challenger-reviewer / verifier / acceptor):
Authority grant relied on (grantee, class, scope, conferring act) or "none required":
Recorded at (project record position / time):
Target item(s) or gate:
Producing configuration, if an AI actor produced this (see Template 11) or "not applicable":
Other producers of this record (all are producers for independence):
Work assignment involved (who assigned what to whom) or "none":
```

One record, one actor identity, one capacity (PR-06, PR-08). If two actors contributed, both are named as producers. If one actor does two things, make two records.

### 0.2 Template Index

| # | Template | Used for |
| --- | --- | --- |
| 1 | Project Establishment Record | The one establishing act (D10; CRC-61) |
| 2 | Role-Position Entry | Role charters in a project |
| 3 | Grant Act Record | Conferral, narrowing, revocation |
| 4 | Source Register Entry | Declared source identity |
| 5 | Claim Record | Claims, material claims, evaluative claims |
| 6 | Evidence Record | Evidence and counter-evidence |
| 7 | Attempt and Negative-Finding Record | Searches and tests, including those finding nothing |
| 8 | Inference Record | Interpretations |
| 9 | Assumption Record | Assumptions being relied on |
| 10 | Hypothesis Record | Testable propositions |
| 11 | Producing-Configuration Statement | AI-produced items and acts |
| 12 | Challenge Record | Challenges and their responses |
| 13 | Gate Definition | Defining a gate before use |
| 14 | Gate Readiness Checklist | Pre-acceptance walk-through |
| 15 | Gate Decision Record | Acceptance, refusal, deferral |
| 16 | Independence Declaration | Part of every consequential acceptance |
| 17 | Conditional Progression Authorization | Grounds G1 and G2 |
| 18 | Exception Record | Waiver or override |
| 19 | Escalation Record | Routing a matter |
| 20 | Authority-Gap Record | No independent resolver available |
| 21 | Revalidation Request and Closure Record | Triggers, requirements, outcomes |
| 22 | Formal-Check Result | One application of a check |
| 23 | Finding That an Acceptance Is Invalid | CRC-59 content |
| 24 | Consequential Commitment That Is Not an Acceptance | DM-09 |
| 25 | Actor-Kind Binding Note | RQ-05 |
| 26 | Imported Prior Work and Carry-Over Candidate | Recovery by new project |
| 27 | Grant Review Record | DM-07 grant review and rotation |
| 28 | Method Issue Log Entry | Issues for STEP-07 and STEP-08 routing |

---

## 1. Project Establishment Record

The first recorded act of a project. It precedes every other recorded act (CRC-61). Guidance: G §4.

```text
[Common Block - the recorder is the establishing identity, a human]

Marked as: the establishing act of this project's authority chain
Project name:
Project boundary (what bodies of work this project governs):
What this project is NOT (neighboring work, earlier projects):
Basis for the establishing identity's standing (an assertion; legitimacy is not checked):

ROOT GRANTS recorded by this act (only these can be roots):
  Grant R1
    Grantee (actor identity, or role position and the identities appointed):
    Authority class: AUTH-P / AUTH-A / AUTH-V / AUTH-G
    Scope (reference or description; if a description, containment is a judgment):
    If AUTH-G: which scope(s) - gate acceptance for ___ / gate definition / validation for ___ / conferral for ___ (class and scope)
    Granting authority: this establishing act
  Grant R2 ...

Everything the establishing identity needs for itself is above: yes / no
  (A later grant to the establishing identity needs an unconflicted conferrer and may be impossible.)

Independent AUTH-G holder(s) named in root grants for the gates expected soon: yes / none yet
  If none: authority gap expected for: ___

Initial role-position appointments (use Template 2 for each):

PRACTICE STATEMENTS (project-level; these are practice, not protocol):
  What counts as "recorded" for this project (shared line of record; private draft; branch):
  Where records are kept:
  Who can write to the record location, and who can edit whose records:
  How record order is established, and by whom/what (not by the recorder's own assertion alone):
  How backdating or out-of-order entries are handled:
  How actor identity is recorded:
  How actor kind is designated and what binding method is recorded (Template 25):
  Source-identity convention (Template 4):
  Producing-configuration convention (Template 11):
  Commitment routing practice (Template 24):
  Grant review practice (Template 27):
  How carried-over work from earlier projects is treated (Template 26):

Known authority gaps and limitations at establishment:
Imported prior work, if any (Template 26):
```

---

## 2. Role-Position Entry

One per role position. Guidance: `prod-w/role-charters.md` §3.

```text
Role position (a convenience label - confers nothing):
Actor(s) assigned (identity and designated kind):
Grants relied on (class, scope, conferring act; one line each):
Is the appointment itself grant-bearing? yes (it is a conferral - record Template 3) / no
Capacities expected:
Items this actor has produced or materially influenced (sets independence limits):
Independence limits and known conflicts:
Combined with another position? yes / no. If yes, the grants as combined and what the combination prevents:
Escalation route (grant class and scope; identities holding it now):
Fallback actor and the grant they would need:
Date or event for review of this entry (a visible prompt, with no automatic effect):
```

---

## 3. Grant Act Record

For any conferral, narrowing, revocation, or renunciation after the establishing act. Guidance: G §16.

```text
[Common Block - the recorder is a human holding AUTH-G with a conferral scope; or the grantee in a renunciation]

Act: conferral / narrowing / revocation / renunciation
Grant affected or created:
  Grantee:
  Class:
  Scope:
  Conferral scope relied on by the recorder (class and scope covered):
Chain from this grant to a root grant (each link and its conferring act):
Is the recorder a producer of any item that a favorable act under this grant could concern? yes / no / unknown
Is any conferrer along the chain such a producer (CRC-64 flag)? yes / no / unknown
If a revocation or narrowing: does the affected holder have standing to challenge any item whose producer is the recorder? yes / no / unknown
Rationale (stated; the purpose of the act is judged by others, HJC-23):
Downstream grants affected (list; revocation cascades prospectively):
Re-conferral needed for: ___ by whom: ___
Effective when recorded. Not retroactive.
```

---

## 4. Source Register Entry

One per distinct source. Give each source a stable project-local source reference at first use and reuse it. Guidance: G §8.3.

```text
Source reference (project-local, stable):
Description (what it is):
Origin or owner (who made or holds it):
Link, repository reference, or location:
Version, edition, or retrieval marker (what exactly was read):
Date observed or accessed:
Kind: primary observation / testimony / artifact or data set / secondary report / search result / synthesized by an agent / advisory
Derived from other sources (references), or "none known":
Related sources that may be the same source (references), and why:
Recorder's comparability note: same as ___ / distinct from ___ / unclear relative to ___
  Reason:
Limits (what this source does not cover):
```

---

## 5. Claim Record

```text
[Common Block]

Claim text:
Claim kind: ordinary / material / evaluative
Materiality designation (a recorded judgment by the recorder) and basis:
  Would a change in its standing plausibly change a decision, a promise to customers, or an investment?
If evaluative: basis-presentation designation, if the recorder states one (Practice, G §7.6):
  presented as observed fact / presented as established by evidence alone / presented as a value judgment / none stated
Evidence attached (Template 6 references), or "none exists":
Counter-evidence attached (Template 6 references), or "none found" with the attempt record (Template 7):
Assumptions relied on (Template 9 references):
Inferences relied on (Template 8 references):
Items that rely on this claim (dependents), and whether each dependency is material or presumed material:
Challenges against this claim (Template 12 references):
Gate or decision this claim bears on, if any:
```

For a material claim the minimum provenance is: what it is, who made it, when, what evidence supports it (or a statement that none exists), who challenged or accepted it, dependency links in both directions, and current recorded condition derivable from history (PR-09; EK §6.4).

---

## 6. Evidence Record

Used for supporting evidence and for counter-evidence. They have the same elements and the same formality (EKR-15). Guidance: G §7.

```text
[Common Block - the recorder is the producer of this record, not necessarily the originator of the information]

Source reference (Template 4):
What the source says or shows (quote, figure, or faithful summary, marked as such):
How the information was obtained (observed, asked, measured, retrieved, computed):
Observation time or period (when the thing observed was true, if different from recording time):
Evidence basis kind: direct observation or measurement / artifact or data set / testimony recorded as testimony / experiment or test result / search result / computation (with lineage)
Evaluation dimension, where relevant: problem / customer / commercial viability / technical feasibility / differentiation / other (state)
Target item (claim, hypothesis, inference, decision):
Relationship to the target: supports / contradicts / qualifies   (per target; the same item may differ per target)
Derived from (items), if derived:
Limitations (what this does not cover, where it may mislead). "None identified" is allowed and can be challenged:
Source-comparability note: other evidence items that rest on the same source or on sources related to this one:
Is this a sourced item or a record of agreement among actors? sourced / agreement record (an agreement record is not evidence; record it as a claim or advisory finding instead)
Presentation: evidence only (no interpretation attached) / contains evaluation (state it; separate the interpretation into an inference, Template 8)
```

---

## 7. Attempt and Negative-Finding Record

For a defined search, test, or attempt to observe something that did not find or confirm it, or found the opposite. The attempt record is the evidence. Any conclusion drawn is a separate inference (EKR-16). Guidance: G §7.4.

```text
[Common Block]

What was looked for (the target question):
Target item the attempt bears on:
What was searched, tested, or attempted, and where (databases, people, channels, artifacts; scope):
Method (how it was done; search terms, interview guide, test procedure):
When (period):
What the attempt could have found, and what it could not have (the reach of the search):
Result: found nothing / found the opposite / found something partial (describe):
Limits (what was out of reach, who was not asked):
Follow-up the project considers still open:
Inference drawn from this result (record separately as Template 8 and cite this record):
```

---

## 8. Inference Record

An inference is an interpretation. It is never evidence and never an observed fact (EKR-27). Guidance: G §7.1.

```text
[Common Block - for an AI-produced inference, include Template 11]

Inference (in the form "X implies Y"):
Cites (evidence, assumptions, other inferences; every chain must reach at least one evidence item or assumption):
Chain grounds in: evidence / assumption only (then it is assumption-rooted and must be identified as such at any gate)
Alternative interpretations considered:
Limits:
Support given to the dependent is: derived (inference) / evidential (evidence)
Items that rely on this inference:
Challenges:
```

---

## 9. Assumption Record

An assumption is an unverified proposition being relied on. It is recorded and visible whether or not material (EKR-22). Guidance: G §7.3.

```text
[Common Block]

Assumption:
What relies on it (dependents) and how (reliance under assumption marks):
Why it is being relied on now:
What would follow if it is false:
Is it testable? yes (then record it as a hypothesis, Template 10, keeping the history) / no
Material? (a recorded judgment): yes / no / presumed
Path to resolution, if known: supported by evidence / refuted / retired / remains open
Consequential reliance (inside a gate acceptance, decision, or commitment)? yes / no
  If yes: Conditional Progression Authorization reference (Template 17) or "none - this is a defect to resolve before acceptance"
```

---

## 10. Hypothesis Record

A hypothesis is testable. Without recorded validation criteria it is an assumption (EKR-21). Guidance: G §7.3.

```text
[Common Block]

Hypothesis:
Validation criteria (recorded BEFORE tests are run):
  What would support it:
  What would weaken it:
  What would refute it:
Scope it would be validated for:
Tests run and results, FAVORABLE OR NOT (Template 7 or 6 references):
Evidence attached:
Counter-evidence attached:
Challenges:
Relied on by (dependents) before validation? yes / no. If yes and consequential: Template 17 reference
Validation: none recorded / validated for ___ by ___ (an AUTH-G holder independent over the validation's accepted set)
  Criteria amended after results were recorded? If yes this is a supersession of the hypothesis, not a correction (GCR-65).
```

---

## 11. Producing-Configuration Statement

For any item or act produced by an AI actor (CRC-39). Recording this confers no independence. Guidance: G §8.1.

```text
Item or act produced:
Actor identity (the accountable actor position - not a model name):

Model (level the provider or operator exposes, with version designation if one exists) or "not determinable" + reason:
Reasoning effort or equivalent setting, or "not applicable" or "not determinable" + reason:
Harness or runtime (the agent framework or interface used), or "not applicable" or "not determinable" + reason:
Tooling (tools and data access the actor had), or "not applicable" or "not determinable" + reason:
Instructions in force at the act:
  Content, or a reference that resolves to what was in force at the act (not to a later version):
  Version-binding method used (how a reader can recover the exact text): copy of the text recorded with this statement / revision identifier / content digest / dated immutable copy / other (state) / not bound (state why)
  Includes: system or standing instructions / task brief / role charter in force / skill or instruction bundle / templates given
Source inputs supplied (references to Template 4 entries):
Human role in the output: generated unaltered / revised by (identity) / summarized by / adopted by (identity - adoption makes the adopter a producer)

Reviewer limitation (for example: reviewer is of the same model family as the producer):
```

---

## 12. Challenge Record

A challenge is an attributable act. Challenges, responses, and closures are separate records. Guidance: G §10.

```text
[Common Block - the recorder is the challenger; capacity: challenger-reviewer; grant: AUTH-A]

Target: item / relationship (designation, dependency link, producer attribution, correction designation) / decision or determination (acceptance, exception, authorization, closure, validity of an act)
Target scope (which aspect): content / source / relationship / designation / omission from a basis / sufficiency of a basis for a stated scope / independence or attribution / validity of an act
Basis (the stated ground): disputed interpretation / identified gap / contradiction citing recorded counter-evidence / request to seek counter-evidence not yet found / independence question / validity question
Counter-evidence cited (Template 6 references), or "none - this challenge has a stated basis only":
Is the challenger a producer of the challenged item? yes (recorded, not independent) / no
Requested response, if any:
Contributes to: contestation; exposure for direct material dependents; a requirement only by routes P1, P2, P3 (GC §7.4)

RESPONSES (each a separate record, any actor, never closes the challenge):
  Response kind: explanation / evidence / concession by revision, withdrawal, or supersession of the target / dispute of standing or scope / escalation
  Response by:
  Content:

CLOSURE (only three kinds):
  Challenger resolution - by the challenger, with a reason
  Authority closure - by an AUTH-G holder independent of the challenged item's accepted set, not the author of a challenged determination, with rationale
  Mootness by withdrawal - the target withdrawn with no successor
  Closer, kind, and rationale:
  If the target was superseded: the challenge carries to the successor, visibly as carried
```

---

## 13. Gate Definition

Recorded **before** the gate is used (GCR-12). Amending it after a refusal or deferral on the same basis applies only as a recorded exception (GCR-13). Guidance: G §12.1.

```text
[Common Block - the recorder holds AUTH-G for the project's gate-definition scope]

Gate name:
PROGRESSION AND SCOPE
  What may cross the gate (movement of work or of reliance):
  For what scope:
  Why this is the right scope (a judgment, recorded):

ACCEPTOR GRANTS AND ACCEPTANCE RULE
  AUTH-G grants that may accept (references):
  Number of valid independent acceptances required (default one):
  Role-conflict resolver for this gate (position or "none designated"):

GATE BASIS
  Subject (the proposal or course of action as it stands):
  Basis items the project expects to be in the accepted set:

REQUIRED EVIDENCE (one block per slot)
  Slot name:
  Target to be evidenced:
  Evaluation dimension:
  Acceptable evidence basis kinds:
  Source-independence expectation (for example: no more than one item may rest on the same source reference):
  Recency criterion, if any (checked once at the acceptance act against recorded observation times):
  Counter-evidence search required: yes / no. What reach is expected:

REQUIRED CHALLENGE CRITERIA
  Targets that must have been challenged:
  Challenger independence required from the producers of the challenged item: yes / no
  Response rule stricter than the default (every standing-record item has a recorded treatment): none / ___

FORMAL CHECKS
  Check name and named criteria (each stated so two competent evaluators reach the same answer from the record):
  Independent verification required: yes / no
  Which criteria are designated decidable from the record (needed for a non-human verifier) and who designated them:

STRICTER CONDITIONS (optional, project-chosen)
  For example: a basis-presentation designation is recorded for every evaluative claim; named configuration facets are required for AI-produced items; disagreement on a named dimension must be resolved:

CONTEXTUAL JUDGMENTS THE ACCEPTOR MUST MAKE (listed so none is forgotten):
  Relevance and sufficiency of evidence for each slot:
  Adequacy of challenge responses:
  Whether residual disagreement is acceptable:
  Whether the scope is right:

WAIVABLE REQUIREMENTS (may be covered by an exception, Template 18):
NOT WAIVABLE (always): independence over the accepted set; explicit attributable human AUTH-G act; citation and treatment of the standing record; visibility of the exception; the decision record's nature and authority basis; the FR-7 conditions where a material hypothesis is relied on

Escalation route:
Review practice (visible prompt only; time never accepts, closes, or expires anything):
```

---

## 14. Gate Readiness Checklist

A pre-acceptance walk-through. It is a practice aid for the acceptor, **not** a check that makes an acceptance valid and not a gate in itself. Completing it is never acceptance (PR-13). It follows the nine validity conditions of GC §5.4.

```text
Gate:
Prepared by (identity):          Acceptor-to-be (identity):

1. Acceptor is a human holding AUTH-G covering this gate's scope.                       yes / no / unknown
2. A gate definition was recorded before this act and the progression is within it.     yes / no / unknown
3. The accepted set can be listed and every member's producers are recorded.            yes / no / unknown
   Members: subject; material basis (transitively); designations incl. non-material ones;
   responses relied on; verification records relied on.
4. The acceptor is a producer of no member of the accepted set (including as assigner who supplied substance, as designation recorder, as verifier, as author of a recommendation later adopted).   yes / no / unknown
5. Each required formal check is satisfied by a verification whose verifier is a producer of nothing verified, or a recorded exception covers the shortfall.   yes / no / unknown
6. Each required-evidence slot and challenge criterion is satisfied, or covered by a recorded exception.
   A visible absence statement does not satisfy a slot.
   A missing validation of a relied-on material hypothesis is covered only by conditional progression.   yes / no / unknown
7. Every item in the standing record is listed below with a treatment:
   challenges and contradicting items (including since withdrawn), exposure, open requirements,
   reliance under assumption or while open, earlier refusals and deferrals on this gate and basis,
   exceptions already applying.   yes / no / unknown
8. Every relied-on unvalidated material hypothesis or assumption (including assumption-rooted items)
   has a conditional progression authorization recorded at or before this act, and every open
   requirement on a basis item is closed or covered by a reliance-while-open authorization.   yes / no / unknown
9. The act will be explicit and attributable, state the determination, and carry an independence declaration (Template 16).   yes / no / unknown

Authorizations and exceptions recorded AFTER the acceptance do not cure it. If anything is "no" or "unknown", the outcome is refusal, deferral, escalation, or a corrected basis. It is not acceptance with a note.

Standing-record items and proposed treatments (answered / conceded or withdrawn by the challenger / moot / accepted as residual / covered by exception):
  Item 1:
  Item 2:
```

---

## 15. Gate Decision Record

Acceptance, refusal, and deferral. An acceptance is recorded as a decision whose subject is the progression (GCR-21). Guidance: G §12.3.

```text
[Common Block - capacity: acceptor (or, for refusal and deferral, the gate authority holder); grant: AUTH-G covering this gate]

Gate and gate definition reference:
Determination: accepted / accepted with exception(s) / refused / deferred
Progression authorized and scope (acceptance only; not inherited by later gates):
Subject as it stood at this act:
Accepted set reference (list or pointer):
Standing record reviewed - each item cited with a treatment:
  Challenges (with their condition: unanswered / answered / resolved / withdrawn) and treatment
  Contradicting items and treatment
  Exposure of basis items and treatment
  Open requirements; reliance under assumption; reliance while open and treatment
  Earlier refusals and deferrals on this gate and basis, and what changed since
  Exceptions already applying
Unresolved matters accepted as residual (named, with rationale). The decision carries a marker: "accepted with unresolved ___":
Formal-check status (satisfied / satisfied under exception / violated / unresolved, with Template 22 references):
Conditional progression authorizations covering this act (Template 17 references):
Exceptions covering this act (Template 18 references):
Contextual sufficiency judgment and rationale (why the basis is sufficient for this scope; this is a judgment and is recorded as one):
Independence declaration (Template 16):
This acceptance is a determination of sufficiency for the stated scope. It is not a finding of truth and it validates no hypothesis.

FOR A REFUSAL: which conditions are unsatisfied or why sufficiency was not found; what would change the determination if known.
FOR A DEFERRAL: what is awaited and from which position. Time does not convert a deferral into anything.
```

---

## 16. Independence Declaration

Part of the acceptance-act content of every consequential acceptance (GCR-09; CRC-11). Presence is checked. Truth is not. Guidance: `prod-w/role-charters.md` §7.

```text
Acceptor (identity):
Act this declaration accompanies:

I, or any identity I control, have (tick each that is true and describe):
  [ ] created, edited, restated, summarized, renamed, or adopted a member of the accepted set:
  [ ] supplied the substance (the conclusion or key content) of a member, even where another actor typed it:
  [ ] assigned production of a member to another actor (to whom; what was specified):
  [ ] recorded a materiality designation, dependency link, or non-material designation shaping the basis:
  [ ] performed a verification relied on in this acceptance:
  [ ] conferred a grant that a favorable act under this acceptance relies on, at any link of the chain:
  [ ] a relationship with a producer or with the matter that a reviewer would want to know:
If none are ticked: "I know of no undisclosed production, assignment, or substantive contribution by me, or by an identity I control, to any member of the accepted set."

Work assignments I know of in this accepted set:
This declaration is an assertion. It can be challenged. It is not proof of independence.
```

---

## 17. Conditional Progression Authorization

Progress or rely while a named condition stays **unresolved and tracked**. It is not validation, ordinary acceptance, or a waiver (GCR-44). Guidance: G §12.5.

```text
[Common Block - capacity: acceptor; grant: AUTH-G for the scope; the recorder is independent of the accepted set of the progression]

Authorization ID:
Ground: G1 (relied-on unvalidated material hypothesis or relied-on assumption) / G2 (relied-on item with an open revalidation requirement)
Progression and scope covered:
Items relied on while unresolved (each identified), with ground (G1 or G2):
For each item:
  What would resolve it (validation criteria for G1; expected outcome for G2):
  Position expected to resolve it:
Rationale - why proceeding is warranted (a contextual judgment):
Reliance bound - which dependents may rely:
Statement: the unmet requirement remains UNSATISFIED and OPEN.
Marks produced: reliance under assumption (G1) / reliance while open (G2), on each dependency link
Review event (optional; visibility only, no automatic effect):
Independence declaration (Template 16):
Ends when: validated / refuted / retired / requirement closed / revoked. Never by time.
Revocation: any AUTH-G holder for the scope may revoke as a conservative act. Existing reliance stays visible, marked "no longer authorized".
Not inherited: a later gate relying on the same item needs its own authorization.
```

---

## 18. Exception Record

Dispensation from one specific unsatisfied gate requirement for one specific progression. It is not conditional progression: the requirement is dispensed with, not left open and tracked (GCR-48). Guidance: G §12.6.

```text
[Common Block - capacity: acceptor; grant: AUTH-G for the gate; the recorder is independent of the accepted set]

Marker: EXCEPTION
Unsatisfied requirement waived (identify the gate definition slot or stricter rule; for an override, the determination or check overridden):
Progression and scope the exception applies to:
Why this requirement is waivable (it is not one of the non-waivable items):
Rationale:
Risk accepted:
What remains visible (the marker travels with the acceptance wherever it is cited):
Recorded at or before the acceptance it covers: yes / no (an exception recorded afterward does not cure the acceptance)
Independence declaration (Template 16):
An exception cannot cover: independence; human explicit AUTH-G authorization; citation and treatment of the standing record; the exception's own visibility; the decision record's identification of its nature and authority; the FR-7 conditions.
```

---

## 19. Escalation Record

An escalation routes a matter. It resolves nothing and remains visible until the addressee records a determination (GCR-37). Guidance: G §14.

```text
[Common Block - the recorder holds AUTH-A, AUTH-P, AUTH-V, or AUTH-G]

Matter (item, challenge, gate, designation, attribution, or determination):
Reason: insufficient evidence / conflict of interest / unresolved disagreement / disputed designation or attribution / refused or deferred gate / authority gap
Resolving authority sought (grant class and scope; the independence condition the resolver must meet):
Identities holding that authority now:
Determination asked for: resolve / refuse / defer / other (state)
What is unaffected while this is open (progression continues only through valid acts by other holders):
Addressee's determination, when recorded (a separate record by the addressee):
```

---

## 20. Authority-Gap Record

Recorded against a matter when no identity meeting the independence condition can fill the resolving authority (GC §8.6; GCR-40).

```text
[Common Block]

Matter:
Resolving authority needed (class, scope, independence condition):
Why no identity qualifies (who holds the grant and why each is a producer or author):
What a conflicted holder may still do: conservative acts only (refuse, defer, escalate, request revalidation, challenge, withdraw or retire own item)
Options (record which is pursued; these are the only cures):
  [ ] Grant of the needed authority to an independent human by a valid conferrer
        Note: a conferral by a conflicted conferrer is flagged and escalation-eligible (CRC-64)
  [ ] Re-basing the subject on independent items, visibly
  [ ] Substitution of the acceptor
  [ ] Stop at this gate (the protocol permits it)
Not cures: acceptance by the conflicted holder; a second role label; a collective identity; an agent or evaluator; a waiver; time; a self-conferred grant.
Progression that depends on this matter: none until cured.
```

---

## 21. Revalidation Request and Closure Record

Guidance: G §13.

```text
REQUEST (ACT-06; any holder of AUTH-A, AUTH-V, or AUTH-G; no independence required of the requester)
[Common Block]
Dependent item (the one whose standing is in question):
Changed, contested, or withdrawn item:
Stated basis - why the requester judges the dependent's standing is in question (including age of evidence, if that is the ground):
Effect: creates a requirement on the dependent. It concludes nothing.

REQUIREMENT (one standing obligation per dependent; each trigger adds a reason)
Reasons present now (list):
Tier: 1 (dependent is a consequential decision or a member of the accepted set of one) / 2 (other)

OUTCOME / CLOSURE (separate record; the closer must meet the authority conditions)
[Common Block - closer]
Outcome: reaffirmed (as it now stands and is now supported) / revised (successor; requirement carries) / retired
Reasons addressed (every reason present at closure must be addressed):
Tier 1 reaffirmation is a fresh acceptance: Template 15 over the accepted set computed on the current basis.
Tier 2 reaffirmation: an AUTH-G holder who produced neither the dependent nor its material basis closure.
Tier 2 revision by the producer closes only as producer-addressed (not independent closure).
Time, silence, absence of objection, agent agreement, completion of downstream work, and withdrawal of the cause do not close a requirement.
New reliance on a dependent with an open requirement needs a closure or a reliance-while-open authorization (Template 17, ground G2).
```

---

## 22. Formal-Check Result

One application of one check. A result informs. It is not gate acceptance and writes nothing into an item's condition (RJ §4.10; RO §12.7). Guidance: G §11.

```text
[Common Block - capacity: verifier where relied on to satisfy a gate-required check; otherwise a producer of an advisory formal-check result]

Check applied (by name, and the criteria it names):
Version of the criteria or rule applied:
Evaluation point (the point in the record the check was applied to):
Record elements examined (each by reference, bound to the version examined):
What the result says: satisfied / violated / satisfied under exception / unresolved
  If violated: the rule or rules violated (named):
  If unresolved: which element is missing or which determination is pending:
Producing actor and standing: AUTH-V holder for ___ / human AUTH-G holder / advisory only
If the producing actor is an AI actor: Template 11 reference
Limits of this result: relative to the record at the evaluation point; says nothing about whether the record is complete or accurate or the world is as recorded
EFFECT CLAIMED: (for example: "satisfies the gate's formal-check slot for criterion C3")
EFFECT NOT CLAIMED: acceptance; sufficiency; validation; progression; independence; corroboration; truth
Link to anything this result creates on dependents, if it is a Template 23 finding:
```

---

## 23. Finding That an Acceptance Is Invalid

The CRC-59 finding. This is the event that gives rise to requirements on what relied on the acceptance (TRG-6). Guidance: G §11.4.

```text
[Common Block - capacity: verifier or acceptor-class finder; grant: AUTH-V for the scope, or AUTH-G (human)]

Acceptance found invalid (reference):
Rule or rules violated (each named):
Evaluation point:
Record elements examined (each by reference):
Is each rule asserted violated decidable from the record? yes / no
  If the recorder is a non-human AUTH-V holder and any answer is "no": this is NOT a finding. Record it as an advisory finding or a revalidation request instead.
Dependents that relied on the acceptance:
Requirement created on each dependent: (via the finding)
This finding is challengeable. A pending challenge does not suspend the requirement it creates.

If the assertion cannot meet this template (for example a bare "this acceptance is invalid" with no rule, evaluation point, or elements examined): do not use this template. Type it by what the recorder actually holds:
  AUTH-A holder -> a challenge (Template 12) citing the concern, or counter-evidence if sourced
  AUTH-A, AUTH-V, or AUTH-G holder -> a revalidation request (Template 21)
  an actor with no applicable authority -> an advisory finding
```

---

## 24. Consequential Commitment That Is Not an Acceptance

For commitments the project makes that are consequential but are neither a gate acceptance nor a recorded decision, and that rely on an unvalidated hypothesis or assumption. This template exists so the reliance does not travel unmarked. It does not add a protocol rule (RJ-OQ-12; DM-09). Guidance: G §15.

```text
[Common Block]

Commitment (what is committed to; to whom; with what effect):
Why it is consequential (commits resources, changes direction, makes an external promise, validates a major claim):
Routing decision (project practice, G §15.2):
  [ ] Routed through a gate acceptance: gate and decision reference. Then CRC-19 applies.
  [ ] Routed through a decision record (ACT-07): decision reference and authority basis. Then CRC-48 applies. A decision by someone without AUTH-G is a recommendation.
  [ ] Neither - a commitment by an authority outside this project's gates. Complete the rest of this record.
Who made the commitment and on what authority (an organizational basis is not a PROD-W grant; say which it is):
Unvalidated hypotheses relied on (references):
Assumptions relied on (references), including assumption-rooted items:
Open requirements relied on (references):
Reliance marks on the dependency links: present / absent
Visible warning stated wherever the commitment is cited: "This commitment relies on ___, which is unvalidated. It is not a PROD-W acceptance and does not validate anything."
Later gate or review that would test the reliance, and who is expected to run it:
Independence: the commitment is not made by a PROD-W gate authority holder acting as a producer of the basis on which it relies, or this is stated:
```

---

## 25. Actor-Kind Binding Note

For consequential acts by a human holding AUTH-G. No representation or record proves that a human acted (RO §9.5). This note only makes the weak point visible. Guidance: G §9.

```text
Actor identity:
Kind as designated, and who designated it, when, under what grant:
Binding method recorded for this act or for this actor's acts (describe; choose none, one, or several):
  [ ] None stated
  [ ] Access-control placement only (the act was made in a place only certain accounts can write)
  [ ] A credential was presented (describe in general terms; record no secrets)
  [ ] Out-of-band confirmation by a second identity (who, how, when)
  [ ] Third-party attestation (by whom; what it attests)
  [ ] Other (state)
Known limits of this method (for example: whoever holds the credential can use it; the confirmer may be the same person):
Claim made: "The record designates this actor as human and states the method above."
Claim NOT made: that the protocol, a schema, a record, or a signature guarantees a human acted.
```

---

## 26. Imported Prior Work and Carry-Over Candidate

For work brought into a new project from an earlier project, or from outside. Nothing in this template makes prior acceptance carry over. Carry-over is **undefined by the protocol** and what this template records is **project practice** (D10; RO §15.1, RQ-15). Guidance: G §16.2.

```text
[Common Block - recorded in the NEW project]

Prior item (reference to the item in the earlier project or outside source):
Earlier project and its authority-chain status (live / ended / unrecoverable):
What the prior record says about it (standing, acceptances, challenges, exceptions, open requirements):
Use in this project: source material / context / evidence through its source (cite the underlying source, not the old acceptance) / carry-over candidate
If a carry-over candidate:
  What the project proposes to rely on and why:
  This is PROJECT PRACTICE, not an accepted protocol carry-over.
  Prior acceptance status in this project: none. The item is not standing here.
  Needs here: a fresh recorded act by the appropriate authority in this project, over its own accepted set.
  Prior challenges and counter-evidence brought across (they remain visible): list
  Dependencies being reconsidered:
Who in this project is a producer of the imported item (if the new project's actors authored it earlier, they remain producers):
```

---

## 27. Grant Review Record

A visible prompt to look at who holds what, so that rotation, departure, and cascades are noticed before they strand someone. It has no automatic effect (time never acts, GCR-67). Guidance: G §16.1.

```text
[Common Block - the reviewer]

Review prompted by: scheduled review event / person joining or leaving / change of role / concern raised / other
Grants reviewed (list: grantee, class, scope, conferring act):
For each:
  Still wanted? yes / no / narrower
  Chain to root still effective? yes / no (a revoked or fallen link cuts everything downstream, prospectively)
  Any downstream grants that depend on it:
  Holder still independent of the sets it is expected to act on? yes / no
Departures expected: grants held by the departing identity and the grants it conferred (renunciation or revocation cascades; list those who would need re-conferral)
Re-conferral plan: grantee, grant, conferrer who holds a covering conferral scope and is not conflicted
Acts relying on a fallen grant after its fall: none / list (these are invalid)
Authority gaps that follow if no re-conferral is possible:
Outcome: no change / grants changed (record Template 3 for each) / escalation (Template 19) / stop at gap
```

---

## 28. Method Issue Log Entry

A place to record problems with the method as they appear in use. It routes questions; it does not answer them (STEP-07 owns pilot validation; STEP-08 owns research and hypothesis disposition).

```text
Issue ID:
Observed during (activity; if during a pilot, the pilot record):
Description:
Protocol area affected (cite the accepted rule, if known) or "none":
Methodology area affected (this guide's section or a template number) or "none":
Impact (what was harder, slower, unclear, or went wrong):
Temporary handling used:
Suggested route: STEP-07 pilot evidence / STEP-08 research disposition / MOD-W Moderator (protocol question) / Product Owner / later architecture / fix in methodology
Is concrete evidence about MOD-W transferability involved? yes (propose it under research governance in research/mod-w-transferability, non-blocking) / no
```

---

## 29. Change Notes

| Date | Version | Change | Reason |
| --- | --- | --- | --- |
| 2026-10-04 | 0.1 | Initial draft | STEP-06 Development Team work product |
| 2026-10-04 | 0.2 | Rewritten. Added the Common Block and templates for roles, grants, sources, attempts, configuration, readiness, independence declaration, escalation, authority gap, invalid-acceptance finding, actor-kind binding, carry-over, and grant review. Corrected the gate definition to the semantic slots of GC §5.2, the decision record to the treatments of GC §5.5, the conditional progression authorization to the nine elements of GC §9.2, and removed any status-like fields. | Draft v0.1 omitted required templates and departed from accepted slot and element lists |

MOD-W v5.0.1
