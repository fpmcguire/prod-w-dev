---
artifact:
  type: evidence-knowledge-model
  id: PROD-W-EKM
  version: 0.1
  created: 2026-09-30
  updated: 2026-09-30
  status: Accepted
  produced_by: Development Team
  produced_under: STEP-02
source:
  step: mod-w/step-02.md
  architecture: mod-w/architecture.md
  domain_language: mod-w/domain-language.md
  product_definition: mod-w/product.md
  protocol_semantics: prod-w/protocol-semantics.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Evidence, Knowledge, and Provenance Model (Initial Conceptual Model)

**Product:** PROD-W - Moderated AI-Assisted Product Development Workflow
**Artifact:** Representation-neutral model of knowledge classes, relationships, provenance, dependencies, and revalidation triggers
**Produced under:** STEP-02
**Status:** Accepted by the MOD-W Moderator on 2026-09-30 after Tech Lead approval.

---

## 1. Purpose and Standing

### 1.1 Purpose

This artifact defines what PROD-W treats as **knowledge** and how the kinds of knowledge relate: claims, evidence, counter-evidence, assumptions, hypotheses, inferences, decisions, challenges, dependencies, provenance, and revalidation triggers.

Its job is the one the Product Definition names as the core problem: plausible ideas, weak evidence, agent agreement, and inherited assumptions accumulating into unjustified confidence that a product should be built. That accumulation happens when different kinds of knowledge are allowed to look alike. This model keeps them distinguishable, keeps their sources traceable, and keeps dependent decisions from staying silently valid when their support changes.

### 1.2 Standing

This is a **product artifact**. It extends the accepted normative core in `prod-w/protocol-semantics.md` (STEP-01) and, per architectural decision D1, is normative at the level of _semantics_. Documents, schemas, state records, prompts, and validators are projections of it, not substitutes for it.

It is **conceptual**. Tables and identifiers here are expository devices for human review, not a protocol representation.

It does not describe or alter the governance of the `prod-w-dev` development project itself (Section 2).

### 1.3 What this artifact deliberately does not select

Operationalizes D2 and NG-1.

Nothing here selects, favors, prototypes, or assumes:

- a serialization or document format, or any metadata model;
- a schema language, or any structural type system;
- a protocol or transport;
- a workflow engine, state machine, lifecycle graph, or orchestration framework;
- a storage model (document metadata, sidecar files, centralized state, ledger, graph store, or a hybrid);
- a validator, CLI tool, agent harness, prompt format, or runtime integration;
- an AI model, vendor, or agent framework;
- any condition or state name. Words such as "validated," "withdrawn," "superseded," and "contested" are descriptive prose for conditions established by recorded events. They are **not** a state vocabulary, and no lifecycle or transition graph is implied (EKR-02).

In particular, no `DIVERGENT` state or equivalent is adopted, and Product Skeptic, Product Advocate, a Product Knowledge Ledger, a null-hypothesis framing pattern, a document-metadata model, and an external-evaluator contract are **not** treated as accepted requirements (NG-4).

The identifiers used here (`EKR-`, `EKO-`, `EKJ-`, `TRG-`, `UAD-`, `EK-OQ-`) are labels for cross-reference only. They avoid collision with STEP-01's `PR-`, `ACT-`, `OBJ-`, `HJ-`, `INV-`, and `PS-OQ-` identifiers.

### 1.4 Limits of what the model can do

The model cannot make suppression of unfavorable information objectively impossible. It can make such information **invalid to ignore once recorded** and **visible when it surfaces**. Section 7.7 and EKR-18 state this plainly rather than implying a guarantee the semantics cannot give.

---

## 2. Governance Context

**This artifact is authored under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-02 acceptance for `prod-w-dev` and is the authority for accepting this artifact. The Development Team produced it and may not accept it.

The **PROD-W Product Moderator** referred to in this document is a _future PROD-W protocol role_. It has no authority in `prod-w-dev`. Nothing here grants, implies, or transfers authority to any actor in `prod-w-dev`. Where this document says an act requires "authorized acceptance," it is stating a property of the future protocol, using STEP-01's authority model unchanged (PR-24).

STEP-02 follows the local adaptation **MW-ADAPT-001**. Section 12 is the required Undecided Architecture Declaration; it routes to the Tech Lead in addition to Moderator review.

**Review gates.** Tech Lead review (Phase 3a) passed on 2026-09-30 in `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02.md`. The MOD-W Moderator accepted the Development Team's STEP-02 work and approved the Tech Lead's STEP-02 approval on 2026-09-30 in `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`.

---

## 3. Relationship to `prod-w/protocol-semantics.md`

### 3.1 What is preserved without change

This artifact does not change, weaken, reinterpret, or add exceptions to any of the following in STEP-01:

- the authority model: actors, roles, authority grants, the four authority classes (AUTH-P, AUTH-A, AUTH-V, AUTH-G), and AUTH-G being human-only (PR-01 to PR-05);
- attribution and capacity rules (PR-06 to PR-09);
- action validity (PR-10, PR-11) and the initial action catalog (ACT-01 to ACT-07);
- acceptance semantics: acceptance is sufficiency, not truth; explicit, attributable, human, and independent where consequential (PR-12, PR-13);
- verification as bounded by named criteria (PR-14);
- advisory findings (PR-15, PR-22, PR-23);
- self-approval invalidity and independence by actor identity (PR-16 to PR-21, PR-27, PR-28);
- the separation of the two Moderator roles (PR-24);
- representation independence and the revalidation minimal statement (PR-25, PR-26).

Where this artifact says an act needs authority, independence, or human authorization, it points to those rules and adds nothing to them.

### 3.2 What this artifact adds

STEP-01 states that "the full evidence model is STEP-02 work" and relied on the domain-language distinctions only. This artifact supplies:

| STEP-01 handed forward | Where this artifact addresses it |
| --- | --- |
| Knowledge classes "remain distinct" (STEP-01 Section 3, D3) | Section 4 |
| Evidence and counter-evidence attached through ACT-02 "with the same formality" | Sections 5, 7 |
| PR-09 provenance elements for material claims | Section 6 |
| HJ-02, HJ-03, HJ-06, HJ-10 and their paired checks | Sections 8, 9, 10, 11 |
| ACT-06 and PR-26 revalidation (minimal statement) | Section 10 |
| PS-OQ-04 (evidence taxonomy), PS-OQ-06 (team as actor), PS-OQ-13 (configuration provenance granularity) | Section 13.2 |

### 3.3 Where this artifact reads STEP-01 provisions together

Two places required a stated reading. Neither changes a STEP-01 rule; both are declared in Section 12 so the Tech Lead can confirm or reject the reading.

1. **Revalidation.** PR-26 says a revalidation requirement _arises_ when a decision's material support changes, is contradicted, or is withdrawn. This artifact applies the same semantics to every dependent item with a material dependency, not decisions only (Section 10.4; UAD-06). ACT-06 and HJ-10 describe _judging_ whether a change is material enough to warrant a request. This artifact reads them as layered: designating a dependency as material is where that judgment is exercised in advance, so a listed trigger event on a material dependency creates the requirement by itself; ACT-06 and HJ-10 remain the route for everything not covered by that. See Section 10.6 and UAD-06.
2. **Challenge targets.** ACT-03 names claim, inference, or decision as challenge targets. This artifact extends the target set to evidence items and to relationships, with no change in the authority required (AUTH-A). See Section 5.3 and UAD-03. STEP-01 says later steps "may not silently reinterpret" catalog entries; this is therefore declared, not silent.

### 3.4 Reading conventions

- "Item" means a **knowledge item** (Section 4.1).
- "Record" means whatever conforming representation carries the item. The model says nothing about what that representation is.
- "Relied on" means used as support or premise for another item's standing, or for a decision.

---

## 4. Knowledge Class Definitions

Operationalizes D3, FR-3, FR-6, FR-7.

### 4.1 Knowledge items

A **knowledge item** is any attributable, recorded unit that belongs to one of the classes below. Every item has at least one recorded producer (PR-06, PR-08) and exactly one class at a time.

A class is defined by **what the item does in the protocol**, not by its subject matter or its wording. Two items with identical text may belong to different classes, because they were produced differently, cite different things, or are being used differently.

### 4.2 The classes at a glance

| Class | Protocol-operational definition | Distinguishing test |
| --- | --- | --- |
| **Claim** | A statement that may require evidence, challenge, acceptance, or qualification. Creating one asserts nothing about its validity (ACT-01). | Does it assert something that could be supported, contradicted, or qualified, without being an observation, a derivation, or a commitment? |
| **Material claim** | A claim consequential enough to affect product direction, gate decisions, user promises, or investment. Materiality is a recorded human judgment (EKJ-01), not a class of its own. | Would a change in its standing plausibly change a decision, a promise to customers, or an investment? |
| **Evidence** | Source-identified information that bears on a target item, whose source is traceable independently of any actor's assertion about the target (EKR-13). | Can a reader follow it to a source that does not itself consist of someone asserting the conclusion? |
| **Counter-evidence** | Evidence standing in a **contradicting** relationship to its target. First-class evidence, not a note or exception (EKR-15). | Does the same kind of item, with the same required elements, weaken or contradict the target? |
| **Negative finding** _(kind of evidence)_ | Evidence recording that a defined search, test, or attempt to observe something did not find or confirm it, or found the opposite (EKR-16). | Does it record a _result of an attempt_, with the attempt itself described? |
| **Assumption** | An unverified proposition being **relied on**. It is visible, reviewable, and never presented as fact (EKR-22). | Is something being leaned on without having been established? |
| **Hypothesis** | A proposition that is **testable**: it carries recorded validation criteria stating what would support, weaken, or refute it (EKR-21). | Does it state what evidence would count against it? |
| **Inference** | A reasoned interpretation derived from cited evidence and/or assumptions (and possibly other inferences). Never evidence, never observed fact (EKR-26, EKR-27). | Does it say "this implies that," and cite what it was drawn from? |
| **Decision** | An authorized commitment or selection among alternatives, citing its basis and its authority (Section 9.3). Without the required authority, the record is a recommendation. | Did an actor with the required authority commit to something, on a stated basis? |
| **Challenge** | An attributable act of questioning, testing, disputing, or seeking counter-evidence against an item, a relationship, or a decision (ACT-03; Section 5.3). | Is there an identified challenger, an identified target, and a stated basis? |
| **Advisory finding** | Output of an actor lacking authority for the matter in question. Informs acceptance; never performs it (PR-15). | Would treating it as a determination exceed the producer's authority? |
| **Dependency** | A directed link showing that one item relies on another (Section 10.1). | Would the dependent's standing be in question if the upstream item changed? |
| **Provenance** | The trace of source, producer, time, evidence basis, producing configuration, challenge history, and acceptance history for an item (Section 6). | Can you say where this came from, who made it, and what has happened to it? |
| **Validation** | A recorded acceptance that a hypothesis's evidence and challenge criteria are satisfied for a stated scope (Section 8.3). Acceptance of sufficiency, not a finding of truth. | Is there an authorized, independent, attributable act saying the criteria are met? |
| **Invalidation** | A recorded determination that an item can no longer be relied on, distinct from the visible fact that it is contested (Section 10.5). | Is there an authorized determination, as opposed to an objection, a challenge, or counter-evidence? |
| **Revalidation trigger** | A recorded event affecting an upstream item that, through a dependency, means a dependent item may no longer be justified (Section 10.4). | Did something happen to an item that another item relies on? |

