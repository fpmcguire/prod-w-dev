---
artifact:
  type: rule-judgment-boundary
  id: PROD-W-RJB
  version: 0.2
  created: 2026-10-02
  updated: 2026-10-02
  status: Draft - narrow revision after QA return; not accepted
  produced_by: Development Team
  produced_under: STEP-04
source:
  step: mod-w/step-04.md
  setup_review: mod-w/reviews/MODERATOR-REVIEW-STEP-04-SETUP.md
  revision_basis:
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-REVISION-BRIEF.md
    - mod-w/reviews/TECH-LEAD-STEP-04-REVISION-BRIEF.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-04-QA.md
    - mod-w/reviews/QA-REVIEW-STEP-04.md
  architecture: mod-w/architecture.md
  domain_language: mod-w/domain-language.md
  product_definition: mod-w/product.md
  protocol_semantics: prod-w/protocol-semantics.md
  evidence_knowledge_model: prod-w/evidence-knowledge-model.md
  gate_challenge_revalidation_semantics: prod-w/gate-challenge-revalidation-semantics.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Rule/Judgment Boundary and Candidate Rule Catalog (Initial Conceptual Boundary)

**Product:** PROD-W - Moderated AI-Assisted Product Development Workflow
**Artifact:** Representation-neutral boundary between objectively checkable protocol conditions and contextual human judgments; candidate rule catalog; human judgment catalog; semantic violation handling
**Produced under:** STEP-04
**Status:** Draft (v0.2), revised narrowly by the Development Team after the QA return of v0.1. Not accepted. Acceptance is the MOD-W Moderator's decision after the reviews in Section 2.3.

---

## 1. Purpose and Standing

### 1.1 Purpose

STEP-01 (`prod-w/protocol-semantics.md`) says who may act and what makes an action invalid. STEP-02 (`prod-w/evidence-knowledge-model.md`) says what knowledge is and how it relates. STEP-03 (`prod-w/gate-challenge-revalidation-semantics.md`) says what happens at gates, challenges, changes to accepted items, and revalidation. Each ended with a list of conditions it called "objectively checkable" (`OBJ-`, `EKO-`, `GCO-`) and a list of contextual judgments (`HJ-`, `EKJ-`, `GCJ-`), and each left the same questions to this step: which of those conditions become rules a conforming implementation could check, how a detected violation is handled, and where exactly the line between checking and judging runs.

This artifact answers them. It does three things.

1. It **defines the boundary** (Sections 4 and 5): what makes a condition objectively checkable, what makes it a contextual judgment, what the allowed middle pattern is, and how an entry is assigned.
2. It **catalogs** (Sections 6 to 8): candidate machine-checkable rules traced to accepted IDs, the paired human judgments, and how each pair divides the work.
3. It **states what detection means** (Sections 9 to 12): what a detected violation does to protocol effect, how semantics-level handling is categorized, and where the boundary falls for authority, provenance, and the evidence-to-revalidation chain. It disposes of the open questions routed to STEP-04 (Section 13).

The product problem it serves is unchanged: plausible ideas, weak evidence, agent agreement, and inherited assumptions must not become unjustified confidence that a product should be built. A boundary that is drawn too loosely lets a mechanical check pretend to judge sufficiency. A boundary drawn too tightly leaves rules unenforced because they were called "judgment." The artifact therefore fixes the line conservatively (BDR-02) and states what is lost on each side of it.

### 1.2 Standing

This is a **product artifact**. It extends the accepted STEP-01, STEP-02, and STEP-03 artifacts without editing them. Per D1 it is normative at the level of _semantics_. Documents, schemas, state records, prompts, validators, and agent instructions are projections of it, not substitutes for it.

It is **conceptual**. Tables, identifiers, and codes are expository devices for human review. They are not a protocol representation, not a rule language, and not a lifecycle or state vocabulary.

It does not describe or alter the governance of the `prod-w-dev` development project (Section 2).

### 1.3 What this artifact deliberately does not select

Operationalizes D2, NG-1, NG-2.

Nothing here selects, favors, prototypes, or assumes:

- a serialization, document format, or metadata model;
- a schema language or structural type system;
- a protocol or transport;
- a workflow engine, state machine, lifecycle graph, or orchestration framework;
- a storage model (document metadata, sidecar files, centralized state, ledger, graph store, or a hybrid);
- a validator, CLI tool, rules engine, agent harness, prompt format, or runtime integration;
- a database, API, or test suite;
- any condition, state, event, or transition name.

The words _invalidating_, _blocking candidate_, _flagging_, _escalating_, _recorded as unresolved_, _visible exception_, and _no automated conclusion_ (Section 9) are **semantic handling categories**: they describe what a detection must or may mean. They are not serialized values, state names, or enforcement mechanisms (BDR-11). `CRC-`, `HJC-`, `DR-`, `DM-`, `DP-`, and `BDR-` identifiers are labels for cross-reference only.

No `DIVERGENT` state or equivalent is adopted. Product Skeptic, Product Advocate, a Product Knowledge Ledger, a null-hypothesis framing pattern, a document-metadata model, an external-evaluator contract, and agent-skills hypotheses are not treated as requirements (NG-4).

### 1.4 Limits of what the boundary can do

Five limits are stated rather than implied.

- **A check is relative to a record.** A check decides a question about what is recorded. It cannot decide whether the record is complete, whether an attribution is accurate, or whether the world matches what was written (Section 4.1, BDR-06, HJC-21).
- **Unrecorded things cannot be checked.** A challenge nobody records, a contradicting finding nobody attaches, or a contribution nobody discloses is invisible to any rule (STEP-02 Section 1.4; STEP-03 Section 1.4).
- **Judgment remains judgment.** This artifact says what may be mechanically confirmed about a judgment (that it was recorded, by whom, under what grant, in what form, and when). It never says that the judgment is right (BDR-05).
- **Absence of a check is not absence of a requirement.** A rule that is hard to check remains binding (BDR-07).
- **Classification is conservative and revisable.** Every entry here is the Development Team's proposal for review. A misclassification toward "objective" is a larger risk than one toward "judgment" (BDR-02). The Development Team cannot certify that it found every hidden classification choice (Section 14.1).

### 1.5 Resolution digest

The open questions this step owns, and where each is resolved. The sections give reasoning; this table gives the answer.

| Question | Resolution in one line | Section |
| --- | --- | --- |
| **GC-OQ-01 / EK-OQ-14 / PS-OQ-10** Which conditions become catalog rules; how violations are handled | All 61 source conditions classified: 48 catalogued rules, 12 recorded-judgment checks, 1 deferred to representation (GCO-22), none out of catalog. 64 candidate entries. Seven semantic handling categories on two layers: protocol consequence is fixed by accepted semantics, handling is what detection must or may do. | 6, 9, 13.1, 13.7 |
| **GC-OQ-02 / PS-OQ-05** Authority grants | Granting is an act. Conferral needs a human holding AUTH-G whose conferral scope covers what is conferred. A project has exactly one establishing act, which precedes every other recorded act; root grants are only the grants it records, and every other grant chains acyclically to one. **Self-conferral is invalid** for every later grant; the establishing identity is a root grantee only in the establishing act itself. Grants take effect when recorded and are never retroactive. Revocation or narrowing cascades prospectively to grants downstream of it, without reaching acts already performed under an effective chain. Conferral by a conflicted producer, at any link of the chain, and revocation of a challenger's standing are flagged and escalation-eligible, not invalid. Conferral practice and grant representation are routed. Read with PR-04 and GCR-08 as a reading tension that is Moderator-visible (Section 3.3). | 3.3, 10.2, 13.2 |
| **GC-OQ-03 / PS-OQ-08 / PS-OQ-02** AI-held AUTH-V; verifier independence | A non-human actor may hold AUTH-V. Its verification satisfies a gate-required check only for criteria decidable from the record, with its examined inputs recorded. The same decidability bound governs a non-human finding that an acceptance is invalid. Verifier independence is non-membership in the producers of every verified item, by identity. No set of verifications is acceptance. | 10.3, 13.3 |
| **GC-OQ-09** Protocol-effective authorization terms | **Not adopted.** A lapse date would be time ending an authorization, which GCR-42 and GCR-67 exclude. Review events stay non-effective. Retained as a pilot question and as a possible Moderator-visible change. | 12.8, 13.4 |
| **GC-OQ-11** Assumption-rooted identification; never-a-correction tripwires | **Both become candidate catalog rules.** Assumption-rooted identification is a flagging rule that gains validity force only through CRC-19. Never-a-correction tripwires make the correction _designation_ ineffective and leave the change as a supersession. | 12.7, 13.5 |
| **EK-OQ-09 / PS-OQ-13** Configuration and lineage granularity; invalidate or weaken | Configuration is recorded at facet level (model, reasoning effort, harness, tooling, instructions), with "not determinable" a permitted visible statement. Lineage is recorded at immediate-derivation and source-comparability level. Insufficient configuration provenance is **flagged and left to judgment, not invalidating**, unless a gate definition requires more. Missing class-defining provenance is a different matter: the item is not evidence. | 11, 13.6 |
| **PS-OQ-10** Handling of detected invalid actions | Invalid actions never produce effect, whether or not detected. Blocking may prevent reliance on an act, never the record of it. Detection is a formal-check result, advisory unless the producing actor holds the grant. A finding that an acceptance is invalid must name the rule or rules violated, the evaluation point, and the record elements examined; a bare assertion is not that finding. | 9, 13.8 |

### 1.6 Reading conventions and identifiers

- "Item," "record," "relied on," "producer," "acceptor," "challenger," "verifier," "standing item," "accepted set," and "gate authority holder" are used as in STEP-01 Section 4.5, STEP-02 Section 3.4, and STEP-03 Sections 1.6 and 4.2.
- "Must" and "may" are used normatively. "Visible" means shown in any view of the item and of its dependents.
- New identifiers avoid collision with earlier steps: `BDR-` boundary rules, `CRC-` candidate rule catalog entries, `HJC-` human judgment catalog entries, `DR-` / `DM-` / `DP-` deferred items (representation, methodology, pilot), `UAD4-` declared choices, `RJ-OQ-` routed open questions, `AC4-` acceptance checks.
- Source identifiers keep their upstream form: `PR-`, `ACT-`, `OBJ-`, `HJ-`, `INV-`, `PS-OQ-` (STEP-01); `EKR-`, `EKO-`, `EKJ-`, `TRG-`, `UAD-`, `EK-OQ-` (STEP-02); `GCR-`, `GCO-`, `GCJ-`, `UAD3-`, `GC-OQ-` (STEP-03).

---

## 2. Governance Context

### 2.1 Authority

**This artifact is authored under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-04 acceptance for `prod-w-dev` and is the authority for accepting this artifact. The Development Team produced it and may not accept it.

The **PROD-W Product Moderator** referred to in this document is a _future PROD-W protocol role_ being defined by the product. It has no authority in `prod-w-dev`. Where this artifact says an act requires "a human holding AUTH-G," it states a property of the future protocol using STEP-01's authority model (PR-24). Nothing here grants authority to any actor in `prod-w-dev`.

### 2.2 MW-ADAPT-001

STEP-04 follows the active local adaptation **MW-ADAPT-001** (`research/mod-w-transferability/adaptations.md`). Section 14 is the required Undecided Architecture Declaration. It lists choices not already decided by accepted upstream artifacts, in particular what is considered objectively checkable, what requires human judgment, and what is merely a candidate for later validation. After the declaration, Tech Lead or QA sampling for unlisted choices is expected before Moderator acceptance, with particular attention to authority, independence, evidence standing, revalidation, and hidden representation choices. Section 14.4 gives the sampling targets the Development Team recommends. The Development Team cannot certify that the declaration is complete (Section 14.1).

### 2.3 Review sequence

| MOD-W point | Expected handling per `mod-w/step-04.md` | Standing for this deliverable |
| --- | --- | --- |
| 1b Setup review | Tech Lead packaging, Moderator approval | Complete: `mod-w/reviews/MODERATOR-REVIEW-STEP-04-SETUP.md`. This approved the work package, not this artifact. |
| 2a Plan approval | Development Team may proceed directly from the work package unless the Moderator requests a separate checkpoint | Not held as a separate checkpoint. The work package and setup review authorize direct implementation. |
| 2b Development Team work product | Development Team drafts the artifact | This artifact. |
| 3a Tech Lead review | Expected before final acceptance; includes MW-ADAPT-001 sampling unless QA is assigned it | The v0.1 review stands as a record of v0.1. Targeted Tech Lead re-review of this revision is **pending**. |
| 3b QA | Expected before final acceptance unless the Moderator waives it beforehand. Samples classifications, traceability, forbidden representation choices | The v0.1 QA review is approved as a review record and returned the artifact for narrow revision. Targeted QA re-sample of this revision is **pending**. |
| 3c Product Owner sign-off | Expected before final acceptance unless waived beforehand | **Held.** Pending this revised artifact. No waiver recorded. |
| 4a Moderator acceptance | Only after required reviews or recorded waivers | **Pending.** The Development Team records no acceptance. |

### 2.4 Production note

Produced by the Development Team using Claude Code (model `claude-sonnet-5-5`). Before submission the Development Team ran document-native consistency checks (identifier and cross-reference resolution, a forbidden-term scan, and a re-read against the acceptance checks); Section 17 records what they found. The checks were run by the producer. That is self-review: it produced revisions and the Section 14 audit pass, and it confers no independence and no verification for gate purposes (PR-27, PR-28). The v0.2 revision (Section 17.5) was produced by the same Development Team under the approved Tech Lead revision brief and its self-checks carry the same standing.

---

## 3. Relationship to STEP-01, STEP-02, and STEP-03

### 3.1 What is preserved without change

This artifact does not change, weaken, reinterpret, or add exceptions to any of the following:

- the authority model: actors, roles, authority grants, the four authority classes, and AUTH-G being human-only (PR-01 to PR-05);
- attribution and capacity rules (PR-06 to PR-09), action validity and the visibility of invalid actions (PR-10, PR-11), and the action catalog (ACT-01 to ACT-07);
- acceptance semantics: sufficiency, not truth; explicit, attributable, human, independent where consequential (PR-12, PR-13); verification as bounded by named criteria (PR-14); advisory findings (PR-15, PR-22, PR-23);
- self-approval invalidity and independence by actor identity (PR-16 to PR-21, PR-27, PR-28), and the separation of the two Moderator roles (PR-24), representation independence (PR-25), and the minimal revalidation statement (PR-26);
- STEP-02's knowledge classes, relationships, provenance elements, evidence expectations, and presumed materiality (EKR-01 to EKR-41);
- STEP-03's accepted set, gate model, challenge model, effect classification, disagreement derivation, conditional progression, waivers, correction and withdrawal authority, revalidation tiers, and time position (GCR-01 to GCR-68), including every refinement STEP-03 declared in its Section 3.3.

Where this artifact says an act needs authority, independence, or human authorization, it points to those rules and adds nothing to them, **except** in the areas the accepted artifacts expressly routed here and where Section 14 declares a choice: authority grants (GC-OQ-02), non-human verification (GC-OQ-03), configuration and lineage granularity (EK-OQ-09), and violation handling (PS-OQ-10).

### 3.2 What this artifact adds

| Handed forward | Where addressed |
| --- | --- |
| STEP-01 Section 9: "STEP-04 owns the full rule catalog and the validation boundary" | Sections 4 to 8 |
| STEP-01 Section 8: invalid action examples as "concrete targets for downstream validation design" | Section 9.9; Section 15.4 |
| STEP-01 PS-OQ-02, PS-OQ-05, PS-OQ-08, PS-OQ-10, PS-OQ-13 | Section 13 |
| STEP-02 Section 11.5: EKO set "is not the machine-checkable rule catalog" | Section 6 |
| STEP-02 EK-OQ-09, EK-OQ-14 | Sections 11, 13.6, 13.7 |
| STEP-03 Section 14.4: "whether each GCO condition is blocked, flagged, or escalated is STEP-04's question" | Sections 6.3, 9, 13.1 |
| STEP-03 GC-OQ-01, GC-OQ-02, GC-OQ-03, GC-OQ-09, GC-OQ-11 | Section 13 |
| STEP-03 Section 15.5, 16.2: items left open for STEP-04 | Section 13 |

### 3.3 Readings the catalog applies together

STEP-02 and STEP-03 are accepted and are not edited. STEP-03 Section 3.4 states a reading hazard: a reader who opens one artifact alone can reach a different answer from the unedited text. A rule catalog cannot avoid the hazard because it must apply all three artifacts to every condition. The tensions below were found while building the catalog. **None is a direct conflict.** Each is a reading, declared so that Tech Lead or QA can confirm or reject it. One of them, the last row (PR-04 and GCR-08 against conferral), is also made **Moderator-visible** because the accepted upstream text did not name conferral scope. If any had been a direct conflict, it would have been routed to the Moderator and not resolved here (`mod-w/step-04.md`, Out of Scope).

| Tension | Where it appears | Reading applied | Declared |
| --- | --- | --- | --- |
| A contradicting claim or inference "creates a requirement by itself" | STEP-02 TRG-2, EKR-37, EKO-19; STEP-03 GCO-28 says "a trigger event of any kind" | STEP-03 Section 3.3 narrows TRG-2: a bare contradicting claim or inference produces contestation and exposure; source-identified counter-evidence produces a requirement. CRC-29 and CRC-51 follow STEP-03. | UAD4-08 |
| EKO-15 lists "a conditional-progression authorization by an identified human exists" for any reliance on an unvalidated hypothesis | STEP-02 EKO-15; STEP-03 Section 9.2 reads "progression" as progression through a gate or consequential commitment | Ordinary work records reliance under assumption and needs no authorization; consequential reliance needs one (CRC-47, CRC-19). CRC-19 invalidates an acceptance that relies under assumption without it. For a consequential commitment that is not an acceptance, this step records the accepted STEP-03 reading and adds no rule (RJ-OQ-12). | UAD4-08 |
| Evidence "is expected to carry" the listed elements, and every evidence item "records" them | STEP-02 EKR-14 versus EKO-05 | Elements split into class-defining (absence means the item is not evidence for that target) and descriptive (absence is flagged). CRC-36, CRC-37. | UAD4-09 |
| EKO-04 joins three tests of different objectivity | STEP-02 EKO-04, EKR-13, and STEP-02 Section 7.6 | Split: source identified and not a concurrence record are objective; "not the asserting actor's assertion" is objective only for record-internal references and is otherwise judgment. | UAD4-09 |
| Material-claim provenance (EKR-08, PR-09) and presumed materiality (EKR-35) | STEP-01 INV-10; STEP-02 EKR-35 | Timing split: designated material at creation is a creation requirement; presumed material because later cited is a flagged obligation. STEP-03 Section 5.4 lists no validity condition for it. | UAD4-10 |
| HJ-05 and EKJ-14 list "none" as paired check | STEP-01 Section 9.3; STEP-03 GCJ-03 pairs GCO-08 | GCO-08 (a treatment is recorded) is the pair. Residual risk acceptance is recorded as a treatment. | UAD4-24 |
| PR-04 says authority "is neither transitive nor inheritable" and "one authority class does not confer another." GCR-08 says "delegation never conveys authority." CRC-61 has a human AUTH-G holder confer grants, including other classes and AUTH-G itself | STEP-01 PR-04; STEP-03 GCR-08; STEP-03 GC-OQ-02 (routed here); CRC-60 to CRC-64 | PR-04 and GCR-08 prohibit authority by mere transitivity, inheritance, delegation, role label, or work assignment. CRC-61 is none of these. It is not delegation and not class-confers-class. Holding AUTH-G, or any class, confers nothing. A conferral creates a **new explicit grant** (PR-02: explicit, attributable, scoped) by a human AUTH-G holder whose **conferral scope**, itself an explicit grant, authorizes that class and scope. A conferral scope is a scope of AUTH-G and not a fifth class (Section 10.2.1). This is a STEP-04 operationalization of GC-OQ-02, not a direct conflict with PR-04 or GCR-08. Because the accepted text did not name conferral scope, the reading is **acknowledged as a tension and routed as Moderator-visible**. No upstream artifact is edited. If the Moderator reads it as a direct conflict, UAD4-13 returns for disposition and is not resolved inside this artifact | UAD4-13 |

**Terms used for the two kinds of assignment.** To keep a reading of PR-04 and GCR-08 from reaching the wrong relation, this artifact uses two terms. **Work assignment** (or production assignment) is the provenance relationship under GCR-08 and PR-27: an actor assigns production of an item or part of it to another. It is recorded as provenance, confers no authority, and makes the assigner a producer only where the assigner supplied the item's substance or adopted it (CRC-11, HJC-12). **Grant-bearing role-position appointment** (also "role-position appointment") is appointing an actor to a role position that carries grants. It is a conferral and is evaluated under CRC-61 and CRC-62 (Section 10.2.5; UAD4-13).

### 3.4 What this artifact does not modify

No accepted STEP-01, STEP-02, or STEP-03 product artifact, no accepted Product Definition, Architecture, Roadmap, or MOD-W template is modified. `mod-w/domain-language.md` is not edited. Terms this artifact introduces are listed in Section 4.11 for the Moderator's later disposition.

---
## 4. Boundary Definitions

Operationalizes D6. The definitions below are the vocabulary the rest of the artifact uses. They restate STEP-01 Section 9.1, STEP-02 Section 11.1, and STEP-03 Section 14.1 as a test that can be applied, and they add the middle pattern those sections gestured at.

### 4.1 The record and the evaluation point

The **record** is the set of recorded items, actions, relationships, designations, grants, determinations, and their history, as they stand at an **evaluation point**: a recorded act, or a stated point in the record's history. The **available record** for a check is whatever is recorded at its evaluation point and nothing else.

This is a semantic notion. It says nothing about where or how the record is kept, how its order is established, or how it is queried (DR-03, DR-10).

Three consequences:

- A check can only answer "does the record show X?" It cannot answer "is X true in the world the record describes?"
- A record element that is absent is absent. It is never read as satisfied (BDR-06).
- The same rule may be evaluated at an act's own evaluation point (does this act satisfy the rule?) or over the record at a later point (does the record still show what the rule requires?). Section 5.4 distinguishes these.

### 4.2 Recorded designation

A **recorded designation** is an attributable record in which an actor states a classification or judgment-bearing characterization that later checks will rely on: that an item is material or not, that a change is a correction, that a proposition carries validation criteria, that a scope is what it is, that a formal-check criterion is decidable from the record.

A check **takes a designation as given**. It applies the designation; it does not evaluate it. Whether the designation is _right_ is judgment (Section 4.4). Whether the designation is _effective_ is itself checkable, because upstream semantics make effectiveness depend on recorded conditions such as confirmation by an independent human, no pending challenge, or a recorded rationale (for example GCR-34, GCR-51).

This is the sense in which STEP-04's scope says an objective check does not judge sufficiency, risk, acceptability, or materiality "beyond recorded designations": the check may use a recorded materiality designation to decide what is in an accepted set. It may not decide whether the designation was warranted.

### 4.3 Objectively checkable condition

**Definition.** A condition is **objectively checkable** when it is decidable from the available record, without interpreting the world the record describes, and without judging sufficiency, relevance, persuasion, risk, materiality, acceptability, warrant, or substantive independence beyond recorded designations.

**Three-part test.** A condition passes only if all three hold.

| Part | Question | Fails when |
| --- | --- | --- |
| **T1. Defined elements** | Do accepted semantics define the record elements the condition needs? | The condition needs an element no accepted artifact defines, or one whose definition depends on a representation or practice choice |
| **T2. Record-only answer** | Is the answer determined by those elements alone? | The answer depends on what a source says about the world, whether a statement is true, or what a person intended |
| **T3. No judgment inside** | Does the answer avoid deciding sufficiency, relevance, persuasion, risk, materiality, acceptability, warrant, or substantive independence, other than by applying a recorded designation? | The only way to reach the answer is to form a view on one of those |

**Agreement corollary.** If two competent evaluators, given the same record and the same evaluation point, could reasonably reach different answers, the condition is not objectively checkable as stated. The test is about the record and the semantics, not about tooling: a condition does not become objective because a program could compute it, and it does not become judgment because it is laborious to compute.

**Objective checks are not conclusions about substance.** That a challenge exists is checkable. That the challenge was good is not. That a source is identified is checkable. That the source is reliable is not.

### 4.4 Contextual human judgment

**Definition.** A **contextual human judgment** is a determination that requires authorized human interpretation of sufficiency, relevance, warrant, risk, persuasion, adequacy, materiality, acceptability, or substantive independence.

It is "contextual" because the answer depends on the situation the record describes. It is "human" and "authorized" where it determines a consequential protocol effect: gate-class determinations (acceptance, refusal, deferral, closure, confirmation, validation, waiver, reaffirmation, invalidation of a hypothesis or of another actor's item, conditional progression) belong to a human holding AUTH-G for the scope (PR-05, PR-13). A finding that an acceptance is invalid is a different thing: a formal-check result recorded under CRC-59. Other actors, including AI agents and external evaluators, may record the same kind of content only as a designation, assertion, challenge, counter-evidence, or advisory finding. Its effect is then what upstream semantics give it, and a human with the authority may adopt, challenge, or override it (PR-15, PR-22; EKR-04).

A judgment is never converted into a number, grade, weight, or confidence value (BDR-14).

### 4.5 Recorded-judgment check

**Definition.** A **recorded-judgment check** is an objective check that confirms a judgment was **recorded** in the required way. It never decides the judgment's substance. This is the allowed middle pattern.

A recorded-judgment check may confirm any of these **facets** of a recorded judgment, and only these:

| Facet | What is confirmed | Example |
| --- | --- | --- |
| **Existence** | A judgment record exists where one is required | A treatment is recorded for each standing-record item (CRC-18) |
| **Recorder identity** | The recorder is an identified actor, of the required kind | The acceptor is a human identity (CRC-03) |
| **Authority** | The recorder held a grant of the required class covering the scope at the act | An acceptance is under AUTH-G for the gate (CRC-02) |
| **Capacity** | The recorder acted in the recorded capacity the act requires | A producer's own challenge is recorded as a challenge, not counted as independent (CRC-12) |
| **Required elements** | The elements the form requires are present | A conditional progression authorization carries its nine elements (CRC-23) |
| **Timing** | The record precedes the act it authorizes, and is not backdated | An authorization recorded after an acceptance does not validate it (CRC-24) |
| **Independence** | The recorder is not a producer of the set the judgment favors | The acceptor produced no member of the accepted set (CRC-07) |
| **Direction** | The act is of the kind the recorder may perform (favorable or conservative) | A producer performs no favorable act over its own set (CRC-09) |

A rationale is **present or absent**. Whether it is adequate is judgment. A declaration is **present or absent**. Whether it is true is judgment (CRC-11, HJC-12).

**The facets and the CR/RJC disposition.** The facets above say what any check of a determination act may confirm (BDR-05). They do not by themselves make a row RJC. A rule that decides the **protocol validity** of a determination act from record facts, such as who acted, under what grant, whether independent, when, of what kind, and in what direction, and that does not evaluate the determination's substance, may remain CR (CRC-02, CRC-03, CRC-07, CRC-09). A row is RJC where the thing it requires is the determination's **content-bearing record** (a rationale, treatment, designation, declaration, the elements of an authorization, or a disposition for each reason), as Section 5.1 states.

### 4.6 Candidate rule

**Definition.** A **candidate machine-checkable rule** (candidate rule) is a normative statement of an objectively checkable condition, with its sources, its evaluation kind, its semantic handling, and its judgment pair, catalogued by this artifact (Section 6).

"Candidate" has a precise meaning here. The condition is _semantically specified_: its required record elements and its decision test are fixed. It is _not yet mapped_ to any representation and _not yet implemented_ by anything. STEP-05 evaluates representations; later work decides whether and how any rule is implemented. Candidate status does **not** weaken the underlying protocol requirement. The requirement binds whether or not any check is ever built (BDR-07).

### 4.7 Detected violation

**Definition.** A **detected violation** is a determination, from the record at an evaluation point, that a candidate rule's condition is not satisfied, or that a record element the rule needs is absent where the source rule makes absence disqualifying (BDR-12).

A detected violation is a **formal-check result**: a record of applying a named rule to a named evaluation point and of the outcome. It is not a finding of truth, a determination of sufficiency, or an acceptance (Section 9.4).

Detection **reveals** a violation. It does not create it. An act that violated an invalidating rule was invalid from the outset, whether or not anyone noticed (STEP-01 Section 6.1; STEP-03 Section 4.7; BDR-08).

### 4.8 Unresolved condition and uncheckable condition

Two different things are easily confused.

- An **unresolved condition** is a candidate rule's condition that cannot currently be decided from the record, because a required element is absent or because the result depends on a determination not yet made, **and** accepted semantics give no conservative default for the interim. It is recorded as unresolved and stays visible. No conclusion is drawn and no clock acts (Section 9.5).
- An **uncheckable condition** is one for which no record-only test exists, because it requires interpretation. It is a contextual human judgment (Section 4.4), not a failed check.

An unresolved condition may become decidable when the missing element is recorded or the pending determination is made. An uncheckable condition does not.

### 4.9 Deferred categories

A candidate whose rule shape is settled but whose computation or parameters depend on a choice this step does not own is **deferred**, never silently dropped.

| Category | Meaning | Owner |
| --- | --- | --- |
| **Deferred to representation** (`DR-`) | The semantic condition stands. How it is computed, stored, or ordered depends on a representation choice | STEP-05 |
| **Deferred to methodology** (`DM-`) | The semantic condition stands. Its parameters, templates, thresholds, or practice depend on methodology | STEP-06 |
| **Deferred to pilot** (`DP-`) | Whether the choice is right needs evidence from using it | STEP-07 |
| **Deferred to research synthesis** | Disposition of a research hypothesis | STEP-08 |

### 4.10 Formal-check result

A **formal-check result** is the record of one application of a candidate rule: the rule applied, the evaluation point, the record elements examined (by reference), and the outcome (satisfied, violated, satisfied under exception, or unresolved). The outcomes are what a result may **say**. They are not a serialized value set or a state vocabulary (BDR-11). Its standing is set by Section 9.4. A result that asserts a violation names the rule or rules violated; a finding that an acceptance is invalid is such a result and has the further content CRC-59 requires.

### 4.11 Terms introduced for later glossary disposition

Not edited into `mod-w/domain-language.md`. For the Moderator's later disposition: _recorded-judgment check_, _candidate rule_, _detected violation_, _formal-check result_, _handling category_, _recorded designation_, _evaluation point_, _conferral scope_, _establishing act_, _root grant_, _work assignment_, _grant-bearing role-position appointment_, _unresolved condition_ (in the sense of Section 4.8).

### 4.12 Boundary rules

| ID | Rule |
| --- | --- |
| BDR-01 | A condition is catalogued as an objective check only if it passes T1, T2, and T3 of Section 4.3. The agreement corollary applies. |
| BDR-02 | **Conservative classification** (declared: UAD4-02). Where it is doubtful whether a condition passes the test, it is classified as a contextual human judgment. Over-claiming objectivity is the larger risk (D6: "prevents both under-governance and false automation"). |
| BDR-03 | **Composite conditions are split** (declared: UAD4-03). A condition that joins objective and judgment parts is catalogued as its objective core, with the judgment residue named and paired (Section 8). The objective core is never presented as deciding the residue. |
| BDR-04 | A check takes a recorded designation as given and applies it. The effectiveness conditions of a designation (confirmation, no pending challenge, recorded rationale, independence of the designator) are themselves candidate rules. |
| BDR-05 | A recorded-judgment check confirms only the facets of Section 4.5. It never decides a judgment's substance, and its outcome is never reported as a verdict on the judgment. |
| BDR-06 | Checks are relative to the available record at an evaluation point. A missing record element is never read as satisfaction. Attribution accuracy and record completeness are not decided by any check (HJC-21). |
| BDR-07 | Candidate status does not relax the underlying requirement. **The absence of a mechanical check does not make a protocol requirement optional.** Structural or format validity never establishes protocol validity (PR-25); candidate rules are checks of protocol semantics over the record. |

---

## 5. Classification Criteria and Decision Tests

### 5.1 Classification outcomes

Every candidate condition receives exactly one **primary disposition**. A residue of judgment, where there is one, is named separately and paired (Section 8).

| Code | Disposition | Meaning |
| --- | --- | --- |
| **CR** | Catalogued rule | Objectively checkable (BDR-01). Enters the candidate catalog with a handling category |
| **RJC** | Recorded-judgment check | The object of the check is a recorded judgment, determination, designation, declaration, treatment, or authorization. Enters the catalog confirming facets only (BDR-05) |
| **DR / DM / DP** | Deferred | Rule shape or parameters belong to representation, methodology, or pilot (Section 4.9) |
| **HJ** | Contextual human judgment | No record-only test exists. Enters the human judgment catalog (Section 7) |
| **OOC** | Out of catalog, with rationale | Not a per-record check: a definition, a constraint on any representation, a duty whose breach is not detectable from a record, or a statement enforced through other entries |

**CR versus RJC.** The discriminator is **what the rule requires of the record**, not whether a determination act is somewhere in view.

- A condition is **RJC** where the rule requires the **content-bearing record of a determination**: the rationale, treatment, designation, declaration, authorization elements, or disposition of each reason through which a determination act records its judgment. The rule confirms that record is present in the required form (BDR-05), and the substance is paired as judgment (Section 8).
- A condition is **CR** where the rule requires a _record element or relation_ (an identity, a link, a type, a time, a count, a reference) **or decides the protocol validity of an act from validity facets** (who acted, under what grant, whether independent, when, of what kind, in what direction) without opening the determination's own content-bearing record. This holds even where the act checked is a determination act. A rule that checks only those facets of an acceptance or closure, and does not evaluate its substance, is CR (CRC-02, CRC-03, CRC-07, CRC-09, CRC-26, CRC-27, CRC-57).
- A row whose rule joins validity facets with a content-bearing record takes **RJC** on the strength of the content-bearing part. Its validity-facet part is still catalogued in its CR entry (for example, EKO-11 is RJC through CRC-46 and relies on CRC-07).

**Closure, worked both ways.** GCO-12 checks that a closure is of a recognized kind and that the closer meets its authority conditions. Kind and authority are validity facets decided from record facts, so GCO-12 is CR (CRC-27). GCO-20 checks that a closure of a requirement names and addresses every reason present. That reaches the closure's reason-addressing record, which is content-bearing, so GCO-20 is RJC with an HJC-16 residue (CRC-52). The same two checks, applied to the same kind of act, come out differently because they ask for different things. The existing classification of all 61 rows is unchanged by this explanation (UAD4-03).

### 5.2 Decision tests

Apply in order to each candidate. Stop at the first outcome.

| # | Question | If no | If yes |
| --- | --- | --- | --- |
| **Q1** | Do accepted semantics define every record element the condition needs (T1)? | Defer: **DR** if the missing definition is a representation choice (identity across change, ordering, computation); **DM** if it is a parameter or practice (thresholds, templates, who holds a scope). If neither, record an open question | Q2 |
| **Q2** | Is the answer determined by those elements alone, without interpreting what a source says about the world (T2)? | **HJ** | Q3 |
| **Q3** | Does reaching the answer require forming a view on sufficiency, relevance, persuasion, risk, materiality, acceptability, warrant, or substantive independence, other than by applying a recorded designation (T3)? | Q4 | **HJ** |
| **Q4** | Would two competent evaluators always agree (agreement corollary)? | **HJ** (BDR-02) | Q5 |
| **Q5** | Does the rule require the content-bearing record of a determination (a rationale, treatment, designation, declaration, authorization elements, or a disposition of each reason), and not only the validity facets or a record element or relation (Section 5.1, CR versus RJC)? | **CR** | **RJC** |
| **Q6** | Does the condition also contain a judgment part (BDR-03)? | Done | Catalog the objective core; name the residue as an **HJ** entry and pair it |
| **Q7** | Does computing the answer depend on a representation or ordering choice? | Done | Keep the rule; record the computation as a **DR** item |

### 5.3 Tests that do not qualify

None of these is a ground for classifying a condition as objective or as judgment.

- That a tool could compute it, or that it is hard to compute (Section 4.3).
- That it appears in a table headed "objective" upstream. Upstream tables are the starting inventory. Section 3.3 shows where this step split a condition.
- That a human wrote the record. A recorded designation is checked as a record (Section 4.2).
- That a violation would be serious. Severity affects handling (Section 9), not classification.
- That a rule is easy to violate quietly. That is a reason to catalog it with strong handling, not to call it objective.

### 5.4 Evaluation kinds and blocking eligibility

Each candidate rule carries one or more evaluation kinds.

| Kind | Code | The rule is evaluated | Typical rules |
| --- | --- | --- | --- |
| **Act-time** | A | Over the record as of the act, to decide whether the act is valid | Authority, independence, required content, gate acceptance validity |
| **Standing** | S | Over the record at any later point, to decide whether the record still shows what the rule requires | Carry-over, derived effects, reliance marks, requirement presence |
| **Historical** | H | By comparing what was recorded earlier with what was recorded later, over the record's history | Append-only producers, history preservation, non-retroactivity, never-a-correction changes |

A rule is **blocking-eligible** (code B in Section 6) if it is act-time and every input it needs is available in the record as of the act (declared: UAD4-23). Eligibility is a semantic property. It is not a decision to block (Section 9.2, BDR-09, BDR-10). **Where an input is a derived condition** (exposure, open requirement, assumption-rooted basis item; DR-01, DR-04), eligibility holds for a given representation only if that representation makes the derived condition available at the evaluation point. Where it does not, the rule is not blocking-eligible there, and a violation of the rule is still a violation (BDR-07). The B tags of CRC-18 and CRC-19 are conditional in this way.

### 5.5 Reclassification

A classification changes only by a revision of this artifact accepted by the MOD-W Moderator (BDR-16). An implementation, a validator, a representation, or a pilot may produce evidence that a classification is wrong (DP-05). Evidence is not reclassification.

| ID | Rule |
| --- | --- |
| BDR-16 | Classification of a condition as objective check, recorded-judgment check, judgment, or deferred changes only by an accepted revision of this artifact. Evidence from implementation or pilot is input to that revision, not a substitute for it. |

---
## 6. Candidate Machine-Checkable Rule Catalog

Operationalizes D6, G-3. Resolves **GC-OQ-01** and **EK-OQ-14** for catalog membership.

### 6.1 How to read the catalog

Each entry states a condition, the accepted IDs it traces to, how it is evaluated, how a detected violation is handled, and the judgment it is paired with. The entry is a **derived grouping over accepted IDs**: several accepted conditions that make the same decidable test are catalogued once, and the sources are listed so no accepted ID is lost (Section 15.1). No entry adds a protocol requirement beyond the accepted rules it traces to, except where Section 14 declares a choice and the entry says so. **The entry says so in its last column**: where an entry applies a declared choice, the column lists the UAD4 identifier (for example, `UAD4-13`). An entry that lists no UAD4 identifier applies no declared choice beyond the global ones (UAD4-01 to UAD4-06, UAD4-08, UAD4-17, UAD4-23, and UAD4-25).

**Evaluation (Eval):** A act-time, S standing, H historical (Section 5.4).

**Handling codes** (defined in Section 9.2):

| Code | Handling |
| --- | --- |
| **I** | Invalidating: the act or designation lacks its intended effect, and stays visible |
| **B** | Blocking-eligible: act-time, all inputs in the record; reliance on the act may be prevented before anyone relies on it. Never prevents the _record_ of the attempt |
| **F** | Flagging: made visible to reviewers and to those who rely on the item; effect unchanged |
| **E** | Escalation-eligible: the matter needs a determination by a particular authority |
| **U** | Recorded as unresolved: cannot be decided from the record, no default applies |
| **X** | Coverable by a visible exception, where the requirement is waivable (Section 9.6) |
| **N** | No automated conclusion: the judgment residue is not decided |

**Judgment pair** points to Section 7. **DR** points to the deferred items in Section 6.6. **UAD4** points to the declared choice in Section 14.2.

### 6.2 The catalog

#### Family A. Attribution and authority

| ID | Condition | Sources | Eval | Handling | Pair / deferral / declared |
| --- | --- | --- | --- | --- | --- |
| CRC-01 | Each action records exactly one acting actor identity, one capacity, a target, a time, and the content its category requires. Attribution resolves to a recorded identity. A relationship is recorded as an assertion by exactly one identity | OBJ-01; PR-06, PR-07, PR-08, PR-10; EKR-03; EKO-02 (part); ACT-01 to ACT-07 (Section 5.1 of STEP-01) | A | I, B | HJC-21; DR-07 |
| CRC-02 | At the act's recorded time, the acting identity holds a well-formed grant of the class the act requires, covering the target's scope. Authority is resolved through grants, never through role names, seniority, prior participation, convention, or a document naming a role | OBJ-02; GCO-02 (part); PR-01, PR-03, PR-04, PR-10, PR-24; INV-09, INV-15 | A | I, B | HJC-25; DR-08 |
| CRC-03 | An act requiring AUTH-G is recorded under an identity whose recorded actor kind is human | OBJ-04; GCO-02 (part); PR-05; INV-04 | A | I, B | HJC-21; DR-07 |
| CRC-04 | An output of an actor lacking the authority an act requires is not recorded as that act. Acceptance, refusal, deferral, conditional progression, waiver or exception, authority closure, correction confirmation, reaffirmation, invalidation of a hypothesis or of another actor's item, validation, consequential decision, and progression authorization are recorded only under AUTH-G. The output is re-typed as the nearest act the actor may make (advisory finding, challenge, counter-evidence; declared: UAD4-22). Evaluator and automated outputs are typed advisory unless a recorded grant says otherwise. "Invalidation" here is the STEP-02 and CRC-57 sense (EKO-12): invalidating a hypothesis or an item. A **finding that an acceptance is invalid** is a different thing: a formal-check result whose recorders and required content CRC-59 fixes (UAD4-29). It is not an act on this list | OBJ-09; EKO-12, EKO-20; GCO-27; PR-15, PR-22, PR-23; EKR-04, EKR-20; GCR-18, GCR-22; ACT-07; INV-05, INV-16 | A | I, B | HJC-17; UAD4-22, UAD4-29 |
| CRC-05 | A verification names the formal criteria it verified; a record naming none is not a verification. A verification is never recorded as acceptance, validation, or progression | OBJ-13; PR-14; ACT-04; INV-07 | A | I, B | none |

#### Family B. Independence and self-approval

| ID | Condition | Sources | Eval | Handling | Pair / deferral / declared |
| --- | --- | --- | --- | --- | --- |
| CRC-06 | The accepted set is computable at the act: every basis link resolves, the closure is computed under the effective designations, and every member has recorded, resolvable producers | GCO-01; GCR-01, GCR-04; EKR-32 | A | I, B | DR-01 |
| CRC-07 | The acceptor, with collective identities expanded to recorded members, is a recorded producer of no member of the accepted set. Disputed attributions count against the disputed actor (CRC-14); acceptance-act content is not production. Identity is the only basis: a second role label, capacity, tool, session, configuration, or elapsed time does not make an actor independent of itself | OBJ-03; GCO-03; EKO-11 (part); PR-16, PR-17, PR-21, PR-27, PR-28; GCR-02, GCR-03, GCR-08, GCR-38 (part); INV-01, INV-02, INV-17 | A | I, B | HJC-12 |
| CRC-08 | Where a gate requires several independent acceptances, the number counted excludes any acceptance by a producer of the accepted set. The default requirement is one valid independent acceptance | PR-18; GCR-16; INV-03 | A | I (the counted acceptance), B | none |
| CRC-09 | A favorable act over an accepted set (acceptance, waiver, conditional progression authorization, correction confirmation, reaffirmation, closure of a challenge in the set's favor, acceptance of residual risk) is not performed by a recorded producer of any member of that set. Conservative acts (refusal, deferral, escalation, request, challenge, withdrawal or retirement of own item, invalidation of an item or hypothesis, a finding under CRC-59) are not restricted. **Direction is read from this closed list of act kinds, not interpreted.** For a closure, the kind is read from CRC-27's list: authority closure of a challenge against a member of the set, and challenger resolution of such a challenge, are on the favorable list (each ends opposition to the set while leaving the target standing); closure by withdrawal of the target with no successor is the producer's own withdrawal and is conservative. A closure whose kind is not on either list, or whose kind the record does not name, has its direction recorded as unresolved, and the matter is escalation-eligible. It is not interpreted | GCR-05, GCR-18 (part), GCR-26; GCO-03 (generalized) | A | I, B, U, E | UAD4-31 |
| CRC-10 | No waiver, exception, deferral, conditional progression, escalation outcome, relabeling, or recorded cure is treated as validating an act that CRC-07 or CRC-09 invalidates. An exception record naming independence as the waived requirement is ineffective | GCR-06, GCR-46 (item 1); GCO-10 (part) | A | I, B | none |
| CRC-11 | The acceptance-act content of every consequential acceptance carries an independence declaration (the acceptor's knowledge of production, work assignment, or contribution to the accepted set, and the work-assignment relations it knows of). Presence is checked. Truth is not | GCO-11 (part); GCR-09 | A | I, B, N | HJC-12 |
| CRC-12 | Where a gate requires a challenge, a challenge on the stated target exists. Where independence is required, its challenger is a producer of nothing challenged. A challenge by a producer of the challenged item is recorded and not counted | OBJ-06; GCO-06; PR-19, PR-28; GCR-15; INV-14 | A | I, X | HJC-07, HJC-12 |
| CRC-13 | Where a gate requires a formal check, a verification exists, names its criteria (CRC-05), has a verifier who is a producer of nothing verified, and was not performed by the acceptor. A producer's self-verification is recorded and not counted | OBJ-13; GCO-07; PR-14, PR-19, PR-28; GCR-10 | A | I, X | HJC-12; UAD4-26 |
| CRC-14 | Recorded producers of an item are added and never removed or transferred out for independence purposes. A recorded removal or transfer is ineffective for independence. A disputed producer attribution treats the disputed actor as a producer for that actor's favorable acts until an independent gate authority holder resolves it | GCO-23; GCR-07; PS-OQ-07 | H, A | I, U | HJC-12 |

#### Family C. Gate acts

| ID | Condition | Sources | Eval | Handling | Pair / deferral / declared |
| --- | --- | --- | --- | --- | --- |
| CRC-15 | A verification by a non-human actor satisfies a gate-required formal check only if (a) the actor holds AUTH-V covering the gate or artifact class; (b) every named criterion is designated in the gate definition as decidable from the record; (c) the verification record states the record elements it examined and its evaluation point; and (d) CRC-13 holds. Otherwise the output is an advisory finding. **The decidability bound of (b) and (c) also governs a non-human actor's finding that an acceptance is invalid (CRC-59):** such a finding counts only where each rule asserted violated is decidable from the record and the finding states the elements examined and its evaluation point; otherwise it stays advisory or request-like and does not itself trigger TRG-6 | GCR-10, GCR-11; PR-14, PR-15; GC-OQ-03 | A | I (as verification; re-typed advisory), B | HJC-24; DR-09; UAD4-16, UAD4-29 |
| CRC-16 | A gate definition was recorded before the act and covers the progression. A consequential decision with no governing definition is recorded as a recommendation and the missing definition is visible. A definition amended after a refusal or deferral on the same basis applies to it only as a recorded exception | GCO-04; GCR-12, GCR-13; ACT-05, ACT-07 | A | I, F, X (amendment only), B | HJC-20 |
| CRC-17 | Each required-evidence slot and required artifact of the gate is filled by present items carrying the designations CRC-36 requires. A visible absence statement does not fill it. A gate-defined recency criterion is checked against recorded observation times at the act | GCO-05; OBJ-07; GCR-14, GCR-68; EKO-04, EKO-05 | A | I, X | HJC-01, HJC-02; DM-01 |
| CRC-18 | Every standing-record item (opposition including withdrawn, exposure, open requirements, reliance marks, earlier refusals and deferrals on the same gate and basis, applying exceptions) is cited with a recorded treatment from the recognised list, determined by the actor the list prescribes. For each basis item, challenges and contradicting items recorded before the decision are cited with how each stood. A gate-defined stricter _response_ rule is a gate requirement and may be waived (CRC-22); the visibility of what exists in the standing record may not (Section 9.6 item 3). **Exposure and open requirements are derived conditions** (DR-04): B holds only where the representation makes them available at the act | GCO-08; EKO-17; GCR-17, GCR-38 (part), GCR-39; EKR-30 | A | I, B (conditional: DR-04) | HJC-07, HJC-08, HJC-09; DR-04 |
| CRC-19 | Every relied-on unvalidated material hypothesis or assumption (including assumption-rooted basis items) is covered by a conditional progression authorization, and every open requirement on a basis item by a closure or a reliance-while-open authorization, recorded at or before the acceptance. New reliance on a dependent with an open requirement needs one of them. This entry invalidates an _acceptance_ that relies under assumption without the required authorization. It adds no rule for a consequential commitment that is not an acceptance (RJ-OQ-12). **Assumption-rooted basis items and open requirements are derived conditions** (DR-01, DR-04): B holds only where the representation makes them available at the act | GCO-09; EKO-15 (part); GCR-16, GCR-33, GCR-42, GCR-47 | A | I, B (conditional: DR-01, DR-04) | HJC-14; DR-01, DR-04; UAD4-08 |
| CRC-20 | Every unsatisfied gate requirement is covered by an exception recording the authorized human, grant, rationale, unsatisfied requirement, scope, provenance, and exception marker. The exception-giver is a human AUTH-G holder independent of the accepted set. None of the six non-waivable conditions is the waived requirement. An override names the overridden determination or check. An instrument that leaves the requirement open and tracked is typed conditional progression and not exception | GCO-10; OBJ-12; GCR-45, GCR-46, GCR-48 | A | I, X | HJC-15 |
| CRC-21 | An acceptance is an explicit, attributable act that states its determination and precedes the progression it authorizes. Silence, elapsed time, absence of objection, completion of prior acts, structural completeness, and agreement are not acceptance. A progression record with no preceding acceptance for its gate is invalid | GCO-11 (part); OBJ-11; PR-13; GCR-20; ACT-05; INV-06 | A | I, B | none |
| CRC-22 | **Composite.** An acceptance is valid only if CRC-02, CRC-03, CRC-06, CRC-07, CRC-08, CRC-11, CRC-12, CRC-13, CRC-16, CRC-17, CRC-18, CRC-19, CRC-20, and CRC-21 hold at the act, or, for a gate requirement that is **waivable under STEP-03 Section 9.4**, the shortfall is covered by a valid exception meeting CRC-20. Waivable requirements include the gate-required slots, challenges, and formal checks (CRC-12, CRC-13, CRC-17), a gate-definition amendment treated as an exception (CRC-16), **gate-required configuration facets** (CRC-39; Section 11.4), and **gate-defined stricter treatment (response) requirements** (CRC-18). The six non-waivable conditions of Section 9.6 cannot be covered. Failing any, the acceptance has no intended effect and remains visible. A finding of that failure is a TRG-6 event only when it meets CRC-59 | GCR-16; PR-10, PR-11, PR-12 | A | I, B, X | UAD4-25, UAD4-26 |
| CRC-23 | A conditional progression authorization records the nine elements of STEP-03 Section 9.2, by a human AUTH-G holder independent of the accepted set, on ground G1 or G2, and states that the unmet requirement remains open. It is not inherited by a later gate and is effective when recorded. It ends only as GCR-42 lists | GCO-21; GCR-42, GCR-43, GCR-44, GCR-48 | A, S | I, B | HJC-14 |
| CRC-24 | An authorization, waiver, exception, confirmation, grant, or closure takes effect when recorded. One recorded after an act does not validate the act. An effective-from earlier than the recording is not honored | GCR-47; UAD3-33 | H | I | DR-03 |
| CRC-25 | A refusal states why. A deferral states what is awaited and from which position. Both are by a human AUTH-G holder for the gate. A defective refusal or deferral has no effect, but it stays visible and is read as a recorded attempt for CRC-18 | GCR-18, GCR-19 | A | I, B | UAD4-21 |

#### Family D. Challenge, disagreement, escalation

| ID | Condition | Sources | Eval | Handling | Pair / deferral / declared |
| --- | --- | --- | --- | --- | --- |
| CRC-26 | A challenge records challenger, target, target scope, and basis. Absent any, it is invalid and visible. Any AUTH-A actor may challenge. A producer's challenge of its own item is recorded and not independent | GCO-12 (part); GCR-23, GCR-24; ACT-03 | A | I, B | HJC-07 |
| CRC-27 | A challenge is closed only by challenger resolution, authority closure, or withdrawal of its target with no successor. A response, supersession, elapsed time, silence, agreement, or a verification does not close. Authority closure is by a human AUTH-G holder independent of the challenged item's accepted set and not the author of a challenged determination | GCO-12 (part); GCR-25, GCR-26 | A | I, B | HJC-07 |
| CRC-28 | A challenge, and any contradicting or qualifying relationship, recorded against an item is carried to its recorded successor and shown as carried | GCO-13; GCR-28 | S | F | HJC-16; DR-05 |
| CRC-29 | Each contribution has its effect: a challenge produces contestation and exposure; source-identified counter-evidence produces a requirement on direct material dependents; a bare contradicting claim or inference produces contestation and exposure, and a requirement only by P1, P2, or P3; qualifying items have no automatic effect; no contribution has no visible effect | GCO-14; GCR-30, GCR-31; EKO-19 (part) | S | F | HJC-16; DR-04; UAD4-08 |
| CRC-30 | A revalidation request is by an actor holding AUTH-A, AUTH-V, or AUTH-G and records requester, dependent, contested or changed item, and a stated basis. Absent any, it creates no requirement | GCO-15; GCR-32; ACT-06 | A | I, B | HJC-16 |
| CRC-31 | An escalation records the escalating actor and capacity, the matter, the resolving authority sought (derived from grants), the reason, and the determination asked for. It closes nothing | GCO-26; GCR-37 | A | I, B | none |
| CRC-32 | Where no identity can satisfy the independence condition of a matter's resolving authority, an authority gap is recorded against the matter. No act by a conflicted holder, collective, agent, evaluator, waiver, elapsed time, or self-conferred grant is treated as a cure | GCO-25; GCR-40 | S | U, E | HJC-12; UAD4-22 |
| CRC-33 | A disagreement is recorded as cleared only by challenger resolution, authority closure, concession with closure or carry-over, or resolution by decision. Elapsed time, silence, absence of objection, headcount, agent agreement, recency, and downstream completion do not clear it | GCR-35 (part), GCR-36, GCR-41; EKR-05, EKR-06 | A | I | HJC-09 |

#### Family E. Provenance, evidence, lineage, configuration

| ID | Condition | Sources | Eval | Handling | Pair / deferral / declared |
| --- | --- | --- | --- | --- | --- |
| CRC-34 | Every item has exactly one recorded class (prior classifications retained), at least one recorded producer identity, and a time | EKO-01, EKO-02; EKR-01, EKR-07 | A | I, B | DR-03 |
| CRC-35 | An item designated material at creation carries the class-specific provenance elements at creation. An item presumed material because a consequential decision or gate acceptance cites it carries them from the citation, unless a non-material designation with rationale is recorded; a designation without rationale is ineffective and the presumption holds. A material claim carries producer, time, and an evidence reference or a visible absence statement | EKO-13, EKO-14; OBJ-05; PR-09; EKR-08, EKR-35; ACT-01; INV-10 | A | I (designated at creation; designation without rationale), F (presumed later) | HJC-03; UAD4-10 |
| CRC-36 | An item recorded as evidence for a target carries the class-defining elements: an identified source that is not solely a concurrence or agreement record (**where the record distinguishes sourced evidence from a concurrence or agreement record**; otherwise the residue is HJC-12 and the remedy is challenge, Section 10.5) and not a resolvable reference to an item by the actor asserting the target; the target and polarity toward it; and, for a negative finding, its attempt record (what, where, when, method, limits). Absent any, the designation as evidence for that target is ineffective and the item is recorded as the class it is | EKO-04, EKO-05 (part), EKO-08; EKR-13, EKR-14 (part), EKR-15, EKR-16, EKR-17; PR-20; INV-11 | A | I, B | HJC-01, HJC-06, HJC-12; DR-06; UAD4-09 |
| CRC-37 | An evidence item records the descriptive elements: category designation (basis kind, and evaluation dimension where relevant), evidence basis, limitations statement ("none identified" is a permitted, challengeable entry), and time recorded with the observation time or period. A shortfall is flagged on the item and in the standing record of any acceptance citing it | EKO-05 (part); EKR-14 (part) | S | F | HJC-02; UAD4-09 |
| CRC-38 | Derived evidence identifies the items it derives from. Evidence items sharing an identified source are identifiable as sharing it. Lineage is recorded at the granularity of Section 11.3 | EKO-06; EKR-11 | A, S | I (derived evidence with no inputs named), F (comparability gap) | HJC-12, HJC-26; DR-06; UAD4-12 |
| CRC-39 | An item or action produced by an AI actor records its producing configuration at facet level (Section 11.2). A facet that cannot be determined is stated as not determinable. Absence of any configuration statement is flagged. Recording configuration confers no independence | EKO-03; EKR-12; PR-27 | A, S | F | HJC-26; UAD4-11 |
| CRC-40 | Evidence, dependency, provenance, basis, and relationship references in an action resolve to recorded items at the evaluation point | OBJ-08; EKR-32 (part), EKR-34 | A | I, B | none |
| CRC-41 | Withdrawal, revision, supersession, invalidation, challenge, acceptance, trigger, and invalid-action events are added to the record. No item, contradiction, or invalid action is overwritten or deleted. Contradicting and challenging items recorded against an item remain resolvable | EKO-07; EKR-05, EKR-09; PR-11 | H | I | DR-03 |

#### Family F. Knowledge-class distinctions, decisions, dependencies, revalidation

| ID | Condition | Sources | Eval | Handling | Pair / deferral / declared |
| --- | --- | --- | --- | --- | --- |
| CRC-42 | Acceptance applies to the item as it stood. Post-acceptance change is recorded as a correction or a supersession. A decision's basis is preserved as of the decision. Later change to a cited item is an event, not an edit to the basis | EKR-10, EKR-31; GCR-20 | H | I | DR-02 |
| CRC-43 | A hypothesis carries recorded validation criteria. A proposition without them is classified and handled as an assumption. Changing between the two is a recorded, attributable reclassification | EKO-09; EKR-21 | A | I (the hypothesis designation), B | HJC-10 |
| CRC-44 | An inference cites at least one evidence item, assumption, or inference; every citation chain reaches an evidence item or an assumption; and the item is not typed as evidence or as observed fact. Derived support is distinguishable from evidential support | EKO-10; EKR-26, EKR-27 | A | I, B | HJC-05; DR-01 |
| CRC-45 | A claim recorded with an evaluative designation is not also recorded under an observed-fact form or as established by evidence alone. **What is checked is the recorded evaluative designation and whether the record presents the claim under an observed-fact or evidence-only form.** Whether the content is in fact evaluative, or the evaluative claim warranted, is not checked (HJC-18) | EKR-28 | S | N | HJC-18; UAD4-32 |
| CRC-46 | A validation is recorded by a human AUTH-G holder for the scope, independent over the validation's accepted set. It states its scope and cites the criteria, the results (favorable or not), and the challenge responses relied on. It is never inferred from accumulation, agreement, elapsed time, absence of objection, completion of dependent work, a verification, or a gate acceptance | EKO-11; EKR-24, EKR-25; GCR-21, GCR-64, GCR-65 | A | I, B | HJC-11 |
| CRC-47 | Reliance on an unvalidated material hypothesis or assumption is marked on every dependency link to it. **The dependent shows its unresolved assumptions wherever it appears.** This is a visibility requirement on any conforming representation (Section 1.6, "visible"); the means of showing it, and any view, are not selected (DR-04; EK-OQ-15). Progression under it is not recorded as validation. Where the reliance is consequential and the commitment is an acceptance, CRC-19 applies. For any other consequential commitment, RJ-OQ-12 | EKO-15; EKR-22 (part), EKR-23; GCR-44 | S | F | HJC-14; DR-04; UAD4-08 |
| CRC-48 | A decision record identifies its basis (or states it has none), its authority basis, and its nature. A consequential decision meets the human, grant, and independence conditions. A record that does not is a recommendation | EKO-16; EKR-29; ACT-07; INV-16 | A | I (re-typed), B | none |
| CRC-49 | A dependency link records dependent, upstream item, kind, materiality designation with its recorder and time, and the link's recorder and time. Removal and re-designation as non-material record a rationale. Citation implies dependency. A dependency change on a decision is a TRG-5 event | EKO-18; EKR-33, EKR-34, EKR-36; TRG-5 | A | I, B | HJC-04 |
| CRC-50 | A challenged non-material designation on a presumed-material item restores the presumption until an independent gate authority holder resolves it. A redesignation or link removal on a standing dependent is treated as still material, for triggers and later accepted sets, until confirmed by a human AUTH-G holder who produced none of the dependent, the upstream item, or the change | GCR-34; EKR-35, EKR-36 | A, S | I (ineffective confirmation), U (while pending) | HJC-04 |
| CRC-51 | Each trigger event (TRG-1, TRG-2 as narrowed, TRG-3, TRG-4, TRG-5, TRG-6) on a material dependency has a corresponding single open requirement on the dependent, with a reason per event. A dependent with an open requirement is not recorded as current without an authorized outcome | EKO-19; GCO-28; OBJ-10; PR-26; EKR-37, EKR-38, EKR-39; GCR-58, GCR-62; TRG-1, TRG-2, TRG-3, TRG-4, TRG-5, TRG-6; INV-12 | S | F (missing requirement), I (currency mark) | HJC-16; DR-04; UAD4-08 |
| CRC-52 | A requirement closes only by reaffirmation, revision, or retirement that meets the tiered authority conditions and whose closure record **names each reason open on the requirement and records a disposition for each**. That presence is what is checked. Whether a disposition adequately addresses its reason is not (HJC-16). No other act, and no passage of time, closes it. Tier 1 reaffirmation is a fresh acceptance over the current accepted set. A requirement is a derived or recorded condition (DR-04) | GCO-20; EKR-38; GCR-59, GCR-60, GCR-61, GCR-63 | A | I | HJC-16; DR-04; UAD4-32 |
| CRC-53 | A gate basis identifies each assumption-rooted item: one whose every support or derivation chain ends only in assumptions or unvalidated hypotheses, derived from recorded classes | GCO-24; GCR-66 | A | F | HJC-10, HJC-14; DR-01; UAD4-18 |
| CRC-54 | **Deferred to representation.** The derived conditions (contested, exposed, open requirement, current validity, disagreement) and the enumeration of dependents and dependencies are derivable from the record, enumerable, attributable, and cleared only by recorded acts | GCO-22; EKR-40; GCR-29, GCR-35 | S | none until DR-04 | DR-04; UAD4-08 |

#### Family G. Correction, supersession, withdrawal

| ID | Condition | Sources | Eval | Handling | Pair / deferral / declared |
| --- | --- | --- | --- | --- | --- |
| CRC-55 | A producer's correction designation on a standing item takes effect only on confirmation by a human AUTH-G holder who is a producer of neither the item nor the change, with notice recorded to the original acceptor and no pending objection. Otherwise the change is treated as supersession for reliance. Later confirmation reclassifies from that point. An overturned designation is supersession as of the change. A non-standing item's designation stands unless challenged | GCO-17; GCR-50, GCR-51, GCR-52 | A | I (the designation), U (while pending) | HJC-13; DR-02 |
| CRC-56 | A change of any of the five kinds in STEP-03 Section 10.3 (criteria changed after results are recorded; reclassification between classes; polarity, target, or source of an evidence item; stated scope of an acceptance, validation, or decision; dependency links or materiality designations) is recorded as supersession whatever its designation says | GCO-18; GCR-53, GCR-65; UAD3-25 | H | I (the correction designation) | HJC-13; DR-02; UAD4-19 |
| CRC-57 | Supersession or invalidation of another actor's item is recorded only by a human AUTH-G holder for the item's scope. Supersession also requires independent acceptance of the replacing item. Reinstatement requires fresh independent acceptance. A producer's own revision, withdrawal, supersession, and retirement need no independent review and erase nothing. Attempts by others are typed as challenge, counter-evidence, or advisory finding | GCO-19; GCR-49, GCR-56; EKR-04 | A | I, B | none |
| CRC-58 | A withdrawal records producer, time, and rationale. The withdrawn item stays recorded and is cited as withdrawn in later decision bases. A requirement created by withdrawn counter-evidence stays open. Withdrawal by fewer than all recorded producers withdraws that producer's endorsement only | GCO-16; GCR-49, GCR-54, GCR-55 | A, S | I (defective withdrawal) | HJC-19 |
| CRC-59 | A finding that an acceptance is invalid, and an acceptor's withdrawal of its own acceptance, are recorded events. Each is the TRG-6 event for what relied on the acceptance. **A CRC-59 finding is a formal-check result (Section 4.10) that names the rule or rules violated, states the evaluation point, and identifies the record elements examined.** A bare assertion that an acceptance is invalid is not a CRC-59 finding and does not trigger TRG-6. It is typed as a challenge, counter-evidence, an advisory finding, or a revalidation request, according to the authority its recorder actually holds. A finding is recorded by an actor holding AUTH-V for the scope or by a human AUTH-G holder. **A non-human AUTH-V holder** may record a CRC-59 finding only where each rule asserted violated is decidable from the record (the bound of CRC-15 (b) and (c)). Where the asserted invalidity depends on interpretation, the non-human output stays advisory or request-like and does not itself trigger TRG-6. **A human AUTH-G holder** states the same three elements but is not limited to that decidability bound where the human is exercising authorized judgment. Any actor holding AUTH-A, AUTH-V, or AUTH-G may in any case request revalidation of the dependents (CRC-30). How findings are recorded and attributed is not selected (DR-09) | GCR-57; TRG-6; UAD3-06 | A | F, E, I (a non-conforming record as a CRC-59 finding; re-typed), B | HJC-16, HJC-24; DR-09; UAD4-07, UAD4-29 |

#### Family H. Authority grants

| ID | Condition | Sources | Eval | Handling | Pair / deferral / declared |
| --- | --- | --- | --- | --- | --- |
| CRC-60 | A grant records grantee (an identity or a role position), authority class, scope, and granting authority (identity and capacity), with a time. Absent any, it is not a grant. It takes effect when recorded, not from an earlier asserted date | PR-02; GCR-47 (extended to grants) | A | I, B | HJC-25; DR-03, DR-08; UAD4-13 |
| CRC-61 | Every grant is either a root grant or is conferred by a human holding AUTH-G whose conferral scope covers the class and scope conferred, as of the conferral. **A project has exactly one establishing act for its authority chain**: a recorded act by an identified human, marked as the establishing act, that precedes every other recorded act of the project. **Root grants are the grants recorded by the establishing act itself, and only those.** Every other grant has an acyclic chain to a root grant, and each link of that chain is effective (recorded, and not revoked or narrowed under CRC-63) at the act that relies on the grant. A later act marked as establishing or as root is not a second root. Any grant it records is an ordinary conferral under this entry. This entry checks that the recorded project-root form exists. It does not decide whether the establishing identity had real-world standing (HJC-22). Establishment practice is DM-03 | PR-01, PR-02, PR-04, PR-05; GCR-40; GCR-47 | A, S | I, B | HJC-22, HJC-25; DR-03, DR-08; DM-03; UAD4-13, UAD4-27, UAD4-30 |
| CRC-62 | **Self-conferral is invalid.** A grant other than a root grant recorded by the establishing act is invalid where its grantee is the conferring identity, or is a collective or role position whose recorded members or appointees include the conferrer, or where its chain returns to the conferrer. This applies to **any later grant**, including a later grant by the establishing identity to itself, to a role position that includes it, to a collective that includes it, or through a cycle returning to it. The establishing identity as a root grantee, **for grants recorded by the establishing act itself**, is not self-conferral under this entry (CRC-61). A **grant-bearing role-position appointment** is a conferral and is evaluated under CRC-61 and this entry. A **work assignment** is provenance and confers nothing (Section 3.3) | GCR-08, GCR-40; GC-OQ-02 | A | I, B | HJC-22, HJC-23; UAD4-14, UAD4-27 |
| CRC-63 | A revocation or narrowing is made by the grantee (renunciation) or by a human holding AUTH-G whose conferral scope covers the grant. It is recorded with a rationale and takes effect when recorded. **Grants downstream of a revoked or narrowed grant fall prospectively with the chain**: those whose CRC-61 chain passes through it, to the extent it no longer covers what they confer. From the recording, they do not validate acts unless independently re-conferred through a valid chain to root. Acts performed while the whole chain was effective are not retroactively invalidated by the later revocation (GCR-47). An act relying on a revoked, narrowed, or fallen grant, recorded after the revocation takes effect, is invalid (CRC-02). Renunciation by the grantee is valid and cascades in the same way. Widening is a new conferral | GCR-47; GC-OQ-02 | A | I | HJC-23; DR-03, DR-08; DM-07; UAD4-15, UAD4-30 |
| CRC-64 | A grant relied on for a favorable act is **flagged**, and the matter is **escalation-eligible**, where **any conferrer along the CRC-61 chain relied on**, from the immediate conferrer up to the root, is a recorded producer of a member of that act's accepted set. A **revocation or narrowing** is likewise flagged and escalation-eligible where it is made by a recorded producer of an item (or of a member of the accepted set the item belongs to) and the grant revoked or narrowed is held by an actor with **standing to challenge** that item or set, **whether or not that actor has a challenge open**. A revocation whose cascade (CRC-63) removes such a grant counts as a revocation of it. Handling is F and E, not I, for this revision. The purpose of the conferral or revocation is HJC-23 | GCR-05 (by analogy), GCR-40; GC-OQ-02 | S | F, E | HJC-23; DP-04; UAD4-14, UAD4-28 |

### 6.3 Classification of every STEP-01 OBJ, STEP-02 EKO, and STEP-03 GCO condition

This table is the explicit classification the work package requires. Primary dispositions are CR (catalogued rule), RJC (recorded-judgment check), and DR (deferred to representation). **No OBJ, EKO, or GCO condition was classified out of catalog.** Two are catalogued only as read together with a later accepted artifact (EKO-15, GCO-28, Section 3.3). One is deferred (GCO-22). The **Note** column gives the paired judgment (HJC) and deferral (DR) references for the entries a row maps to, and short primary notes. Section 8.2 is the complete pairing.

#### STEP-01 OBJ

| ID | Condition (short) | Disposition | Entry | Handling | Note |
| --- | --- | --- | --- | --- | --- |
| OBJ-01 | Every action has one identified acting actor | CR | CRC-01 | I, B | HJC-21; DR-07 |
| OBJ-02 | Actor holds a grant of the required class covering the scope | CR | CRC-02 | I, B | HJC-25; DR-08 |
| OBJ-03 | Acceptor is not a recorded producer | CR | CRC-07 | I, B | HJC-12; Section 10.4 |
| OBJ-04 | Consequential acceptor is a human | CR | CRC-03 | I, B | HJC-21; DR-07 |
| OBJ-05 | Material claim carries provenance | CR | CRC-35 | I, F | HJC-03; timing split, UAD4-10 |
| OBJ-06 | Required independent challenge exists, challenger independent | CR | CRC-12 | I, X | Adequacy is HJC-07; HJC-12 |
| OBJ-07 | Gate-required artifacts and evidence present | CR | CRC-17 | I, X | HJC-01, HJC-02; which are required: DM-01 |
| OBJ-08 | References resolve | CR | CRC-40 | I, B | none |
| OBJ-09 | Non-AUTH-G output not recorded as acceptance or decision | CR | CRC-04 | I, B | HJC-17 |
| OBJ-10 | Decision with an open requirement not recorded as current | CR | CRC-51 | I, F | HJC-16; DR-04 |
| OBJ-11 | Progression preceded by attributable acceptance | CR | CRC-21 | I, B | none |
| OBJ-12 | Waiver or exception record complete and marked | RJC | CRC-20 | I, X | Warrant is HJC-15 |
| OBJ-13 | Verification names its criteria | CR | CRC-05, CRC-13 | I, B | HJC-12 (CRC-13); HJC-24 for a non-human verifier (CRC-15) |

#### STEP-02 EKO

| ID | Condition (short) | Disposition | Entry | Handling | Note |
| --- | --- | --- | --- | --- | --- |
| EKO-01 | One class per item; priors retained | CR | CRC-34 | I, B | DR-03 |
| EKO-02 | Producer(s) and time recorded | CR | CRC-34 | I, B | none |
| EKO-03 | AI-produced item records producing configuration | CR | CRC-39 | F | HJC-26; granularity: Section 11 |
| EKO-04 | Evidence identifies a source; not a concurrence record, **where the record distinguishes sourced evidence from a concurrence or agreement record**; not the actor's own assertion | CR | CRC-36 | I, B | Composite, BDR-03; residue HJC-01, HJC-12; UAD4-09 |
| EKO-05 | Evidence records target, polarity, category, basis, limitations, times | CR | CRC-36, CRC-37 | I (class-defining), F (descriptive) | HJC-02; UAD4-09 |
| EKO-06 | Derived evidence identifies inputs | CR | CRC-38 | I, F | HJC-12, HJC-26; DR-06 |
| EKO-07 | Contradicting and challenging items resolvable and visible | CR | CRC-41 | I | DR-03; views: DR-04 |
| EKO-08 | Negative finding records its attempt | CR | CRC-36 | I, B | HJC-06 |
| EKO-09 | Hypothesis carries validation criteria | CR | CRC-43 | I, B | Adequacy HJC-10 |
| EKO-10 | Inference cites, is grounded, not typed as evidence | CR | CRC-44 | I, B | HJC-05; DR-01 |
| EKO-11 | Validation by an authorized, independent, human acceptor | RJC | CRC-46, CRC-07 | I, B | Substance HJC-11 |
| EKO-12 | Unauthorized validation or invalidation (of a hypothesis or item) not recorded as one | CR | CRC-04 | I, B | HJC-17 |
| EKO-13 | Material items carry class-specific provenance | CR | CRC-35 | I, F | HJC-03; UAD4-10 |
| EKO-14 | Cited items carry a materiality designation or are treated as material | RJC | CRC-35 | I (designation without rationale) | Warrant HJC-03 |
| EKO-15 | Reliance on an unvalidated hypothesis is marked, visible, and authorized | RJC | CRC-47, CRC-19 | F, I | CR part: reliance marks on dependency links (CRC-47). RJC part: the recorded authorization (CRC-19). Visibility: DR-04. HJC-14. Read with STEP-03 Section 9.2 (Section 3.3). Non-acceptance commitments: RJ-OQ-12 |
| EKO-16 | Decision record carries basis, authority basis, nature | CR | CRC-48 | I, B | none |
| EKO-17 | Decision cites opposition and how each stood | RJC | CRC-18 | I, B | Adequacy HJC-07 |
| EKO-18 | Dependency link elements and rationales recorded | CR | CRC-49 | I, B | Warrant HJC-04 |
| EKO-19 | Trigger on a material dependency has an open requirement | CR | CRC-51 | F, I | HJC-16; DR-04; TRG-2 as narrowed (Section 3.3) |
| EKO-20 | Advisory output typed as advisory | CR | CRC-04 | I, B | HJC-17 |

#### STEP-03 GCO

| ID | Condition (short) | Disposition | Entry | Handling | Note |
| --- | --- | --- | --- | --- | --- |
| GCO-01 | Accepted set computable | CR | CRC-06 | I, B | DR-01 |
| GCO-02 | Acceptor is a human holding AUTH-G for the scope | CR | CRC-02, CRC-03 | I, B | HJC-25, HJC-21 |
| GCO-03 | Acceptor produced no member of the accepted set | CR | CRC-07, CRC-09 | I, B | Substance HJC-12 |
| GCO-04 | Gate definition precedes the act; no moved standard | CR | CRC-16 | I, F, X | HJC-20 |
| GCO-05 | Required evidence slots filled; absence statement does not fill | CR | CRC-17 | I, X | Sufficiency HJC-01 |
| GCO-06 | Required challenge exists, independent, treated | CR | CRC-12, CRC-18 | I, X | HJC-07 |
| GCO-07 | Required formal check independently verified | CR | CRC-13, CRC-15 | I, X | HJC-12; HJC-24 (CRC-15) |
| GCO-08 | Every standing-record item cited with a treatment | RJC | CRC-18 | I, B | HJC-07, HJC-08, HJC-09; B conditional on derived exposure (DR-04) |
| GCO-09 | Relied-on unresolved items covered by authorization or closure | RJC | CRC-19 | I, B | HJC-14; B conditional on derived conditions (DR-01, DR-04) |
| GCO-10 | Shortfalls covered by a valid exception; none non-waivable | RJC | CRC-20, CRC-10 | I, X | HJC-15 |
| GCO-11 | Declaration and determination recorded; precedes progression | RJC | CRC-11, CRC-21 | I, B, N | HJC-12 |
| GCO-12 | Valid challenge form; closure of a recognized kind and authority | CR | CRC-26, CRC-27 | I, B | HJC-07; closure kind and authority are validity facets (Section 5.1) |
| GCO-13 | Challenge and relationships carried to successor | CR | CRC-28 | F | HJC-16; DR-05 |
| GCO-14 | Each contribution has its STEP-03 Section 7.3 effect | CR | CRC-29 | F | HJC-16; DR-04 |
| GCO-15 | Request records its stated basis | CR | CRC-30 | I, B | HJC-16 |
| GCO-16 | Withdrawal records producer, time, rationale; effects persist | CR | CRC-58 | I | HJC-19 |
| GCO-17 | Correction confirmed independently, notice recorded | RJC | CRC-55 | I, U | HJC-13; receipt not checkable |
| GCO-18 | Five kinds of change recorded as supersession | CR | CRC-56 | I | HJC-13; DR-02 |
| GCO-19 | Acts on another actor's item only by authorized human | CR | CRC-57 | I, B | none |
| GCO-20 | Single requirement record; closure addresses every reason | RJC | CRC-52, CRC-51 | I, F | HJC-16; the closure's reason-addressing record is content-bearing (Section 5.1) |
| GCO-21 | Conditional progression authorization has its nine elements | RJC | CRC-23 | I, B | HJC-14 |
| GCO-22 | Exposure is derivable | DR | CRC-54 | none until DR-04 | Representation conformance property |
| GCO-23 | Producer sets append-only | CR | CRC-14 | I, U | HJC-12 |
| GCO-24 | Assumption-rooted basis items identified | CR | CRC-53 | F | HJC-10, HJC-14; DR-01; GC-OQ-11 |
| GCO-25 | Authority gap recorded; no purported cure | CR | CRC-32 | U, E | HJC-12 |
| GCO-26 | Escalation records its elements | CR | CRC-31 | I, B | none |
| GCO-27 | Advisory outputs typed; not recorded as acts | CR | CRC-04 | I, B | HJC-17 |
| GCO-28 | Trigger of any kind on a material dependency has an open requirement | CR | CRC-51 | F, I | HJC-16; DR-04; TRG-2 as narrowed (Section 3.3); includes TRG-6, which a CRC-59 finding triggers only when it meets CRC-59 |

### 6.4 What the catalog is not

- It is not a validator specification. No entry says how a check is run, by what, or when.
- It is not a state vocabulary. "Open requirement," "contested," "exposed," "standing," and "current" are semantic conditions named in prose.
- It is not a conformance claim for any representation. DR-04 and the others say what a representation must make answerable. They do not say how.

### 6.5 Accepted rules that produce no per-record entry

Some accepted rules are definitions, constraints on any representation, duties whose breach is not detectable from a record, or statements enforced through other entries. They are listed with a reason so that none is silently dropped.

| Rule | Why no per-record entry | Where its force lies |
| --- | --- | --- |
| PR-12, GCR-20 (first sentence) | Acceptance concerns sufficiency, not truth. This limits what an acceptance means. It is not a checkable condition | HJC-01; CRC-21, CRC-22 |
| PR-24 | The two Moderator roles are distinct. Distinctness is enforced by CRC-02: authority comes only through grants | CRC-02 |
| PR-25, EKR-02, EKR-19 | Constraints on any representation and on how conditions are named. They are not per-record conditions | BDR-07, BDR-11, BDR-14; STEP-05 conformance (DR-04) |
| EKR-06 | No inference is elevated by headcount or agreement. The clearing of disagreement is checked; the "weighing" is judgment | CRC-33; HJC-09 |
| EKR-18 | The duty to record contradicting information an actor holds. Breach is not detectable from a record that lacks the information. It is detectable when the information surfaces | CRC-18 (once recorded); challenge; Section 1.4 |
| EKR-22 (first part) | Every assumption is recorded and visible. An unrecorded assumption is not detectable | CRC-47 (recorded ones); HJC-10 |
| EKR-41 | Restates the boundary rule for EKO. Restated and enforced through BDR-05 and BDR-14. The accepted rule is preserved, not changed (Section 3.1) | BDR-05, BDR-14 |
| GCR-27 | Defines unanswered and unresolved without clocks. A definition | CRC-27, CRC-33 |
| GCR-67 | Time never acts. Enforced through the entries that would be the vehicle of a time effect | CRC-04, CRC-27, CRC-33, CRC-52 |

### 6.6 Deferred register

#### Deferred to representation (STEP-05)

| ID | What is deferred | Needed by | Routing |
| --- | --- | --- | --- |
| DR-01 | Computation of the accepted-set closure, citation-chain grounding, and assumption-rooted derivation | CRC-06, CRC-19, CRC-44, CRC-53 | GC-OQ-04 |
| DR-02 | Item identity across change: how a successor, a correction, and a never-correction change are related to the item they change | CRC-42, CRC-55, CRC-56 | EK-OQ-12; GC-OQ-04 |
| DR-03 | Record order, effective-from-recording, and history preservation. Includes the ordering by which the establishing act precedes every other recorded act | CRC-24, CRC-34, CRC-41, CRC-60, CRC-61, CRC-63 | RJ-OQ-01 |
| DR-04 | Derived conditions and dependency enumeration; whether derived or stored. Where a derived condition (exposure, open requirement, assumption-rooted status) is an input to a B-tagged rule, whether the representation makes it available at the evaluation point. Visibility of unresolved assumptions on the dependent (CRC-47) is a semantic requirement on any conforming representation. How it is made visible is this item's to decide | CRC-18, CRC-19, CRC-29, CRC-47, CRC-51, CRC-52, CRC-54 | EK-OQ-11; EK-OQ-15; GC-OQ-04 |
| DR-05 | Whether carry-over is derived or stored | CRC-28 | GC-OQ-04 |
| DR-06 | Source identity comparability: how two sources are determined to be the same | CRC-36, CRC-38 | RJ-OQ-10 |
| DR-07 | Attribution integrity, actor-kind designation, and authentication | CRC-01, CRC-03 | RJ-OQ-02 |
| DR-08 | Scope vocabulary, scope containment, and grant-chain reconstruction as of a point in time, including which downstream grants have fallen with a revoked or narrowed link (CRC-63) | CRC-02, CRC-60, CRC-61, CRC-63 | RJ-OQ-04 |
| DR-09 | How formal-check results and findings are recorded and attributed. The content a CRC-59 finding must state (rules violated, evaluation point, record elements examined) is fixed semantically by CRC-59. How it is recorded and attributed is not | Section 9.4; CRC-15, CRC-59 | RJ-OQ-03a |
| DR-10 | Evaluation-point semantics: act-time versus standing evaluation | Section 4.1, 5.4 | RJ-OQ-01 |

#### Deferred to methodology (STEP-06)

| ID | What is deferred | Needed by | Routing |
| --- | --- | --- | --- |
| DM-01 | Evidence categories, thresholds, and gate-slot contents by product category | CRC-17 | GC-OQ-06; EK-OQ-01 |
| DM-02 | Role positions and who holds gate-definition, validation, and conferral scopes | CRC-61 | GC-OQ-06 |
| DM-03 | Practice for project establishment and root grants. STEP-04 decides the protocol effect (one establishing act, first, whose own grants are the roots; CRC-61). STEP-06 owns how a project carries out establishment | CRC-61 | RJ-OQ-05 |
| DM-04 | Independence, work-assignment disclosure, and the substance test for teams of one or two | CRC-07, CRC-11 | GC-OQ-07 |
| DM-05 | Conventions for stating producing configuration, including "not determinable" and what counts as instructions | CRC-39 | RJ-OQ-05 |
| DM-06 | Guidance on designating formal-check criteria as decidable from the record | CRC-15 | RJ-OQ-05 |
| DM-07 | Grant review practice and role rotation, including re-conferral after a revocation or renunciation cascades downstream | CRC-63 | RJ-OQ-05 |
| DM-08 | Guidance on stating the required content of a formal-check result or finding (rules violated, evaluation point, record elements examined) and on typing a bare assertion as a challenge, counter-evidence, advisory finding, or request | CRC-15, CRC-59 | RJ-OQ-03b |

#### Deferred to pilot (STEP-07)

| ID | What needs evidence | Routing |
| --- | --- | --- |
| DP-01 | Burden of detection: flag volume, false positives, effort to record treatments, configuration recording burden | GC-OQ-08; RJ-OQ-06 |
| DP-02 | Whether blocking-eligible rules are better blocked or detected-and-flagged in use | RJ-OQ-06 |
| DP-03 | Whether authorizations or grants need protocol-effective terms | GC-OQ-09; RJ-OQ-07 |
| DP-04 | Strength of handling for conflicted conferral and revocation (flag and escalation, F/E, versus invalidating, I). **Evidence sought:** adversarial or near-adversarial cases of proxy conferral, ancestor-chain conflict (a conflicted conferrer upstream of the grant relied on), and challenger-standing suppression (revocation or narrowing of a challenger's grant before a challenge is recorded). **Trigger for reconsidering F/E versus I:** observed use, or plausible rehearsal, showing that a flagged conflicted conferral or revocation can materially enable a favorable acceptance or suppress challenge standing before review. **Pilot owner: STEP-07.** Targeted Tech Lead review of the pilot evidence is a review need before any strengthening is proposed. The Tech Lead is not a step owner. A strengthening is an accepted revision of this artifact (BDR-16) | RJ-OQ-09 |
| DP-05 | Adequacy of the five never-a-correction kinds and of any classification in this artifact | RJ-OQ-08; RJ-OQ-11 |
| DP-06 | Whether non-human verification is adopted and its effect | RJ-OQ-06 |

---

## 7. Human Judgment Catalog

Operationalizes D6, HA-1, HA-2. Resolves the judgment half of **GC-OQ-01**.

### 7.1 How to read the catalog

Each entry is a **derived grouping over accepted judgment IDs**: judgments that decide the same kind of question are listed once, and the sources are named so none is lost (Section 15.2). Six entries (HJC-21 to HJC-26) name judgments the accepted artifacts left implicit at the edge of a check; they are **derived** from this step's classification work and are declared (UAD4-24).

"Exercised by" states who holds the judgment, using accepted authority. Where an actor without AUTH-G may record the same kind of content, it is a designation or advisory finding (Section 4.4), not the determination.

### 7.2 The catalog

| ID | Judgment | Sources | Exercised by | Why it is judgment |
| --- | --- | --- | --- | --- |
| HJC-01 | Whether evidence and the gate basis are relevant to, sufficient for, and persuasive for the target and scope, including whether evidence age matters | HJ-01; EKJ-02; GCJ-01, GCJ-13 | The acceptor (human AUTH-G); validation by the independent human AUTH-G | Requires interpreting what the evidence shows about the world |
| HJC-02 | Whether an evidence item's category designation, basis, and limitations statement are adequate and complete | EKJ-03 | The acceptor; any AUTH-A actor may challenge | Adequacy of a description |
| HJC-03 | Whether a claim, hypothesis, assumption, or inference is material | HJ-02; EKJ-01 | The recorder of the designation (human or non-human, AUTH-P or AUTH-A); a disputed non-material designation is resolved by an independent human AUTH-G | Depends on the decision, promise, or investment the item bears on |
| HJC-04 | Whether a dependency should be designated material, is missing, or a redesignation is warranted | EKJ-10; GCJ-07 | The recorder; disputes by an independent human AUTH-G | Whether a change upstream would put the dependent in question |
| HJC-05 | Whether an inference is warranted by what it cites | HJ-03; EKJ-05 | The acceptor; any AUTH-A actor may challenge | Warrant of a reasoning step |
| HJC-06 | Whether a recorded attempt is adequate to support an absence inference | EKJ-08 | The acceptor | Adequacy of a search or test to find what it looked for |
| HJC-07 | Whether a response adequately answers a challenge, and whether a challenge stands | HJ-04; EKJ-12 (part); GCJ-02 | The challenger (resolution); a human AUTH-G independent of the set (authority closure) | Adequacy of an answer |
| HJC-08 | Whether residual disagreement or residual risk is acceptable for the gate | HJ-05; EKJ-12 (part), EKJ-14 (part); GCJ-03 | The acceptor | Acceptability of risk |
| HJC-09 | Whether disagreement is sufficiently resolved to proceed, and which position to act on | HJ-08; EKJ-12 (part) | The acceptor; resolution by decision by an independent human AUTH-G | Sufficiency of resolution |
| HJC-10 | Whether a proposition is a testable hypothesis or an assumption, and whether recorded criteria are adequate | HJ-06; EKJ-06; GCJ-12 (part) | The producer designates; the acceptor or a challenger assesses | Testability and adequacy of criteria |
| HJC-11 | Whether a hypothesis's required criteria are satisfied, what scope a validation covers, and whether to accept validation | EKJ-07; GCJ-12 (part) | A human AUTH-G independent over the validation's accepted set | Sufficiency of evidence against criteria |
| HJC-12 | Substantive independence of sources, producers, challengers, evaluators, and verifiers beyond identity distinctness, including whether an assigner supplied substance, undisclosed relationships, shared lineage nobody recorded | HJ-07; EKJ-04; GCJ-09 | The acceptor declares; any AUTH-A actor may challenge; an independent human AUTH-G resolves a dispute | Two identities may be one person; a source may share an unrecorded origin |
| HJC-13 | Whether a revision alters meaning (correction or supersession), outside the five never-a-correction kinds | EKJ-09; GCJ-06 | An independent human AUTH-G confirmer | Whether meaning changed |
| HJC-14 | Whether conditional progression is warranted | HJ-09; GCJ-04 | The authorizer (human AUTH-G independent of the set) | Warrant of proceeding under an unresolved condition |
| HJC-15 | Whether a waiver or exception is warranted | GCJ-05 | The exception-giver (human AUTH-G independent of the set) | Warrant of dispensing with a requirement |
| HJC-16 | Whether a trigger, a bare contradiction, a qualifying item, or evidence age undermines a dependent, and whether the outcome is reaffirmation, revision, or retirement | HJ-10; EKJ-11; GCJ-08 | The requester (request); the closer by tier | Whether the dependent survives the change |
| HJC-17 | What weight an advisory finding or evaluator output deserves | EKJ-13; GCJ-11 | The acceptor | Weight is a sufficiency question |
| HJC-18 | Whether content is evaluative, and whether an evaluative claim is warranted | EKJ-14 (part); EKR-28 | The acceptor | Whether a statement is a value judgment |
| HJC-19 | Whether a withdrawal's rationale is genuine | GCJ-10 | A challenger; the closer | Whether a stated reason is the real one |
| HJC-20 | Whether a gate definition's slots are adequate for the product category | GCJ-14 | The gate definer; later challengers | Adequacy of a standard |
| HJC-21 | **Derived.** Whether a recorded attribution or actor-kind designation is accurate: that an act recorded under an identity was in substance performed by it, and that an identity designated human is a human | The limits of CRC-01, CRC-03 | A challenger (target: validity of the act); authority closure | A check applies the record. It cannot decide whether the record describes who acted |
| HJC-22 | **Derived.** Whether the establishing act, and so its root grants, legitimately establishes the project's authority, including whether the establishing identity had real-world standing to do so | The limits of CRC-61, CRC-62 | Outside the record (project establishment); recorded as root | Root legitimacy is a fact about the world the protocol cannot check |
| HJC-23 | **Derived.** Whether a conferral (at any link of the chain), revocation, or narrowing was done to enable or defeat a particular act, or to suppress a challenger's standing | The limits of CRC-62, CRC-63, CRC-64 | A challenger; an independent human AUTH-G | Purpose is not in the record |
| HJC-24 | **Derived.** Whether a named formal-check criterion, or a rule asserted violated in a non-human CRC-59 finding, is decidable from the record without interpretation | GCR-11 (applied to CRC-15 and, for non-human findings, CRC-59) | The gate definer records the designation; any AUTH-A actor may challenge | The decidability test (BDR-01) applied to a particular criterion |
| HJC-25 | **Derived.** Whether a scope stated without resolvable references contains another scope, and whether a stated scope is the right one | The limits of CRC-02, CRC-60, CRC-61 | The conferrer designates; a challenger disputes | Containment of descriptions requires interpretation |
| HJC-26 | **Derived.** Whether recorded producing configuration and lineage are adequate for weighing an item | EK-OQ-09 (applied to CRC-38, CRC-39) | The acceptor | Adequacy of provenance is a sufficiency question |

---

## 8. Paired Objective-Check / Human-Judgment Table

Operationalizes D6.

### 8.1 How the pairs work

For every judgment, the **paired objective check** is the mechanical fact that can support it. It never decides it (STEP-01 Section 9.3). Each pair says which recorded-judgment **facets** (Section 4.5) are confirmed, and what remains judgment.

### 8.2 The pairs

| Judgment | Paired entries | What the check confirms | What stays judgment |
| --- | --- | --- | --- |
| HJC-01 | CRC-17, CRC-35, CRC-36, CRC-37 | Required items are present with the required designations; recorded observation times meet a gate-defined recency criterion | Whether the evidence is relevant, sufficient, persuasive; whether age matters |
| HJC-02 | CRC-36, CRC-37 | The category, basis, limitations, and time elements exist | Whether they are adequate and complete |
| HJC-03 | CRC-35 | A designation exists, or the item is treated as material; a non-material designation has a rationale | Whether the item is material |
| HJC-04 | CRC-49, CRC-50 | Links and designations are recorded; a redesignation is confirmed by a qualified independent human | Whether the dependency should be material or is missing |
| HJC-05 | CRC-40, CRC-44 | Citations exist and resolve; chains are grounded; the item is not typed as evidence | Whether the inference is warranted |
| HJC-06 | CRC-36 | The attempt record (what, where, when, method, limits) exists | Whether the attempt could have found what it looked for |
| HJC-07 | CRC-12, CRC-18, CRC-26, CRC-27 | A challenge exists and is well-formed; a treatment is recorded; a closure is of a recognized kind by a qualified closer | Whether the response is adequate; whether the challenge stands |
| HJC-08 | CRC-18 | A treatment "accepted as residual" is recorded by the acceptor | Whether the residual risk or disagreement is acceptable |
| HJC-09 | CRC-18, CRC-33 | Unresolved challenges and contradictions are present and cited; clearing was by a recognized act | Whether disagreement is resolved enough to proceed |
| HJC-10 | CRC-43, CRC-53 | Validation criteria exist; assumption-rooted items are identified from recorded classes | Whether the proposition is testable; whether criteria are adequate |
| HJC-11 | CRC-46, CRC-07 | The validator is a human with authority, independent; scope, criteria, results, and responses are cited | Whether the criteria are met; whether to validate |
| HJC-12 | CRC-07, CRC-11, CRC-12, CRC-13, CRC-14, CRC-32, CRC-36, CRC-38 | Identities are distinct; the declaration exists; work-assignment relations are recorded; lineage is identified where recorded | Whether the distinct identities are substantively independent; unrecorded lineage |
| HJC-13 | CRC-55, CRC-56 | Designation exists, is attributed, retained; confirmed independently; never-a-correction kinds are recognized | Whether meaning changed, outside the five kinds |
| HJC-14 | CRC-19, CRC-23, CRC-47, CRC-53 | The authorization is complete and recorded before the acceptance; reliance is marked | Whether proceeding is warranted |
| HJC-15 | CRC-20 | The exception record is complete and marked; independence holds; no non-waivable condition is waived | Whether the exception is warranted |
| HJC-16 | CRC-28, CRC-29, CRC-30, CRC-51, CRC-52, CRC-59 | The effect classification applies; the requirement exists with its reasons; a closure meets authority conditions and names each open reason with a recorded disposition; a finding of an invalid acceptance names the rule, evaluation point, and elements examined | Whether the change undermines the dependent; whether a disposition adequately addresses its reason; the outcome |
| HJC-17 | CRC-04 | The output is typed as advisory | What weight it deserves |
| HJC-18 | CRC-45 | An evaluative designation exists and the record does not present the claim under an observed-fact or evidence-only form | Whether content is evaluative; whether it is warranted |
| HJC-19 | CRC-58 | A rationale is recorded | Whether the rationale is genuine |
| HJC-20 | CRC-16 | A gate definition exists before the act | Whether its slots are adequate |
| HJC-21 | CRC-01, CRC-03 | An identity and an actor-kind designation are recorded | Whether they are accurate |
| HJC-22 | CRC-61, CRC-62 | A single establishing act is recorded, precedes every other recorded act, and records the root grants. The root-grantee case is limited to that act | Whether the establishing act is legitimate; whether the establishing identity had real-world standing |
| HJC-23 | CRC-62, CRC-63, CRC-64 | Later self-conferral is detected; the producer-of-set relation is flagged along the whole chain; a conflicted revocation or narrowing affecting a challenger's standing is flagged | The purpose of the conferral or revocation |
| HJC-24 | CRC-15, CRC-59 | A checkability designation is recorded for each criterion; a non-human finding states the elements examined and the evaluation point | Whether the criterion, or a rule asserted violated, is decidable from the record |
| HJC-25 | CRC-02, CRC-60, CRC-61 | Scope references resolve; containment is decided where scopes are references | Containment of scopes stated by description |
| HJC-26 | CRC-38, CRC-39 | A configuration statement and lineage identification exist | Whether they are adequate for weighing the item |

### 8.3 Judgments with no pair

None. STEP-01 listed HJ-05 as having no paired check. STEP-03 GCJ-03 paired the residual-risk judgment with GCO-08 (a treatment is recorded), and CRC-18 carries that pairing (Section 3.3). The pair confirms that a treatment exists. It says nothing about whether the risk is acceptable.

### 8.4 How a pair must not be read

- A satisfied check is not a partial verdict on its judgment. A fully present evidence item may be irrelevant. A recorded declaration may be false. A well-formed challenge may be poor.
- A violated check does not decide the judgment either way. A missing limitations statement is flagged. It does not show the evidence is weak.
- The number of satisfied checks is not a measure of sufficiency (BDR-14).

---
## 9. Violation-Handling Semantics

Operationalizes D6, D8; FR-4. Resolves **PS-OQ-10** and the handling half of **GC-OQ-01** and **EK-OQ-14**. Handling is semantic. This section selects no validator, enforcement mechanism, user interface, schema keyword, or workflow engine.

### 9.1 Two layers

Two questions are easily run together.

- **What does the violation do to protocol effect?** This is fixed by accepted semantics. An implementation does not choose it.
- **What must or may a detection do?** This is the handling category. It governs visibility, routing, and prevention. It never changes the first answer.

**Protocol consequence (fixed by source rules).**

| Consequence | Meaning | Source |
| --- | --- | --- |
| **Invalidity** | The act lacks its intended effect from the outset and stays visible as invalid | PR-10, PR-11; GCR-16 |
| **Ineffective designation** | A designation, typing, or classification has no effect. The item is treated as what it is | EKR-04, EKR-13, EKR-21; GCR-52, GCR-53 |
| **Unsatisfied gate requirement** | A requirement of the gate definition is unmet. The acceptance is invalid unless a valid exception covers it, and non-waivable conditions can never be covered | STEP-03 Section 5.4, 9.4 |
| **Non-conformance without invalidity** | An obligation is unmet. The act keeps its effect. The shortfall is visible and cited | EKR-14; GCR-66 |
| **Conservative default pending determination** | Until an authorized determination, the cautious reading applies | GCR-07, GCR-34, GCR-52 |

### 9.2 Handling categories

| Category | Meaning | Must | May | Must not |
| --- | --- | --- | --- | --- |
| **I. Invalidating** | The detection recognizes that the act lacked, or the designation lacks, its intended effect | Never be presented as having effect. Stay visible as invalid or ineffective. Be recorded as the event the source rule names (for an invalid acceptance, a CRC-59 finding, which is the TRG-6 event) | Be recognized at the act or later | Erase the record. Be treated as a decision about substance |
| **B. Blocking candidate** | The rule is act-time and all its inputs are in the record, so a conforming practice could prevent _reliance_ on the act before anyone relies on it. An invalid act never has effect whether or not it is blocked (Section 9.1). Blocking does not give it effect otherwise | Record the attempt as visible and invalid | Prevent reliance on the act | Prevent the _record_ of the attempt (BDR-09). Prevent a challenge, counter-evidence, withdrawal, retirement, request, escalation, refusal, or deferral from being recorded (BDR-10). Decide substance |
| **F. Flagging** | The condition is made visible to reviewers and to those who rely on the item. The act keeps its effect | Show the flag wherever the item appears, and in the standing record of any acceptance citing it where the entry says so. Keep it until a recorded act cures it | Surface it in any view | Clear it by elapsed time, silence, or absence of objection. Change the item's effect |
| **E. Escalating** | The matter needs a determination by a particular authority. The detection routes it there | Make an escalation record (STEP-03 Section 8.4, CRC-31) by an actor entitled to make one. Where the detector holds no applicable grant, surface the result so a human with one may escalate | Be made by an automated actor holding an applicable grant | Close, resolve, or decide the matter |
| **U. Recorded as unresolved** | The condition cannot be decided from the record, and accepted semantics give no interim default | Record it as unresolved and keep it visible. Draw no conclusion | Become decidable when the missing element or determination is recorded | Be cleared by time. Be reported as satisfied or violated |
| **X. Visible exception** | A shortfall of a waivable gate requirement is covered by a valid exception | Report the result as _satisfied under exception_, distinct from satisfied. Keep the marker visible wherever the acceptance is cited | Be raised only with the content CRC-20 requires | Cover a non-waivable condition. Be recorded after the act and relied on retroactively (CRC-24) |
| **N. No automated conclusion** | The entry has a judgment residue | Report presence or absence of the recorded element only | Surface the residue for a human | Report sufficient, insufficient, adequate, acceptable, warranted, or independent in substance. Convert the residue into a score, grade, weight, or confidence value |

Categories combine. An invalid acceptance is **I** and, once found in a finding that meets CRC-59, also **F** to dependents (through TRG-6) and **E** toward an authority able to reaffirm.

### 9.3 Handling-assignment principles

Each catalog entry's handling follows from its source, not from a preference.

| Principle | Handling |
| --- | --- |
| The source makes the condition part of action validity: authority, attribution, required content, independence, a gate validity condition (PR-10; GCR-16) | **I**, and **B** if act-time with inputs in the record |
| The source makes a gate requirement unmet, and the requirement is waivable | **I** for the acceptance, with **X** available |
| The source states an obligation or a visibility condition without making the act invalid | **F** |
| The source supplies a conservative default pending a determination | The default applies. **U** records the pending matter |
| The matter needs a determination by a particular authority | **E** |
| The entry has a judgment residue | **N** on the residue |
| The detection concerns a conservative or opposition act | Never prevented from being recorded (BDR-10) |

Section 3.3 lists the three places where the handling assignment is a declared choice (UAD4-09, UAD4-10, UAD4-11): the class-defining versus descriptive split of evidence elements, the timing of presumed materiality, and producing configuration.

### 9.4 Detection, protocol effect, and the standing of detection results

#### 9.4.1 Invalidity does not depend on detection

An invalid act does not produce its intended effect. It does not become valid because nobody noticed. It does not become invalid because someone noticed. The record of the attempt stays visible (PR-11). Discovery is a recorded event that starts the consequences the source rules attach to _finding_ (TRG-6, through a finding that meets CRC-59), not a moment at which the act becomes invalid (STEP-03 Section 4.7).

#### 9.4.2 What "no intended effect" withholds

| Act or designation | What does not happen | What stays visible |
| --- | --- | --- |
| Acceptance | Progression is not authorized. Dependents that relied on it are given TRG-6 on a finding that meets CRC-59 | The attempt, as invalid |
| Refusal or deferral, defective | Nothing about progression changes. The record has no effect of its own | The attempt, read as recorded for CRC-18 |
| Challenge, invalid form | No contestation or exposure arises | The attempt, as invalid |
| Closure, purported | The challenge or requirement stays open | The attempt, as invalid |
| Request, invalid form | No requirement arises | The attempt, as invalid |
| Grant, invalid | No authority is conferred. Acts under it fail CRC-02 | The attempt, as invalid |
| Correction designation, ineffective | Acceptance is not inherited. The change is a supersession for reliance | The designation and the change |
| Evidence designation, ineffective | The item is not evidence for that target | The item, as the class it is |
| Waiver or exception, ineffective | The requirement stays unsatisfied | The attempt |
| Withdrawal, defective | The item is not withdrawn | The attempt |
| Validation, invalid | The hypothesis is not validated | The attempt |
| Verification, non-conforming | The gate-required check is not satisfied. The output is an advisory finding | The output, typed advisory |
| Conditional progression authorization, invalid | Reliance stays uncovered | The attempt |
| Currency mark on a dependent with an open requirement | The dependent is not recorded as current | The mark, as invalid |

#### 9.4.3 Detection results

A detection result is a **formal-check result** (Section 4.10). It is produced by any actor, human or non-human, or by a representation's own enforcement.

- It is **advisory**. It informs reviewers. It does not itself change protocol effect, because the effect was fixed by the source rule (BDR-08, BDR-13, BDR-17).
- It gains **additional standing** only in two cases: when it is relied on to satisfy a gate-required formal check, in which case the producing actor must hold AUTH-V and CRC-13 and CRC-15 apply; and when it is recorded as a **finding that an acceptance is invalid** (CRC-59), in which case the producing actor must hold AUTH-V for the scope or be a human holding AUTH-G, and the finding must name the rule or rules violated, state the evaluation point, and identify the record elements examined. A bare assertion has no such standing (Section 9.4.5). The decidability bound of CRC-15 governs a non-human finding.
- It is **challengeable**. A dispute about whether the record supports a detection is a dispute about the validity of an act (GCR-23). It is resolved by authority closure under GCR-26. A pending challenge does **not** suspend TRG-6, in line with EKR-39: effects do not wait for adjudication. A finding that proves wrong is answered by reaffirmation under CRC-52.
- It confers **no independence and no corroboration**. Two detectors agreeing is agreement (PR-20). A detector that is a producer of the checked item is a producer for CRC-13.
- It is **record-relative**. A result of "satisfied" says the record shows the condition. It does not say the record is complete or accurate (BDR-06).

#### 9.4.4 Blocking

Blocking is the semantic possibility of preventing **reliance** on an act that is invalid. An invalid act never has effect, blocked or not (Section 9.1). Blocking is not a mechanism and not a requirement. It matches D6, which leaves block-or-flag to the implementation. This artifact adds three constraints that any practice of blocking must respect.

1. Blocking may prevent **reliance**, never the **record**. The attempt is recorded and visible as invalid (BDR-09).
2. Blocking never prevents the recording of an opposition or conservative act, even a malformed one. A malformed challenge is recorded and visible as invalid (BDR-10; GCR-23).
3. Blocking does not decide substance. A rule is blockable only because its answer is in the record (BDR-01, Section 5.4).

#### 9.4.5 The finding of an invalid acceptance

STEP-03 Section 4.7 makes "an acceptance on which a dependent relied is found invalid, or withdrawn by its acceptor" the TRG-6 event, without saying who finds or what a finding contains. CRC-59 answers both.

- **Who.** A finding is recorded by an AUTH-V holder or a human AUTH-G holder. Any AUTH-A, AUTH-V, or AUTH-G actor may in any case raise a request for the dependents (GCR-31, route P3).
- **What it contains.** A CRC-59 finding is a formal-check result (Section 4.10) that names the rule or rules violated, states the evaluation point, and identifies the record elements examined. This is the reproducible basis that makes its TRG-6 effect proportionate. A **bare assertion** that an acceptance is invalid is not a CRC-59 finding and does not trigger TRG-6. It is typed as a challenge, counter-evidence, an advisory finding, or a revalidation request, according to the authority the recorder actually holds.
- **Non-human recorders.** The CRC-15 decidability bound governs. A non-human AUTH-V holder may record a CRC-59 finding only where each rule asserted violated is decidable from the record, and the finding states the elements examined and the evaluation point. Where the asserted invalidity depends on interpretation, the output stays advisory or request-like and does not itself trigger TRG-6.
- **Human AUTH-G recorders.** A human holding AUTH-G states the same three elements. The human is not limited to the non-human decidability criteria where the human is exercising authorized judgment.
- **Recording.** DR-09 still owns how findings are recorded and attributed. This section fixes content semantically and selects no representation.

The choice is declared (UAD4-07, UAD4-29). It adds no authority class. It does mean a mechanical detection of invalidity, recorded by a checker that holds AUTH-V and meets the bound, creates a requirement on dependents. That is consistent with this boundary: the detection decides validity of an act from the record, not sufficiency, and the requirement it creates is closed only by a human (CRC-52). Section 10.6 keeps the cost of a mistaken finding visible.

### 9.5 Fail-closed, defaults, and unresolved

| Situation | Treatment |
| --- | --- |
| The source rule makes a record element a validity condition, and it is absent | **Violation** (I). An acceptance whose accepted set cannot be computed is invalid (CRC-06). Absence is never read as satisfaction (BDR-06) |
| The source supplies a conservative default pending a determination | The default applies, and the pending matter is recorded as unresolved (U). Examples: a disputed attribution (CRC-14), a challenged non-material designation or an unconfirmed redesignation (CRC-50), an unconfirmed correction designation (CRC-55) |
| Neither applies, and the answer cannot be decided from the record | Recorded as **unresolved** (U). No conclusion. No clock |
| A given representation cannot compute the answer | The condition is **not** thereby satisfied. The requirement stays, and falls to human review until the representation supplies the computation (BDR-07, DR items) |

### 9.6 Visible exception

A waivable gate requirement that is unsatisfied may be covered by a recorded exception with the content CRC-20 requires. The check result is then **satisfied under exception**, which is a distinct result. The exception marker travels with the acceptance and is visible wherever it is cited (GCR-45).

**Which requirements are waivable.** A gate requirement waivable under STEP-03 Section 9.4 can be covered by a valid CRC-20 exception. That includes gate-required slots, challenges, and formal checks, gate-required configuration facets (Section 11.4), and gate-defined stricter treatment (response) requirements. A condition in the list below cannot (CRC-22).

Not coverable by any exception (GCR-46; CRC-10, CRC-20):

1. independence over the accepted set;
2. human, explicit, attributable authorization by an actor holding AUTH-G;
3. citation of the standing record and recording of treatments;
4. the visibility of the exception itself;
5. the decision record's identification of its nature and authority basis;
6. the FR-7 conditions where a material hypothesis is relied on.

A shortfall covered this way is reported as satisfied under exception and stays visible (BDR-15; declared: UAD4-26). CRC-13 has two parts. That the verifier be independent of the verified item is a gate requirement and is waivable. That the acceptor did not perform the verification it relies on follows from CRC-07 and is not waivable.

### 9.7 No automated conclusion

An entry with handling **N** reports one of: the recorded element is present, or absent. It never reports a verdict on the residue. A fully populated evidence item is not "good evidence." A recorded independence declaration is not "independence." A present rationale is not "adequate."

No handling produces a confidence score, numeric sufficiency weight, grade, or any figure that implies a judgment was decided (BDR-14; EKR-19; GR-4; PE-4). Uncertainty is carried by the visible conditions the catalog flags: limitations statements, challenges, counter-evidence, "not determinable" facets, and unresolved conditions.

### 9.8 What mechanical detection may never do

Detection **may** block, flag, escalate, record as unresolved, or show invalidity, at the semantic level. It **must not**:

- decide a contextual judgment, present one as decided, or convert one into a score;
- replace human gate acceptance, or make a gate accepted because every check passes (PR-13: structural completeness is never acceptance);
- close a challenge, a requirement, or a disagreement;
- promote an advisory finding into acceptance, a decision, validation, or progression (PR-15, PR-22, PR-23);
- treat agreement among detectors, models, or configurations as evidence or independence (PR-20, PR-28);
- establish protocol validity from structural validity (PR-25).

### 9.9 Invalid action examples

STEP-01 Section 8 gave seventeen invalid action examples as targets for this step. Section 15.4 traces each to its catalog entry and handling.

### 9.10 Rules

| ID | Rule |
| --- | --- |
| BDR-08 | Detection reveals a violation. It does not create one. An invalid act was invalid from the outset, an undetected invalid act is not valid, and a detection result is not a finding of truth. |
| BDR-09 | An invalid act or ineffective designation produces no intended effect, and the attempt stays recorded and visible. Blocking may prevent reliance on the act, never the record of it. |
| BDR-10 | No handling prevents the recording of a challenge, counter-evidence, withdrawal, retirement, request, escalation, refusal, deferral, or invalid attempt. A defect in such an act makes it ineffective or flagged as the catalog says. It never makes it unrecordable. |
| BDR-11 | Handling categories are semantic effects. They are not state names, serialized values, or enforcement mechanisms. The same holds for the outcomes a formal-check result may state (Section 4.10): they are what a result may say, not a selected value set. |
| BDR-12 | Where a source rule makes a record element a validity condition, its absence is a violation. Where a source rule supplies a conservative default pending a determination, the default applies and the pending matter is recorded as unresolved. Otherwise the condition is recorded as unresolved with no conclusion. |
| BDR-13 | A detection result is a formal-check result. It is advisory, challengeable, and does not suspend a trigger it creates. It gains standing only as Section 9.4.3 states. A result relied on to satisfy a gate-required formal check is subject to CRC-13 and CRC-15. A result recorded as a finding that an acceptance is invalid must meet CRC-59 (rule or rules violated, evaluation point, record elements examined), and a non-human finding is also bounded by the decidability criteria of CRC-15 (UAD4-29). |
| BDR-14 | Mechanical detection may block, flag, escalate, record as unresolved, or show invalidity only at the semantic level. It must not decide a contextual judgment, present one as decided, convert one into a score, grade, weight, or confidence value, or replace human gate acceptance. No number or combination of satisfied checks is acceptance, validation, or progression. |
| BDR-15 | A shortfall covered by a valid exception is reported as satisfied under exception and stays visible. A non-waivable condition is never covered. |
| BDR-17 | Evaluator outputs, automated checks, verification records, and validator findings remain advisory or formal-check results unless accepted PROD-W protocol grants the relevant authority (PR-22). |

---

## 10. Authority, Independence, and Self-Approval Rule Boundary

Operationalizes D4, D8; FR-4, HA-1, HA-2. Resolves **GC-OQ-02** and **GC-OQ-03**, and addresses **PS-OQ-05**, **PS-OQ-08**.

### 10.1 What is checkable

Authority and independence are the area where the protocol's headline constraint (PR-16) lives, and where "objective" is most tempting to over-claim. The boundary falls here.

| Question | Class | Entries |
| --- | --- | --- |
| Who acted, in what capacity, at what time | Objective | CRC-01 |
| Whether the actor held a grant of the required class over the scope | Objective, given the grant records | CRC-02, CRC-60, CRC-61 |
| Whether the project's single establishing act is recorded, precedes every other recorded act, and records the root grants | Objective, given record order (DR-03) | CRC-61 |
| Whether a grant's chain is effective at the act, after any revocation or narrowing upstream | Objective, given the grant records and their order | CRC-61, CRC-63 |
| Whether a finding that an acceptance is invalid names its rule, evaluation point, and elements examined | Objective | CRC-59 |
| Whether the actor is recorded as human | Objective against a recorded designation | CRC-03 |
| Whether the acceptor, verifier, or challenger is a recorded producer | Objective given recorded producers | CRC-07, CRC-12, CRC-13, CRC-14 |
| Whether an output may be recorded as the act it claims to be | Objective | CRC-04 |
| Whether the declaration of independence exists | Recorded-judgment check | CRC-11 |
| Whether two distinct identities are substantively independent | Judgment | HJC-12 |
| Whether a recorded attribution or a human designation is accurate | Judgment | HJC-21 |
| Whether a grant was conferred or revoked for a particular purpose | Judgment | HJC-23 |

### 10.2 Authority grants (GC-OQ-02)

STEP-01 Section 4.3 defines a grant as an explicit, attributable, scoped permission with four elements, and defers how grants are created, changed, revoked, and audited (PS-OQ-05). STEP-03 Section 8.6 added that a self-conferred grant is not a valid cure for an authority gap and routed self-conferral here. This section disposes of each facet.

| Facet | Disposition | Rule | What remains |
| --- | --- | --- | --- |
| **Creation** | Granting is an **act**, recorded and attributable (PR-06). It requires a **human holding AUTH-G whose conferral scope covers** the class and scope conferred. A project has exactly one establishing act, preceding every other recorded act. Root grants are only the grants it records. Every other grant has an acyclic chain, effective at the relying act, to a root grant (Section 10.2.2) | CRC-60, CRC-61 | Who holds conferral scopes in a project: DM-02. Establishment practice: DM-03 |
| **Scope** | A grant's scope is stated and resolvable (PR-02). A conferrer cannot confer beyond its own conferral scope. Containment is decided where scopes are references. A scope stated by description is a designation with a judgment residue | CRC-02, CRC-60, CRC-61; HJC-25 | Scope vocabulary and containment computation: DR-08 |
| **Change** | Widening is a new conferral under CRC-61. Narrowing is a revocation of the wider grant and a conferral of the narrower | CRC-63 | none |
| **Revocation** | By the grantee (renunciation) or by a human holding AUTH-G whose conferral scope covers the grant. Recorded with a rationale. Effective when recorded, never retroactive. Grants downstream of the revoked or narrowed grant fall prospectively with the chain. Acts relying on a revoked or fallen grant after revocation are invalid. Acts performed while the whole chain was effective stand (Section 10.2.4). Challengeable | CRC-63 | Conflicted revocation, including revocation of a challenger's standing: CRC-64 (flag and escalation) |
| **Audit** | Grants and grant acts are records, cumulative and never erased (EKR-09). Every act's authority basis cites the grant it relied on (STEP-02 Section 9.3), and through it the chain to root. Reconstructing who held what authority as of a point in time is a requirement on any representation | CRC-41, CRC-60, CRC-61 | As-of reconstruction: DR-03, DR-08. Review practice: DM-07 |
| **Self-conferral** | **Invalid** for every later grant: one whose grantee is the conferring identity, a collective or role position whose recorded members or appointees include the conferrer, or whose chain returns to the conferrer. The establishing identity as a root grantee, in the establishing act's own grants, is the one bounded case and is not self-conferral. A grant-bearing role-position appointment is a conferral (Section 10.2.5) | CRC-62 | Purpose of a conferral: HJC-23. Legitimacy of the establishing act: HJC-22 |

#### 10.2.1 Why AUTH-G with a conferral scope

STEP-01 has four authority classes. None names the power to confer grants. Three ways of filling the gap were considered.

- **A fifth authority class for conferral.** Rejected. Creating one is an architecture-level step. STEP-03 declined the same step for a lesser acceptance class (UAD3-23, UAD3-24).
- **Conferral by any actor holding a grant covering the scope.** Rejected. It would let AUTH-P and AUTH-A holders, including AI agents, expand authority. HA-1 and HA-2 require consequential authority decisions to be explicit and human.
- **Conferral as a scope of AUTH-G.** Adopted. STEP-03 already treats "the project's gate-definition scope" as a scope of AUTH-G (Section 5.2), so a conferral scope follows an accepted precedent and adds no class. It is human-only by PR-05.

This is an architecture-level choice and is declared at level A (UAD4-13). It is not delegation and not class-confers-class, and Section 3.3 states the reading of PR-04 and GCR-08 that follows.

#### 10.2.2 Root grants and establishment

A chain of conferrals has to end somewhere. This artifact fixes where, and keeps the end from being movable.

1. **One establishing act.** A PROD-W project has exactly one protocol-establishing act for its authority chain: a recorded act by an identified human, marked as the establishing act.
2. **First.** The establishing act precedes every other recorded act of the project. A later act cannot become a second root merely because no later act has yet relied on it.
3. **Roots come only from it.** A **root grant** is a grant recorded by the establishing act itself. Every other grant chains acyclically to a root grant (CRC-61). A later act that is marked as establishing or as root is not a second root. Any grant it records is an ordinary conferral, and is invalid unless its conferrer holds a conferral scope covering it.
4. **The establishing identity as a root grantee.** The establishing identity may be a root grantee, but only for grants recorded by the establishing act itself. This is what lets a team of one exist: a founder establishes the project and grants themselves authority in the same act. CRC-62 does not treat that case as self-conferral. CRC-62 applies in full to any later grant, including a later grant by the establishing identity to itself, to a role position that includes it, to a collective that includes it, or through a cycle returning to it. A founder therefore records every grant the founder needs for itself in the establishing act. Anything later is a conferral by a holder whose scope covers it.
5. **Legitimacy is not checked.** The protocol checks that the recorded project-root form exists. It does not decide whether the establishing identity had real-world standing to establish the project (HJC-22).

Establishment practice, such as how a project begins its record so that the establishing act comes first, is methodology (DM-03). STEP-04 decides the protocol effect, and STEP-06 owns the practice. Role positions and who holds conferral scopes are methodology (DM-02). Record order is a representation question (DR-03). The choice is declared at level A (UAD4-27).

#### 10.2.3 Conferral by a conflicted holder

STEP-03 Section 8.6 allows an authority gap to be cured by a grant to an independent human by a granting authority. A conferrer who is itself a producer of the matter's accepted set can confer authority on someone who then performs an act favorable to that set. Calling that conferral invalid would make a gap incurable whenever the only available conferrer is conflicted, which is the common case in a small team. Calling it unrestricted would reopen the self-approval path through a proxy.

The selected handling sits between: the relation is **objectively detectable**, so it is **flagged** and **escalation-eligible** (CRC-64), and it is challengeable as the validity of the grant (GCR-23). Whether the conferral was done to enable the act is judgment (HJC-23). A project may stop at an authority gap (STEP-03 Section 8.6).

**The whole chain is evaluated.** CRC-61 already requires a recorded chain from the grant relied on to the root, so every link is available to the check. CRC-64 evaluates every link: a grant relied on for a favorable act is flagged and escalation-eligible if **any** conferrer along that chain is a recorded producer of a member of the act's accepted set. Testing only the immediate conferrer would leave an avoidable laundering path: a conflicted holder confers a conferral scope on an unconflicted intermediary, who confers the gate grant. The argument for flagging a proxy conferral applies equally to the second hop.

**Revocation covers standing to challenge.** CRC-64 also covers revocation or narrowing of a grant held by any actor with **standing to challenge** the relevant item or set, not only a holder who already has a challenge open when the revocation is recorded. Standing to challenge is the standing CRC-26 gives: an actor holding AUTH-A covering the target's scope. A conflicted holder who revokes a challenger's grant before the challenger records anything would otherwise use a conferral-layer act to suppress opposition. The flag applies where the revoker is a recorded producer of the item, or of a member of the accepted set the item belongs to. It applies equally where the revocation works by cascade (CRC-63).

**What does not change.** The handling stays **F and E, not I**, for this revision. The recorded challenge is still recordable (BDR-10). A challenge recorded after a revocation of standing is typed by CRC-26 and stays visible. The purpose of the conferral or revocation remains HJC-23.

The choices are declared at level A (UAD4-14, UAD4-28) and named as a known soft spot (Section 10.6). Whether F/E is strong enough is a pilot question with a named owner, evidence, and trigger (DP-04, RJ-OQ-09).

#### 10.2.4 Revocation, narrowing, and downstream grants

CRC-61 makes an effective chain to a root part of a grant's validity. It follows that a grant cannot stay valid after the chain that supports it has been cut. This section states the consequence, which UAD4-15 left undeclared.

- **Prospective cascade.** Grants downstream of a revoked or narrowed grant fall prospectively with the chain. A downstream grant falls to the extent that the revoked or narrowed grant no longer covers what the downstream grant confers. From the revocation's recording, a fallen grant validates no act, unless it is independently re-conferred through a valid chain to a root.
- **Re-conferral.** An independent re-conferral is a new conferral under CRC-61 by a human holding a conferral scope that covers it, recorded after the revocation. It takes effect when recorded. A revoked or fallen holder cannot re-confer on its own behalf.
- **No retroactivity.** Acts performed while the whole chain was effective are not retroactively invalidated by a later revocation. This preserves GCR-47: effects begin when recorded and are not undone by a later record.
- **Acts after the cut.** An act relying on a revoked, narrowed, or fallen grant, recorded after the revocation takes effect, fails CRC-02 and is invalid.
- **Renunciation.** A grantee's renunciation is a revocation and cascades in the same way. A conferrer who renounces its conferral scope therefore leaves its own appointees to be re-conferred. This is a cost (Section 10.6; DM-07).

The choice is declared at level A (UAD4-15, UAD4-30). Computation of which grants have fallen, as of a point in time, is DR-08.

#### 10.2.5 Work assignment and role-position appointment

The words "assignment" and "assign" appear in the sources for two different relations. This artifact keeps them apart.

| Term | Meaning | Effect | Where |
| --- | --- | --- | --- |
| **Work assignment** (production assignment) | Provenance: an actor assigns production of an item, or part of one, to another | Confers no authority. Makes the assigner a producer only where the assigner supplied the item's substance or adopted it | GCR-08; PR-27; CRC-11; HJC-12 |
| **Grant-bearing role-position appointment** | Appointing an actor to a role position that carries grants | A conferral. Evaluated under CRC-61 for the conferrer's scope and under CRC-62 for self-conferral | CRC-61, CRC-62; UAD4-13, UAD4-14 |

Appointment to a role position that carries no grants is not a conferral. Which role positions exist and who holds them is DM-02. Reading CRC-62 as reaching work assignment, or reading work assignment as appointment, would misapply both. Section 3.3 carries the reading of PR-04 and GCR-08 that goes with this distinction.

### 10.3 Verification, AI-held AUTH-V, and verifier independence (GC-OQ-03)

#### 10.3.1 May an AI agent hold AUTH-V?

**Yes, bounded.** AUTH-V confirms that defined formal criteria were satisfied and that required checks occurred (STEP-01 Section 4.4). That is exactly the kind of question an objective check answers (BDR-01). Nothing in STEP-01 limits AUTH-V to humans: PR-05 limits only AUTH-G. The bound is the one STEP-03 set as an interim constraint (GCR-11), now stated as a rule form.

| Element | Rule | Entry |
| --- | --- | --- |
| **Grant** | A non-human actor holds AUTH-V only by a grant conferred under CRC-61, covering the gate or artifact class | CRC-15 (a), CRC-61 |
| **Criteria** | A gate-required formal check names its criteria. For a non-human verifier, each criterion carries a recorded designation, in the gate definition, that it is decidable from the record. The designation is itself a recorded judgment (HJC-24), challengeable, and checked by the test of BDR-01 | CRC-15 (b) |
| **Reproducibility** | The verification record states the record elements it examined and its evaluation point, so that a human or another verifier can re-run it. This goes beyond OBJ-13 and is declared (UAD4-16) | CRC-15 (c) |
| **Findings of invalid acceptance** | The same decidability bound governs a non-human finding under CRC-59. A non-human AUTH-V holder may record one only where each rule asserted violated is decidable from the record, and the finding states the elements examined and its evaluation point. If the asserted invalidity depends on interpretation, the output stays advisory or request-like and does not itself trigger TRG-6. Declared (UAD4-29) | CRC-59, CRC-15 |
| **Otherwise** | Where a criterion requires interpretation, the output is an advisory finding (GCR-11) | CRC-04, CRC-15 |

#### 10.3.2 Verifier independence, rule form

Independence of a verifier is **non-membership in the producers of every verified item**, evaluated on actor identity (GCR-10; PR-19). The rule form is the same for human and non-human verifiers:

- the verifier is a recorded producer of nothing verified (CRC-13);
- the verification relied on is a member of the accepted set, so the acceptor cannot be its verifier (CRC-07);
- a producer's self-verification is recorded and not counted (PR-19, PR-28);
- re-running a role under a different configuration produces a verification by the same identity, not an independent one (PR-27).

What is not checked is substantive independence: whether a non-human verifier whose identity differs from the producer's shares an operator, a model, or a set of instructions with it. That is HJC-12, supported by the acceptor's independence declaration (CRC-11) and by recorded work-assignment relations, and by recorded configuration (CRC-39).

#### 10.3.3 Verification never becomes acceptance

A verification is bounded by its criteria (PR-14). Its output is typed as a verification (CRC-05), satisfies a gate's formal-check slot at most (CRC-13), and is never recorded as acceptance, validation, or progression. No number or combination of verifications is acceptance (BDR-14). A gate whose every mechanical condition is satisfied is not thereby accepted (PR-13).

#### 10.3.4 Relation to detection

A checker that produces a detection result relied on to satisfy a gate-required formal check is performing an AUTH-V act and is subject to this subsection. A checker whose output is recorded as a finding that an acceptance is invalid is also subject to it, through the CRC-59 bound above. A checker producing ordinary conformance results (Section 9.4.3) is not relied on as a verification. This links a validator to the authority model without selecting one: a validator is an actor, or part of a representation, whose results have the standing Section 9.4.3 gives them.

### 10.4 Identity versus substance, collectives, and evaluators

- **Identity is checked. Substance is declared and left open to challenge.** CRC-07 evaluates producer sets by recorded identity, with collectives expanded to recorded members (GCR-08) and disputed attributions counted against the disputed actor (CRC-14). Whether two identities are one person, or one supplied the other's substance, is HJC-12. The independence declaration (CRC-11) makes the acceptor state what it knows, and the statement is challengeable.
- **Configuration is provenance, not identity.** Changing the model, effort, harness, tools, or instructions does not change the accountable actor, so it cannot create independence (PR-27). Recording it (CRC-39) is for weighing, not for independence.
- **A record is checked as recorded.** Attribution accuracy and authentication of identity are not decided by any entry (BDR-06, HJC-21, DR-07).
- **External evaluators** remain advisory unless an approved PROD-W revision grants authority (PR-22, PR-23). An evaluator may satisfy the _existence_ of a required independent challenge (CRC-12), supply a verification within CRC-13 and CRC-15, request revalidation, and escalate. It never performs an act CRC-04 reserves to AUTH-G (BDR-17).

### 10.5 Self-approval routes, closed and open

STEP-01 Section 6.3 listed eight circumvention patterns. STEP-03 closed three more (citation, correction, withdrawal). This step adds the routes through conferral and through the finding path (self-conferral, a second root, conflicted conferral or revocation, appointees of a revoked conferrer, a non-human verifier on an interpretive criterion, and an unreasoned finding of invalidity). The table shows where each is caught, and what the catalog cannot catch.

| Route | Caught by | Detected as | Left to judgment |
| --- | --- | --- | --- |
| Producer accepts under a second role carrying AUTH-G | CRC-07 | I, B | none |
| Producer adds a co-acceptor and counts its own | CRC-08 | I | none |
| Producer challenges its own claim and counts it as independent | CRC-12 | I, X | HJC-12 |
| Producer verifies its own artifact and treats it as acceptance | CRC-05, CRC-13, CRC-21 | I, X | none |
| Several agents agree with the producer, treated as corroboration | CRC-36 (a concurrence record is not evidence) | I, where the record distinguishes concurrence from sourced evidence | HJC-12 where it does not |
| One of several co-producers accepts the joint item | CRC-07 | I, B | none |
| An item is restated by a second actor so the original producer can accept | CRC-14 | I | HJC-12 (assigner substance) |
| The same role re-run under a different configuration is treated as an independent reviewer | CRC-07, CRC-12, CRC-13 when the record attributes both runs to one identity | I, X | HJC-12 when the record attributes them to different identities |
| Producer reaches acceptance through citation | CRC-06, CRC-07 (accepted set) | I, B | HJC-12 |
| Meaning-changing edit passed off as a correction | CRC-55, CRC-56 | I | HJC-13 |
| Producer withdraws or supersedes its own opposition | CRC-58, CRC-18, CRC-28 | I, F | HJC-19 |
| Actor confers authority on itself, directly, through a role position or collective that includes it, or through a cycle | CRC-62 | I, B | HJC-23 |
| Actor records a later "establishing act" or "root" to mint authority | CRC-61 (exactly one establishing act, first; later roots are ordinary conferrals) | I, B | HJC-22 |
| Conflicted conferrer, at any link of the chain, confers authority to enable an act, or revokes or narrows a challenger's standing | CRC-64 (whole chain; challenger standing) | F, E | HJC-23 |
| A revoked conferrer's earlier appointees keep authority | CRC-63 (prospective cascade), CRC-61 | I | HJC-23 |
| A verifier that is a producer, or a non-human verifier on an interpretive criterion | CRC-13, CRC-15 | I, X | HJC-24 |
| A cheap, unreasoned finding that an acceptance is invalid, to create requirements on dependents | CRC-59 (rule, evaluation point, elements examined; non-human decidability bound) | I (as a finding; re-typed), B | HJC-24 |

### 10.6 Known soft spots

The Development Team can name these. They are offered as sampling targets (Section 14.4), not as a complete list.

- **Conflicted conferral** is flagged, not invalidated, though now evaluated over the whole chain and over revocation of a challenger's standing (Section 10.2.3). F/E may still be too weak against a determined proxy. The evidence and trigger for reconsidering are named (DP-04).
- **Root multiplicity and establishing-act uniqueness** are bounded choices (UAD4-27). The project has exactly one establishing act, and it precedes every other recorded act. The rule is strict: a later act is never a second root. How a project begins its record so that establishment comes first is DM-03 and DR-03. A record that begins with other acts has no valid establishing act under this rule. Whether that is too strict for real projects is a sampling target.
- **Root-grantee limit.** The establishing identity may be a root grantee only in the establishing act's own grants. A founder who omits a self-grant from that act cannot add it later. It needs a conferrer whose scope covers it, and the founder cannot be its own conferrer. This is deliberate, because the alternative reopens self-conferral, and it is a friction (DM-03).
- **Cascade cost.** A revocation or renunciation cascades to downstream grants (Section 10.2.4). A conferrer who leaves the project, or who is revoked, strands its appointees until they are re-conferred. DM-07 and DP-01 carry the practice and the burden.
- **Root legitimacy** is not checkable and not checked (HJC-22).
- **Actor kind** is a recorded designation. Whether a human-designated identity is a human is HJC-21.
- **Substantive independence of AI identities** that share an operator or model is judgment (HJC-12). The catalog defines no rule that treats a shared accountable position as sameness, because that would define AI actor identity, which PR-27 and PS-OQ-06 leave open.
- **Notice receipt** (CRC-55) is a recorded event. Receipt is not checkable.
- **A detector's own errors** are challengeable but do not suspend TRG-6. A mistaken finding costs dependents a requirement that a human must close. The finding's required content (rule, evaluation point, elements examined) and the non-human decidability bound limit how cheaply that can happen (CRC-59; UAD4-29). A human AUTH-G finding that rests on judgment is still not limited by the decidability bound. It must still state its three elements.
- **Human-only conferral** may add friction for teams that onboard many agents (DP-01, DM-02).

---

## 11. Provenance, Producing-Configuration, and Lineage Rule Boundary

Operationalizes D3, D6, D7; FR-6, PE-1. Resolves **EK-OQ-09** and **PS-OQ-13**.

### 11.1 The question

EK-OQ-09 asks: at what granularity must producing configuration and evidence lineage be recorded, and does insufficient provenance **invalidate an action**, **weaken standing**, **trigger a flag**, or **remain a human judgment**?

### 11.2 Producing-configuration granularity

PR-27 names the configuration facets: model, reasoning effort, harness, tooling, and the instructions given. The catalog requires a configuration statement at the level of these five **facets** for an item or action produced by an AI actor (CRC-39).

| Element | Requirement |
| --- | --- |
| **Facets** | A statement for each of the five facets, or a statement that the facet is not applicable |
| **Not determinable** | A facet that cannot be determined is stated as _not determinable_, with the reason where known. This satisfies the presence check, stays visible, and is an input to HJC-26. It is permitted because the alternative is pressure to state what is not known (PE-4) |
| **Model** | Identified at the level the operator or provider exposes, with a version designation where one exists. The catalog fixes no finer level |
| **Instructions** | The instructions given, stated by content or by a reference that resolves to what was in force at the act, not to a later version |
| **Skills** | A named instruction bundle is a kind of instructions. It is covered when the instruction statement resolves to what was given. The catalog does not add skill name and version as a separate element. That research input (`research/topics/agent-skills-and-protocol-relationship.md`, Routing) is used only as input, adds no requirement, and its other questions remain with STEP-05 (H-C) and STEP-08 |
| **Not required** | Sub-facet detail such as sampling parameters, token counts, internal tool-call traces. Anything finer is a gate-defined stricter condition, or methodology (DM-05) |

### 11.3 Evidence-lineage granularity

| Element | Requirement |
| --- | --- |
| **Immediate derivation** (declared: UAD4-12) | Derived evidence identifies the items it derives from (EKR-11). Transitive lineage is computed from the recorded links (DR-01). Lineage is not recorded at passage, field, or transformation level |
| **Source comparability** | Evidence items sharing an identified source are identifiable as sharing it. How two sources are determined to be the same is a representation question (DR-06) |
| **Unrecorded lineage** | Cannot be discovered by any check. It is substantive independence and belongs to HJC-12 |

### 11.4 Consequence of insufficiency

| Situation | Consequence | Handling | Why |
| --- | --- | --- | --- |
| No configuration statement for an AI-produced item or action | **Flagged.** Visible on the item and, where the item is cited, in the acceptance's standing record. The act keeps its effect | F | PR-10's "required attribution and content" is defined by the action category (STEP-01 Section 5.1), and configuration is not in that minimum |
| A facet stated as not determinable | Presence satisfied. Visible. Weight left to judgment | N | Honest uncertainty is permitted, and the weighing is HJC-26 |
| A facet stated but inadequate or unverifiable | **Remains human judgment** | N | Adequacy is a sufficiency question (HJC-26). The catalog checks presence |
| A gate definition requires named configuration facets for items it relies on | Unsatisfied gate requirement. Acceptance invalid unless a valid exception covers it | I, X | The gate definition is a human governance act. The slot machinery already exists (STEP-03 Section 5.2, "stricter conditions") |
| Class-defining provenance missing: no identified source, no attempt record, no derived-from inputs | The item is **not evidence** for that target. The designation is ineffective and the item stays visible as the class it is | I | These elements define what evidence is (EKR-13). Their absence is not a weakness of evidence. It is the absence of evidence |

**Why configuration is flagged and not invalidating.** Four reasons follow from accepted semantics.

1. **Configuration does not enter authority, independence, or acceptance validity.** Those are evaluated on identity and grants (PR-17, PR-27). Invalidating on configuration would invalidate acts that no accepted rule makes invalid for any other reason.
2. **Honest recording must not be punished harder than silence.** An invalidating rule would reward recording nothing over recording partially.
3. **Hosted tools may not expose facets.** "Not determinable" is a legitimate answer. Invalidation would make it a violation.
4. **The conservative-invalidation recommendation** (`mod-w/step-04.md`, Tech Lead Recommendation 4) points the same way. The consequence is declared at level A (UAD4-11).

**Why "weakens standing" is not a handling.** The protocol assigns evidence no graded standing, and defines no weight or confidence (EKR-19, BDR-14). What a flag does is make the gap visible so that the person who weighs the item can weigh it knowing. The weighing is HJC-26.

### 11.5 What this section does not decide

Representation of configuration records and how identities of sources are compared are routed (DR-06, RJ-OQ-10). Conventions for stating configuration are DM-05. Whether skills are generated projections of the protocol remains with STEP-05 (H-C) and STEP-08. A separate skill-name and version configuration element is not open for research. UAD4-11 holds that skills are instructions, and a separate element would need an accepted revision of this artifact (BDR-16). Burden of recording is a pilot question (DP-01).

---

## 12. Evidence, Assumption, Inference, Disagreement, Gate, Correction, Exposure, and Revalidation Rule Boundary

Operationalizes D3, D5, D6, D7. This section shows where the boundary falls along the chain from a piece of evidence to a reopened decision. It adds no entry that Section 6 does not contain. It states the division of work.

### 12.1 Evidence and counter-evidence

| Objective part | Judgment part | Handling |
| --- | --- | --- |
| A source is identified; the item is not solely a concurrence record, where the record distinguishes it from sourced evidence; target and polarity recorded; negative findings carry their attempt record; derived evidence names its inputs (CRC-36, CRC-38). Descriptive elements present (CRC-37). Required slots filled (CRC-17). References resolve (CRC-40) | Relevance, sufficiency, persuasion, adequacy of the descriptive elements, adequacy of an attempt, independence of sources (HJC-01, HJC-02, HJC-06, HJC-12, HJC-26) | I for class-defining, F for descriptive, N on residue |

Counter-evidence is evidence: the same checks apply, and polarity is per target (EKR-15). The duty to record contradicting information an actor holds (EKR-18) is not detectable from a record that lacks it (Section 6.5). Agent agreement is detectable as non-evidence only where the record distinguishes a concurrence record from sourced evidence (CRC-36); otherwise the remedy is challenge (STEP-02 Section 7.6).

### 12.2 Assumptions and hypotheses

| Objective part | Judgment part | Handling |
| --- | --- | --- |
| A hypothesis carries recorded criteria (CRC-43). Reliance is marked, and the dependent shows its unresolved assumptions (CRC-47). A validation is by an independent authorized human and cites scope, criteria, results, responses (CRC-46). Consequential reliance is covered by an authorization recorded before the acceptance (CRC-19). Assumption-rooted items are identified (CRC-53) | Testability and adequacy of criteria; whether criteria are met; whether to validate; whether proceeding is warranted (HJC-10, HJC-11, HJC-14) | I for designation and validation, F for marks and identification, N on residue |

### 12.3 Inference and value judgment

| Objective part | Judgment part | Handling |
| --- | --- | --- |
| An inference cites, is grounded, and is not typed as evidence (CRC-44). A claim with an evaluative designation is not recorded under an observed-fact or evidence-only form (CRC-45) | Whether the inference is warranted; whether content is evaluative; whether an evaluative claim is warranted (HJC-05, HJC-18) | I for typing and grounding, N on residue |

### 12.4 Challenge, disagreement, escalation

| Objective part | Judgment part | Handling |
| --- | --- | --- |
| A challenge is well-formed (CRC-26). A closure is of a recognized kind by a qualified closer (CRC-27). Challenges carry to successors (CRC-28). Each contribution has its effect (CRC-29). Requests and escalations have their elements (CRC-30, CRC-31). Authority gaps are recorded (CRC-32). Disagreement clears only by recognized acts (CRC-33) | Whether an answer is adequate; whether a challenge stands; whether disagreement is resolved enough to proceed; which position to act on (HJC-07, HJC-08, HJC-09) | I for form and closure, F for derived effects, U and E for gaps, N on residue |

Disagreement is a derived condition (GCR-35). Its derivation is a representation requirement (DR-04). The catalog checks that it is never cleared by anything but a recorded act (CRC-33). It does not check that a disagreement is resolved enough to proceed.

### 12.5 Gates, outcomes, and instruments

| Objective part | Judgment part | Handling |
| --- | --- | --- |
| The acceptance is by a human holding AUTH-G, independent over the accepted set, after a recorded gate definition, with required slots filled and checks independently verified, each standing-record item treated, relied-on unresolved items covered, exceptions complete, declaration present, determination explicit and prior to progression (CRC-02 to CRC-22). Conditional progression is complete (CRC-23). Refusals and deferrals state their reasons (CRC-25) | Sufficiency, acceptability of residual risk, warrant of conditional progression, warrant of an exception, adequacy of the gate definition, weight of advisory findings (HJC-01, HJC-08, HJC-14, HJC-15, HJC-17, HJC-20) | I for validity conditions, X for waivable shortfalls, N on residue |

No conjunction of satisfied checks is an acceptance (BDR-14). The determination that a gate's conditions are sufficient is the one act this boundary reserves entirely (PR-12, PR-13).

### 12.6 Correction, supersession, withdrawal, exposure, and revalidation

| Objective part | Judgment part | Handling |
| --- | --- | --- |
| A correction designation on a standing item is effective only on independent confirmation (CRC-55). Five kinds of change are never corrections (CRC-56). Acts on another actor's item need AUTH-G (CRC-57). A withdrawal records its elements and its effects persist (CRC-58). Dependency links and redesignations are well-formed and confirmed (CRC-49, CRC-50). A trigger on a material dependency has a single open requirement with reasons, and a currency mark is not recorded over it (CRC-51). A requirement closes only by a qualified outcome that names every open reason and records a disposition for each (CRC-52). A finding of an invalid acceptance is a TRG-6 event only where it names the rule or rules violated, its evaluation point, and the record elements examined, and a non-human finding is bounded by decidability (CRC-59) | Whether a revision alters meaning; whether a dependency is material or missing; whether a withdrawal rationale is genuine; whether a change undermines a dependent; the outcome (HJC-04, HJC-13, HJC-16, HJC-19) | I for designations and closures, F for missing requirements and findings, U while confirmation is pending, N on residue |

Exposure and the other derived conditions are DR-04. The catalog requires that they be derivable and that effect follows from the source rule regardless of whether they are shown (CRC-28, CRC-29).

### 12.7 Assumption-rooted identification and never-a-correction tripwires (GC-OQ-11)

GC-OQ-11 asks whether these two conditions become catalog rules. **Both do.**

**Assumption-rooted identification (CRC-53).** A basis item is assumption-rooted when every support or derivation chain beneath it ends only in assumptions or unvalidated hypotheses and none reaches an evidence item (STEP-03 Section 12.4). That is derivable from recorded classes and chains, so it passes the test of BDR-01 **relative to the recorded classifications**. Whether a proposition is a hypothesis or an assumption is HJC-10 and is taken as recorded (BDR-04).

- **Handling: flagging (F).** Omitting the identification does not by itself make an acceptance invalid. The accepted validity conditions (STEP-03 Section 5.4) already require that every relied-on assumption and unvalidated hypothesis be covered by a conditional progression authorization (CRC-19). If an assumption-rooted item is relied on and the assumptions beneath it are uncovered, CRC-19 invalidates the acceptance. If they are covered, the missing identification is a visibility defect. This preserves STEP-03's list of validity conditions without adding to it.
- **Declared:** UAD4-18.

**Never-a-correction tripwires (CRC-56).** The five kinds of change are recognizable from the recorded history of the item and its changes (STEP-03 Section 10.3) and force the answer "supersession" regardless of the producer's or confirmer's designation.

- **Handling: invalidating the correction _designation_ (I).** The change itself is a valid producer revision. A designation of correction on a never-correction change has no effect, the change stands as a supersession, and the attempt stays visible. A confirmation by an independent human does not rescue it, because the five kinds do not turn on judgment.
- **Deferred computation:** the checks compare a change with the item it changes, which needs a notion of identity across change (DR-02, EK-OQ-12). The rule is fixed. How the relation is realized is STEP-05's.
- **Criteria amended after results.** This case is included in CRC-56 (GCR-65). It is the one tripwire that depends on record order (DR-03).
- **Declared:** UAD4-19. The adequacy of the five kinds is a pilot question (DP-05).

### 12.8 Time, review events, and protocol-effective terms (GC-OQ-09)

GC-OQ-09 asks whether authorizations may carry protocol-effective terms, such as a lapse date set by the authorizer. **Not adopted.**

| Candidate | Disposition | Reason |
| --- | --- | --- |
| **Review event** on an authorization (STEP-03 Section 9.2, element 9) | Stays as accepted: recorded for visibility, no automatic effect. Not a catalog rule, because no violation can exist | GCR-42 |
| **Lapse date** on a conditional progression authorization | **Rejected for the catalog.** Time would end an authorization. GCR-42 lists the ending conditions and says "never by time." GCR-67 says elapsed time never ends anything. Adopting a lapse would revise those accepted rules. This step does not reopen them, and a Moderator-visible change would be needed | GCR-42, GCR-67 |
| **Term on a grant** (expiry) | Same disposition. Rotation is by explicit revocation (CRC-63). Review practice is DM-07 | GCR-67; PR-01 |
| **Reminder that a review event date has been reached** | Not a catalog rule, because nothing is violated and nothing changes effect. A practice may surface it. It has no protocol effect | GCR-67 |
| **Evidence-age recency criterion** | Already accepted: a gate-defined criterion evaluated at the acceptance act against recorded observation times (CRC-17; GCR-68). It is a check at a point, not a clock | GCR-68 |

The question is retained as a pilot question (DP-03, RJ-OQ-07): whether teams need lapse semantics. If evidence supports it, the route is a Moderator-visible revision of GCR-42 and GCR-67, not a STEP-04 rule. The choice is declared at level A (UAD4-20).

---
## 13. Open-Question Dispositions and Routing

Each question routed to STEP-04 is carried forward in its original wording and disposed. Sections 6 to 12 give the reasoning.

### 13.1 GC-OQ-01. Which GCO conditions become catalog rules, and are violations blocked, flagged, or escalated?

**Carried forward.** "For each GCO condition: is a violation blocked, flagged, or escalated? Which become the machine-checkable rule catalog?" (STEP-03 Section 16.1; PS-OQ-10; EK-OQ-14).

**Disposition.** All 28 GCO conditions are classified (Section 6.3): **20 catalogued rules, 7 recorded-judgment checks, 1 deferred to representation (GCO-22), none out of catalog.** The handling profile of each is:

| Handling profile | GCO conditions |
| --- | --- |
| Invalidating, blocking-eligible (I, B) | GCO-01, GCO-02, GCO-03, GCO-08, GCO-09, GCO-11, GCO-12, GCO-15, GCO-19, GCO-21, GCO-26, GCO-27 |
| Invalidating the acceptance, with the shortfall coverable by a visible exception (I, X) | GCO-04, GCO-05, GCO-06, GCO-07, GCO-10 |
| Invalidating, not blocking-eligible because the check is historical or standing, or turns on a pending confirmation (I, with U or F) | GCO-16, GCO-17, GCO-18, GCO-20, GCO-23 |
| Flagging only (F) | GCO-13, GCO-14, GCO-24 |
| Flagging a missing requirement, invalidating a currency mark (F, I) | GCO-28 |
| Recorded as unresolved and escalation-eligible (U, E) | GCO-25 |
| Deferred to representation | GCO-22 |

**Blocking eligibility of GCO-08 and GCO-09 is conditional.** CRC-18 and CRC-19 depend on derived conditions (exposure, open requirements, assumption-rooted basis items; DR-01, DR-04). B holds for a given representation only where that representation makes the derived condition available at the act (Section 5.4). The invalidating handling does not depend on it.

**Semantic handling categories** are the seven of Section 9.2: invalidating, blocking candidate, flagging, escalating, recorded as unresolved, visible exception, and no automated conclusion. **They are semantic, not mechanisms** (BDR-11). **Where escalation is the handling,** it is the consequence of a matter that needs an authority's determination (GCO-25; CRC-59, CRC-64), never a way to resolve one (BDR-14).

### 13.2 GC-OQ-02. Authority grants: creation, scope, change, revocation, audit, and self-conferral

**Carried forward.** "How are authority grants created, scoped, changed, revoked, and audited? Is self-conferral of AUTH-G over a scope an invalid action?" (STEP-03 Section 16.1; PS-OQ-05).

**Disposition.** Disposed by rule in Section 10.2. **Creation:** granting is an act; conferral needs a human AUTH-G holder whose conferral scope covers what is conferred (CRC-60, CRC-61). A project has **exactly one establishing act**, which precedes every other recorded act. Root grants are only the grants it records, and every other grant chains acyclically, through an effective chain, to one (CRC-61; UAD4-27). **Scope:** stated, resolvable, bounded by the conferrer's own (CRC-02, CRC-60, CRC-61). **Change:** widening is a new conferral, narrowing is revocation plus conferral (CRC-63). **Revocation:** by renunciation or by a human AUTH-G holder whose conferral scope covers the grant, effective when recorded, never retroactive. Grants downstream of a revoked or narrowed grant **fall prospectively with the chain** and validate no act unless independently re-conferred. Acts performed while the whole chain was effective are not invalidated (CRC-63; UAD4-15, UAD4-30). **Audit:** grants are cumulative records, authority basis cites the chain, as-of reconstruction is a representation requirement (CRC-41, DR-03, DR-08).

**Self-conferral of AUTH-G over a scope is invalid** (CRC-62), as is self-conferral of any class, including through a collective, a role position, or a cycle. This applies to every later grant. The establishing identity is a root grantee only for grants recorded by the establishing act itself, and CRC-62 does not treat that case as self-conferral. This is a rule, not an interim constraint. STEP-03's interim position (a self-conferred grant is not a valid cure for an authority gap) stands and is now the special case of this rule.

**Conflicted conferral and revocation.** CRC-64 evaluates every link of the chain relied on, and covers revocation or narrowing of a grant held by an actor with standing to challenge, not only a holder with an open challenge. It remains flag and escalation (F, E), not invalidation (UAD4-14, UAD4-28).

**Terms and reading.** Work assignment (provenance) and grant-bearing role-position appointment (conferral) are distinct terms (Section 10.2.5). The reading of PR-04 and GCR-08 against conferral is a tension, not a direct conflict, and is Moderator-visible (Section 3.3).

**Routed.** Who holds conferral scopes, and establishment practice: STEP-06 (DM-02, DM-03). Scope vocabulary, record order, and as-of reconstruction: STEP-05 (DR-03, DR-08). Strength of handling for conflicted conferral and revocation (flagged, not invalidated): STEP-07 (DP-04), with the evidence and trigger DP-04 names and targeted Tech Lead review of that evidence before any strengthening is proposed. Purpose of a conferral: judgment (HJC-23).

### 13.3 GC-OQ-03. AI-held AUTH-V and the rule form for verifier independence

**Carried forward.** "May AI agents hold AUTH-V, and what rule form carries verifier independence?" (STEP-03 Section 16.1; PS-OQ-08; PS-OQ-02 remainder).

**Disposition.** A non-human actor **may** hold AUTH-V. Its verification satisfies a gate-required formal check only where every named criterion is designated decidable from the record, the verification states the record elements examined and its evaluation point, and the verifier is a producer of nothing verified (CRC-15, CRC-13). Otherwise its output is an advisory finding. Verifier independence is non-membership in the producers of every verified item, by identity, and the verification relied on joins the accepted set so the acceptor cannot be the verifier (CRC-07, CRC-13). **Verification never becomes acceptance.** No set of verifications is acceptance, validation, or progression (CRC-05, CRC-21, BDR-14). The same decidability bound governs a non-human finding that an acceptance is invalid: such a finding counts under CRC-59 only where each rule asserted violated is decidable from the record and the finding states the elements examined and its evaluation point. Otherwise it stays advisory or request-like and does not itself trigger TRG-6 (CRC-15, CRC-59; UAD4-29). Section 10.3 gives the reasoning.

**Routed.** Guidance on designating criteria as decidable: STEP-06 (DM-06). Guidance on stating the content of a finding: STEP-06 (DM-08). Recording and attribution of findings: STEP-05 (DR-09). Adoption and effect of non-human verification: STEP-07 (DP-06). Substantive independence of a non-human verifier: judgment (HJC-12).

### 13.4 GC-OQ-09. Protocol-effective authorization terms

**Carried forward.** "May authorizations carry protocol-effective terms, such as a lapse date set by the authorizer?" (STEP-03 Sections 16.1 and 13.3).

**Disposition.** **Rejected for the catalog.** Review events remain non-effective and are not rules. A lapse date would be time ending an authorization, which accepted GCR-42 and GCR-67 exclude, and this step does not reopen them. The same disposition covers terms on grants. Retained as a **pilot question** (DP-03, RJ-OQ-07). If evidence supports it, the route is a Moderator-visible revision of GCR-42 and GCR-67. Not a representation question: no representation is asked to implement a time-driven effect. Section 12.8.

### 13.5 GC-OQ-11. Assumption-rooted identification and never-a-correction tripwires

**Carried forward.** "Should the 'assumption-rooted' identification (Section 12.4) and the 'never a correction' tripwires (Section 10.3) become catalog rules?" (STEP-03 Section 16.1).

**Disposition.** **Both become candidate catalog rules.** Assumption-rooted identification (CRC-53) is a flagging rule, relative to recorded classes, which gains validity force only through CRC-19. The never-a-correction tripwires (CRC-56) make the correction _designation_ ineffective and leave the change as a supersession. Computation of grounding and of the change-to-item relation is deferred to representation (DR-01, DR-02). Adequacy of the five kinds is a pilot question (DP-05, RJ-OQ-11). Section 12.7.

### 13.6 EK-OQ-09. Producing-configuration and evidence-lineage granularity; does insufficiency invalidate or weaken

**Carried forward.** "At what granularity must producing configuration and evidence lineage be recorded, and does insufficient provenance invalidate an action or merely weaken it?" (STEP-02 Section 13.1; PS-OQ-13).

**Disposition.** **Granularity:** configuration at the level of the five PR-27 facets, with "not determinable" a permitted visible statement (Section 11.2); lineage at immediate-derivation and source-comparability level (Section 11.3). **Consequence:** an absent configuration statement is **flagged**, does not invalidate the action, and is not a graded weakening. A statement that is present but inadequate **remains human judgment** (HJC-26). A gate definition may require more, and then a shortfall is an unsatisfied gate requirement. Class-defining provenance (source, attempt record, derived-from inputs) is different: its absence means the item is not evidence for that target. Section 11.4 gives the reasoning.

**Routed.** Source comparability: STEP-05 (DR-06). Conventions: STEP-06 (DM-05). Burden: STEP-07 (DP-01). Skills as configuration: UAD4-11 stands (skills are instructions), and a separate skill-name and version element would need an accepted revision of this artifact (BDR-16). The remaining skills questions stay with STEP-05 (H-C) and STEP-08.

### 13.7 EK-OQ-14. Which EKO conditions become machine-checkable rules; how violations are handled

**Carried forward.** "Which of the EKO conditions are catalogued as machine-checkable rules, and how are detected violations handled?" (STEP-02 Section 13.1; PS-OQ-10).

**Disposition.** All 20 EKO conditions are classified (Section 6.3): **16 catalogued rules, 4 recorded-judgment checks (EKO-11, EKO-14, EKO-15, EKO-17), none deferred or out of catalog.** Two are catalogued as read together with a later accepted artifact (EKO-15, EKO-19; Section 3.3). Two are catalogued as composites whose objective core is the entry and whose residue is paired (EKO-04, EKO-05; BDR-03). Handling profile:

| Handling profile | EKO conditions |
| --- | --- |
| Invalidating, blocking-eligible (I, B) | EKO-01, EKO-02, EKO-04, EKO-08, EKO-09, EKO-10, EKO-11, EKO-12, EKO-16, EKO-17, EKO-18, EKO-20 |
| Invalidating for class-defining elements, flagging for descriptive ones | EKO-05, EKO-06, EKO-13 |
| Invalidating only | EKO-07, EKO-14 |
| Flagging only | EKO-03 |
| Flagging a missing requirement, invalidating a currency mark (F, I) | EKO-19 |
| Flagging unmarked reliance (F); invalidating an _acceptance_ that relies under assumption without the required authorization (I, through CRC-19) | EKO-15 |

**EKO-15 and consequential reliance.** CRC-19 invalidates an acceptance that relies under assumption without the required authorization. The accepted STEP-03 reading (Section 9.2 of that artifact) treats "progression" as progression through a gate or any consequential commitment. STEP-04 records that reading. It adds no new rule for a consequential commitment that is not an acceptance, and no such rule is claimed by the handling profile above. Enforcement detail for non-acceptance commitments, unless an accepted rule already covers it (for example CRC-48 for decisions), is routed (RJ-OQ-12). The EKO-15 row also mixes a CR check (the reliance marks on dependency links, CRC-47) and an RJC check (the recorded authorization, CRC-19). Section 6.3 splits them in its note. The primary disposition stays RJC.

Detected violations are handled by the categories of Section 9.2. EKR-41 is restated and enforced through BDR-05 and BDR-14 (the accepted rule is preserved, Section 3.1): an implementation may block or flag an EKO-class violation and must not decide an EKJ-class question (BDR-05, BDR-14).

### 13.8 Upstream questions routed to STEP-04

| Question | Disposition |
| --- | --- |
| **PS-OQ-02** Verification independence | Resolved by STEP-03 for gate-required checks (GCR-10). Catalogued as CRC-13. Non-human verification: GC-OQ-03 above. Where a gate does not require independent verification, a verification is an ordinary record. No change |
| **PS-OQ-05** Grants created, scoped, changed, revoked, audited; is granting an action category | Disposed with GC-OQ-02. Granting is an act (CRC-60 to CRC-64). The ACT catalog is non-exhaustive. This step declares granting as an act without assigning it an `ACT-` number, since the catalog is expository (UAD4-13) |
| **PS-OQ-08** AI-held AUTH-V | Disposed with GC-OQ-03 |
| **PS-OQ-10** How invalid actions are surfaced and handled | Disposed in Section 9. Invalid actions never produce effect. Blocking may prevent reliance on an act, never the record of it. Detection is a formal-check result, advisory unless the producing actor holds the grant. A finding that an acceptance is invalid must meet CRC-59 |
| **PS-OQ-13** Granularity of producing-configuration recording; invalidate or weaken | Disposed with EK-OQ-09 |

### 13.9 Open questions routed onward

#### New questions arising from STEP-04

| ID | Question | Routed to | Notes |
| --- | --- | --- | --- |
| RJ-OQ-01 | How are record order, effective-from-recording, history preservation, and act-time versus standing evaluation realized? | STEP-05 | DR-03, DR-10. Needed by CRC-24, CRC-41, CRC-60, CRC-61, CRC-63 |
| RJ-OQ-02 | How are actor kind, attribution integrity, and authentication of identity established and checked? | STEP-05, later implementation work | DR-07; HJC-21. Not a rule of this catalog |
| RJ-OQ-03a | **Representation-owned part.** How are formal-check results and findings of invalidity recorded and attributed? | STEP-05 | DR-09. The content a CRC-59 finding must state is fixed by CRC-59. Section 9.4.3 states their standing |
| RJ-OQ-03b | **Guidance-owned part.** What guidance helps actors state the required content of a formal-check result or finding, and type a bare assertion correctly? | STEP-06 | DM-08 |
| RJ-OQ-04 | What is the scope vocabulary, and how are containment and as-of grant-chain reconstruction computed? | STEP-05 | DR-08; HJC-25 |
| RJ-OQ-05 | Practice: who holds conferral scopes; project establishment and root practice (STEP-04 fixes the protocol effect, STEP-06 owns the practice); independence practice for small teams; configuration-statement conventions; designating criteria as decidable; grant review and re-conferral after a cascade | STEP-06 | DM-02, DM-03, DM-04, DM-05, DM-06, DM-07 |
| RJ-OQ-06 | Burden of detection; whether blocking-eligible rules are better blocked or detected and flagged; adoption of non-human verification | STEP-07 (pilot) | DP-01, DP-02, DP-06. Pilot evidence, not requirements |
| RJ-OQ-07 | Do teams need protocol-effective terms on authorizations or grants? | STEP-07; MOD-W Moderator | DP-03; GC-OQ-09 |
| RJ-OQ-08 | Do pilot findings require reclassification of any entry? | STEP-07, then an accepted revision | DP-05; BDR-16 |
| RJ-OQ-09 | Is flagging and escalation the right strength for conflicted conferral and revocation? | STEP-07 (owner) | DP-04. Governance and review need: targeted Tech Lead review of the pilot evidence before any strengthening is proposed. The Tech Lead is not a step owner |
| RJ-OQ-10 | How is source identity compared? | STEP-05 | DR-06. A separate skill-name and version configuration element is **not** routed here as an open research question. UAD4-11 decided that skills are instructions, and BDR-16 requires an accepted revision of this artifact to change it. `research/topics/agent-skills-and-protocol-relationship.md` remains available as input to such a revision |
| RJ-OQ-11 | Are the five never-a-correction kinds adequate? | STEP-07 | DP-05 |
| RJ-OQ-12 | For a consequential commitment that is not an acceptance, what enforcement detail applies when it relies under assumption without the required authorization? | STEP-06 (practice). Any rule would be a later accepted revision of semantics, Moderator-visible | CRC-19 covers acceptances only. STEP-03 Section 9.2 reading recorded (Section 3.3). No rule is added here |

#### Inherited questions that remain with their owners, not duplicated here

| ID | Question (short) | Routed to |
| --- | --- | --- |
| GC-OQ-04 | Representation of derived conditions, item identity across change, closure computation | STEP-05 |
| GC-OQ-05 | Representation of collective identities and work-assignment relations (not role-position appointment, Section 10.2.5) | STEP-05 |
| GC-OQ-06 | Evidence categories and thresholds per gate; who holds scopes; role positions | STEP-06 |
| GC-OQ-07 | Independence practice for teams of one or two (DM-04) | STEP-06 |
| GC-OQ-08 | Burden and friction measures | STEP-07 |
| GC-OQ-10 | Whether Product Moderator authority is reviewable or overridable | MOD-W Moderator; STEP-06 |
| GC-OQ-12 | Whether STEP-03 transferability observations change MW-ADAPT-001 standing | STEP-08; MOD-W Moderator |
| EK-OQ-01 | Evidence categories per gate; customer-evidence sufficiency | STEP-06; STEP-07 |
| EK-OQ-11, EK-OQ-12, EK-OQ-15 | Explicit versus derived conditions; item identity across change; role-specific and machine views | STEP-05 |
| PS-OQ-11 | External evaluator contract | Deferred (D8) |
| Agent-skills H-A, H-B, H-C | Disposition of skills | STEP-05 (H-C); STEP-08 |
| Product OQ-1, OQ-6 | Product Skeptic and Advocate roles; speed versus rigor | Not addressed (NG-4) |

### 13.10 Ownership preserved

**STEP-05 owns representation choices.** This artifact preserves STEP-05's ownership of representation for derived conditions, item identity across change, accepted-set closure computation, serialized state vocabulary, lifecycle graphs, and machine views. Each is a `DR-` item with the semantic requirement stated and the realization left open. The `A`, `S`, `H` evaluation kinds describe the question a rule asks, not how or when a representation stores or computes it.

**STEP-06 owns methodology.** This artifact preserves STEP-06's ownership of methodology templates, role charters, evidence-category thresholds, gate templates, examples, and practitioner guidance. Each is a `DM-` item. This artifact states no role charter, no gate template, no worked example, and no threshold.

| ID | Rule |
| --- | --- |
| BDR-18 | This artifact selects no representation and no methodology. Where a rule's shape is settled and its realization or parameters are not, the rule is catalogued and the remainder is a `DR-`, `DM-`, or `DP-` item owned by the step named. |

---

## 14. Undecided Architecture Declaration

Required by **MW-ADAPT-001** (`research/mod-w-transferability/adaptations.md`). Routes to the Tech Lead in addition to MOD-W Moderator review. After this declaration, Tech Lead or QA sampling for unlisted choices is expected before Moderator acceptance, with a sampling note in the review record (Section 14.4).

### 14.1 How this declaration was compiled

The declaration was compiled by an **audit pass over the finished draft** against the accepted upstream artifacts (`mod-w/product.md`, `mod-w/architecture.md`, `mod-w/domain-language.md`, `prod-w/protocol-semantics.md`, `prod-w/evidence-knowledge-model.md`, `prod-w/gate-challenge-revalidation-semantics.md`, and `mod-w/step-04.md` with its setup review).

**Working test.** A choice is declared if a reasonable alternative reading of the upstream artifacts would have produced a materially different boundary or catalog, **or** if it touches what is considered objectively checkable, what requires human judgment, what is a candidate for later validation, authority, actor identity, independence, evidence standing, revalidation, violation handling, or any element of a representation. Choices that only restate what upstream artifacts already state are treated as operationalization and are not declared.

**Limits, stated plainly.** The working test is this team's judgment. MW-OBS-010, MW-OBS-011, and MW-OBS-015 show that architecture-level choices are hard to see from inside the artifact that contains them, and each earlier step found choices that slipped past a self-audit. The Development Team **cannot certify** that it has found every such choice, **cannot classify its own choices as lower-level**, and cannot show that nothing slipped past, because it is the same actor as the producer. The **level** column is a proposal. The Tech Lead or QA determines both completeness and levels.

This step's boundary work has an extra hazard. The work is about classification, so a classification choice is the easiest kind to make silently. The audit pass therefore re-read every entry of Sections 6 and 7 for the question "would a reasonable reader have put this on the other side of the line?"

**Revision audit (v0.2).** QA sampling of v0.1 found choices that neither this audit pass nor the Tech Lead sampling had listed (QA4-01 to QA4-04). The revision declares them (UAD4-27 to UAD4-30, with UAD4-07, UAD4-13, UAD4-14, UAD4-15 revised) together with two further choices the recommended fixes introduced (UAD4-31, UAD4-32). Before submitting v0.2, the Development Team re-read every changed catalog entry, Section 10.2, and Section 9.4 for any new or changed choice about authority, independence, evidence standing, revalidation, or violation handling, and linked each to its declaration from the entry that applies it (Section 6.1). This re-read has the same limit as the original: the Development Team cannot certify completeness.

### 14.2 Declared decisions

Level scale as in STEP-02 and STEP-03: **A** = architecture-level candidate (touches what counts as checkable, authority, identity, independence, evidence standing, revalidation, violation handling, or representation; recommend Tech Lead review before acceptance); **M** = model-level (a choice within a defined space; recommend confirmation); **L** = low (organizing or completing an accepted principle; listed for visibility).

| ID | Decision made | What upstream left open | Reasoning, and input derived from | Level |
| --- | --- | --- | --- | --- |
| UAD4-01 | **What is objectively checkable** is defined by a three-part test (defined elements, record-only answer, no judgment inside) and an agreement corollary. A recorded designation is taken as given | STEP-01 Section 9.1 says "decided from the record alone, without interpreting the world." It does not say how to apply that to a condition | Gives the boundary a test that reviewers can apply and dispute. From: D6, STEP-01 Section 9, `mod-w/step-04.md` Scope and Tech Lead Recommendation 2 | **A** |
| UAD4-02 | **Conservative classification.** Where it is doubtful whether a condition is objective, it is classified as judgment | D6 warns against both under-governance and false automation, without a tie-break | Over-claiming objectivity lets a mechanical check pretend to decide a judgment. From: D6, GR-4 | M |
| UAD4-03 | **Composite conditions are split** into an objective core and a named residue. CR versus RJC is decided by what the rule requires of the record: the content-bearing record of a determination (RJC), or a record element, relation, or the validity facets of an act decided from record facts (CR), even where the act is a determination act (Section 5.1). A row joining both is RJC | Upstream tables list composite conditions as one row (EKO-04, EKO-05). The discriminator was not stated | Keeps the core from being presented as deciding the residue, and makes the Q5 test reproducible without reclassifying any row. From: STEP-02 Section 7.6, EKR-17, HJ-01 pairing | M |
| UAD4-04 | **Recorded designations are taken as given**, and their effectiveness conditions are themselves candidate rules | STEP-04 scope says "beyond recorded designations" without defining it | Lets a check use a materiality or checkability designation without judging it, while keeping designations challengeable. From: GCR-34, GCR-51 | **A** |
| UAD4-05 | **The recorded-judgment check** is limited to eight facets: existence, recorder identity, authority, capacity, required elements, timing, independence, direction | `mod-w/step-04.md` allows "an objective check may confirm that a judgment was recorded by an authorized actor" without enumerating what that can include | Bounds the middle pattern so it cannot grow into a check of substance. From: HJ pairings, GCO-08, GCO-11 | **A** |
| UAD4-06 | **Two-layer violation model.** Protocol consequence is fixed by source rules. Handling is seven categories. Blocking may prevent reliance on an act and never the record of it. No handling prevents an opposition or conservative act from being recorded | PS-OQ-10 asks "blocked, flagged, or escalated"; STEP-01 Section 6.1 leaves block-or-flag to the implementation | Keeps handling from changing effect, and keeps a blocking practice from suppressing dissent. From: PR-11, GCR-23, WD-2, D6 | **A** |
| UAD4-07 | **Standing of detection.** A detection result is a formal-check result, advisory, challengeable, and does not suspend a trigger it creates. A finding that an acceptance is invalid is recorded by an AUTH-V holder or a human AUTH-G holder and is the TRG-6 event, **provided it meets the content and non-human bounds declared at UAD4-29** | STEP-03 Section 4.7 makes "found invalid" a trigger without saying who finds or what a finding contains | Connects a validator to the authority model without selecting one. Applied at CRC-59 and Sections 9.4.3 and 9.4.5. From: PR-14, PR-15, EKR-39, GCR-23 | **A** |
| UAD4-08 | **Catalog membership.** The classification of all 61 OBJ, EKO, and GCO conditions (Section 6.3), including EKO-15 read with STEP-03 Section 9.2, GCO-28 and EKO-19 read with narrowed TRG-2, GCO-22 deferred to representation, and no condition out of catalog. CRC-19 invalidates an acceptance that relies under assumption without the required authorization. This step adds no rule for a consequential commitment that is not an acceptance, and routes it (RJ-OQ-12) | `mod-w/step-04.md` asks for classification; upstream tables label every condition objective. STEP-03 Section 9.2 reads "progression" more widely than the acceptance condition it ties invalidity to | Membership is the main product of this step. Narrowing the claim avoids adding rule surface beyond the accepted acceptance-condition source. From: Section 3.3 | **A** |
| UAD4-09 | **Evidence elements are split.** Class-defining elements (identified source, not a concurrence record where the record distinguishes sourced evidence from a concurrence or agreement record, target and polarity, attempt record, derived-from inputs) make an ineffective _designation_ when absent. Descriptive elements (category, basis, limitations, times) are flagged | EKR-14 says "expected"; EKO-05 says "records." STEP-01 PR-10 says required content invalidates | Reads the two together. Conservative invalidation (Tech Lead Recommendation 4). From: EKR-13, EKR-14, EKO-05, PR-10 | **A** |
| UAD4-10 | **Timing of presumed materiality.** An item designated material at creation must carry class-specific provenance at creation. An item presumed material by a later citation is flagged. A non-material designation without rationale is ineffective | EKR-08 and EKR-35 do not say when the obligation attaches. STEP-03 Section 5.4 lists no validity condition for it | Prevents a later citation from retroactively invalidating an earlier valid creation, and keeps STEP-03's list of validity conditions unchanged. From: EKR-08, EKR-35, INV-10 | **A** |
| UAD4-11 | **Producing-configuration granularity and consequence.** Five facets, "not determinable" permitted, no finer level, skills are instructions. An absent statement is flagged and not invalidating. A gate may require more. Class-defining provenance is a different matter | EK-OQ-09 | Section 11.4 | **A** |
| UAD4-12 | **Lineage granularity.** Immediate derivation and source comparability. Not passage, field, or transformation level | EK-OQ-09 | Passage-level lineage would be a practice and representation choice. From: EKR-11 | M |
| UAD4-13 | **Grants.** Granting is an act. Conferral requires a human holding AUTH-G whose conferral scope covers what is conferred. Non-root grants chain to a root, with the root structure declared at UAD4-27. A conferral scope is a scope of AUTH-G, not a fifth class. **Reading of PR-04 and GCR-08:** those rules prohibit authority by mere transitivity, inheritance, delegation, role label, or work assignment. A conferral under CRC-61 is not delegation and not class-confers-class. It creates a new explicit grant by a human AUTH-G holder whose explicit conferral scope authorizes it. Holding a class confers nothing. This is a STEP-04 operationalization of GC-OQ-02 and not a direct conflict, and it is Moderator-visible because accepted upstream text did not name conferral scope (Section 3.3). **Terms:** work assignment (provenance, no authority) is distinct from grant-bearing role-position appointment (a conferral) (Section 10.2.5) | PS-OQ-05; PS Section 4.3 says "who conferred it" without saying who may. PR-04 and GCR-08 do not name conferral scope | Section 10.2.1. From: PR-01, PR-02, PR-04, PR-05, GCR-08, STEP-03 Section 5.2 (gate-definition scope), HA-1, HA-2 | **A** |
| UAD4-14 | **Self-conferral is invalid** for every later grant, including through a collective, a role position, or a cycle. The establishing identity as a root grantee, for the establishing act's own grants only, is not self-conferral (UAD4-27). A grant-bearing role-position appointment is a conferral. Conferral or revocation by a conflicted producer is flagged and escalation-eligible, not invalid, with the chain-depth and standing-to-challenge scope declared at UAD4-28 | GC-OQ-02; STEP-03 Section 8.6 interim | Section 10.2.3. From: GCR-05, GCR-08, GCR-40 | **A** |
| UAD4-15 | **Grants take effect when recorded.** Revocation is prospective. Revocation is by the grantee or by a human AUTH-G holder whose conferral scope covers the grant. Acts relying on a revoked grant after revocation are invalid. The cascade to downstream grants is declared at UAD4-30 | GC-OQ-02 | Extends GCR-47 from authorizations, waivers, confirmations, and closures to grants. From: GCR-47, PR-01 | **A** |
| UAD4-16 | **Non-human AUTH-V.** Permitted for criteria designated decidable from the record. The verification records the elements examined and its evaluation point. The designation is a challengeable judgment | GC-OQ-03; GCR-11 interim | Section 10.3.1. The reproducibility element goes beyond OBJ-13. From: PR-14, GCR-10, GCR-11 | **A** |
| UAD4-17 | **Absent elements.** Where a source rule makes an element a validity condition, absence is a violation. Where the source supplies a conservative default, it applies and the matter is recorded as unresolved. Otherwise unresolved with no conclusion | Upstream does not say how a check treats a missing element | Prevents absence from reading as satisfaction. From: PR-10, GCR-07, GCR-34, GCR-52 | **A** |
| UAD4-18 | **Assumption-rooted identification** is a candidate rule with flagging handling. Validity force only through CRC-19 | GC-OQ-11 | Preserves STEP-03's list of validity conditions. From: GCR-66, STEP-03 Section 5.4 | M |
| UAD4-19 | **Never-a-correction tripwires** are a candidate rule. The correction _designation_ is ineffective. The change stands as a supersession | GC-OQ-11 | A confirmation does not rescue a never-correction change. From: GCR-53, GCR-52 | M |
| UAD4-20 | **Protocol-effective terms are not adopted.** Review events stay non-effective. Terms on grants likewise | GC-OQ-09 | Adoption would revise GCR-42 and GCR-67. From: GCR-42, GCR-67 | **A** |
| UAD4-21 | **Defective conservative acts** stay visible. A defective refusal or deferral is read as a recorded attempt for CRC-18, to prevent form defects from scrubbing refusals | GCR-19 requires reasons; PR-10 makes missing content invalid. Neither says what a defective refusal does to the standing record | Anti-shopping intent of GCR-39. From: PR-11, GCR-39 | **A** |
| UAD4-22 | **Re-typing and authority gaps.** An output lacking required authority is re-typed by rule (CRC-04). An authority gap is recorded as unresolved and escalation-eligible (CRC-32) | EKR-04 states re-typing as a recording rule. GCR-40 states the gap as a visible condition | Makes both checkable. From: EKR-04, GCR-40 | M |
| UAD4-23 | **Evaluation kinds and blocking eligibility.** Act-time, standing, historical. Blocking-eligible if act-time with all inputs in the record. Where an input is a derived condition, eligibility holds only if the representation makes it available at the evaluation point (CRC-18, CRC-19). Blocking may prevent reliance on an act and never the record of it | D6 says implementations may block or flag, without saying which rules can be blocked | Describes the question a rule asks. Not a storage or timing choice | M |
| UAD4-24 | **Newly named judgments.** HJC-21 to HJC-26 are named as the judgments at the edge of a check. GCO-08 pairs HJ-05 and EKJ-14 residual risk | STEP-01 Section 9.3 lists HJ-05 with no paired check | Makes the limits of CRC-01, CRC-03, CRC-15, CRC-38, CRC-39, CRC-60 to CRC-64 explicit. From: BDR-02, GCJ-03 | M |
| UAD4-25 | **Derived groupings.** Catalog entries and judgment entries are groupings over accepted IDs. CRC-22 is a composite over other entries | Accepted tables list conditions one by one | Avoids duplicating the same decidable test. Sources remain listed (Section 15) | L |
| UAD4-26 | **Visible exception semantics.** "Satisfied under exception" is a distinct result. CRC-13's verifier-independence requirement is waivable as a gate requirement. Its requirement that the acceptor did not perform the verification is not. **Any gate requirement waivable under STEP-03 Section 9.4 can be covered by a valid CRC-20 exception**, including gate-required configuration facets and gate-defined stricter treatment (response) requirements. The six non-waivable conditions cannot (CRC-22) | GCR-46 lists six non-waivable conditions. GCR-10 makes verification a member of the accepted set. STEP-03 Sections 5.5 and 9.4 make stricter response rules waivable | Keeps CRC-07 non-waivable. Replaces a closed list in CRC-22 that disagreed with Section 11.4. From: GCR-06, GCR-10, GCR-46 | M |
| UAD4-27 | **One establishing act; root grants; limited root-grantee case** (added in v0.2 for QA4-01). A PROD-W project has exactly one protocol-establishing act for its authority chain. It precedes every other recorded act of the project. Root grants arise only from it, and every other grant chains acyclically to one. The establishing identity may be a root grantee only for grants recorded by the establishing act itself. CRC-62 does not treat that case as self-conferral, and applies in full to any later grant, including a later grant by the establishing identity to itself. A later act marked as establishing or root is not a second root. Root legitimacy remains HJC-22 | PS-OQ-05 and STEP-03 Section 8.6 say nothing about roots. v0.1 defined a root as an act "at project establishment, before any act relies on it" without saying how many there are, who may record one, or how a root grantee relates to CRC-62 | Section 10.2.2. Prevents root minting through a later "establishing act," and keeps a team of one possible. Establishment practice stays DM-03. Record order stays DR-03. From: PR-01, PR-02, PR-05, GCR-40, HA-1, HA-2 | **A** |
| UAD4-28 | **Conflicted conferral covers the whole chain and challenger standing** (added in v0.2 for QA4-02). CRC-64 evaluates every link of the CRC-61 chain relied on, not only the immediate conferrer. It also covers revocation or narrowing, including by cascade, of a grant held by any actor with standing to challenge the relevant item or set, whether or not a challenge is open. Handling stays F and E, not I. DP-04 names the evidence, trigger, and owner for reconsidering F/E versus I | v0.1 tested the immediate conferrer only, and flagged revocation only against a holder with an open challenge | Section 10.2.3. Closes a one-hop laundering path and a standing-suppression path without invalidating, because the artifact leaves the strength of handling to pilot evidence (DP-04). From: GCR-05 (by analogy), GCR-40, GCR-23 | **A** |
| UAD4-29 | **A CRC-59 finding must be a formal-check result; non-human findings are bounded** (added in v0.2 for QA4-03). A finding that an acceptance is invalid names the rule or rules violated, states the evaluation point, and identifies the record elements examined. A bare assertion is not a CRC-59 finding and does not trigger TRG-6. It is typed as a challenge, counter-evidence, advisory finding, or revalidation request. A non-human AUTH-V holder may record a CRC-59 finding only where each rule asserted violated is decidable from the record (CRC-15 bound). A human AUTH-G finding states the same elements and is not limited by that bound where the human exercises authorized judgment. DR-09 keeps recording and attribution | STEP-03 Section 4.7 makes a finding a TRG-6 event without stating its content. v0.1 required none | Sections 9.4.3, 9.4.5, 10.3.1. A finding is cheaper than a revalidation request, which needs a stated basis, but has a stronger effect. This keeps detection standing and requires a reproducible basis. From: PR-14, PR-15, GCR-11, GCR-23, EKR-39 | **A** |
| UAD4-30 | **Revocation cascades prospectively** (added in v0.2 for QA4-04). Grants downstream of a revoked or narrowed grant fall prospectively with the chain, to the extent the revoked or narrowed grant no longer covers what they confer. They validate no act after the recording unless independently re-conferred through a valid chain to a root. Acts performed while the whole chain was effective stand (GCR-47). Renunciation cascades in the same way | v0.1 declared prospective revocation but not what happens to grants the revoked holder had conferred. Two readings were open | Section 10.2.4. CRC-61 makes an effective chain to a root part of a grant's validity, so a cut chain cannot support a downstream grant. From: GCR-47, PR-01 | **A** |
| UAD4-31 | **Direction is read from a closed list; an unlisted closure kind is unresolved** (added in v0.2 for QA4-05). CRC-09 reads the direction of a closure from CRC-27's three closure kinds (authority closure and challenger resolution of a challenge against a member of the set are favorable; withdrawal of the target with no successor is conservative). A closure whose kind is not listed, or is not named in the record, has direction recorded as unresolved and the matter is escalation-eligible. It is not interpreted | GCR-05 says "closure of a challenge in the set's favor" without saying which closure kinds favor the set | Section 6.2, CRC-09. Makes the independence rule reproducible from the record. From: GCR-05, GCR-18, GCR-26 | **A** |
| UAD4-32 | **Record forms checked by CRC-52 and CRC-45** (added in v0.2 for QA4-05). CRC-52 checks that a closure names each open reason and records a disposition for each. Adequacy is HJC-16. CRC-45 checks the recorded evaluative designation and whether the record presents the claim under an observed-fact or evidence-only form. Whether content is evaluative or warranted is HJC-18 | EKR-28 and GCR-59 to GCR-63 do not say which record form is checked | Section 6.2. Satisfies the agreement corollary (Section 4.3) without changing either entry's classification. From: EKR-28, GCR-59, GCR-61 | M |

### 14.3 Recommended Tech Lead priority

If review time is limited:

1. **What counts as checkable:** UAD4-01, UAD4-04, UAD4-05, UAD4-08. These decide the line the whole step draws.
2. **Violation handling and the standing of detection:** UAD4-06, UAD4-07, UAD4-17, UAD4-21, UAD4-29.
3. **Authority grants and verification:** UAD4-13, UAD4-14, UAD4-15, UAD4-16, UAD4-27, UAD4-28, UAD4-30, UAD4-31. These add rules in areas STEP-03 routed here and decide whether authority can expand through conferral or through a verifier.
4. **Evidence standing and provenance:** UAD4-09, UAD4-10, UAD4-11.
5. Then UAD4-20 (time terms), UAD4-26, and UAD4-32.

Options for each, offered without preference: confirm as operationalization; promote to an architecture decision; return for revision. Several (UAD4-01, UAD4-06, UAD4-13) govern behavior that `mod-w/architecture.md` does not state. As with STEP-02's and STEP-03's declared choices, the rules would then live only in this product artifact. Whether any should be promoted is a Tech Lead and Moderator question.

**Recommendation stated for the Moderator.** The Tech Lead revision brief recommends promoting UAD4-13, UAD4-14, and UAD4-15, as revised, to architecture decisions or decision records after STEP-04 acceptance. They define core authority-chain semantics: grant creation, root establishment, self-conferral, conflicted conferral, and revocation cascade. Their revised content is partly carried by UAD4-27, UAD4-28, and UAD4-30. Those would need to travel with them if promoted. **The Moderator decides promotion.** This revision does not edit `mod-w/architecture.md` and records no decision.

### 14.4 Sampling targets for the independent pass

For the Tech Lead or QA sampling MW-ADAPT-001 expects before acceptance. These are where the Development Team believes unlisted choices are most likely to remain.

| Area | Probe |
| --- | --- |
| **What counts as checkable** | Pick any entry marked CR and ask whether two competent evaluators could disagree on a record. Pick any entry marked RJC and ask whether it reaches the substance of the judgment. Look for entries where the "decision test" depends on interpreting a source |
| **Authority** | For every act in Sections 6 and 10: which grant does it need? Find any act that appears to need none. Check that the conferral scope (CRC-61) does not give AUTH-G a power STEP-01 did not name, and that the PR-04 and GCR-08 reading (Section 3.3) holds. Check that "human-only conferral" cannot be bypassed by a grant-bearing role-position appointment. Check that a project cannot acquire a second root, and that the strict first-act rule (Section 10.6) is not unworkable. Check that a revoked conferrer's appointees cannot keep acting (CRC-63) |
| **Independence** | Check CRC-62 and CRC-64 for a path by which an actor confers authority on a proxy, directly or several links up the chain, and then performs a favorable act, or revokes a challenger's standing before a challenge is recorded. Check CRC-15 for a non-human verifier that is the producer under another identity |
| **Evidence standing** | Check the class-defining versus descriptive split (UAD4-09) for any element that is placed on the wrong side. Check that a detection result cannot be presented as evidence, corroboration, or acceptance |
| **Revalidation** | Check CRC-59 and UAD4-07, UAD4-29: can a false finding of invalidity create a requirement cheaply, now that a finding needs a rule, evaluation point, and elements examined, and a non-human finding needs a decidable rule? Check CRC-51 and CRC-52 for any reason that can be dropped |
| **Violation handling** | Check that no handling in Section 9 prevents an opposition or conservative act from being recorded. Check that "blocking-eligible" cannot be read as "must block" |
| **Hidden representation choices** | See the probe below |

#### Hidden representation choices: the Development Team's own probe

| Term or device | Where it could carry a representation choice | Treatment here |
| --- | --- | --- |
| "Record," "evaluation point," "recorded time," "order" | A store, a log, an ordering guarantee | Defined semantically (Section 4.1). Realization deferred (DR-03, DR-10) |
| "Chain to root," "acyclic," "closure," "citation chain," "establishing act precedes every other act," "falls with the chain" | A graph structure, a graph store, a log order | Described as relations over recorded items and as semantic ordering. Computation and order deferred (DR-01, DR-03, DR-08) |
| "Handling category" (invalidating, blocking, flagging) | An enforcement mechanism or a state value | Stated as semantic effects (BDR-11). No value set |
| "Formal-check result" | A record type, or a value set | Defined as a semantic notion. What a result may state is semantic and not a selected value set (BDR-11). The content a CRC-59 finding must state is fixed. How it is recorded is DR-09 |
| "Actor kind" | An identity attribute | Treated as a recorded designation. Authentication deferred (DR-07) |
| "Conferral scope" | A scope vocabulary | A scope of AUTH-G like STEP-03's gate-definition scope. No vocabulary. DR-08 |
| Five configuration facets | A structured record | The facets are PR-27's. Content is stated, not structured |
| Evaluation kinds A, S, H | A distinction between event and state storage | Describes the question the rule asks (Section 5.4), not where it is stored |
| Identifier scheme and table columns | A serialized form | Expository devices for review (Section 1.2) |

### 14.5 Decisions considered and not made

The following were considered and deliberately left open. This is not a declaration that nothing else was decided.

- Any representation, schema, storage model, serialization, or condition and state name, including for the handling categories.
- Any validator, enforcement mechanism, user interface, or tooling, including whether any rule is blocked in practice.
- A fifth authority class or a lesser acceptance class (rejected for now; UAD3-23, UAD3-24, UAD4-13).
- A definition of AI actor identity beyond PR-27, including whether a shared accountable position is sameness (PS-OQ-06 remainder).
- Which people hold conferral, gate-definition, or validation scopes, or any role catalog (DM-02).
- Evidence categories, thresholds, or customer-evidence sufficiency (DM-01).
- Protocol-effective terms (UAD4-20).
- Invalidating, rather than flagging, conflicted conferral or revocation (considered at the revision and left to pilot evidence; DP-04, UAD4-28).
- A rule for a consequential commitment that is not an acceptance, and an extension of CRC-19 to it (RJ-OQ-12).
- Any root grant, or any establishing-identity self-grant, outside the single establishing act (UAD4-27).
- Any edit to `mod-w/architecture.md`, including promotion of UAD4-13 to UAD4-15 (the Moderator decides; Section 14.3).
- An override hierarchy among gate authority holders (GC-OQ-10).
- Reclassification of any accepted STEP-01, STEP-02, or STEP-03 condition, other than the readings of Section 3.3.
- Anything about external evaluator contracts (PS-OQ-11), the agent-skills hypotheses beyond the routing in Section 11.2, or speed-versus-rigor tradeoffs.

### 14.6 Note for the MW-ADAPT-001 re-evaluation

MW-ADAPT-001 was re-evaluated at STEP-02 and applied with independent sampling at STEP-03. This step is the first whose subject is classification itself. The Development Team's report on the first half (did the declaration produce findings) is that the v0.1 audit pass produced twenty-six declared choices, of which sixteen were self-assessed level A. The second half (did anything slip past) it cannot answer, for the reason in Section 14.1. The record since v0.1 bears on it: QA sampling found four areas of unlisted choice (QA4-01 to QA4-04) that the audit pass and the Tech Lead sampling did not. The revision declares them, plus two further choices the recommended fixes introduced. **v0.2 therefore carries thirty-two declared choices, of which twenty-one are self-assessed level A.** This is offered to the Moderator as evidence for the MW-ADAPT-001 re-evaluation. The Development Team proposes no observation and edits no register. The Moderator decides separately. The tension to watch is that a boundary artifact must make dozens of small classification calls, so its declaration lists categories of choice (UAD4-01, UAD4-08) and not every row. That is why Section 6.3 shows every row, so a reviewer can sample classification at the row level.

---

## 15. Traceability to STEP-01, STEP-02, and STEP-03 Identifiers

### 15.1 Rule-ID coverage

Every accepted rule, action, and trigger identifier appears below with its disposition. **CR** is a catalogued rule, **OOC** is out of catalog with the reason in Section 6.5, and **DR** is deferred. Judgment identifiers are in Section 15.2.

#### STEP-01: PR and ACT

| IDs | Disposition | Entries |
| --- | --- | --- |
| PR-01, PR-02, PR-03 | CR | CRC-02, CRC-60, CRC-61 |
| PR-04 | CR, read as in Section 3.3: no authority by mere transitivity, inheritance, delegation, role label, or work assignment. Conferral is a new explicit grant under a conferral scope (UAD4-13). Moderator-visible reading tension | CRC-02, CRC-60, CRC-61, CRC-62 |
| PR-05 | CR | CRC-03, CRC-61 |
| PR-06, PR-07, PR-08 | CR | CRC-01 |
| PR-09 | CR | CRC-35 |
| PR-10, PR-11 | CR (consequence of every entry) | Section 9; CRC-01, CRC-22, CRC-41 |
| PR-12 | OOC | Section 6.5; CRC-21, CRC-22 |
| PR-13 | CR | CRC-21 |
| PR-14 | CR | CRC-05, CRC-13, CRC-15, CRC-59 (non-human bound) |
| PR-15 | CR | CRC-04, CRC-15 |
| PR-16, PR-17, PR-18, PR-21 | CR | CRC-07, CRC-08 |
| PR-19 | CR | CRC-12, CRC-13 |
| PR-20 | CR where the record distinguishes concurrence from evidence | CRC-36; HJC-12 |
| PR-22, PR-23 | CR | CRC-04; BDR-17 |
| PR-24 | OOC | Section 6.5; CRC-02 |
| PR-25 | OOC | Section 6.5; BDR-07 |
| PR-26 | CR | CRC-51 |
| PR-27 | CR | CRC-07, CRC-39 |
| PR-28 | CR | CRC-07, CRC-12, CRC-13 |
| ACT-01 | CR | CRC-34, CRC-35 |
| ACT-02 | CR | CRC-36, CRC-37, CRC-38 |
| ACT-03 | CR | CRC-26 |
| ACT-04 | CR | CRC-05, CRC-13, CRC-15 |
| ACT-05 | CR | CRC-16, CRC-21, CRC-22 |
| ACT-06 | CR | CRC-30 |
| ACT-07 | CR | CRC-04, CRC-16, CRC-48 |

#### STEP-02: EKR and TRG

| IDs | Disposition | Entries |
| --- | --- | --- |
| EKR-01, EKR-07 | CR | CRC-34 |
| EKR-02 | OOC | Section 6.5; BDR-11 |
| EKR-03 | CR | CRC-01 |
| EKR-04 | CR | CRC-04, CRC-57 |
| EKR-05, EKR-09 | CR | CRC-33, CRC-41 |
| EKR-06 | CR (clearing); judgment (weighing) | CRC-33; HJC-09 |
| EKR-08 | CR | CRC-35 |
| EKR-10, EKR-31 | CR | CRC-42 |
| EKR-11 | CR | CRC-38 |
| EKR-12 | CR | CRC-39 |
| EKR-13, EKR-15, EKR-16, EKR-17 | CR | CRC-36 |
| EKR-14 | CR | CRC-36, CRC-37 |
| EKR-18 | OOC | Section 6.5 |
| EKR-19 | OOC | Section 6.5; BDR-14 |
| EKR-20 | CR | CRC-04 |
| EKR-21 | CR | CRC-43 |
| EKR-22 | CR (recorded assumptions); OOC (unrecorded) | CRC-47; Section 6.5 |
| EKR-23 | CR | CRC-47 |
| EKR-24, EKR-25 | CR | CRC-46 |
| EKR-26, EKR-27 | CR | CRC-44 |
| EKR-28 | CR (designation); judgment (content) | CRC-45; HJC-18 |
| EKR-29 | CR | CRC-48 |
| EKR-30 | CR | CRC-18 |
| EKR-32 | CR | CRC-06, CRC-40 |
| EKR-33, EKR-34 | CR | CRC-49, CRC-40 |
| EKR-35, EKR-36 | CR | CRC-35, CRC-49, CRC-50 |
| EKR-37, EKR-38, EKR-39 | CR | CRC-51, CRC-52 |
| EKR-40 | DR | CRC-54; DR-04 |
| EKR-41 | OOC (restated and enforced through BDR-05 and BDR-14; preserved, not superseded) | Section 6.5; BDR-05, BDR-14 |
| TRG-1 | CR | CRC-51; CRC-55, CRC-56 (supersession consequence); CRC-58 |
| TRG-2 | CR (as narrowed) | CRC-29, CRC-51 |
| TRG-3 | CR | CRC-51, CRC-57 |
| TRG-4 | CR | CRC-51, CRC-55, CRC-56, CRC-57 |
| TRG-5 | CR | CRC-49, CRC-51 |
| TRG-6 | CR (a finding is the event only where it meets CRC-59) | CRC-51, CRC-59 |

#### STEP-03: GCR

| IDs | Disposition | Entries |
| --- | --- | --- |
| GCR-01, GCR-04 | CR | CRC-06, CRC-07 |
| GCR-02, GCR-03 | CR | CRC-07 |
| GCR-05 | CR (CRC-09: closed list of act kinds, closure kind read from CRC-27, UAD4-31). By analogy for CRC-64 (UAD4-14, UAD4-28) | CRC-09, CRC-64 |
| GCR-06 | CR | CRC-10 |
| GCR-07 | CR | CRC-14 |
| GCR-08 | CR, read as in Section 3.3: delegation and work assignment convey no authority; a grant-bearing role-position appointment is a conferral under CRC-61 and CRC-62. Moderator-visible reading tension | CRC-07, CRC-62 |
| GCR-09 | CR (presence); judgment (truth) | CRC-11; HJC-12 |
| GCR-10 | CR | CRC-13, CRC-15 |
| GCR-11 | CR | CRC-15 |
| GCR-12, GCR-13 | CR | CRC-16 |
| GCR-14, GCR-68 | CR | CRC-17 |
| GCR-15 | CR | CRC-12 |
| GCR-16 | CR | CRC-22 |
| GCR-17, GCR-39 | CR | CRC-18 |
| GCR-18 | CR | CRC-04, CRC-09, CRC-25 |
| GCR-19 | CR | CRC-25 |
| GCR-20 | CR (scope and inheritance); OOC (sufficiency not truth) | CRC-21, CRC-42; Section 6.5 |
| GCR-21 | CR | CRC-46 |
| GCR-22 | CR | CRC-04 |
| GCR-23, GCR-24 | CR | CRC-26 |
| GCR-25, GCR-26 | CR | CRC-09, CRC-27 |
| GCR-27 | OOC | Section 6.5 |
| GCR-28 | CR | CRC-28 |
| GCR-29 | DR | CRC-54; DR-04 |
| GCR-30, GCR-31 | CR | CRC-29 |
| GCR-32 | CR | CRC-30 |
| GCR-33 | CR | CRC-19 |
| GCR-34 | CR | CRC-50 |
| GCR-35 | CR (clearing); DR (derivation) | CRC-33, CRC-54 |
| GCR-36, GCR-41 | CR | CRC-33 |
| GCR-37 | CR | CRC-31 |
| GCR-38 | CR | CRC-07, CRC-18 |
| GCR-40 | CR (authority gap, CRC-32); new rules built on it, not restatements (CRC-61, CRC-62, CRC-64; UAD4-13, UAD4-14, UAD4-27, UAD4-28) | CRC-32, CRC-61, CRC-62, CRC-64 |
| GCR-42 | CR | CRC-19, CRC-23 |
| GCR-43 | CR | CRC-23 |
| GCR-44 | CR | CRC-23, CRC-47 |
| GCR-45 | CR | CRC-20 |
| GCR-46 | CR | CRC-10, CRC-20 |
| GCR-47 | CR (extended to grants, with the prospective cascade of CRC-63; UAD4-15, UAD4-30) | CRC-19, CRC-24, CRC-60, CRC-61, CRC-63 |
| GCR-48 | CR | CRC-20, CRC-23 |
| GCR-49, GCR-54, GCR-55 | CR | CRC-57, CRC-58 |
| GCR-50, GCR-51, GCR-52 | CR | CRC-55 |
| GCR-53 | CR | CRC-56 |
| GCR-56 | CR | CRC-57 |
| GCR-57 | CR. GCR-57 states the acceptor's own withdrawal. A finding by someone else, its recorders, its required content, and the non-human bound are STEP-04 declared choices (UAD4-07, UAD4-29), not restatements of GCR-57 | CRC-59 |
| GCR-58, GCR-62 | CR | CRC-51 |
| GCR-59, GCR-60, GCR-61, GCR-63 | CR. Closure is read as naming and disposing of each open reason (record form; UAD4-32). Adequacy is HJC-16. A TRG-6 requirement from a CRC-59 finding closes by Tier 1 reaffirmation (GCR-60) | CRC-52 |
| GCR-64 | CR | CRC-46 |
| GCR-65 | CR | CRC-46, CRC-56 |
| GCR-66 | CR | CRC-53 |
| GCR-67 | OOC | Section 6.5 |

### 15.2 Judgment-ID coverage

| Source | Judgments | Entry |
| --- | --- | --- |
| STEP-01 HJ | HJ-01 | HJC-01 |
| | HJ-02 | HJC-03 |
| | HJ-03 | HJC-05 |
| | HJ-04 | HJC-07 |
| | HJ-05 | HJC-08 |
| | HJ-06 | HJC-10 |
| | HJ-07 | HJC-12 |
| | HJ-08 | HJC-09 |
| | HJ-09 | HJC-14 |
| | HJ-10 | HJC-16 |
| STEP-02 EKJ | EKJ-01 | HJC-03 |
| | EKJ-02 | HJC-01 |
| | EKJ-03 | HJC-02 |
| | EKJ-04 | HJC-12 |
| | EKJ-05 | HJC-05 |
| | EKJ-06 | HJC-10 |
| | EKJ-07 | HJC-11 |
| | EKJ-08 | HJC-06 |
| | EKJ-09 | HJC-13 |
| | EKJ-10 | HJC-04 |
| | EKJ-11 | HJC-16 |
| | EKJ-12 | HJC-07, HJC-08, HJC-09 |
| | EKJ-13 | HJC-17 |
| | EKJ-14 | HJC-08, HJC-18 |
| STEP-03 GCJ | GCJ-01 | HJC-01 |
| | GCJ-02 | HJC-07 |
| | GCJ-03 | HJC-08 |
| | GCJ-04 | HJC-14 |
| | GCJ-05 | HJC-15 |
| | GCJ-06 | HJC-13 |
| | GCJ-07 | HJC-04 |
| | GCJ-08 | HJC-16 |
| | GCJ-09 | HJC-12 |
| | GCJ-10 | HJC-19 |
| | GCJ-11 | HJC-17 |
| | GCJ-12 | HJC-10, HJC-11 |
| | GCJ-13 | HJC-01 |
| | GCJ-14 | HJC-20 |

### 15.3 Requirements

| Requirement | Where addressed |
| --- | --- |
| FR-3 Evidence requirements: checkable conditions and contextual sufficiency | Sections 6, 7, 11, 12.1; CRC-17, CRC-36, CRC-37; HJC-01, HJC-02 |
| FR-4 Self-approval invalid or detectably invalid | Sections 9, 10; CRC-07 to CRC-14, CRC-62; Section 10.5 |
| FR-6 Provenance: status, challenge history, acceptance history | Section 11; CRC-34, CRC-35, CRC-39, CRC-41, CRC-58 |
| G-3 Machine-readable protocol that validates objective rules while remaining human-reviewable | Sections 4 to 6, 9; BDR-01 to BDR-18 |
| PE-1 Material claims require traceable evidence | CRC-35, CRC-36, CRC-17 |
| PE-2 Agent agreement is not independent evidence | CRC-36; Section 9.8; BDR-14 |
| PE-3 Inference and fact remain distinct | CRC-44, CRC-45 |
| PE-4 / GR-4 No artificial precision | Sections 9.7, 11.4; BDR-14 |
| HA-1 / HA-2 Consequential decisions require authorized human judgment | Section 4.4; CRC-03, CRC-04, CRC-61; Section 10.2.1 |
| WD-2 Unresolved disagreement may remain visible | CRC-33; BDR-10; Section 12.4 |
| WD-6 Dependent decisions require revalidation | CRC-51, CRC-52, CRC-59; Section 12.6 |
| NG-1 / NG-2 No premature technology selection or tooling | Sections 1.3, 13.10; BDR-11, BDR-18 |

### 15.4 STEP-01 invalid action examples

| ID | Attempted action (short) | Entry | Handling |
| --- | --- | --- | --- |
| INV-01 | Producer accepts the gate depending on its claim | CRC-07 | I, B |
| INV-02 | Producer accepts as "Product Moderator" | CRC-07 | I, B |
| INV-03 | Producer's acceptance counted toward a two-acceptor requirement | CRC-08 | I |
| INV-04 | AI agent accepts a go/build gate | CRC-03 | I, B |
| INV-05 | Evaluator finding recorded as acceptance | CRC-04 | I, B |
| INV-06 | Gate treated as accepted for lack of objection | CRC-21 | I, B |
| INV-07 | QA verification recorded as acceptance | CRC-05 | I, B |
| INV-08 | Claim recorded with no acting actor | CRC-01 | I, B |
| INV-09 | AUTH-G holder for one gate accepts another | CRC-02 | I, B |
| INV-10 | Material claim with no evidence reference or provenance | CRC-35 | I at creation, F if presumed later |
| INV-11 | Agreement of three agents attached as corroborating evidence | CRC-36 | I, where the record distinguishes concurrence from evidence |
| INV-12 | Decision stays current after its evidence is withdrawn | CRC-51 | F, I (currency mark) |
| INV-13 | Record passes structure checks and is treated as protocol-conformant | BDR-07 | Every CRC entry is a protocol check. A pass on structure never substitutes |
| INV-14 | Producer challenges its own claim; independent-challenge requirement marked met | CRC-12, CRC-26 | I, X |
| INV-15 | Actor acts because a document names its role "Moderator" | CRC-02 | I, B |
| INV-16 | Recommendation recorded as a decision | CRC-48, CRC-04 | I (re-typed), B |
| INV-17 | Same role re-run under a stronger model recorded as the independent review | CRC-07, CRC-12, CRC-13 | I, X, where the record attributes both runs to one identity |

### 15.5 Architecture decisions

| Decision | Where operationalized |
| --- | --- |
| D1 Protocol semantics are normative | Sections 1.2, 3.1 |
| D2 Protocol, schema, and state are separate | Sections 1.3, 9.2 (BDR-11), 13.10 |
| D3 Knowledge classes are first-class | Sections 12.1 to 12.3; CRC-34, CRC-36, CRC-43, CRC-44 |
| D4 Authority is modeled separately from role labels | Section 10; CRC-02, CRC-07, CRC-60 to CRC-64 |
| D5 Disagreement is a preserved condition | Section 12.4; CRC-28, CRC-33; DR-04 |
| D6 Objectively checkable governance is separated from human judgment | Sections 4 to 9 |
| D7 Provenance and dependencies support revalidation | Sections 11, 12.6; CRC-49 to CRC-52, CRC-59 |
| D8 External evaluators are advisory unless explicitly granted authority | Sections 9.4.3, 10.4; BDR-17; CRC-04 |
| D9 Working product artifacts live under `prod-w/` | This artifact lives under `prod-w/` |

---

## 16. Acceptance-Check Traceability

The checks in `mod-w/step-04.md` are unnumbered. They are numbered here in the order they appear there. "Satisfied" below is the Development Team's statement of where each is addressed. It is not an acceptance. Review remains with the Tech Lead, QA, the Product Owner, and the Moderator.

| # | Acceptance check | Where addressed |
| --- | --- | --- |
| AC4-01 | `prod-w/rule-judgment-boundary.md` is added and is explicitly representation-neutral | This file; Sections 1.2, 1.3, 13.10, 14.4 (hidden-choice probe); BDR-11, BDR-18 |
| AC4-02 | Defines objective checkability as decidability from the available record without interpreting the world or judging sufficiency, persuasion, risk, materiality, acceptability, or substantive independence | Sections 4.1, 4.3, 5.2; BDR-01 |
| AC4-03 | Defines contextual human judgment as requiring authorized human interpretation of sufficiency, relevance, warrant, risk, materiality, acceptability, or substantive independence | Section 4.4; Section 7 |
| AC4-04 | Distinguishes a check that a judgment was recorded by an authorized actor from the judgment's substance | Section 4.5; Sections 8.1, 8.4; BDR-05 |
| AC4-05 | Defines candidate machine-checkable rule, detected violation, recorded-judgment check, unresolved condition, and deferred-to-representation categories | Sections 4.5 to 4.9; Section 6.6 |
| AC4-06 | Rule catalog traces every entry to STEP-01, STEP-02, or STEP-03 IDs (`PR-`, `ACT-`, `OBJ-`, `HJ-`, `EKR-`, `EKO-`, `EKJ-`, `TRG-`, `GCR-`, `GCO-`, `GCJ-`) | Sources column of Section 6.2; Section 7.2; Section 15 |
| AC4-07 | Classifies STEP-01 `OBJ-*`, STEP-02 `EKO-*`, and STEP-03 `GCO-*` as catalogued rules, recorded-judgment checks, deferred candidates, or out-of-catalog with rationale | Section 6.3 (61 rows). Section 6.5 for rules out of catalog |
| AC4-08 | Carries forward and disposes `GC-OQ-01`: which GCO conditions become catalog rules and the handling categories | Section 13.1; Section 6.3; Section 9.2 |
| AC4-09 | Carries forward and disposes `GC-OQ-02`: grant creation, scope, change, revocation, audit, self-conferral | Sections 3.3, 10.2 (10.2.2 to 10.2.5); Section 13.2; CRC-60 to CRC-64; DP-04; UAD4-13, UAD4-14, UAD4-15, UAD4-27, UAD4-28, UAD4-30. Creation (single establishing act), scope, change, revocation (prospective cascade), audit, and self-conferral are each disposed. The PR-04 and GCR-08 reading is Moderator-visible |
| AC4-10 | Carries forward and disposes `GC-OQ-03`: AI-held AUTH-V and verifier independence, without verification becoming acceptance | Section 10.3; Section 13.3; CRC-13, CRC-15; CRC-59 (non-human finding bound); Sections 9.4.3, 9.4.5; UAD4-16, UAD4-29 |
| AC4-11 | Carries forward and disposes `GC-OQ-09`: protocol-effective authorization terms | Section 12.8; Section 13.4 |
| AC4-12 | Carries forward and disposes `GC-OQ-11`: assumption-rooted identification and never-a-correction tripwires | Section 12.7; Section 13.5; CRC-53, CRC-56 |
| AC4-13 | Carries forward and disposes `EK-OQ-09`: configuration and lineage granularity; invalidate, weaken, flag, or judgment | Section 11; Section 13.6; CRC-38, CRC-39 |
| AC4-14 | Carries forward and disposes `EK-OQ-14`: which EKO conditions become rule candidates and how violations are handled | Section 13.7; Section 6.3 |
| AC4-15 | Preserves STEP-05's ownership of representation choices | Section 13.10; Section 6.6 (DR items); Section 14.4 (probe) |
| AC4-16 | Preserves STEP-06's ownership of methodology | Section 13.10; Section 6.6 (DM items) |
| AC4-17 | States that evaluator outputs, automated checks, verification records, and validator findings remain advisory or formal-check results unless granted authority | Sections 9.4.3, 10.4; BDR-13, BDR-17 |
| AC4-18 | States that mechanical detection may block, flag, escalate, or show invalidity only at the semantic level and must not decide contextual sufficiency or replace human gate acceptance | Sections 9.2, 9.8; BDR-14 |
| AC4-19 | States that absence of a mechanical check does not make a requirement optional | BDR-07; Sections 1.4, 9.5 |
| AC4-20 | Introduces no confidence scores, numeric sufficiency weights, or artificial precision | Section 9.7; BDR-14; Section 11.4 |
| AC4-21 | Includes the Undecided Architecture Declaration with catalog membership, violation handling, configuration granularity, authority grants, verifier independence, and derived groupings | Section 14 (UAD4-08, UAD4-06, UAD4-11, UAD4-13, UAD4-16, UAD4-25). Authority choices revised and added in v0.2: UAD4-13, UAD4-14, UAD4-15, UAD4-27, UAD4-28, UAD4-30. Detection and revalidation: UAD4-07, UAD4-29. Each is linked from the catalog entry that applies it (Section 6.1) |
| AC4-22 | Declaration followed by Tech Lead or QA sampling before Moderator acceptance, with a sampling note in the review record | **Not satisfiable by the Development Team.** Section 14.4 supplies targets. Section 2.3 records the v0.1 reviews and the pending targeted re-review and re-sample of v0.2. The sampling note belongs to the review record |
| AC4-23 | Remaining open questions routed without duplicating ownership | Section 13.9 (RJ-OQ-03a and RJ-OQ-03b split the original question into representation-owned and guidance-owned parts; RJ-OQ-09 owned by STEP-07 with Tech Lead review as a review need; RJ-OQ-10 aligned with BDR-16; RJ-OQ-12 added); Section 6.6 (DM-08, DP-04) |
| AC4-24 | No schema language, storage model, workflow engine, validator implementation, lifecycle graph, serialized state vocabulary, protocol transport, CLI, prompt format, or runtime integration selected | Sections 1.3, 13.10, 14.4, 14.5; BDR-11, BDR-18 |
| AC4-25 | Concrete transferability evidence encountered is proposed under research governance | Section 17.3 |
| AC4-26 | Final acceptance is not recorded until Phase 3a, 3b, and 3c have occurred or been waived | Section 2.3. The Development Team records no acceptance. Phase 3a re-review and 3b re-sample are pending, 3c is held, and 4a is the Moderator's |

---

## 17. Change Notes

### 17.1 Change notes

| Date | Version | Change | Reason |
| --- | --- | --- | --- |
| 2026-10-02 | 0.1 | Initial rule/judgment boundary and candidate rule catalog produced under STEP-04 | Fourth PROD-W product artifact. Extends STEP-01, STEP-02, and STEP-03 without modifying them. Twenty-six decisions beyond accepted upstream artifacts are declared in Section 14 under MW-ADAPT-001 and routed to the Tech Lead. |
| 2026-10-02 | 0.2 | **Narrow revision after QA return**, under the approved Tech Lead revision brief. Required: QA4-01 (one establishing act; root grants; limited root-grantee case), QA4-02 (conflicted conferral over the whole chain and challenger standing; DP-04 evidence, trigger, owner), QA4-03 (CRC-59 findings need rule, evaluation point, elements examined; non-human bound; CRC-04 wording), QA4-04 (prospective revocation cascade; work assignment versus role-position appointment; PR-04 and GCR-08 reading note). Same revision: QA4-05 to QA4-14 (record forms for CRC-52, CRC-09, CRC-45; derived-condition dependencies and conditional B tags; CRC-22 waivability rule; CR versus RJC discriminator explained; CRC-36 and EKO-04 qualifier; Section 6.3 Note column; UAD4 forward links; EKO-15 and consequential reliance narrowed; routing corrections; representation-neutral wording). Section 14 now declares thirty-two choices (UAD4-27 to UAD4-32 added; UAD4-03, 06, 07, 08, 09, 13, 14, 15, 23, 26 revised). Sections 1.5, 2.3, 3.3, 13, 15, and 16 updated for consistency | Returned by the Moderator for narrow revision (`MODERATOR-REVIEW-STEP-04-QA.md`), directed by the approved Tech Lead brief (`MODERATOR-REVIEW-STEP-04-REVISION-BRIEF.md`). The 61-row classification, boundary definitions, and catalog structure are not reopened. No row membership changed. Accepted STEP-01, STEP-02, and STEP-03 artifacts, and `mod-w/architecture.md`, are not edited. **No acceptance is recorded.** |

### 17.2 Pre-submission checks (v0.1)

These are the v0.1 checks as originally recorded. The revision's checks are in Section 17.5. The Development Team ran these document-native checks after assembling the draft. They were throwaway scripts and are not part of the deliverable. Each result can be reproduced by searching this file. The checks were run by the producer and confer no independence (PR-27, PR-28). No build, test, or validator exists for this repository, and none was selected or built.

| Check | Result |
| --- | --- |
| **Identifier coverage.** All 266 upstream identifiers appear in this file: PR-01 to PR-28, ACT-01 to ACT-07, OBJ-01 to OBJ-13, HJ-01 to HJ-10, INV-01 to INV-17, EKR-01 to EKR-41, EKO-01 to EKO-20, EKJ-01 to EKJ-14, TRG-1 to TRG-6, GCR-01 to GCR-68, GCO-01 to GCO-28, GCJ-01 to GCJ-14. No upstream identifier of those families lies outside those ranges | 0 missing |
| **Defined versus cited, new identifiers.** CRC (64), HJC (26), DR (10), DM (7), DP (6), UAD4 (26), RJ-OQ (11), BDR (18), AC4 (26) | First run: no undefined identifier. **Seven defined but cited nowhere else** (DM-04, UAD4-02, UAD4-03, UAD4-12, UAD4-22, UAD4-23, BDR-15). Corrected by adding the citation where each choice applies. Re-run: none. AC4 entries are leaf checks cited only in Section 16 |
| **Section references.** Each reference to a section of this file resolves to a heading | First run: two unqualified references resolved to sections of an upstream artifact (Sections 7.3 and 7.6), and a manual listing found one more ambiguous pair (a STEP-03 section named next to one of this file). All qualified. Re-run: every remaining unmatched reference is explicitly qualified with an upstream artifact |
| **Summary tables against the classification table.** Section 6.3 against Sections 1.5, 13.1, 13.7, and 14.6 | 61 rows: 48 catalogued rules, 12 recorded-judgment checks, 1 deferred. GCO 20, 7, 1. EKO 16, 4. OBJ 12, 1. The handling profiles of 13.1 and 13.7 cover all 28 GCO and all 20 EKO conditions once each. UAD4 levels: 16 A, 9 M, 1 L. Every entry cited in 6.3 is defined in 6.2. No mismatch |
| **Forbidden-term scan.** Representation, tooling, and state-vocabulary terms | Hits only in non-selection statements (Sections 1.2, 1.3, 9, 13.10, 14.5, 15.5, 16) |
| **Re-read against the acceptance checks** | Two defects found during drafting and the audit pass and corrected: the composite acceptance rule (CRC-22) did not allow for exception coverage, and the revocation rule (CRC-63) did not say who may revoke |

**Not run.** Independent Tech Lead, QA, or Product Owner review. No validator exists or was built. The sampling MW-ADAPT-001 expects is for the review record (AC4-22).

### 17.3 Transferability evidence

Concrete evidence emerged and is proposed, not accepted, under the research governance route: **MW-OBS-016** is appended to `research/mod-w-transferability/observations.md` with status _Proposed for Moderator review_. It records (1) that the work package pre-stated per-point review handling and no Phase 3a clarification was needed, (2) the document-native checks of Section 17.2 and what they found, (3) the six reading tensions of Section 3.3 across unedited accepted artifacts, and (4) how MW-ADAPT-001 behaved in a step whose subject is classification. It proposes no adaptation. The Moderator decides whether to accept, modify, or reject it. (The Moderator has since dispositioned it, as recorded in the review record. The v0.2 revision adds a seventh reading tension to Section 3.3, PR-04 and GCR-08 against conferral. It is not part of MW-OBS-016, and no observation is proposed here. The QA finding that sampling found choices the audit pass missed is noted for the Moderator in Section 14.6.)

### 17.4 Files changed in this delivery

- `prod-w/rule-judgment-boundary.md` (added).
- `research/mod-w-transferability/observations.md`: MW-OBS-016 appended as proposed, and the next-ID note in the Open Observation Log updated to `MW-OBS-017`.

`mod-w/domain-language.md` is not edited. The terms this artifact introduces are listed in Section 4.11 for the Moderator's later disposition. No accepted Product Definition, Architecture, Roadmap, STEP-01, STEP-02, or STEP-03 deliverable, no Step definition, and no MOD-W template was modified. Review and status records are the Moderator's and were not touched.

The 17.4 list is the v0.1 delivery. The v0.2 revision changed only `prod-w/rule-judgment-boundary.md` (Section 17.5).

### 17.5 Revision (v0.2) record

#### Where each finding was addressed

| Finding | Changed areas |
| --- | --- |
| **QA4-01** Roots, establishing act, CRC-62 | CRC-61, CRC-62; Section 10.1, 10.2 table, 10.2.2, 10.5, 10.6; UAD4-27 (new), UAD4-13, UAD4-14 (revised); DM-03, DR-03; HJC-22; Sections 1.5, 13.2 |
| **QA4-02** Conflicted conferral, chain depth, revocation limb, DP-04 | CRC-64; Section 10.2.3, 10.5, 10.6; UAD4-28 (new), UAD4-14 (revised); DP-04 (evidence, trigger, owner STEP-07); RJ-OQ-09; HJC-23; Sections 13.2, 14.4 |
| **QA4-03** CRC-59 findings; non-human bound; CRC-04 wording | CRC-59, CRC-15, CRC-04, CRC-09 (list wording); Sections 4.4, 4.10, 9.2, 9.4.2, 9.4.3, 9.4.5, 10.3.1, 10.3.4; BDR-13; UAD4-29 (new), UAD4-07 (revised); HJC-24, HJC-16; DR-09, DM-08 (new); RJ-OQ-03a, RJ-OQ-03b; Sections 1.5, 12.6, 13.3, 15.1 |
| **QA4-04** Cascade; PR-04 and GCR-08; assignment terms | CRC-61, CRC-62, CRC-63; Sections 3.3 (new reading row and terms paragraph), 4.11, 10.2.4, 10.2.5 (new); UAD4-30 (new), UAD4-13, UAD4-15 (revised); Sections 1.5, 13.2, 15.1 (PR-04, GCR-08, GCR-47 notes), 16 (AC4-09) |
| **QA4-05** CRC-52, CRC-09, CRC-45 | CRC-52, CRC-09, CRC-45; Sections 8.2, 12.3, 12.6; UAD4-31, UAD4-32 (new) |
| **QA4-06** Derived and view dependencies | CRC-18, CRC-19, CRC-47, CRC-52; DR-01, DR-04; Sections 5.4, 6.3, 13.1; UAD4-23 |
| **QA4-07** CRC-22 waivable list | CRC-22, CRC-18; Section 9.6; UAD4-26 |
| **QA4-08** CR versus RJC | Sections 4.5, 5.1, 5.2 (Q5), 6.3 (notes on GCO-12, GCO-20); UAD4-03. No row changes disposition |
| **QA4-09** CRC-36, EKO-04 qualifier | CRC-36; Section 6.3 (EKO-04), 12.1; UAD4-09 |
| **QA4-10** Section 6.3 Note column | Section 6.3 intro and Note cells for the rows QA named, and for the other rows whose note disagreed with their catalog pairing |
| **QA4-11** UAD4 forward links | Section 6.1; the last column of every family table (renamed "Pair / deferral / declared") for each entry that applies a declared choice |
| **QA4-12** Consequential reliance outside acceptance | Sections 3.3, 13.7; CRC-19, CRC-47; Section 6.3 (EKO-15 note); RJ-OQ-12 (new); UAD4-08 |
| **QA4-13** Routing | RJ-OQ-03a and 03b, RJ-OQ-09, RJ-OQ-10, RJ-OQ-12; Sections 11.3, 11.5, 13.6; Section 6.5 (EKR-41); Section 15.1 |
| **QA4-14** Representation-adjacent wording | Sections 4.10, 5.4, 9.2 (B row), 9.4.4, 12.7; BDR-09, BDR-11; UAD4-06, UAD4-23; Sections 1.5, 6.1, 13.8 |

#### Where the revision follows the approved Tech Lead brief rather than QA's suggestion

- **QA4-04, PR-04 and GCR-08.** QA left open whether this is a reading or a direct conflict. The brief decides it is a reading tension, and directs that it be acknowledged and routed as Moderator-visible. Section 3.3 and UAD4-13 do that.
- **QA4-08, CR versus RJC.** QA suggested either reclassifying the facet rows or rewording Section 4.5. The brief directs an explanatory fix only. Section 5.1, Section 4.5, and Q5 now state the discriminator. No row is reclassified.
- **QA4-12, non-acceptance commitments.** QA suggested adding the case to CRC-19 or narrowing the profile text. The brief directs narrowing only. CRC-19 is not extended. The routed question is RJ-OQ-12.
- **QA4-02, strength of handling.** QA noted the Moderator might want to name what would move CRC-64 from F/E to I. The brief keeps F/E and names evidence, trigger, and owner (DP-04). It directs no invalidation.
- **QA4-10 and QA4-11.** QA offered an alternative (define the column as "primary note only"; relax Section 6.1). The brief prefers filling references and keeping Section 6.1's promise. The revision does both of the latter.
- **QA4-13, RJ-OQ-03.** The split adds a guidance item (DM-08) so that the guidance-owned part has a methodology entry in the register.

#### Checks run on v0.2

Document-native checks run by the producer after the revision. They confer no independence (PR-27, PR-28). They were throwaway scripts and are not part of the deliverable.

| Check | Result |
| --- | --- |
| **Identifier coverage.** The 266 upstream identifiers still appear. PR, ACT, EKR, GCR, and TRG each still appear in Section 15.1 | 0 missing |
| **Defined versus cited, new identifiers.** CRC (64), HJC (26), DR (10), DM (8), DP (6), UAD4 (32), BDR (18), RJ-OQ (13: 01, 02, 03a, 03b, 04 to 12), AC4 (26) | No undefined identifier cited. Every identifier except the AC4 leaf checks is cited at least twice. A stale unqualified RJ-OQ-03 reference found and corrected |
| **Section references.** Each reference to a section of this file resolves to a heading | Resolved. The only unmatched references are the qualified upstream references recorded in 17.2 |
| **Summary tables against the classification table.** Section 6.3 against Sections 1.5, 13.1, 13.7 | Unchanged: 61 rows, 48 catalogued rules, 12 recorded-judgment checks, 1 deferred. GCO 20, 7, 1. EKO 16, 4. OBJ 12, 1. No row membership changed. The handling profiles of 13.1 and 13.7 still cover every GCO and EKO condition once |
| **UAD4 levels.** Section 14.2 against Section 14.6 | 32 declared: 21 A, 10 M, 1 L. UAD4-27 to UAD4-31 are A, UAD4-32 is M. Existing levels unchanged |
| **Forward links.** Each entry that applies a declared choice names its UAD4 in the last column | CRC-04, 09, 13, 15, 19, 22, 25, 29, 32, 35 to 39, 45, 47, 51 to 54, 56, 59 to 64 link forward. Every UAD4 entry is cited from at least one catalog entry or other section that applies it |
| **Forbidden-term scan.** Representation, tooling, and state-vocabulary terms in the added text | Hits only in non-selection statements (BDR-11, Section 14.4 probe) and in the expository use of "checker" and "representation" |
| **Stale-wording scan.** "Superseded" for EKR-41, "successive recorded states," "prevents effect," "surfaced," "assignees," and a root defined as "before any act relies on it" | None remain, except the upstream question title in PS-OQ-10 ("surfaced and handled"), a negated use ("not superseded"), and text quoting v0.1 |

**Not run.** Targeted Tech Lead re-review, targeted QA re-sample, and Product Owner sign-off. No validator exists or was built.

#### Moderator-visible items

1. **PR-04 and GCR-08 reading tension** (Section 3.3, UAD4-13). Acknowledged as a reading, not a direct conflict. Routed as Moderator-visible because the accepted upstream text did not name conferral scope. No upstream artifact is edited.
2. **Promotion of UAD4-13, UAD4-14, UAD4-15 to architecture decisions** (Section 14.3). The Tech Lead recommends it, as revised, after acceptance. Their revised content is partly carried by UAD4-27, UAD4-28, and UAD4-30. The Moderator decides. `mod-w/architecture.md` is not edited.
3. **MW-ADAPT-001 evidence** (Section 14.6). QA sampling found unlisted choices that the audit pass and the Tech Lead sampling did not. No observation is proposed here.
4. **Soft spots introduced or sharpened by this revision** (Section 10.6). Strict first-act rule for the establishing act. Root-grantee limit. Cascade on renunciation. Each is a sampling target for the targeted re-review.

**Acceptance status:** Not accepted. This v0.2 revision is returned for targeted Tech Lead re-review (with MW-ADAPT-001 sampling of the changed areas) and targeted QA re-sample. Phase 3c Product Owner sign-off is held. No waiver is recorded. Final acceptance is the MOD-W Moderator's decision.