Related but not classes: **acceptance**, **disagreement**, **supersession**, and **withdrawal** are defined in STEP-01 or in Sections 5 and 10 as acts, conditions, or relationships over these classes. They are named in D3 or the domain language and appear below where they matter.

### 4.3 Classes that need more than one line

**Claim versus decision.** A claim asserts; a decision commits. "Small teams lack evidence discipline" is a claim. "Proceed to prototype" is a decision. A recommendation produced without the required authority is not a decision and must not be represented as one (ACT-07, INV-16).

**Claim versus inference.** A claim is offered as something to be supported. An inference is offered as derived from things already cited. An inference cites; a claim need not. If a statement "follows from" evidence but cites none, it is a claim, and EKO-10 identifies the missing citation.

**Evidence versus inference.** Evidence is information that arrives from a source. An inference is what someone concludes from it. The same actor may produce both, but they are different items: the interpretation is never carried in the evidence item, and an inference is never attached in evidence's place (EKR-27).

**Challenge versus counter-evidence.** A challenge questions; counter-evidence contradicts with sourced information. A challenge may cite counter-evidence, may consist only of a stated basis, or may seek counter-evidence not yet found. A challenge with no counter-evidence is still a challenge and still stays visible (EKR-05).

**Validation versus verification.** Verification (STEP-01, AUTH-V) confirms that _defined formal criteria_ were met. Validation, here, is acceptance that a hypothesis's evidence and challenge criteria are met _for a stated scope_. Verification can establish that required items exist. It cannot establish sufficiency and never substitutes for validation (PR-14).

**Advisory finding versus evidence.** An advisory finding is an item about someone's assessment. If it carries or points to sourced information, that information can be evidence through its source. The opinion is not evidence of the matter it opines on (EKR-20).

### 4.4 Classification rules

| ID | Rule |
| --- | --- |
| EKR-01 | Every knowledge item has exactly one recorded class at any time. Classes are not collapsed into generic notes. Reclassification is a recorded, attributable action; the prior classification remains visible. Collapsing distinct classes is a protocol-level failure (STEP-01 Section 3), not a formatting preference. |
| EKR-02 | The conditions this artifact describes ("validated," "relied on under assumption," "contested," "withdrawn," "superseded," "invalidated," "open revalidation requirement") are descriptive. They are not state names, they do not define a lifecycle, and they may be represented later by any mechanism that preserves the semantics (D2, D5). |

---

## 5. Relationship Model

Operationalizes D3, D5, D7.

### 5.1 Relationships are attributable records

A relationship between items is not a fact about the items. It is an **assertion by an actor**, in a recorded capacity, at a recorded time. "Evidence E supports claim C" is an interpretation that someone made. That is why relationships carry provenance (Section 6.3), and why they can be challenged (Section 5.3).

### 5.2 The relationships

Each row states what the relationship means, which items it connects, how it is recorded using STEP-01 actions, and what it does **not** mean. No new action category is created and no authority is added; where a relationship asserted without the required authority would exceed it, it is recorded as the nearest thing the asserter _is_ authorized to do (EKR-04).

| Relationship | Connects (source to target) | Meaning | Recorded through | Does not mean |
| --- | --- | --- | --- | --- |
| **supports** | evidence, or inference (as derived support), to claim, hypothesis, inference, or decision | The source bears in favor of the target. Two kinds must be distinguishable: _evidential_ support (from evidence) and _derived_ support (from an inference). | ACT-02 (AUTH-P); derived support through ACT-01 (AUTH-P) | That the target is established, or that the support is sufficient (EKJ-02) |
| **contradicts** | evidence (counter-evidence), claim, or inference, to claim, hypothesis, inference, or decision | The source bears against, or is incompatible with, the target. | ACT-02 (AUTH-P or AUTH-A); ACT-01 for a contradicting claim or inference | That the target is refuted, or that the source prevails |
| **qualifies** | evidence, claim, or inference, to claim, hypothesis, inference, or decision | The source narrows the target's scope or conditions without contradicting it ("holds only for teams over fifty"). Corresponds to STEP-01's evidence attached "as context." | ACT-02 or ACT-01 | That the target is weakened in general |
| **depends on** | any relying item, to the item relied on | The dependent's standing relies on the upstream item (Section 10.1). | Recorded with the relying item; citation implies dependency (EKR-34) | That the upstream item is correct |
| **derives from** | inference (or derived evidence), to what it was drawn from | The source was drawn from the cited items; the citation chain is the inference path (GR-3). | ACT-01 or ACT-02 | That the derivation is warranted (EKJ-05) |
| **challenges** | challenge, to item, relationship, or decision | The source questions, disputes, or tests the target. | ACT-03 (AUTH-A) | That the target is wrong or answered |
| **validates** | validation, to hypothesis | An authorized acceptance that the hypothesis's criteria are satisfied for a stated scope. | An acceptance act (PR-12, PR-13); AUTH-G, human, independent where consequential | That the hypothesis is true; that the criteria were the right ones |
| **invalidates** | invalidation, to item | An authorized determination that the item can no longer be relied on. | A determination by the actor with acceptance authority for the item's scope; a producer may withdraw its own item (Section 10.5) | That the item was never valid, or that anything dependent has been resolved |
| **supersedes** | replacing item, to replaced item | The source replaces the target for purposes of reliance. The target remains recorded. | Producer of the replaced item, as revision (AUTH-P); otherwise Section 10.5 | That the replaced item was wrong |
| **requires revalidation** | trigger event, to dependent item | A trigger affecting an upstream item has made the dependent's continued reliance open to question (Section 10). | By the event (EKR-37); recorded via ACT-06 where a judgment is involved | That the dependent has been decided against |

### 5.3 Challenges may target items, relationships, and decisions

ACT-03 in STEP-01 names claim, inference, or decision as targets. That leaves no way to dispute evidence itself or the interpretation that connects it to a claim, which is where a great deal of real disagreement lives ("that interview does not say what you say it says"; "that survey is not about our customers").

This artifact therefore extends challenge targets, with the same AUTH-A requirement and no new authority:

- an **evidence item** (its source, basis, category designation, or limitations);
- a **relationship** (that E in fact supports C, that a dependency is or is not material, that an inference is drawn from what it cites);
- a **decision** (including its basis and any omission from it).

A challenge to a relationship is a challenge to the actor's interpretation, and is recorded against the relationship's asserter as a challenge to that assertion. See UAD-03.

### 5.4 Disagreement is a condition that relationships produce

Operationalizes D5 and FR-5.

**Disagreement** is the visible, unresolved conflict among claims, interpretations, evidence, or role judgments (domain language). In this model it is not an item class and not a state. It is a **condition derivable from the record**:

> Two or more items stand in a contradicting or challenging relationship, at least one is not withdrawn, and no authorized resolution has been recorded.

Sources of the condition:

| Source | Example |
| --- | --- |
| A challenge against an item, relationship, or decision | A challenger disputes that a pilot's results generalize |
| Counter-evidence against an item | A failed customer-interest test against a demand claim |
| Conflicting inferences | Two inferences from the same evidence reaching incompatible conclusions |
| Contradicting claims from different producers | Product Owner and Tech Lead disagree about feasibility |
| Evidence pulling in different directions | Two sourced items on the same target with opposing polarity |

The condition is:

- **attributable** (producers and challengers are identified),
- **evidence-linked** (what each side cites is recorded),
- **routable** (the record identifies the items and actors, so that whoever holds the authority to resolve it can be pointed at it).

_Routing_ mechanics, resolution, escalation, and how the condition is named or represented are STEP-03 work and are not defined here (EK-OQ-11, EK-OQ-13). What this artifact fixes is the property STEP-03 needs: **the record must never force consensus in order to proceed.**

| ID | Rule |
| --- | --- |
| EKR-03 | A relationship is an attributable record: asserted by exactly one actor identity, in one recorded capacity, at a recorded time (PR-06, PR-08). The producer of an item is not thereby the asserter of relationships that others record against it. |
| EKR-04 | A relationship confers no authority. An actor may record only what its grants permit (PR-01, PR-10). A "validates" or "invalidates" assertion by an actor without the required authority is recorded as an advisory finding, challenge, or counter-evidence, whichever the actor is authorized to make, and is not recorded as validation or invalidation (PR-15; PS OBJ-09). |
| EKR-05 | Contradiction and challenge are retained. Neither party's item is removed by the other. An unresolved contradiction or challenge persists as a visible condition, and no requirement of this model forces it to be reconciled in order for work to continue (WD-2, D5). |
| EKR-06 | Conflicting inferences remain separate items. No inference is elevated over another by number of agreeing actors, agreement among models, or recency alone (PR-20). |

---

## 6. Provenance Requirements

Operationalizes D3, D6, D7, FR-6, PE-1.

### 6.1 Principles

- **Provenance is cumulative.** It records what has happened to an item, not only what the item now says.
- **Provenance is a conceptual layer.** Whether an element lives in a document, in protocol state, or somewhere else is undecided (OQ-8; STEP-05).
- **Presence is checkable; adequacy is not.** The model can require that a source is identified. It cannot require that the source is trustworthy (Section 11).
- **Provenance concerns attribution, not correctness.** It says who and what and when; it does not say the item is right.

### 6.2 Common provenance elements

Every knowledge item carries:

| Element | Meaning |
| --- | --- |
| **Item identity** | Enough to refer to the item unambiguously, so that citations resolve (PS OBJ-08) |
| **Class** | Exactly one at a time (EKR-01), with prior classifications retained |
| **Producer(s)** | One or more actor identities; all are producers for independence purposes (PR-21) |
| **Time** | When the item was produced or recorded |
| **Basis** | What the item rests on: cited items, an identified source, or a stated absence of either |
| **Producing configuration** | Where the producer is an AI agent: model, reasoning effort, harness, tooling, instructions (PR-27) |
| **History** | Events since production: revisions, challenges, acceptances, withdrawal, supersession, invalidation, and triggers affecting it |

Producing configuration is provenance, not identity. Nothing in this artifact changes PR-27.

### 6.3 Class-specific elements

Elements required **in addition to** the common ones. "Material" includes items presumed material under EKR-35.

| Class | Additional required elements |
| --- | --- |
| **Material claim** | What the claim is; supporting evidence or a visible statement that none exists; who challenged or accepted it and with what outcome; dependency links to what it relies on and what relies on it; current recorded condition, derivable from history (PR-09, FR-6) |
| **Evidence item** | Source identification; the evidence-target relationship and its polarity; category designation; evidence basis; limitations statement; the time recorded and, where different, the time or period the observation refers to; lineage where derived (Section 7.2, EKR-11) |
| **Inference** | What it cites; the chain to its grounding evidence or assumptions (EKR-26); producer and producing configuration; whether the support it gives is derived rather than evidential |
| **Decision** | Basis (Section 9.3); authority basis: the acting actor, capacity, and the grant relied on; what challenges and contradicting items stood against the cited basis at the time; upstream decisions relied on; whether it is a decision or a recommendation |
| **Challenge** | Challenger identity; target; stated basis; whether counter-evidence is cited; history of responses and outcome (PS Section 4.5) |
| **Hypothesis** | Validation criteria; relied-on status; validation history (Section 8) |
| **Assumption** | What is relied on and by what; who authorized reliance where reliance is under conditional progression; resolution history (Section 8.5) |
| **Relationship** | The asserting actor, capacity, and time; the kind of relationship; and for support, whether it is evidential or derived (Section 5.1) |
| **Dependency change** | What changed (link added, removed, or its materiality designation altered), who changed it, when, and rationale for removal or for a non-material designation (EKR-36) |
| **Advisory finding** | Producer and producing configuration; what was inspected; criteria or method; time |

### 6.4 The material-claim minimum

The acceptance intent for FR-6 is that a material claim's provenance be sufficient to identify producer, time, evidence basis, challenge and acceptance history where applicable, and dependency links. This maps as follows:

| FR-6 element | Provided by |
| --- | --- |
| What the claim is | Item content and class |
| Who made it | Producer(s) |
| When | Time |
| What evidence supports it | Basis; support relationships and their evidence items |
| Who accepted or challenged it | History; challenge and acceptance records |
| Current status | Recorded condition, derivable from history; no state name fixed (EKR-02) |
| Dependency links | Dependency records, in both directions (Section 10.1) |

### 6.5 Source and producer are different things

**Source** is where information came from: a document, dataset, observation, experiment, interview subject, publication, or system. A source need not be an actor in the protocol.

**Producer** is the actor that created the item in the record: the researcher who ran and recorded the interview, the agent that retrieved and quoted the document.

Keeping these apart resolves the part of PS-OQ-06 that concerns evidence. An organization or publication can be a _source_ without becoming an _actor identity_, and a customer who is interviewed is the source of testimony while the interviewer is its producer. Whether a team or an agent fleet may be a single _actor_ identity is unaffected and remains open (EK-OQ-03). It matters for independence, and it stays with STEP-03.

The distinction also lets independence questions be asked correctly. A claim's producer and an evidence item's producer being the same actor is checkable. Whether the _source_ is independent of the claim is a judgment (EKJ-04). See UAD-11.

### 6.6 Lineage

Evidence is often derived from other evidence: three articles citing one survey, or a summary of a dataset. Three items that trace to one source are not three independent sources.

Where an evidence item is derived from other items, it identifies them. This makes shared lineage visible to whoever judges independence. The model cannot discover lineage nobody recorded. That limit is stated here rather than hidden (EKR-11, EKJ-04).

### 6.7 History, identity across change, and the acceptance boundary

STEP-01 (PR-11) keeps invalid actions visible. Architectural decision D7 requires prior decision history to be preserved and current validity to be distinguishable from historical acceptance. This artifact applies both to **every knowledge item**:

- Withdrawal, revision, supersession, invalidation, challenge, and acceptance are **events added to the record**. Nothing is silently overwritten or deleted.
- **Acceptance applies to the item as it stood when accepted.** If accepted content later changes, the change is recorded either as a **correction** (meaning unchanged; visible in history; no trigger) or as a **supersession** (the new content replaces the old for reliance; acceptance is not inherited by it). Whether a change alters meaning is a contextual judgment (EKJ-09), and the designation is attributable and challengeable.

The second point is a decision this artifact makes and declares (UAD-04). Without it, an accepted item can be quietly reworded into something nobody accepted while its acceptance travels along.

### 6.8 Rules

| ID | Rule |
| --- | --- |
| EKR-07 | Every knowledge item carries the common provenance elements of Section 6.2. |
| EKR-08 | Every material item carries the class-specific elements of Section 6.3. A material claim carries at least those required by FR-6 and PR-09 (Section 6.4). |
| EKR-09 | History is cumulative. Withdrawal, revision, supersession, invalidation, challenge, acceptance, and trigger events are added to the record. No item is silently overwritten or deleted. Invalid actions remain visible (PR-11). |
| EKR-10 | Acceptance applies to the item as it stood when accepted. Post-acceptance change is recorded as a correction or a supersession. Acceptance is not inherited by superseding content. |
| EKR-11 | Where an evidence item is derived from other items, it identifies them. Items sharing an identified source are identifiable as sharing it. |
| EKR-12 | Where an item is produced by an AI agent, its producing configuration is recorded as provenance (PR-27). Recording configuration confers no independence. The granularity required, and whether insufficient configuration provenance invalidates or merely weakens an action, remain open (PS-OQ-13; EK-OQ-09). |

---

## 7. Evidence and Counter-Evidence Expectations

Operationalizes D3, D6, FR-3, AH-3, PE-1, PE-2, PE-4.

### 7.1 What makes something evidence

**Evidence** is source-identified information used to support, weaken, or contextualize a target (domain language). This model adds a test that cuts most of what the failure pattern feeds on:

> The source must be traceable **independently of any actor's assertion about the target.**

Consequences:

- A statement that a claim is true, however confident, is a claim, not evidence for itself.
- Agreement among actors is not a source (Section 7.6).
- An output generated by an agent from its own training or reasoning, with no source a reader can follow, is a claim, an inference, or an advisory finding. It is not evidence about the world, whatever its fluency.
- An agent that _retrieves_ a source and reports it can produce evidence, through the source. The evidence is the source's content and provenance, attributed to its actual origin, with the retrieval recorded as the producer's act and configuration.

### 7.2 Expected elements

Every evidence item is expected to carry the following. Each is a **presence** expectation (EKO-04, EKO-05). None is an adequacy judgment.

| Element | Expectation |
| --- | --- |
| **Source identification** | The source is identified specifically enough for a reader to trace it. |
| **Producer** | The actor that produced the item in the record (Section 6.5). |
| **Time** | When the item was recorded and, where different, the time or period the observation refers to. Evidence age is relevant to sufficiency, which is a judgment (EKJ-02). |
| **Target** | The claim, hypothesis, inference, or decision it bears on. An item with no target counts as evidence for nothing, but remains visible in the record. |
| **Relationship polarity** | Supports, contradicts, or qualifies its target (Section 5.2). Polarity is per target (EKR-15). |
| **Category** | Designations for evidence basis kind and, where relevant, the evaluation dimension it bears on (Section 7.3). |
| **Evidence basis** | How the information was obtained: what was observed, asked, measured, retrieved, or computed. |
| **Limitations** | A statement of what the evidence does not cover or where it may mislead. "None identified" is a permissible entry, and it is an assertion that can be challenged. |
| **Provenance** | The common elements of Section 6.2, and lineage where derived (EKR-11). |

### 7.3 Categories: illustrative, not a taxonomy

FR-3 says gates specify required evidence categories where applicable, and full taxonomy is downstream (PS-OQ-04). This step provides a vocabulary sufficient for the model, and closes nothing.

**Evidence basis kind** (how the information came to exist), illustratively: direct observation or measurement; an artifact, record, or data set; testimony or statement, recorded as testimony; an experiment or test result; a search result, including a negative one; a computation over other evidence, with lineage.

**Evaluation dimension** (what it bears on), illustratively: problem, customer, commercial viability, technical feasibility, differentiation. WD-3 keeps technical feasibility and commercial viability distinct, and so evidence that bears on one is not automatically evidence on the other. The dimension designation lets that separation be seen and challenged.

These are not a closed set. Adding kinds or dimensions does not change this artifact. Which categories a gate requires, and what counts as sufficient customer evidence in any product category, are out of scope (Section 13.1, EK-OQ-01). See UAD-12.

### 7.4 Counter-evidence is first-class evidence

Operationalizes AH-3, PE-1.

**Counter-evidence is evidence.** It has the same required elements, the same formality, and the same retention as supporting evidence. It is not a note, an exception, a caveat in prose, or an appendix.

The model makes this concrete in three ways:

- **Polarity is relational.** Whether an item is counter-evidence is a property of its relationship to a target, not of the item itself. A survey may support a demand claim among small teams and contradict it among large ones. Because polarity is per target, no item is filed as "the negative one" and lost (EKR-15; UAD-01).
- **Counter-evidence cannot be dropped from the basis.** A decision citing an item must cite what stands against it (EKR-30).
- **Counter-evidence triggers revalidation** where a material dependency exists (TRG-2).

Counter-evidence does not defeat its target by being recorded, and does not have to be reconciled before work continues (EKR-05).

### 7.5 Negative findings

A **negative finding** is evidence that a defined search, test, or attempt to observe something did not find or confirm it, or found the opposite. It is a kind of evidence and is recorded with the same formality as a positive finding (AH-3).

The record has two parts and keeps them apart:

1. **The attempt record**: what was searched or tested, where, when, by what method, and with what limits. This is the evidence.
2. **Any inference drawn**: "therefore no competitor exists," "therefore customers do not want this." This is an inference. It cites the attempt record and can be challenged like any inference.

An unrecorded attempt cannot support an absence inference. A search that found nothing is informative only in proportion to what the search could have found, so the attempt record is required. It is what lets a reviewer judge whether the search was adequate to the inference (EKJ-08). "Absence of discovered competition" is therefore not evidence of novelty in itself. A recorded search whose scope and limits are stated is evidence, and the conclusion drawn from it is an inference. That protocol invariant is a research candidate (`research/topics/prod-w-protocol-first-rationale.md`) and is used here only as an illustration, not as an accepted requirement.

Where a hypothesis has validation criteria, results of tests against those criteria are recorded whether or not they favor the hypothesis (EKR-18).

### 7.6 Agent agreement is not evidence

Operationalizes PE-2 and PR-20.

Agreement among actors, including among AI agents, models, configurations, or evaluators, has **no evidentiary standing**. It is not a source and it does not create independence.

- An agreement record may be kept, as a claim or advisory finding by each agreeing actor. It carries no weight as evidence.
- **Corroboration requires separately present, attributable source evidence.** If Agents A, B, and C each conclude X, the record needs the source evidence each rests on. If they rest on the same source, that is one source (EKR-11).
- Agents agreeing does not raise an inference over a conflicting one (EKR-06).
- Re-running the same role under a different model or configuration produces findings and revisions, not independent corroboration (PR-28).

Detection is objective only where the record distinguishes sourced evidence from a concurrence record (EKO-04). Where an agent presents agreement as evidence and the record does not distinguish them, the failure is a misclassification the model can name but the record may not reveal. Challenge is the remedy.

### 7.7 Selective recording

The most damaging counter-evidence is the kind that is never attached. This model cannot detect an unrecorded finding. It can state the obligation and make the obligation's breach visible when it surfaces:

- An actor that has produced or obtained information contradicting an item it relies on or produced **must record it** as counter-evidence (EKR-18).
- Any actor with AUTH-A may attach counter-evidence they hold (STEP-01 Section 4.4).
- Once recorded, contradicting items cannot be omitted from a decision basis that cites the item they contradict (EKR-30).
- Evidence items with no target remain visible, so that "collected but never attached" is a visible condition.

Omission remains possible. It is a conformance failure that becomes detectable through challenge, lineage, or an actor's own later disclosure. See Section 1.4.

### 7.8 Advisory findings and external evaluators

Operationalizes D8.

External evaluator outputs, and outputs of any actor lacking authority for the matter in question, are **advisory findings** unless authority is explicitly granted by accepted PROD-W protocol (PR-22). Within the knowledge model:

| An evaluator output may be... | ...recorded as | Constraint |
| --- | --- | --- |
| An identified gap or dispute | A challenge (evaluators may hold AUTH-A) | Persists whether answered or not |
| Sourced contradicting information | Counter-evidence, through its source | The evaluator's opinion that it contradicts is not itself evidence |
| Sourced supporting information | Evidence, through its source | Same |
| A confirmation of formal criteria | A verification, where the evaluator holds AUTH-V | Bounded by named criteria (PR-14, OBJ-13) |
| An interpretation or assessment | An advisory finding, or an inference by the evaluator | Does not perform acceptance |
| A conclusion that a hypothesis holds or a decision is sound | An advisory finding | Never a validation, an acceptance, or a decision (PR-23) |

The evaluator's identity, what it inspected, its criteria or method, its time, and its producing configuration are recorded (Section 6.3). An evaluator's finding is not strengthened by being automated, independent, persuasive, or repeated. Its weight is a contextual judgment for the actor with acceptance authority (EKJ-13). No evaluator contract is defined here (PS-OQ-11).

### 7.9 Presence and provenance are separate from sufficiency

Operationalizes D6.

Everything this section calls an expectation is a **presence or provenance** condition: a source is identified, an element is recorded, a relationship exists, a citation resolves. These can be decided from the record alone.

**Sufficiency is a different question**: whether the evidence is relevant, persuasive, independent enough, complete enough, or strong enough for a stated purpose. That is a contextual human judgment (EKJ-02), and a consequential one belongs to the acceptance authority (PR-12, PR-13).

- Presence never implies sufficiency. A fully populated evidence item may be irrelevant, misleading, or weak.
- Absence of a mechanical check never means a requirement does not apply (PS Section 9.4).
- This model deliberately defines no confidence score, weight, grade, or numeric strength for evidence. Any such number would present a sufficiency judgment as though it were decided (GR-4, PE-4). Uncertainty is carried in the limitations statement and in the visible presence of challenges and counter-evidence.

### 7.10 Rules

| ID | Rule |
| --- | --- |
| EKR-13 | Evidence is source-identified information whose source is traceable independently of any actor's assertion about its target. A statement or output lacking such a source is not evidence, however it is worded. |
| EKR-14 | An evidence item is expected to carry source identification, producer, time, target, relationship polarity, category designation, evidence basis, limitations statement, and provenance. |
| EKR-15 | Counter-evidence is evidence: same elements, same formality, same retention. Polarity is a property of the relationship between an evidence item and a target. The same item may bear differently on different targets. |
| EKR-16 | A negative finding is evidence and is recorded with its attempt record (what, where, when, method, limits). Any absence inference drawn from it is a separate inference. |
| EKR-17 | Agreement among actors, agents, models, configurations, or evaluators is not evidence and creates no independence (PR-20). Corroboration requires separately present, attributable source evidence. |
| EKR-18 | An actor that has produced or obtained information contradicting an item it produced or relies on must record it as counter-evidence, and must record results of tests against a hypothesis's validation criteria whether or not they favor it. Breach is a conformance failure detectable when it surfaces. |
| EKR-19 | Presence and provenance conditions are separate from sufficiency judgments. Presence never implies sufficiency. No confidence score, weight, or numeric strength is defined or required. |
| EKR-20 | Output of an evaluator or of any actor lacking authority for the matter is an advisory finding. It may carry or point to sourced evidence and may be recorded as a challenge, counter-evidence, or (where AUTH-V is held) a verification. It is never recorded as a validation, an acceptance, a decision, or progression (PR-15, PR-22, PR-23). |

---

## 8. Assumption and Hypothesis Handling

Operationalizes D3, FR-7, AH-1, AH-2, GR-2.

### 8.1 Two classes, distinguished

The Product Definition draws the line in two sentences. Every assumption is recorded and marked for validation or challenge (AH-1). A hypothesis that cannot be tested or challenged is an assumption, not a hypothesis (AH-2). This model turns those into differences that can be seen in the record.

| | **Assumption** | **Hypothesis** |
| --- | --- | --- |
| What it is | An unverified proposition **being relied on** | A **testable** proposition |
| What defines it | Reliance without having established it | Recorded validation criteria: what would support, weaken, or refute it |
| Can it be untestable? | Yes | No. Without criteria it is an assumption (EKR-21) |
| What moves it | Being supported by accepted evidence, refuted, or no longer relied on (Section 8.5) | Test results, challenge, counter-evidence, and validation (Section 8.3) |
| Must it be visible? | Always, whether or not material (GR-2, AH-1) | Yes; when material, unvalidated status is visible (FR-7) |
| Why it matters | Hidden assumptions are how unjustified confidence accumulates | An untestable "hypothesis" hides an assumption under a respectable name |

A proposition may be both testable and relied on before being tested. That is the FR-7 case, handled in Section 8.4. The two aspects are never merged into one and never confused.

### 8.2 The testability line

Whether a proposition is a testable hypothesis or merely an assumption is a **contextual judgment** (HJ-06; EKJ-06). What is objectively checkable is whether **validation criteria are recorded** (EKO-09).

- A hypothesis record without validation criteria is not a hypothesis. It is an assumption, and is classified and handled as one (EKR-21).
- An assumption may become a hypothesis when criteria are recorded, by a recorded, attributable action. The earlier classification stays in history (EKR-01).
- Recorded criteria may still be poor. Whether they are adequate is EKJ-06; the model checks only that they exist.

### 8.3 Validation of material hypotheses

Operationalizes FR-7, AH-1, AH-2.

A material hypothesis is treated as **validated** only when both hold:

1. the **required evidence and challenge criteria** for its scope are satisfied; and
2. **authorized acceptance** has been recorded.

Validation is an acceptance (PR-12): a determination that the hypothesis's criteria are sufficient for a stated scope. It is not a finding that the hypothesis is true. Consequently:

- A consequential validation requires an explicit, attributable act by a human actor holding AUTH-G for that scope, independent of every recorded producer of the item accepted (PR-13, PR-16 to PR-21).
- Which criteria a gate requires, and whether validation of a hypothesis that is not tied to a consequential gate needs AUTH-G or a lesser acceptance, are not decided here (EK-OQ-01, EK-OQ-02).
- The **objective part** is checkable: the criteria the gate defines are recorded as met, the required challenge exists, the acceptor is independent, human, and authorized. The **judgment part** is whether the evidence and the challenge response are sufficient (EKJ-07).
- A validation is a recorded item. It is preserved as history if the hypothesis later loses standing (Sections 6.7, 10.9).

None of these constitutes validation: an accumulation of supporting items, agreement among agents (PR-20), passage of time, absence of objection (PR-13), completion of the work that depended on the hypothesis, or a verification of formal criteria (PR-14).

### 8.4 Unresolved-assumption handling

Operationalizes FR-7.

A project may continue while a material hypothesis is unvalidated **only when the appropriate human role explicitly authorizes conditional progression**. Where that happens, the hypothesis is **handled as an unresolved assumption**. The proposition keeps one identity with two aspects:

| Aspect | What happens |
| --- | --- |
| **Classification** | Unchanged. The hypothesis remains a hypothesis and remains unvalidated. Reliance never validates it. |
| **Handling** | Changed. It appears wherever unresolved assumptions are surfaced (GR-2), and each dependency on it is marked as a reliance under assumption. |

FR-7's four conditions become four record requirements:

| FR-7 condition | Requirement |
| --- | --- |
| The hypothesis remains classified as unvalidated | Its classification and validation history are unchanged by reliance |
| The assumption remains visible | It appears in the surfaced set of unresolved assumptions |
| Dependent decisions remain traceable to the unresolved assumption | Every item relying on it carries a dependency link marked as reliance under assumption |
| Progression under assumption is not represented as validation | No validation is recorded, and no record presents progression as such |

The **authorization** of conditional progression is an explicit act by a human role, identified and attributable, with the rationale and the requirement left unsatisfied. Its complete form, its relationship to gate waivers (GR-7), and who may give it are STEP-03 work (EK-OQ-08). This artifact requires only that it exist and be visible (EKO-15).

### 8.5 How an assumption is resolved

An assumption stays open until something is recorded that changes it. Without naming or ordering conditions, the ways it can end are:

- **Supported**: evidence bearing on it is attached and accepted for a stated scope. It is then a claim with accepted support, with the assumption history retained.
- **Refuted**: counter-evidence or invalidation is recorded. This is a trigger for everything that relied on it (TRG-2, TRG-3).
- **Retired**: nothing relies on it any longer. Retirement is recorded and does not erase the history of what did rely on it.
- **Remains open**: it stays visible. Time does not resolve it.

### 8.6 Rules

| ID | Rule |
| --- | --- |
| EKR-21 | A hypothesis carries recorded validation criteria. A proposition without them is classified and handled as an assumption (AH-2). Changing between the two is a recorded, attributable reclassification. |
| EKR-22 | Every assumption is recorded and visible, whether or not material, and is available for challenge and validation (AH-1, GR-2). An assumption is never presented as fact. |
| EKR-23 | A material hypothesis relied on before validation is handled as an unresolved assumption: it remains classified as unvalidated, remains visible, every dependency on it is marked as reliance under assumption, and progression under it is not represented as validation. Progression requires explicit authorization by the appropriate human role (FR-7). |
| EKR-24 | A material hypothesis is treated as validated only when its required evidence and challenge criteria are satisfied and authorized acceptance is recorded, subject to STEP-01 acceptance and independence rules. Accumulated support, agreement, elapsed time, absence of objection, and verification do not constitute validation. |
| EKR-25 | Validation is acceptance of sufficiency for a stated scope, not a finding of truth (PR-12). It is subject to the trigger semantics of Section 10. A validated hypothesis can lose that standing. |

---

## 9. Inference and Decision Support Rules

Operationalizes D3, D4, D7, PE-3, GR-3, HA-1, FR-6.

### 9.1 Inference

An **inference** is a reasoned interpretation. It is "X implies Y." It is separate from "we observe X" and separate from "Y is desirable" (PE-3).

- An inference **cites** what it was drawn from: evidence, assumptions, or other inferences. The citation is its inference path, so that "if X, then Y" claims can be traced and, if X proves wrong, the consequences can be found (GR-3).
- An inference must be **grounded**: following its citations through any chain of inferences must reach at least one evidence item or assumption. A chain that reaches nothing is a claim wearing an inference's clothes (EKO-10).
- An inference **is never evidence** and is never an observed fact. It may be cited as **derived support**, and the record must let a reader tell derived support from evidential support (Section 5.2). The evidentiary weight of a derived claim lies with what the inference cites, not with the inference.
- An inference is an interpretation by a producer. Its producing configuration is recorded (EKR-12).
- Whether an inference is warranted by what it cites is a contextual judgment (HJ-03; EKJ-05). What is checkable is that the citation exists and resolves.

This means agent synthesis, which is the dominant form of AI contribution to product work, is captured as what it is: an inference from cited material, produced by an identified configuration, challengeable, and never mistaken for observation.

### 9.2 Value judgments

PE-3 names three levels: "we observe X," "X implies Y," and "Y is desirable." The first two are evidence and inference. The third is a **value judgment**.

This artifact does not create a class for it. A value judgment is a **claim whose content is evaluative**. It is identified as evaluative, so that it cannot be presented as observation or as something evidence alone can establish (EKR-28). Evidence can inform it. No quantity of evidence converts it into a fact. It is settled by an authorized decision, not by inference (HA-1, WD-3). See UAD-09.

### 9.3 Decision records

Operationalizes D4, D7, FR-6.

A **decision** is an authorized commitment or selection among alternatives. A decision record retains:

| Element | Content |
| --- | --- |
| **Basis** | The items it relies on: supporting claims, evidence, assumptions and hypotheses (relied-on unvalidated ones marked as such), inferences, and upstream decisions |
| **Challenges and contradicting items considered** | Those recorded against the cited basis at the time of decision, and how each stood (answered, unresolved, or otherwise) |
| **Authority basis** | The acting actor, the capacity, and the authority grant relied on (PR-10) |
| **Provenance** | Common and decision-specific elements (Sections 6.2, 6.3) |
| **Nature** | Decision or recommendation (ACT-07) |

This artifact adds no gate authority and alters no gate authority rule. It requires that a decision **retain its links** to the authority and provenance STEP-01 already requires.

The following STEP-01 constraints apply unchanged:

- A consequential decision requires AUTH-G, is human, and is subject to independence exactly as ACT-05 is (ACT-07).
- A record produced without AUTH-G is a recommendation and is not represented as a decision (INV-16).
- An evaluator finding, a verification, or an agreement of agents is never recorded as a decision (PR-15, PR-22, PR-23, PR-14, PR-20).

### 9.4 Basis completeness

A decision that cites a claim while omitting a challenge or counter-evidence that stood against it is a decision made as though the opposition did not exist. This is the failure pattern in small: "alternative hypotheses and counter-evidence disappear."

Three requirements follow, each checkable from the record:

1. **Cite the opposition.** For each item the decision cites as basis, challenges and contradicting items recorded against it _before the decision_ are cited by the decision record, with how each stood.
2. **State absence.** Where a decision's basis contains no evidence, or rests on assumptions, that is stated. "Absence of evidence is visible" (PE-1). It is permitted; hiding it is not. Whether such a basis is sufficient is not the model's question (EKJ-02).
3. **Preserve the basis as it was.** The basis is preserved as of the decision. Later changes to cited items are events that may trigger revalidation. They are not edits to the basis (Sections 6.7, 10.9).

Requirement 1 is where this model touches gate mechanics. It states only what the decision _record_ must show. Who must respond to an unanswered challenge, what constitutes a response, and how gate acceptance reacts are STEP-03 (EK-OQ-04). See UAD-13.

### 9.5 Independence over cited items

STEP-01 states that an acceptance is invalid where the acceptor is a producer of _the accepted item_ (PR-16, PR-21). It does not define which set of items counts as "the accepted item" when a decision cites items produced by others, or by the decision-maker.

This artifact does not define that set (EK-OQ-05). It ensures every cited item's producers are recorded and resolvable, so that whatever set STEP-03 defines can be checked. It does not relax independence.

### 9.6 Rules

| ID | Rule |
| --- | --- |
| EKR-26 | An inference cites at least one evidence item, assumption, or other inference, and is grounded: every citation chain reaches at least one evidence item or assumption. Its producing configuration is recorded (EKR-12). |
| EKR-27 | An inference is never evidence and never an observed fact, and is never attached in evidence's place. It may be cited as derived support; derived and evidential support are distinguishable in the record. |
| EKR-28 | A claim whose content is evaluative is identified as evaluative. Evidence may inform it; it is not established by evidence or inference alone and is not presented as observed fact. |
| EKR-29 | A decision record retains its basis, the challenges and contradicting items considered, its authority basis, and its provenance. It states its nature as a decision or a recommendation. It adds no authority and alters no STEP-01 gate authority rule. |
| EKR-30 | A decision record cites, for each basis item, the challenges and contradicting items recorded against that item before the decision, and how each stood. Where the basis contains no evidence or rests on assumptions, the record states so. |
| EKR-31 | A decision's basis is preserved as of the decision. Later change to a cited item is an event under Section 10, never an edit to the basis. |
| EKR-32 | Every cited item's producers are recorded and resolvable, so that STEP-01 independence constraints can be evaluated over whatever set later steps define as the accepted item. |

---

## 10. Dependency and Revalidation-Trigger Semantics

Operationalizes D7, FR-6, FR-7, WD-6, GR-5. Full gate, challenge, and revalidation mechanics are STEP-03 work.

### 10.1 Dependency

A **dependency** is a directed link recording that a **dependent** item relies on an **upstream** item. It is what lets the protocol answer "what is affected if this changes."

A dependency link records:

- the dependent and the upstream item;
- the **kind**: support (relies on it as evidence or as a supporting claim), derivation (an inference drawn from it), reliance under assumption (Section 8.4), or upstream decision (a decision relying on another decision);
- a **materiality designation** (Section 10.2), by whom, when, and rationale where required;
- who recorded the link and when.

Decisions depend on claims, evidence, assumptions, hypotheses, inferences, challenges considered, and other decisions. A claim can depend on evidence and inference. An inference depends on what it cites. Dependencies are recorded in both directions: from the dependent, what it relies on; from the upstream item, what relies on it.

Dependency is not decisive on its own. A link can be added, mistaken, or missing. Whether a dependency _should_ be designated material, and whether a dependency is _missing_ from a decision's record, are contextual judgments (EKJ-10). Anyone with AUTH-A can challenge a decision's basis for omitting a dependency (Section 5.3).

### 10.2 Material dependency

A dependency is **material** where the dependent's standing would be in question if the upstream item changed, was contradicted, or was withdrawn. This is the same standard WD-6 uses ("material supporting assumptions, evidence, or upstream claims"). Its designation is a human judgment (EKJ-10), and that designation is where the judgment of HJ-10 is exercised in advance (Section 10.6).

Citation implies dependency. Citation does not imply materiality, and neither does the reverse. Because producers have an interest in narrow designations, the model closes the obvious gap:

> An item cited as basis by a **consequential decision or gate acceptance**, directly or through inferences, is **treated as material** for provenance and dependency purposes **unless a non-material designation with rationale is recorded**. That designation is attributable and challengeable, and does not remove the item or its link from the record.

An item not so cited need not carry a materiality designation. This spares ordinary notes a burden while keeping the loophole shut, because a claim that matters for a decision cannot avoid the provenance obligations by never being called material. See UAD-05. How a disputed designation is resolved is STEP-03 (EK-OQ-07).

### 10.3 Dependency changes

A dependency change is: a link added, a link removed, or a materiality designation altered. It is recorded with provenance (Section 6.3).

- **Removal** of a link, or **re-designation as non-material**, carries a recorded rationale. This blocks quietly detaching a decision from support that has gone bad.
- A dependency change on a decision is itself a change to that decision's basis. It is a trigger for the decision (TRG-5).

### 10.4 Revalidation trigger

A **revalidation trigger** is a recorded event affecting an upstream item that, through a dependency, means a dependent item may no longer be justified. It exists so that dependent decisions do not "remain silently valid when their material supporting assumptions, evidence, or upstream claims are changed, contradicted, or invalidated" (WD-6).

**Scope: every dependent item.** WD-6 and PR-26 are stated for decisions. This artifact applies the same semantics to **every dependent item that has a material dependency**: a claim, hypothesis, inference, or decision. A claim resting on withdrawn evidence is exactly as silently valid as a decision resting on it, and a decision-only scope would leave the claims beneath decisions unmarked while the decisions above them were flagged. Decisions remain the case that matters most, and the case STEP-01 states (PR-26; PS OBJ-10). The extension from decisions to all dependent items is declared in UAD-06.

The event and the consequence are different things:

- The **trigger** is the event.
- The **revalidation requirement** is the obligation it creates on the dependent: to be visibly open to question until an authorized actor reaffirms, revises, or retires it (PR-26).
- **Revalidation** is the act of reaching that outcome. It is not defined here beyond what PR-26 states.

### 10.5 The trigger catalog

Initial and non-exhaustive. Each trigger is defined by the event, not by a state.

| ID | Trigger | Event |
| --- | --- | --- |
| **TRG-1** | Material change or withdrawal of support | An upstream item is **withdrawn**, or its content is changed in a way that alters its meaning, recorded as a **supersession** (Section 6.7). |
| **TRG-2** | Contradiction | Counter-evidence, or a contradicting claim or inference, is recorded against the upstream item. |
| **TRG-3** | Invalidation | The upstream item is **invalidated**: an authorized determination that it can no longer be relied on. |
| **TRG-4** | Supersession | The upstream item is **superseded** by a replacing item; the replaced item remains recorded. |
| **TRG-5** | Dependency change | A material dependency link on the dependent itself is added, removed, or re-designated. |

Supporting definitions:

- **Withdrawal**: the producer retracts its own item. The item remains recorded and visible. A producer may withdraw its own item as an act of revision (AUTH-P), and this does not require acceptance.
- **Supersession**: a replacing item takes the place of the replaced one for purposes of reliance. A producer may supersede its own item as revision. Effective supersession of **another actor's item**, and invalidation of another actor's item, need the acceptance authority of the item's scope, because they are judgments about reliance, not about the producer's own work. Until then, a non-producer's proposal is a visible challenge, counter-evidence, or advisory finding, and TRG-2 still applies (EK-OQ-06).
- **Invalidation**: distinguished from being contested. An item can be contested by a challenge or counter-evidence, and that is already visible and already a trigger (TRG-2). Invalidation is the further, authorized determination that reliance must stop.

**A challenge alone is not a trigger.** It produces **exposure** (Section 10.7), and any authorized actor may raise a revalidation request on its basis through ACT-06. Whether an unresolved challenge on a material upstream item should itself create a requirement is open (EK-OQ-04). Making every challenge a trigger would let the cheapest act in the protocol put every dependent item in doubt. Making none of them visible would bury dissent. Exposure sits between.

### 10.6 Objective aspect and judgment aspect

Every trigger has both. Keeping them separate is what stops the model from either automating a judgment or letting a judgment become an excuse.

| Aspect | What it is | Character |
| --- | --- | --- |
| **The event** | A withdrawal, supersession, invalidation, contradiction, or dependency change was recorded on an upstream item | Objectively checkable from the record |
| **The link** | The dependent has a material dependency on that item (including presumed material under EKR-35) | Objectively checkable given recorded links |
| **The consequence** | A revalidation requirement exists on the dependent, visible until an authorized outcome is recorded | Objectively checkable: the requirement must be present and open |
| **Whether the change actually undermines the dependent** | Whether the dependent survives on other support, is weakened, or must be retired | Contextual judgment (EKJ-11) |
| **Changes not listed above** | Revisions of doubtful significance, qualifications, challenges without counter-evidence, non-material links, indirect exposure | Contextual judgment (HJ-10; EKJ-11), exercised through ACT-06 |

**Reconciliation with STEP-01.** PR-26 says a requirement _arises_. ACT-06 and HJ-10 speak of _judging_ whether a change is material enough to request. These are consistent if the judgment of materiality was **already exercised when the dependency was designated material**. The designation is a standing determination that changes to that upstream item matter. A listed trigger on a material link therefore creates the requirement by itself, and no further judgment is needed to make it exist. ACT-06 remains the act by which any authorized actor raises a requirement in the cases the trigger catalog does not reach, or makes one visible. What remains reserved to judgment is the _outcome_: whether the dependent is reaffirmed, revised, or retired. See UAD-06.

**Triggers do not wait for adjudication.** A requirement arises when counter-evidence is recorded, not when someone decides the counter-evidence is persuasive. Otherwise the party who benefits from the dependent item remaining current could delay the determination and thereby delay the requirement (EKR-39).

### 10.7 Exposure

**Exposure** is the visible fact that an item depends, directly or through others, on an item that is contested, has an open trigger, or has an open revalidation requirement. It is derivable from the dependency records, and it is what makes indirect consequences findable.

- **Direct dependents** of an item with a trigger receive a requirement (Section 10.6).
- **Indirect dependents** are not automatically given requirements. Consequences propagate through the _outcomes_ of revalidation: if a dependent B is retired or superseded as a result, that is a trigger for A, which depends on B. If B is reaffirmed, A has nothing to reopen.
- Indirect dependents are **exposed** in the meantime. It must be possible to enumerate what depends, directly or indirectly, on any item (EKR-40).
- Whether reliance may continue while a requirement is open, or exposure exists, is a gate question and belongs to STEP-03 (EK-OQ-04).

### 10.8 How a requirement ends

Under PR-26 a revalidation requirement stays visible until an authorized actor **reaffirms, revises, or retires** the dependent. PR-26 states this for decisions; Section 10.4 applies it to every dependent item. This artifact adds only:

- It is not closed by elapsed time, silence, absence of objection, agreement among agents, or completion of downstream work (PR-13 applies by analogy, unchanged).
- The authorized actor must be one with authority over the dependent's scope, human where the dependent is a consequential decision or is cited by one, and subject to STEP-01 independence rules (PR-16 to PR-21). Who may close a requirement on a dependent that is not a decision, and whether that differs, is routed as EK-OQ-16.
- The outcome is a recorded event and preserves the earlier history (EKR-09). Reaffirmation is acceptance of the dependent _as now supported_, and it applies to the dependent as it stands after the change (EKR-10).
- Whether time alone, such as evidence age, can create a requirement is open (EK-OQ-10).

### 10.9 Current validity is not historical acceptance

D7 requires the protocol to "distinguish current validity from historical acceptance." In this model:

- **Historical acceptance** is a fact about the past: an authorized actor accepted an item, on a stated basis, at a stated time. It is never erased.
- **Current validity** is a question about now: whether that acceptance can still be relied on given what has happened since. It is answered by the item's history, its dependencies, and its open requirements.

An accepted decision with an open revalidation requirement was accepted and is not currently reliable without an authorized outcome. Neither fact hides the other (PR-26, PS OBJ-10). How "current" is represented is a state question and is not answered here (EK-OQ-11).

### 10.10 Rules

| ID | Rule |
| --- | --- |
| EKR-33 | A dependency link records the dependent, the upstream item, the kind, a materiality designation with its recorder and time, and who recorded the link and when. Links are recorded in both directions. |
| EKR-34 | Citation implies dependency. An item cited as support, or from which an inference is drawn, is a dependency of the citing item. |
| EKR-35 | An item cited as basis, directly or through inferences, by a consequential decision or gate acceptance is treated as material for provenance and dependency purposes unless a non-material designation with rationale is recorded. Such a designation is attributable and challengeable, and does not remove the item or its link from the record. |
| EKR-36 | Adding, removing, or re-designating a dependency link is recorded with provenance. Removal, and re-designation as non-material, carry a recorded rationale. A dependency change on a decision is a trigger for it (TRG-5). |
| EKR-37 | A trigger event (TRG-1 to TRG-5) affecting an item on which any dependent item has a material dependency creates a revalidation requirement on that dependent by the event itself. The dependent may be a claim, hypothesis, inference, or decision. No further determination is required for the requirement to exist. |
| EKR-38 | A revalidation requirement remains visible until an authorized actor records reaffirmation, revision, or retirement of the dependent, subject to PR-16 to PR-21. It is not closed by time, silence, absence of objection, agreement, or downstream completion. A dependent item with an open requirement is not recorded as current without an authorized outcome; for decisions this is PS OBJ-10. |
| EKR-39 | A trigger arises when the event is recorded, not when the event is adjudicated. Contradiction and challenge take visible effect immediately. Invalidation, which is a determination, does not gate the trigger that contradiction already created. |
| EKR-40 | A conforming representation permits enumerating, for any item, what depends on it directly and indirectly, and what it depends on. Indirect dependents of an item with an open trigger or requirement are identifiable as exposed. |

---

## 11. Objectively Checkable Conditions and Contextual Human Judgments

Operationalizes D6 and E-9. It extends PS Section 9 and does not replace STEP-04's rule catalog.

### 11.1 The boundary, restated

A check is **objectively checkable** when it can be decided from the record alone, without interpreting the world the record describes. Everything else is a **contextual judgment** reserved to an appropriately authorized human.

This boundary is narrow on purpose. The model can require that a source is identified. It cannot check that the source is telling the truth. It can require that a challenge exists. It cannot check that the challenge was good.

### 11.2 Objectively checkable conditions (initial set)

These are checkable **given a record that carries the elements Section 6 requires**. Each is a candidate for later rule design (STEP-04). None is a specification of how it is checked.

| ID | Condition | Rule |
| --- | --- | --- |
| EKO-01 | Every item has exactly one recorded class; prior classifications are retained | EKR-01 |
| EKO-02 | Every item has at least one recorded producer identity and a time | EKR-07 |
| EKO-03 | Every AI-produced item records its producing configuration | EKR-12; PR-27 |
| EKO-04 | Every evidence item identifies a source; it is not solely a concurrence or agreement record; and the source is not the asserting actor's assertion about the target | EKR-13, EKR-17 |
| EKO-05 | Every evidence item records target, polarity, category, basis, and limitations statement, and its time(s) | EKR-14 |
| EKO-06 | An evidence item whose basis is derivation from other items identifies them | EKR-11 |
| EKO-07 | Contradicting and challenging items recorded against an item remain resolvable and visible | EKR-05, EKR-09 |
| EKO-08 | Every negative finding records the attempt elements: what, where, when, method, limits | EKR-16 |
| EKO-09 | Every hypothesis carries validation criteria; absent criteria, it is classified as an assumption | EKR-21 |
| EKO-10 | Every inference cites at least one evidence item, assumption, or inference; every citation chain reaches at least one evidence item or assumption; no inference is typed as evidence | EKR-26, EKR-27 |
| EKO-11 | A recorded validation is an acceptance by an actor with authority for the scope, not a recorded producer of the item, and human where consequential | EKR-24; PS OBJ-03, OBJ-04 |
| EKO-12 | A validation or invalidation asserted by an actor without the required authority is not recorded as one | EKR-04; PS OBJ-09 |
| EKO-13 | Every material item, including presumed material, carries its class-specific provenance | EKR-08, EKR-35 |
| EKO-14 | An item cited by a consequential decision or gate acceptance carries a materiality designation, or is treated as material | EKR-35 |
| EKO-15 | Reliance on an unvalidated material hypothesis is marked on every dependency link to it; the hypothesis is surfaced with unresolved assumptions; a conditional-progression authorization by an identified human exists | EKR-23 |
| EKO-16 | A decision record identifies its basis (or states that it has none), its authority basis, and its nature; consequential decisions meet STEP-01's human, grant, and independence conditions | EKR-29; PS OBJ-02, OBJ-04, OBJ-08 |
| EKO-17 | A decision record cites the challenges and contradicting items recorded before it against each cited basis item | EKR-30 |
| EKO-18 | Every dependency link records dependent, upstream, kind, materiality designation, recorder, and time; removal and non-material re-designation record a rationale | EKR-33, EKR-36 |
| EKO-19 | A trigger event on a material dependency has a corresponding visible revalidation requirement on the dependent item, open until an authorized outcome is recorded; a dependent with an open requirement is not recorded as current without one | EKR-37, EKR-38; PS OBJ-10 (decisions) |
| EKO-20 | An advisory finding is typed as such and is not recorded as validation, acceptance, decision, or progression | EKR-20; PS OBJ-09 |

### 11.3 Contextual human judgments (initial set)

For each judgment, the **paired objective check** is the mechanical fact that can support it. It never decides it.

| ID | Judgment | Extends | Paired objective check |
| --- | --- | --- | --- |
| EKJ-01 | Whether a claim, hypothesis, assumption, or inference is material | HJ-02 | EKO-14 (a designation exists, or the item is treated as material) |
| EKJ-02 | Whether evidence is relevant to, and sufficient or persuasive for, its target, including whether its age matters | HJ-01 | EKO-04, EKO-05, EKO-13 (presence only) |
| EKJ-03 | Whether an evidence item's category designation, basis, and limitations statement are adequate and complete | HJ-01 | EKO-05 (presence only) |
| EKJ-04 | Whether sources, producers, or challengers are substantively independent, including shared lineage nobody recorded | HJ-07 | EKO-06 (recorded lineage); producer identity distinctness |
| EKJ-05 | Whether an inference is warranted by what it cites | HJ-03 | EKO-10 (the citation exists and resolves) |
| EKJ-06 | Whether a proposition is a testable hypothesis or an assumption, and whether its recorded criteria are adequate | HJ-06 | EKO-09 (criteria exist) |
| EKJ-07 | Whether a hypothesis's required evidence and challenge criteria are satisfied, and whether to accept validation | HJ-01 | EKO-11 (acceptor, authority, independence); criteria recorded as met |
| EKJ-08 | Whether the recorded attempt behind a negative finding was adequate to support any absence inference | HJ-03 | EKO-08 (the attempt record exists) |
| EKJ-09 | Whether a revision alters meaning: correction or supersession | new | The designation exists, is attributed, and is retained in history |
| EKJ-10 | Whether a dependency should be designated material, and whether a dependency is missing | new | EKO-18 (links and designations are recorded) |
| EKJ-11 | Whether a trigger actually undermines the dependent; whether changes outside the catalog warrant a request; whether the outcome is reaffirmation, revision, or retirement | HJ-10 | EKO-19 (the requirement exists and is open) |
| EKJ-12 | Whether a challenge has been adequately answered, and whether disagreement is resolved enough to proceed | HJ-04, HJ-08 | Presence of unresolved challenges and contradictions |
| EKJ-13 | What weight an advisory finding or evaluator output deserves | new | EKO-20 (it is typed as advisory) |
| EKJ-14 | Whether an evaluative claim is warranted, and whether residual risk is acceptable | HJ-05 | None |

### 11.4 Rules about the boundary

- An implementation **may** block or flag an EKO-class violation. It **must not** decide an EKJ-class question, present one as decided, or convert one into a numeric score or grade that implies it was decided (GR-4; EKR-19).
- The absence of a mechanical check never implies that a requirement does not apply. Rules in this artifact that are hard to check remain binding.
- Requirements on **any** conforming representation, whatever it is: distinguish classes (EKR-01); carry provenance (EKR-07 to EKR-12); preserve history (EKR-09); represent relationships as attributable records (EKR-03); and permit dependency enumeration (EKR-40).

| ID | Rule |
| --- | --- |
| EKR-41 | Implementations may block or flag EKO-class violations and must not decide EKJ-class questions, present them as decided, or convert them to scores. The absence of a mechanical check does not relax a requirement. |

### 11.5 What this section does not do

The EKO set is an initial classification of this artifact's own conditions. It is not the machine-checkable rule catalog. STEP-04 owns that catalog, the validation boundary, and the handling of detected violations (PS-OQ-10).

---

## 12. Undecided Architecture Declaration

Required by **MW-ADAPT-001** (`research/mod-w-transferability/adaptations.md`). Routes to the Tech Lead in addition to MOD-W Moderator review.

### 12.1 How this declaration was compiled

The declaration was compiled by an **audit pass over the finished draft**, not from a running list kept during drafting. Each modelling choice was tested against accepted upstream artifacts (`mod-w/product.md`, `mod-w/architecture.md`, `mod-w/domain-language.md`, `prod-w/protocol-semantics.md`, and `mod-w/step-02.md`).

**Working test.** A choice is declared here if a reasonable alternative reading of the upstream artifacts would have produced a materially different model, **or** if the choice touches authority, actor identity, independence, revalidation semantics, or what counts as evidence. Choices that only restate or organize what upstream artifacts already state are treated as operationalization and are not declared.

The working test is itself this team's judgment. MW-ADAPT-001 does not define "did not already decide," and MW-OBS-010 shows that architecture-level choices are hard to see from inside the artifact that contains them: PR-27 read as protocol semantics because it was. The **self-assessed level** column below is therefore a proposal. The Development Team cannot certify that it has found every such choice, and cannot classify its own choices as lower-level. The Tech Lead determines both.

### 12.2 Declared decisions

Level scale: **A** = architecture-level candidate (touches identity, authority, independence, revalidation, or what evidence is; recommend Tech Lead review before acceptance); **M** = model-level (choice within a defined space; recommend confirmation); **L** = low (organizing or completing an accepted principle; listed for visibility).

| ID | Decision made | What upstream left open | Reasoning, and input derived from | Level |
| --- | --- | --- | --- | --- |
| UAD-01 | Counter-evidence is evidence in a contradicting **relationship**. Polarity belongs to the evidence-target relationship, and one item can bear differently on different targets. | D3 and the domain language list counter-evidence as a concept but do not say whether it is an item class or a relationship. ACT-02 attaches evidence "in support, in contradiction, or as context." | The relational reading matches ACT-02's single action category and AH-3's "same formality." It also prevents filing an item as "the negative one." From: ACT-02, AH-3, domain language. | M |
| UAD-02 | Relationships (supports, contradicts, and so on) are **attributable records** that carry provenance and can themselves be challenged. | STEP-01 attributes _actions_; it does not say a relationship is an assertion open to challenge. | "X supports Y" is an interpretation by someone. Making it attributable follows from PR-06 and lets interpretive disputes be recorded. From: PR-06, PR-09, D3. | L |
| UAD-03 | **Challenge targets extend to evidence items and relationships**, under the same AUTH-A. | ACT-03 names claim, inference, decision. STEP-01 says catalog entries may not be silently reinterpreted. | Without this, evidence quality and support relationships cannot be disputed. The Product Definition allows AUTH-A actors to "analyze evidence, dispute interpretation." No authority is added. From: `mod-w/product.md` Human Authority Boundary; STEP-01 Section 4.4. | M |
| UAD-04 | **Acceptance applies to the item as it stood when accepted.** Post-acceptance change is a **correction** (meaning unchanged) or a **supersession**; acceptance is not inherited. | D7 requires history preserved and current validity distinguished from historical acceptance. It does not define what happens to acceptance when content changes. | Without it, accepted content can be reworded while its acceptance travels along. It is a decision about item identity across change. From: D7, PR-11, PR-12. | **A** |
| UAD-05 | Items cited as basis by a consequential decision or gate acceptance are **presumed material** unless a non-material designation with rationale is recorded. Uncited items need no designation. | PS says HJ-02 is a human judgment and "presence of a designation is checkable" but not for which claims a designation is required. | A producer could avoid provenance and dependency obligations by not calling a claim material. The presumption closes that gap without loading every note. From: HJ-02, PR-09, WD-6, A-5. | **A** |
| UAD-06 | **Revalidation is layered.** A listed trigger on a material dependency creates a requirement by itself, on **any dependent item** (claim, hypothesis, inference, or decision); ACT-06 and HJ-10 govern what the catalog does not reach. | PR-26 says a requirement _arises_ and is stated for decisions. ACT-06 and HJ-10 speak of _judging_ materiality before a request. PS calls PR-26 a minimal statement. | Reconciles the two: materiality was judged when the link was designated. Reading them the other way would let non-request suppress revalidation. Extends PR-26 and WD-6 from decisions to all dependent items, because a claim on withdrawn evidence is as silently valid as a decision on it, and D7 connects decisions to claims, evidence, assumptions, and hypotheses alike. From: PR-26, ACT-06, HJ-10, D7, WD-6. | **A** |
| UAD-07 | The initial **trigger set** (TRG-1 to TRG-5), the concept of **exposure**, and **challenge alone is not a trigger**. | Step scope lists material support changes, contradiction, invalidation, supersession, and dependency changes. It does not settle challenges or indirect dependents. | Challenge-as-trigger would let the cheapest act put every dependent in doubt; ignoring challenges would bury dissent. Exposure sits between. Propagation through outcomes avoids automatic transitive flooding. From: WD-6, WD-2, GR-5, D5, D7. | **A** |
| UAD-08 | A proposition keeps **one identity with two aspects**, classification and handling. Testability is determined by recorded validation criteria. | FR-7 and AH-2 fix the principle; how a relied-on hypothesis is represented is open. | Avoids duplicate items that can diverge. Keeps classification stable while handling changes, so reliance cannot validate. From: FR-7, AH-1, AH-2, GR-2. | M |
| UAD-09 | **Value judgments are not a class.** A claim with evaluative content is identified as evaluative. | PE-3 names three levels, and the domain language defines no class for the third. | A new class would exceed D3. Identifying evaluative claims preserves PE-3 without one. From: PE-3, HA-1, WD-3. | M |
| UAD-10 | **Inference chains** are allowed if grounded, and derived support is distinguishable from evidential support. | Domain language defines inference as drawn "from evidence." | Real inferences build on inferences. Grounding stops a chain from floating. From: PE-3, GR-3. | L |
| UAD-11 | **Source and producer are distinct.** A source need not be an actor. Lineage is recorded where evidence is derived. | PS-OQ-06 asks whether a team or organization may be a single actor and was routed here. | Settles evidence's side of PS-OQ-06 without deciding actor-identity granularity, which stays open. Enables independence questions. From: PR-07, PS-OQ-06, PE-2. | M |
| UAD-12 | Evidence **category** has two designations, basis kind and evaluation dimension, with an **illustrative** vocabulary, not a taxonomy. | PS-OQ-04 routed the taxonomy to STEP-02 and STEP-03. | Provides the minimum FR-3 needs, and keeps WD-3's separation visible, while leaving gate-specific categories to STEP-03. From: FR-3, WD-3, PS-OQ-04. | L |
| UAD-13 | A **decision record must cite** challenges and contradicting items recorded against its basis, state where the basis has no evidence, and preserve the basis as of the decision. | D7 and FR-6 require decision provenance. They do not say what a decision record must show about opposition. | The failure pattern is decisions made as though opposition did not exist. This is stated as record content only. Its consequences for gates are left to STEP-03. It sits near gate mechanics. From: `mod-w/product.md` Failure Pattern, AH-3, PE-1, FR-5, D7. | M |
| UAD-14 | **Negative findings** are evidence requiring an **attempt record**; an absence inference is a separate inference. | AH-3 requires "failed searches" to be recorded with the same formality. It does not say what a failed-search record contains. | A failed search is informative only relative to what it could have found. From: AH-3, PE-3. | L |
| UAD-15 | **Validation** is modeled as an **acceptance-type record**, distinct from verification, subject to STEP-01 acceptance and independence rules. | FR-7 requires "authorized acceptance." Who validates non-consequential hypotheses is open. | Reuses STEP-01 rather than inventing authority. From: FR-7, PR-12 to PR-14. | L |
| UAD-16 | **History is cumulative for every item**, not only decisions and invalid actions. | D7 names "prior decision history." PR-11 covers invalid actions. | Extends PR-11/D7 uniformly, since a dependency model is unreliable if any upstream item can be silently overwritten. From: D7, PR-11. | L |

### 12.3 Recommended Tech Lead priority

If the Tech Lead's time is limited: **UAD-04, UAD-05, UAD-06, UAD-07** first. All four touch identity, materiality, or revalidation, the area where D7 gives a direction and STEP-03 owns the mechanics. Then **UAD-03**, which touches the STEP-01 action catalog. Then UAD-11 and UAD-13.

Options for each, offered without preference: confirm as operationalization; promote to an architecture decision; return for revision.

### 12.4 Decisions considered and not made

The following were considered and deliberately left open. This is not a declaration that nothing else was decided; it records what the team refrained from.

- Condition or state names, including for disagreement (no `DIVERGENT`), for validated, contested, or open-requirement conditions.
- Lifecycle graphs, transition mechanics, and sequencing of acts.
- Any representation, schema, storage model, or serialization; how item identity across change is realized.
- Which evidence categories a gate requires; customer-evidence sufficiency thresholds.
- Who holds validation authority for non-consequential hypotheses.
- Whether time or evidence age triggers revalidation.
- Whether unresolved challenges create a revalidation requirement.
- Whether a team or agent fleet may be a single actor identity.

These are routed in Section 13.

### 12.5 Note for the MW-ADAPT-001 re-evaluation

MW-ADAPT-001's re-evaluation condition asks at the STEP-02 gate whether the declaration produced findings and whether architecture-level content still slipped past it. The Development Team's self-report on the first half is that the audit pass produced sixteen declared choices, of which four are self-assessed level A. On the second half it has nothing to report, and cannot: it is the same actor as the producer and cannot show that nothing slipped past. See the proposed observation `MW-OBS-011`.

---

## 13. Open Questions Routed to Later Steps

### 13.1 New questions

| ID | Question | Routed to |
| --- | --- | --- |
| EK-OQ-01 | Which evidence categories does each gate require, and what criteria define "required evidence and challenge criteria" for validating a hypothesis? What counts as sufficient customer evidence, by product category? | STEP-03; STEP-06; product OQ-2 |
| EK-OQ-02 | Who may accept validation of a material hypothesis that is not tied to a consequential gate? Is that AUTH-G, or may a lesser acceptance apply? | STEP-03 (PS-OQ-09) |
| EK-OQ-03 | May a team, organization, or agent fleet be a single actor identity, and how is delegation recorded? (The evidence-source half is settled by UAD-11; the actor half remains.) | STEP-03 (PS-OQ-06) |
| EK-OQ-04 | Does an unresolved challenge on an upstream material item itself create a requirement? May reliance continue while a requirement is open or exposure exists? What must respond to an unanswered challenge cited in a decision basis? | STEP-03 |
| EK-OQ-05 | What set of items is "the accepted item" for independence purposes when a decision cites items produced by others or by the decision-maker? | STEP-03 |
| EK-OQ-06 | How does supersession or invalidation of another actor's item become effective, and by whom? | STEP-03 (PS-OQ-07) |
| EK-OQ-07 | How is a disputed materiality designation resolved? | STEP-03 |
| EK-OQ-08 | What is the complete form of a conditional-progression authorization, and how does it relate to gate waivers? | STEP-03 (PS-OQ-12; GR-7) |
| EK-OQ-09 | At what granularity must producing configuration and evidence lineage be recorded, and does insufficient provenance invalidate an action or merely weaken it? | STEP-04 (PS-OQ-13) |
| EK-OQ-10 | Can the passage of time, or evidence age, itself create a revalidation requirement? | STEP-03 |
| EK-OQ-11 | Are conditions such as contested, validated, or open-requirement explicit state or derived from the record? How is "current validity" represented? | STEP-03; STEP-05 (PS-OQ-01) |
| EK-OQ-12 | How is item identity across change, corrections, and supersession realized in a representation? | STEP-05 |
| EK-OQ-13 | Is unresolved disagreement a named condition, a relationship, or an artifact property? | STEP-03 (PS-OQ-03; product OQ-3) |
| EK-OQ-14 | Which of the EKO conditions are catalogued as machine-checkable rules, and how are detected violations handled? | STEP-04 (PS-OQ-10) |
| EK-OQ-15 | How are a role-specific view and a machine view of the knowledge model separated, given that provenance and dependency information may burden human readers? | STEP-05 (`research/topics/document-metadata-and-human-machine-views.md`; product OQ-8) |
| EK-OQ-16 | Who may reaffirm, revise, or retire a dependent item that is not a decision (a claim, hypothesis, or inference) when a revalidation requirement is open on it? Is that AUTH-G, or may a lesser authority apply, and does it depend on whether a consequential decision cites the item? (Distinct from EK-OQ-02, which concerns accepting validation of a material hypothesis.) | STEP-03 (PS-OQ-09) |

### 13.2 STEP-01 questions routed to STEP-02 and their disposition

| STEP-01 question | Disposition here |
| --- | --- |
| PS-OQ-04: full evidence taxonomy and which evidence conditions are checkable | **Partly addressed.** Checkable presence conditions defined (Sections 7.2, 11.2). Illustrative categories only (7.3). Gate-specific categories and thresholds remain (EK-OQ-01). |
| PS-OQ-06: may a team, organization, or agent fleet be a single actor identity | **Partly addressed.** The evidence-source half is settled by distinguishing source from producer (6.5; UAD-11). The actor-identity half remains (EK-OQ-03). |
| PS-OQ-13: granularity of producing-configuration recording | **Partly addressed.** Presence is required (EKR-12, EKO-03). Granularity and consequence of insufficiency remain (EK-OQ-09). |

---

## 14. Traceability

### 14.1 Requirements

| Requirement | Where addressed |
| --- | --- |
| FR-2 Governance semantics for progression | Sections 3.3, 10.6 to 10.9; EKR-37, EKR-38 |
| FR-3 Evidence requirements | Sections 7, 11; EKR-13 to EKR-20; EKO-04, EKO-05 |
| FR-5 Unresolved disagreement visible | Sections 5.4, 7.4, 9.4; EKR-05, EKR-06, EKR-30 |
| FR-6 Provenance tracking | Section 6; EKR-07 to EKR-12; EKO-02, EKO-13 |
| FR-7 Hypothesis validation or visible assumption handling | Section 8; EKR-21 to EKR-25; EKO-09, EKO-11, EKO-15 |
| PE-1 Material claims require traceable evidence | Sections 6.3, 6.4, 9.4; EKR-08, EKR-30 |
| PE-2 Agent agreement is not independent evidence | Section 7.6; EKR-17; EKO-04 |
| PE-3 Inference and fact remain distinct | Sections 9.1, 9.2; EKR-26 to EKR-28 |
| PE-4 / GR-4 No artificial precision | Section 7.9; EKR-19; EKR-41 |
| AH-1 Assumptions surfaced and tracked | Sections 8.1, 8.4; EKR-22 |
| AH-2 Hypotheses remain testable | Section 8.2; EKR-21; EKO-09 |
| AH-3 Counter-evidence first-class | Sections 7.4, 7.5; EKR-15, EKR-16 |
| GR-2 Assumptions visible and reviewable | Sections 8.1, 8.4; EKR-22, EKR-23 |
| GR-3 Inference paths traceable | Section 9.1; EKR-26; EKO-10 |
| WD-2 Unresolved disagreement may remain visible | Section 5.4; EKR-05 |
| WD-3 Feasibility distinct from viability | Section 7.3 (evaluation dimension); UAD-12 |
| WD-4 Marketing claims trace to evidence | Sections 4.2 (material claim includes user promises), 6.3 |
| WD-5 Implementation may trigger reconsideration | Sections 10.4 to 10.6 (new evidence as TRG-2; supersession as TRG-4) |
| WD-6 Dependent decisions require revalidation | Section 10 (stated for decisions; applied to all dependent items, Section 10.4, UAD-06); EKR-33 to EKR-40 |
| A-5 Material claims distinct from background knowledge | Sections 4.2, 10.2; EKR-35 |
| NG-1 No premature technology selection | Section 1.3 |
| NG-4 Hypotheses are not requirements | Section 1.3 |
| RG-1 / AC-4 Transferability evidence | `research/mod-w-transferability/observations.md` (MW-OBS-011, MW-OBS-012) |

### 14.2 Architectural decisions

| Decision | Where operationalized |
| --- | --- |
| D1 Protocol semantics are normative | Sections 1.2, 3.1 |
| D2 Protocol, schema, state separate | Sections 1.3, 4.4 (EKR-02), 10.9, 11.4 |
| D3 Knowledge classes first-class | Section 4; EKR-01 |
| D4 Authority separate from role labels | Sections 3.1, 5.2, 9.3; EKR-04, EKR-29 |
| D5 Disagreement is a preserved condition | Sections 5.4, 10.5; EKR-05, EKR-06 |
| D6 Objective checks separate from judgment | Sections 7.9, 11; EKR-19, EKR-41; EKO and EKJ tables |
| D7 Provenance and dependencies support revalidation | Sections 6, 10; EKR-07 to EKR-12, EKR-33 to EKR-40 |
| D8 Evaluators advisory unless granted authority | Section 7.8; EKR-20; EKO-20 |
| D9 Working artifacts under `prod-w/` | This product artifact lives under `prod-w/`. The one `mod-w/` edit, appending a pending STEP-02 terms section to `mod-w/domain-language.md`, is the pending-terms routing change that `mod-w/step-02.md` (Expected File Changes) allows; the accepted terms table is untouched and no other `mod-w/` governance artifact changed (see Section 15) |

### 14.3 STEP-02 acceptance checks

The checks in `mod-w/step-02.md` are unnumbered. They are numbered here in the order they appear there.

| # | Acceptance check | Where satisfied |
| --- | --- | --- |
| AC-01 | Distinguishes claim, material claim, evidence, counter-evidence, assumption, hypothesis, inference, decision, challenge, dependency, provenance, and revalidation trigger | Section 4.2 (all twelve, plus negative finding, advisory finding, validation, invalidation), 4.3, 4.4; EKR-01; EKO-01 |
| AC-02 | Treats counter-evidence and negative findings as first-class evidence artifacts | Sections 7.4, 7.5; EKR-15, EKR-16; EKO-08; UAD-01, UAD-14 |
| AC-03 | Agent agreement explicitly excluded as independent evidence unless source evidence is separately present and attributable | Section 7.6; EKR-17; EKR-06; EKO-04 |
| AC-04 | Material claims require traceable provenance: producer, time, evidence basis, challenge and acceptance history, dependency links | Sections 6.2 to 6.4, 6.8; EKR-07, EKR-08, EKR-35; EKO-02, EKO-13, EKO-14 |
| AC-05 | Evidence presence and provenance separated from contextual sufficiency judgments | Sections 7.9, 11.1 to 11.4; EKR-19, EKR-41; EKO-04, EKO-05; EKJ-02, EKJ-03 |
| AC-06 | Assumptions and hypotheses remain distinct; unvalidated material hypotheses cannot be treated as validated without required evidence and authorized acceptance | Sections 8.1 to 8.4; EKR-21 to EKR-25; EKO-09, EKO-11, EKO-15 |
| AC-07 | Inferences are interpretations derived from evidence or assumptions, not evidence or observed facts | Sections 9.1, 4.3; EKR-26, EKR-27; EKO-10 |
| AC-08 | Decisions cite supporting claims, evidence, assumptions, and challenges, and retain authority and provenance links without changing STEP-01 gate authority | Sections 9.3 to 9.5, 3.1; EKR-29 to EKR-32; EKO-16, EKO-17 |
| AC-09 | Dependencies identify downstream items that may require revalidation when material support changes | Sections 10.1 to 10.4 (scope: every dependent item), 10.7; EKR-33 to EKR-37, EKR-40; EKO-18, EKO-19 |
| AC-10 | Revalidation triggers defined conceptually, without selecting state names, lifecycle graphs, workflow engines, or serialization | Sections 10.4 to 10.9, 1.3; EKR-02, EKR-37 to EKR-39; EKO-19 |
| AC-11 | Challenges, counter-evidence, and conflicting inferences can create visible unresolved disagreement without forcing consensus or adopting `DIVERGENT` | Sections 5.4, 7.4, 1.3; EKR-05, EKR-06; EK-OQ-13 |
| AC-12 | External evaluator outputs remain advisory findings unless authority is explicitly granted | Section 7.8; EKR-20; EKO-20; EKJ-13 |
| AC-13 | Includes an "Undecided Architecture Declaration" listing decisions beyond upstream architecture, or states none | Section 12 (sixteen declared decisions) |
| AC-14 | No implementation technology, schema language, storage model, protocol transport, or validator selected | Sections 1.3, 3.1, 12.4 |
| AC-15 | Transferability evidence proposed under research governance | `research/mod-w-transferability/observations.md`: MW-OBS-011, MW-OBS-012 (proposed); Section 12.5 |

### 14.4 STEP-02 scope items

| Scope item | Where |
| --- | --- |
| Knowledge classes, including advisory finding, validation, invalidation, revalidation trigger | Section 4 |
| Relationships: supports, contradicts, qualifies, depends on, derives from, challenges, validates, invalidates, supersedes, requires revalidation | Section 5.2 |
| What makes a claim material, as contextual judgment | Sections 4.2, 10.2; EKJ-01; EKR-35 |
| Evidence expectations in representation-neutral terms | Section 7.2, 7.3 |
| Counter-evidence as first-class | Sections 7.4, 7.5 |
| Assumptions and hypotheses distinct; when a hypothesis is a visible unresolved assumption | Section 8 |
| Inference as separate, citing evidence and/or assumptions | Section 9.1 |
| Decision records | Sections 9.3 to 9.5 |
| Provenance requirements | Section 6 |
| Dependency concepts | Sections 10.1 to 10.3 |
| Initial revalidation-trigger semantics | Sections 10.4 to 10.9 |
| Objectively checkable versus contextual judgment | Section 11 |
| Open questions routed to STEP-03, STEP-04, STEP-05 | Section 13 |

---

## 15. Change Notes

| Date | Version | Change | Reason |
| --- | --- | --- | --- |
| 2026-09-30 | 0.1 | Initial evidence, knowledge, and provenance model produced under STEP-02 | Second PROD-W product artifact; extends `prod-w/protocol-semantics.md` without modifying it. Sixteen decisions beyond accepted upstream artifacts are declared in Section 12 under MW-ADAPT-001 and routed to the Tech Lead. |
| 2026-09-30 | 0.1 (revised) | Tech Lead review returned for minor revision: (1) revalidation scope made consistent, choosing **every dependent item with a material dependency** and aligning Sections 10.4 and 10.8, EKR-37, EKR-38, EKO-19, UAD-06, and traceability (AC-09, WD-6); (2) D9 traceability row corrected to state that the artifact lives under `prod-w/` and that the `mod-w/domain-language.md` edit is the allowed pending-terms routing change | Tech Lead confirmed UAD-03 to UAD-07 as valid operationalization subject to the revalidation-scope correction. The scope choice extends PR-26 and WD-6 from decisions to all dependent items and is declared in UAD-06 for Tech Lead confirmation. |
| 2026-09-30 | 0.1 (accepted) | MOD-W Moderator accepted the Development Team's STEP-02 work and approved the Tech Lead's STEP-02 approval | Moderator approval recorded in `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`; Tech Lead approval recorded in `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02.md`. |

**Files changed in this delivery:** `prod-w/evidence-knowledge-model.md` (added); `mod-w/domain-language.md` (a pending-terms section appended; the accepted terms table untouched); `research/mod-w-transferability/observations.md` (MW-OBS-011 and MW-OBS-012 appended as proposed). No accepted Product Definition, Architecture, Roadmap, STEP-01 deliverable, STEP-02 definition, or MOD-W template was modified.

**Acceptance status:** Accepted by MOD-W Moderator on 2026-09-30 after Tech Lead approval.
