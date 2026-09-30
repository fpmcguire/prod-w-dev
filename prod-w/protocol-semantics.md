---
artifact:
  type: protocol-semantics
  id: PROD-W-PS
  version: 0.1
  created: 2026-09-30
  updated: 2026-09-30
  status: Accepted by MOD-W Moderator
  produced_by: Development Team
  produced_under: STEP-01
source:
  step: mod-w/step-01.md
  architecture: mod-w/architecture.md
  domain_language: mod-w/domain-language.md
  product_definition: mod-w/product.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Protocol Semantics (Initial Normative Core)

**Product:** PROD-W - Moderated AI-Assisted Product Development Workflow
**Artifact:** Normative protocol semantics for actors, roles, authority, actions, acceptance, and self-approval invalidity
**Produced under:** STEP-01
**Status:** Accepted by MOD-W Moderator (see Section 13 for conditions)

---

## 1. Purpose and Standing

This artifact defines the initial **normative protocol semantics** of PROD-W: what may happen, who may make it happen, under what conditions, and what makes an action invalid.

It is a product artifact. It describes the PROD-W protocol that PROD-W-governed product-development projects will later follow. It does not describe or alter the governance of the `prod-w-dev` development project itself.

Per architectural decision D1, these semantics are the **normative layer**. Documents, schemas, state records, prompts, validators, and agent instructions are projections or implementations of this layer, not substitutes for it.

This artifact is deliberately **representation-neutral**. It selects no serialization, schema language, tooling, or storage model. See Section 9.

### What this artifact covers

Actors, roles, authority grants, participation capacities (authorship, review/challenge, verification, acceptance), actions, acceptance semantics, self-approval invalidity, an initial action catalog, invalid-action examples, and the boundary between objectively checkable rules and contextual human judgments.

### What this artifact does not cover

Evidence taxonomy and sufficiency criteria (STEP-02), gate/challenge/disagreement/revalidation mechanics in full (STEP-03), the machine-checkable rule catalog as an implementable specification (STEP-04), representation choice (STEP-05), and methodology guidance (STEP-06). Final condition or state names are **not** defined here; see Section 10.

---

## 2. Governance Context

**This artifact is authored under MOD-W v5.0.1 governance.** The MOD-W Moderator governs `prod-w-dev` and is the authority for accepting this artifact. The Development Team produced it and may not accept it.

The **PROD-W Product Moderator** described in this document is a _future PROD-W protocol role_. It has no authority in `prod-w-dev`. Nothing in this document grants, implies, or transfers authority to any actor in `prod-w-dev`.

The two roles are never interchangeable:

|                                     | MOD-W Moderator                                                              | PROD-W Product Moderator                                              |
| ----------------------------------- | ---------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Exists                              | Now, in `prod-w-dev`                                                         | Only inside future PROD-W-governed projects                           |
| Governs                             | This development project, its gates, and the transferability research record | Product decisions and consequential product gates in a PROD-W project |
| Authority over this artifact        | Yes - accepts, returns, or modifies it                                       | None                                                                  |
| Authority over PROD-W product gates | None (no PROD-W project is running)                                          | Yes, where explicitly assigned                                        |
| Defined by                          | MOD-W v5.0.1                                                                 | This artifact and later PROD-W artifacts                              |

Rule **PR-24** below states this separation normatively for PROD-W itself.

---

## 3. Layer Distinction: Protocol, Schema, State

Operationalizes D2 and D3.

PROD-W separates three layers that are frequently conflated. The separation is normative: a conforming PROD-W implementation must keep them distinguishable.

| Layer        | Answers                                                    | Governs                                                                                           | Cannot decide                                          |
| ------------ | ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| **Protocol** | What is allowed to happen, by whom, under what conditions? | Actors, roles, authority, actions, constraints, acceptance, independence, progression             | Nothing is exempt; the protocol is the normative layer |
| **Schema**   | What does a valid record look like?                        | Structure, required elements, types, references                                                   | Authority, sequencing, independence, sufficiency       |
| **State**    | Where is this item now?                                    | The current recorded condition of a claim, evidence item, challenge, gate, decision, or work item | What is permitted next, on its own                     |

### Normative consequences

- **Structural validity is not protocol validity.** A record that satisfies every structural requirement may still be the product of an invalid action (PR-25).
- **State is an effect, not a source of authority.** A recorded condition results from valid actions. A condition that was reached by an invalid action does not become legitimate because it is recorded.
- **The protocol is prior to its representation.** Replacing the schema, storage model, or tooling must not change which actions are valid.

### Knowledge classes remain distinct (D3)

The protocol operates over distinguishable knowledge classes - claim, material claim, evidence, counter-evidence, assumption, hypothesis, inference, decision, challenge, acceptance, disagreement, provenance, dependency, revalidation - as defined in `mod-w/domain-language.md`. Collapsing any of these into a generic note is a protocol-level failure, not a formatting preference. Their full model is STEP-02 work; this artifact relies only on the distinctions already accepted in the domain language.

---

## 4. Actors, Roles, and Authority

Operationalizes D4 and FR-1.

### 4.1 Actor

An **actor** is an identified participant that performs actions: a human, an AI agent, an external evaluator, or an automated system.

- Actor identity must be **stable** (the same actor is recognizable across actions) and **distinguishable** (two actors are never silently merged).
- A role label, a tool or product name, a model name, a session, or a document byline is **not** by itself an actor identity.
- Whether a team or organization may be a single actor identity is an open question (PS-OQ-06).

#### Producing configuration is provenance, not identity

Where an actor is an AI agent, the configuration that produced an action - model, reasoning effort, harness, tooling, and the instructions given - can materially affect the output. That configuration is therefore part of the action's **provenance** and must be recordable.

It is **not** part of actor identity. This is a deliberate decision with a specific consequence: if changing model or configuration created a new actor identity, any actor could manufacture independence by switching configurations, which is exactly the failure Section 6 exists to prevent. Configuration varies; the accountable actor position does not (PR-27).

### 4.2 Role

A **role** is a named bundle of authority grants and expectations, valid within a stated scope.

The name is a convenience for humans. It is never the source of authority. Two roles sharing a name in different scopes are different authorities; a role name that appears in a document confers nothing.

### 4.3 Authority grant

An **authority grant** is the explicit, attributable, scoped permission that makes an action authorized. A grant must identify:

1. the **grantee** - an actor identity, or a role position that actors are assigned to;
2. the **authority class** - one of the four classes in 4.4;
3. the **scope** - the items, artifact classes, or gates the grant covers;
4. the **granting authority** - who conferred it, and when.

A grant that omits any of these is not a grant. Authority is never implicit, inherited, transitive, or acquired by participation, capability, or seniority.

How grants are created, changed, and revoked is deferred (PS-OQ-05).

### 4.4 Authority classes

PROD-W distinguishes four classes of authority. They are separate; holding one never implies another.

| ID         | Class                              | May do                                                                                                                                                  | May not do                                                                                                           |
| ---------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **AUTH-P** | Production authority               | Create claims, gather and attach evidence and counter-evidence, record assumptions, hypotheses and inferences, produce artifacts                        | Determine that its own output is sufficient; accept any gate                                                         |
| **AUTH-A** | Assessment and challenge authority | Analyze evidence, dispute interpretation, identify gaps, seek and attach counter-evidence, raise challenges                                             | Accept a gate; close a challenge as sufficiently answered where that judgment is reserved to a gate authority        |
| **AUTH-V** | Verification authority             | Confirm that defined formal criteria were satisfied and that required checks occurred                                                                   | Determine contextual sufficiency; accept a consequential gate                                                        |
| **AUTH-G** | Consequential gate authority       | Accept or refuse a consequential gate within its scope; authorize progression; authorize conditional progression; resolve role conflicts where assigned | Be exercised by a non-human actor; be exercised outside its scope; be exercised over its own holder's produced items |

**AUTH-G is human-only** (PR-05). This is intentional governance, not a capability limitation (HA-2).

### 4.5 Participation capacities

Authority says what an actor _may_ do. A **participation capacity** records what an actor _did_ in relation to a specific item. Both are required; neither substitutes for the other.

| Capacity                  | Meaning                                                                      | Recorded on                                                      |
| ------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| **Producer** (author)     | The actor that created or originated the item                                | Every claim, evidence item, artifact, inference, decision record |
| **Challenger / reviewer** | The actor that questioned, disputed, or sought counter-evidence for the item | Every challenge                                                  |
| **Verifier**              | The actor that confirmed defined formal criteria were satisfied              | Every verification                                               |
| **Acceptor**              | The actor that determined sufficiency for a stated scope                     | Every acceptance                                                 |

#### Artifact authorship

Every item carries at least one recorded producer identity. Authorship is an attribution of origin, not a claim of correctness, and it is not a grant of any authority over the item. An item may have multiple producers; all are recorded, and all count as producers for independence purposes (PR-21).

#### Review and challenge participation

A challenge is an attributable act, not an informal remark. Recording a challenge requires the challenger's identity, the item challenged, and the basis of the challenge. A challenge is recorded regardless of whether it is later answered; disagreement that remains unresolved stays visible rather than being retracted into consensus (WD-2). How challenges are answered, routed, or escalated is STEP-03 work.

An actor may hold several capacities over time with respect to different items. For any single action, exactly one capacity is recorded, and capacities are never merged retroactively (PR-08). Holding one capacity for an item constrains which others the same actor may later occupy for that item - this is the mechanism of Section 6.

### 4.6 Why role names alone are insufficient

Operationalizes D4 directly.

A protocol that authorizes by role name cannot detect the failures PROD-W exists to prevent:

- the same actor producing an artifact and then accepting it under a second role label;
- an actor named "Moderator" in one scope acting on a gate belonging to another scope;
- an advisory actor whose findings are treated as decisions because its label sounds authoritative;
- an AI agent occupying a role whose name implies human judgment.

Therefore: **a conforming implementation resolves authority through grants and resolves independence through actor identity. Name matching is never sufficient for either** (PR-01, PR-03, PR-17).

### 4.7 Role composition (illustrative, not normative)

PROD-W requires that **at least one human role position holds AUTH-G** for each consequential gate. That position is the **Product Moderator**.

Beyond that, PROD-W does not fix a role catalog in this step. The stakeholder categories in the accepted Product Definition (Product Owner / Product Researcher, Product Architect / Tech Lead, Implementation Team, QA / Validator, External Evaluators) are **illustrative compositions** of the four authority classes, not a normative role list:

| Illustrative position         | Typical grants                      | Standing                                       |
| ----------------------------- | ----------------------------------- | ---------------------------------------------- |
| Product Moderator             | AUTH-G (scoped), and usually AUTH-A | Required: some human position must hold AUTH-G |
| Product Owner / Researcher    | AUTH-P, AUTH-A                      | Illustrative                                   |
| Product Architect / Tech Lead | AUTH-P, AUTH-A                      | Illustrative                                   |
| Implementation Team           | AUTH-P                              | Illustrative                                   |
| QA / Validator                | AUTH-V, AUTH-A                      | Illustrative                                   |
| External evaluator            | AUTH-A, sometimes AUTH-V            | Illustrative; never AUTH-G by default (PR-22)  |

**Not treated as accepted roles.** Product Skeptic, Product Advocate, and any similar position remain open research hypotheses (OQ-1). Nothing in this artifact adopts them. A project may compose such a position from existing authority classes without PROD-W recognizing it as a protocol role.

### 4.8 External evaluators

Operationalizes D8.

An **external evaluator** is an actor outside the project's own production and gate structure that inspects artifacts, challenges claims, identifies gaps, supplies counter-evidence, or verifies conformance against defined criteria.

Evaluator output is an **advisory finding**. An advisory finding informs an acceptance decision; it never performs one, and it never becomes acceptance by being persuasive, automated, independent, or repeated. An evaluator acquires AUTH-G only through an explicit grant recorded in an approved PROD-W revision (PR-22, PR-23).

No evaluator is a required dependency of PROD-W, and no evaluator conformance contract is defined here (PS-OQ-11).

---

## 5. Actions

Operationalizes FR-2 and D1.

### 5.1 What an action is

An **action** is an attributable protocol event by which an actor changes the record. Every action carries, at minimum:

1. the **acting actor identity** (exactly one - PR-06);
2. the **capacity** in which the actor acted;
3. the **target item** or gate;
4. the **time** of the action;
5. whatever **content** the action category requires.

An action with missing or unresolvable attribution is invalid (PR-10).

### 5.2 Action validity

An action is valid only if **all** of the following hold:

- the acting actor is identified;
- the actor holds an authority grant of the required class covering the target's scope;
- the required attribution and content elements are present and resolvable;
- no invalidating constraint applies (notably the independence constraints of Section 6).

An invalid action **does not produce its intended effect**. Recording it does not make it valid. Invalid actions are not erased: they remain visible as invalid, so that the attempt and its handling stay auditable (PR-11).

### 5.3 Initial action categories

This is the **initial, non-exhaustive** catalog. Later steps may add categories; they may not silently reinterpret these.

| ID     | Action                 | Required authority                                                                        | Independence requirement                                                                                   |
| ------ | ---------------------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| ACT-01 | Create claim           | AUTH-P                                                                                    | None                                                                                                       |
| ACT-02 | Attach evidence        | AUTH-P                                                                                    | None for the act; independence of the _source_ is a separate judgment (HJ-07)                              |
| ACT-03 | Challenge claim        | AUTH-A                                                                                    | None for the act; only an independent challenger satisfies an _independent-challenge_ requirement (PR-19)  |
| ACT-04 | Verify formal criteria | AUTH-V                                                                                    | None normatively in this step (PS-OQ-02); producer self-verification does not count as independent (PR-19) |
| ACT-05 | Accept gate            | AUTH-G, human actor                                                                       | **Required.** Acceptor must not be a producer of the accepted item (PR-16 to PR-21)                        |
| ACT-06 | Request revalidation   | AUTH-A, AUTH-V, or AUTH-G                                                                 | None; any of these actors may raise it                                                                     |
| ACT-07 | Record decision        | AUTH-G where the decision is consequential; otherwise AUTH-P as a recorded recommendation | Required where consequential, as for ACT-05                                                                |

#### ACT-01 - Create claim

Records a statement that may require evidence, challenge, acceptance, or qualification. Creating a claim asserts nothing about its validity. Where the claim is material, the provenance elements of PR-09 are required at creation. Whether a claim is material is a human judgment (HJ-02), though the _presence_ of a materiality designation is checkable.

#### ACT-02 - Attach evidence

Links source-identified information to a claim, in support, in contradiction (counter-evidence), or as context. Counter-evidence is attached through the same action category and carries the same formality as supporting evidence (AH-3). Attaching evidence does not establish sufficiency. Agreement among actors is not evidence and may not be attached as such (PR-20).

#### ACT-03 - Challenge claim

Records an attributable act of questioning, disputing, testing, or seeking counter-evidence against a claim, inference, or decision. A challenge is a first-class record; it persists whether or not it is answered. Answering, routing, and escalating challenges are STEP-03 work.

#### ACT-04 - Verify formal criteria

Records confirmation that **defined formal criteria** were satisfied and that required checks occurred. Verification is bounded by the criteria it names. It is not a sufficiency judgment and never substitutes for acceptance (PR-14). A verification whose criteria are not stated is not a verification.

#### ACT-05 - Accept gate

Records an authorized determination that a defined gate's conditions are sufficient for its stated scope, and authorizes progression through it. Acceptance concerns **sufficiency, not truth** (PR-12). For a consequential gate it requires an explicit, attributable act by a human actor holding AUTH-G, and it is subject to the full independence constraints of Section 6. Silence, elapsed time, absence of objection, completion of prior actions, structural completeness, or agent agreement never constitute acceptance (PR-13).

Gate waivers and exceptions are not ordinary acceptance: they must identify the authorized human, the rationale, the unsatisfied requirement, and remain visible as exceptions (GR-7). Their representation is STEP-03 work (PS-OQ-12).

#### ACT-06 - Request revalidation

Records that a decision's material support has changed, is contested, or has been withdrawn, and that the decision may no longer be relied upon without reconsideration. The request makes the revalidation requirement visible; it does not itself reaffirm, revise, or retire the decision - only an authorized actor may do that (PR-26). Judging whether a change is material enough to warrant the request is a human judgment (HJ-10); once a request exists, tracking that it remains open is mechanical (OBJ-10).

#### ACT-07 - Record decision

Records an authorized commitment or selection among alternatives, together with what it depends on. A consequential decision requires AUTH-G and independence, exactly as ACT-05 does. A record produced without AUTH-G is a **recommendation**, not a decision, and must not be represented as one.

---

## 6. Self-Approval Invalidity

Operationalizes FR-4, D4, and D6. This is the headline normative constraint of STEP-01.

### 6.1 The constraint

**An acceptance is invalid where the accepting actor is a producer of the item being accepted.**

Natural-language instruction ("agents should not approve their own work") is insufficient, because it depends on the instructed party's compliance and leaves no trace when violated. PROD-W states self-approval as a condition of action validity: the acceptance does not take effect, whether or not anyone notices at the time. Whether an implementation _blocks_ the action or _detects and flags_ it is an implementation choice (D6); the invalidity is not.

### 6.2 Independence is a property of actor identity

Independence is evaluated between **actor identities**, not between role labels, capacities, tools, sessions, documents, or model instances. The same actor is the same actor:

- acting under a second role label;
- acting in a different capacity;
- acting through a different tool, harness, interface, or session;
- acting through a different model, reasoning configuration, or agent instance (PR-27);
- acting at a later time;
- acting after the item was reformatted, renamed, restated, or moved.

### 6.3 Circumvention patterns that do not restore independence

| Pattern                                                                                                                                          | Why it fails                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Producer accepts under a second role that has AUTH-G                                                                                             | Independence is by identity, not label (PR-17)                                                                                                    |
| Producer adds a co-acceptor and counts their own acceptance toward the requirement                                                               | A required acceptance needs at least one _independent_ acceptor; the producer's acceptance is not counted (PR-18)                                 |
| Producer challenges their own claim, then treats the independent-challenge requirement as met                                                    | A self-challenge is recorded but is not independent (PR-19)                                                                                       |
| Producer verifies their own artifact against formal criteria and treats that as acceptance                                                       | Verification is not acceptance (PR-14), and self-verification is not independent (PR-19)                                                          |
| Several agents agree with the producer, and the agreement is treated as independent corroboration                                                | Agreement is not evidence and does not create independence (PR-20)                                                                                |
| One of several co-producers accepts the jointly produced item                                                                                    | Every recorded producer is a producer (PR-21)                                                                                                     |
| The item is restated or re-authored by a second actor purely so the original producer can accept it                                              | The original producer remains a recorded producer; producers are not removed by restatement                                                       |
| The same role is re-run under a different model or reasoning configuration, and the second run is treated as an independent reviewer or acceptor | Configuration is provenance, not identity (PR-27). The practice is legitimate and valuable - see 6.5 - but it produces findings, not independence |

### 6.4 What makes this checkable

Self-approval invalidity is objectively checkable **given a record that identifies producers and acceptors by stable actor identity**. This is precisely why Section 4 requires actor identity to be separate from role labels: without it, the rule is unenforceable in practice. What remains non-mechanical is whether two nominally distinct identities are _substantively_ independent (for example, the same person operating two accounts), which is a contextual judgment (HJ-07).

### 6.5 Self-review and controlled re-execution

Self-approval invalidity must not be read as discouraging self-review. The two are different acts, and conflating them would suppress a practice that demonstrably improves work.

**Controlled re-execution** is the deliberate re-running of the same role, on the same inputs, under a different model, reasoning configuration, or agent instance, in order to compare outputs. It is an instrument for producing evidence about the _producer_ - about where a configuration's judgment is weak - and secondarily about the artifact.

What controlled re-execution and self-review legitimately produce:

- **Revisions.** A producer may always correct its own work. Revision is an exercise of production authority (AUTH-P) and needs no independence.
- **Advisory findings** (PR-15), including findings the producer cannot itself act on.
- **Escalations.** Findings that exceed the producer's authority are routed to an actor that holds the necessary authority.
- **Research evidence** about configuration variance, recorded under whatever research governance applies.

What they never produce:

- Independence. The accountable actor position is unchanged (PR-27).
- Satisfaction of an independent-challenge or independent-verification requirement (PR-19).
- Verification for gate purposes, or acceptance of any kind (PR-28).

The distinguishing test is simple: **self-review feeds production and escalation; it never feeds acceptance.** A producer that re-reviews its own artifact and revises it has done good work. The same producer that re-reviews its own artifact and marks it accepted has performed self-approval, whatever configuration the second pass ran under.

Two common-mode limits are worth stating, because they are why re-execution cannot substitute for independence. Both runs share the same inputs and the same instructions, so a defect originating in either is invisible to both; and agreement between two runs is agreement, not corroboration (PR-20).

---

## 7. Normative Rules

The rules below are the normative statements of this artifact. Section references indicate where each is developed.

### Authority and roles

| ID    | Rule                                                                                                                                                                                                              |
| ----- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PR-01 | Authority is conferred only by an explicit authority grant. No action is authorized by role name, seniority, capability, prior participation, or convention.                                                      |
| PR-02 | Every authority grant identifies grantee, authority class, scope, and granting authority. A grant missing any element is not a grant.                                                                             |
| PR-03 | A role is a named bundle of authority grants within a scope. Roles sharing a name across scopes are different authorities. Conformance evaluation resolves authority through grants, never through name matching. |
| PR-04 | Authority is neither transitive nor inheritable. One authority class does not confer another, and authority in one scope does not extend to another.                                                              |
| PR-05 | AUTH-G may be held and exercised only by a human actor. It may not be delegated to an AI agent, automated system, or external evaluator.                                                                          |

### Attribution and provenance

| ID    | Rule                                                                                                                                                                                               |
| ----- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PR-06 | Every action is attributable to exactly one acting actor identity.                                                                                                                                 |
| PR-07 | Actor identity is stable and distinguishable. A role label, tool name, model name, session, or byline is not an actor identity.                                                                    |
| PR-08 | An action records exactly one participation capacity. Capacities are never merged retroactively.                                                                                                   |
| PR-09 | Every material claim retains provenance sufficient to identify what the claim is, who made it, when, what evidence supports it, who accepted or challenged it, and its current recorded condition. |

### Action validity

| ID    | Rule                                                                                                                                                                                                         |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| PR-10 | An action is valid only if the actor is identified, holds a grant of the required class covering the target's scope, supplies the required attribution and content, and violates no invalidating constraint. |
| PR-11 | An invalid action does not produce its intended effect. Recording it does not validate it. Invalid actions remain visible rather than being deleted.                                                         |

### Acceptance and verification

| ID    | Rule                                                                                                                                                                                                                                                                       |
| ----- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PR-12 | Acceptance is an authorized determination of sufficiency for a stated scope. It is not a determination of truth.                                                                                                                                                           |
| PR-13 | Consequential gate acceptance requires an explicit, attributable action by a human actor holding AUTH-G for that gate. Silence, absence of objection, elapsed time, completion of prior actions, structural completeness, and agent agreement never constitute acceptance. |
| PR-14 | Verification confirms that defined formal criteria were satisfied. It is bounded by those criteria, is not a sufficiency judgment, and never substitutes for acceptance.                                                                                                   |
| PR-15 | Output from an actor without AUTH-G for the gate in question is an advisory finding. Advisory findings inform acceptance; they never perform it.                                                                                                                           |

### Independence and self-approval

| ID    | Rule                                                                                                                                                                                                                                                                                                                                   |
| ----- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PR-16 | An acceptance is invalid where the accepting actor is a recorded producer of the accepted item.                                                                                                                                                                                                                                        |
| PR-17 | Independence is evaluated on actor identity. A second role label, capacity, tool, session, or elapsed time does not make an actor independent of itself.                                                                                                                                                                               |
| PR-18 | Self-approval is not cured by co-acceptance. A required acceptance is satisfied only by at least one independent actor holding AUTH-G; a producer's own acceptance is not counted toward it.                                                                                                                                           |
| PR-19 | A challenge or verification performed by a producer of the item is recorded but does not satisfy an independent-challenge or independent-verification requirement.                                                                                                                                                                     |
| PR-20 | Agreement among actors is not evidence and does not establish independence.                                                                                                                                                                                                                                                            |
| PR-21 | Where an item has several recorded producers, independence requires the accepting actor to be none of them.                                                                                                                                                                                                                            |
| PR-27 | The configuration that produced an action - model, reasoning effort, harness, tooling, instructions - is part of the action's provenance and must be recordable. It is not part of actor identity. Re-executing a role under a different configuration is a distinct action by the same accountable actor and confers no independence. |
| PR-28 | Self-review and controlled re-execution produce revisions under the producer's own production authority, advisory findings, escalations, and research evidence. They never satisfy an independence requirement, never constitute verification for gate purposes, and never constitute acceptance.                                      |

### Evaluators and governance boundary

| ID    | Rule                                                                                                                                                                                                             |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PR-22 | External evaluator findings are advisory by default. An evaluator holds AUTH-G only through an explicit grant recorded in an approved PROD-W revision. No default, implied, or de facto grant exists.            |
| PR-23 | An evaluator finding must not be recorded as acceptance, as a sufficiency determination, or as gate progression.                                                                                                 |
| PR-24 | The PROD-W Product Moderator and the MOD-W Moderator are distinct roles in distinct governance systems. Neither inherits the other's authority, and a document defining one never grants authority to the other. |

### Representation and continuity

| ID    | Rule                                                                                                                                                                                                                                                                                                                         |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PR-25 | These semantics are normative independently of representation. A conforming representation preserves all of them. Structural validity under a schema never establishes protocol validity, and no representation is authoritative merely because it is machine-readable.                                                      |
| PR-26 | When the material support for a recorded decision changes, is contradicted, or is withdrawn, the decision does not remain silently valid. A revalidation requirement arises and remains visible until an authorized actor reaffirms, revises, or retires the decision. (Minimal statement; full semantics are STEP-03 work.) |

---

## 8. Invalid Action Examples

These examples exist to give downstream validation design (STEP-04) concrete targets. They are illustrative, not exhaustive.

| ID     | Attempted action                                                                                                                                      | Rule violated       | Why invalid                                                                                             | Checkable from the record?                                    |
| ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| INV-01 | The producer of a market-viability claim accepts the gate that depends on it                                                                          | PR-16               | Producer and acceptor are the same identity                                                             | Yes                                                           |
| INV-02 | The producer accepts their own artifact while acting as "Product Moderator"                                                                           | PR-16, PR-17        | A second role label does not create independence                                                        | Yes                                                           |
| INV-03 | The producer records their own acceptance alongside one independent acceptance and counts both toward a two-acceptor requirement                      | PR-18               | Producer acceptance is not counted; the requirement is unmet                                            | Yes                                                           |
| INV-04 | An AI agent records acceptance of a go/build gate                                                                                                     | PR-05, PR-13        | AUTH-G is human-only                                                                                    | Yes                                                           |
| INV-05 | An external evaluator's conformance finding is recorded as gate acceptance                                                                            | PR-22, PR-23        | Evaluators hold no AUTH-G by default; findings are advisory                                             | Yes                                                           |
| INV-06 | A gate is treated as accepted because no objection was raised within a period                                                                         | PR-13               | Acceptance requires an explicit attributable act                                                        | Yes                                                           |
| INV-07 | A QA verification of formal criteria is recorded as gate acceptance                                                                                   | PR-14               | Verification is bounded by its criteria and is not acceptance                                           | Yes                                                           |
| INV-08 | A claim is recorded with no identified acting actor                                                                                                   | PR-06, PR-10        | Attribution is missing                                                                                  | Yes                                                           |
| INV-09 | An actor holding AUTH-G for the technical-feasibility gate accepts the commercial-viability gate                                                      | PR-04               | Authority does not extend beyond its scope                                                              | Yes                                                           |
| INV-10 | A material claim is recorded without any evidence reference or provenance                                                                             | PR-09               | Required provenance elements absent                                                                     | Yes                                                           |
| INV-11 | Three agents independently agree with a claim, and the agreement is attached as corroborating evidence                                                | PR-20               | Agreement is not evidence                                                                               | Yes, where agreement is distinguishable from sourced evidence |
| INV-12 | Evidence supporting an accepted decision is withdrawn, and the decision remains recorded as current with no revalidation requirement                  | PR-26               | Dependent decisions do not remain silently valid                                                        | Yes, where dependencies are recorded                          |
| INV-13 | A record passes schema validation and is therefore treated as protocol-conformant                                                                     | PR-25               | Structural validity is not protocol validity                                                            | Yes, by re-running protocol checks                            |
| INV-14 | A producer challenges their own claim, and the independent-challenge requirement is marked satisfied                                                  | PR-19               | A self-challenge is not independent                                                                     | Yes                                                           |
| INV-15 | An actor acts on a gate because a document elsewhere names their role "Moderator"                                                                     | PR-01, PR-03        | No grant covering that gate exists                                                                      | Yes                                                           |
| INV-16 | A recommendation produced without AUTH-G is recorded as a decision                                                                                    | PR-15, ACT-07       | Only an authorized actor produces a consequential decision                                              | Yes                                                           |
| INV-17 | The same role is re-run under a stronger model, finds no further issues, and the second run is recorded as the independent review satisfying the gate | PR-19, PR-27, PR-28 | Configuration change does not change the accountable actor; agreement between runs is not corroboration | Yes, where producing configuration is recorded as provenance  |

---

## 9. Objective Checks and Contextual Human Judgments

Operationalizes D6 and E-9.

### 9.1 The boundary

A check is **objectively checkable** when it can be decided from the record alone, without interpreting the world the record describes. Everything else is a **contextual judgment** reserved to an appropriately authorized human.

This boundary is narrow on purpose. PROD-W can mechanically check that an evidence source is identified; it cannot check that the source is telling the truth. It can check that a required challenge exists; it cannot check that the challenge was good.

### 9.2 Objectively checkable conditions (initial set)

| ID     | Condition                                                                                                                                         |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| OBJ-01 | Every action has exactly one identified acting actor.                                                                                             |
| OBJ-02 | The acting actor holds a grant of the required authority class covering the target's scope.                                                       |
| OBJ-03 | The accepting actor is not a recorded producer of the accepted item.                                                                              |
| OBJ-04 | The accepting actor for a consequential gate is a human actor.                                                                                    |
| OBJ-05 | A material claim carries its required provenance elements (producer, time, evidence reference).                                                   |
| OBJ-06 | Where an independent challenge is required, a challenge exists and its challenger is not a producer of the challenged item.                       |
| OBJ-07 | Artifacts and evidence items required by a gate are present.                                                                                      |
| OBJ-08 | Evidence, dependency, and provenance references resolve to existing items.                                                                        |
| OBJ-09 | Output from an actor without AUTH-G is not recorded as acceptance or as a decision.                                                               |
| OBJ-10 | A decision with an open revalidation request is not recorded as current without an authorized reaffirmation, revision, or retirement.             |
| OBJ-11 | Progression through a gate is preceded by an attributable acceptance action for that gate.                                                        |
| OBJ-12 | A gate waiver or exception record identifies the authorized human, the rationale, and the unsatisfied requirement, and is marked as an exception. |
| OBJ-13 | A verification record names the formal criteria it verified.                                                                                      |

### 9.3 Contextual human judgments (initial set)

| ID    | Judgment                                                                                              | Paired objective check                                                            |
| ----- | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| HJ-01 | Whether evidence is sufficient or persuasive for a consequential gate                                 | OBJ-05, OBJ-07 (presence only)                                                    |
| HJ-02 | Whether a claim is material                                                                           | Presence of a materiality designation is checkable; the designation itself is not |
| HJ-03 | Whether an inference is warranted by the evidence it cites                                            | OBJ-08 (the citation resolves)                                                    |
| HJ-04 | Whether a challenge has been adequately answered                                                      | OBJ-06 (a challenge exists)                                                       |
| HJ-05 | Whether residual risk is acceptable                                                                   | None                                                                              |
| HJ-06 | Whether a proposition is a testable hypothesis or an assumption                                       | Presence of validation criteria is checkable                                      |
| HJ-07 | Whether a source, challenger, or evaluator is substantively independent, beyond identity distinctness | OBJ-03, OBJ-06 (identity distinctness only)                                       |
| HJ-08 | Whether disagreement is sufficiently resolved to proceed                                              | Presence of unresolved challenges is checkable                                    |
| HJ-09 | Whether conditional progression under an unresolved assumption is warranted                           | OBJ-12 (the authorization record is complete)                                     |
| HJ-10 | Whether a change to upstream support is material enough to require revalidation                       | OBJ-10 (an open request is tracked)                                               |

### 9.4 Rules about the boundary itself

- An implementation **may** block or flag an OBJ-class violation. It **must not** decide an HJ-class question, present an HJ-class question as decided, or convert one into a numeric score that implies it was decided (GR-4).
- The absence of a mechanical check never implies that a requirement does not apply. Rules in Section 7 that are hard to check remain binding.
- This split is an initial classification. STEP-04 owns the full rule catalog and the validation boundary.

---

## 10. Representation Neutrality and Deliberate Non-Selection

Operationalizes D2 and NG-1.

Nothing in this artifact selects, favors, prototypes, or assumes:

- a serialization or document format (YAML, JSON, Markdown metadata, sidecar files, or any other);
- a schema language (JSON Schema, TypeScript/Zod, or any other);
- a protocol or transport (MCP, A2A, or any other);
- a workflow engine, state machine implementation, or orchestration framework;
- a storage model (document metadata, centralized protocol state, or a hybrid);
- a validator, CLI tool, agent harness, prompt format, or runtime integration;
- an AI model, vendor, or agent framework.

The tables and identifiers in this document are **expository devices for human review**, not a protocol representation. A conforming implementation may use entirely different structures provided it preserves the semantics in Section 7 (PR-25).

**Condition and state names are deliberately not defined.** This artifact describes conditions in prose ("a claim with an unresolved challenge", "a decision with an open revalidation requirement") specifically to avoid hardening a state vocabulary before STEP-03 evaluates the options. In particular, no `DIVERGENT` state or equivalent is adopted; unresolved disagreement is required to remain visible (WD-2, D5), and how it is represented is open (OQ-3).

Research hypotheses remain hypotheses. Product Skeptic and Product Advocate roles, a document-metadata state model, a Product Knowledge Ledger, external evaluator contracts, and agent-harness conformance are **not** treated as requirements by this artifact (NG-4).

---

## 11. Open Questions for Later Steps

| ID       | Question                                                                                                                                                                                                                                                                | Routed to               |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- |
| PS-OQ-01 | What are the condition/state names, and is state explicit or derived from the action record?                                                                                                                                                                            | STEP-03, STEP-05        |
| PS-OQ-02 | Should verification carry a normative independence requirement, as acceptance does, or is independent acceptance sufficient protection on its own? PR-27 and PR-28 settle that re-execution cannot supply that independence; they do not settle whether it is required. | STEP-03 / STEP-04       |
| PS-OQ-03 | Should unresolved disagreement be a named condition, a relationship, or an artifact property?                                                                                                                                                                           | STEP-03 (OQ-3)          |
| PS-OQ-04 | What is the full evidence taxonomy, and which evidence conditions are checkable?                                                                                                                                                                                        | STEP-02, STEP-03 (OQ-2) |
| PS-OQ-05 | How are authority grants created, scoped, changed, revoked, and audited? Is granting itself an action category?                                                                                                                                                         | STEP-03 / STEP-04       |
| PS-OQ-06 | May a team, organization, or agent fleet be a single actor identity, and how is delegation recorded?                                                                                                                                                                    | STEP-02 / STEP-03       |
| PS-OQ-07 | May the recorded producer set of an item change (transfer or addition of authorship), and with what effect on independence?                                                                                                                                             | STEP-03                 |
| PS-OQ-08 | May an AI agent hold AUTH-V, and under what constraints?                                                                                                                                                                                                                | STEP-03 / STEP-04       |
| PS-OQ-09 | Which human role positions may hold AUTH-G for which gates, and may a project define more than one?                                                                                                                                                                     | STEP-03 (OQ-4, OQ-7)    |
| PS-OQ-10 | How are invalid actions surfaced and handled once detected - blocked, flagged, or escalated?                                                                                                                                                                            | STEP-04                 |
| PS-OQ-11 | Does an external evaluator interface or conformance contract enter core PROD-W scope?                                                                                                                                                                                   | Deferred (OQ-5, D8)     |
| PS-OQ-12 | How are gate waivers and exceptions represented so they remain visibly exceptional?                                                                                                                                                                                     | STEP-03 (GR-7)          |
| PS-OQ-13 | At what granularity must producing configuration be recorded (PR-27), and does insufficient configuration provenance invalidate an action or merely weaken it?                                                                                                          | STEP-02 / STEP-04       |

---

## 12. Traceability

### 12.1 Requirements

| Requirement                               | Where addressed                                                           |
| ----------------------------------------- | ------------------------------------------------------------------------- |
| FR-1 Roles and authority                  | Sections 4.1-4.8; PR-01 to PR-05, PR-22 to PR-24                          |
| FR-2 Governance semantics for progression | Sections 5.1-5.3; PR-10 to PR-15; Section 8                               |
| FR-4 Self-approval invalid                | Section 6; PR-16 to PR-21, PR-27, PR-28; INV-01 to INV-03, INV-14, INV-17 |
| FR-6 Provenance tracking                  | Sections 4.1, 4.5, 5.1; PR-06 to PR-09, PR-27; OBJ-05, OBJ-08             |
| GR-1 Human authority explicit             | PR-05, PR-13; ACT-05                                                      |
| GR-7 Gate exceptions visible              | ACT-05; OBJ-12; PS-OQ-12                                                  |
| PE-2 Agent agreement is not evidence      | PR-20; INV-11                                                             |
| NG-1 No premature technology selection    | Section 10                                                                |
| NG-4 Hypotheses are not requirements      | Sections 4.7, 10                                                          |

### 12.2 Architectural decisions

| Decision                                          | Where operationalized                                                     |
| ------------------------------------------------- | ------------------------------------------------------------------------- |
| D1 Protocol semantics are normative               | Sections 1, 3; PR-25                                                      |
| D2 Protocol, schema, state separate               | Section 3; Section 10; PR-25                                              |
| D3 Knowledge classes first-class                  | Section 3 (closing subsection); action categories ACT-01 to ACT-07        |
| D4 Authority modeled separately from role labels  | Sections 4.1-4.6; PR-01 to PR-04, PR-17, PR-27                            |
| D6 Objective checks separated from human judgment | Section 6.4; Section 9                                                    |
| D8 Evaluators advisory unless granted authority   | Section 4.8; PR-15, PR-22, PR-23                                          |
| D5, D7                                            | Touched minimally (PR-26, Section 10); fully owned by STEP-02 and STEP-03 |

### 12.3 STEP-01 acceptance checks

| Acceptance check                                                            | Where satisfied                                                         |
| --------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Protocol semantics distinguish protocol, schema, and state                  | Section 3; PR-25                                                        |
| Roles and authority defined without relying on role names alone             | Sections 4.2-4.4, 4.6; PR-01 to PR-04                                   |
| Actor identity, producer, reviewer/challenger, and approver distinguishable | Sections 4.1, 4.5; PR-06 to PR-08, PR-27                                |
| Self-approval invalidity stated as a normative constraint                   | Section 6; PR-16 to PR-21, PR-27, PR-28                                 |
| Consequential gate acceptance explicitly human-authorized                   | PR-05, PR-13; ACT-05; OBJ-04                                            |
| External evaluator findings advisory unless authority granted               | Section 4.8; PR-15, PR-22, PR-23; INV-05                                |
| MOD-W Moderator and PROD-W Product Moderator not conflated                  | Section 2; PR-24                                                        |
| No implementation technology or serialization selected                      | Section 10                                                              |
| Transferability evidence proposed under research governance                 | MW-OBS-008 proposed in `research/mod-w-transferability/observations.md` |

---

## 13. Change Notes

| Date       | Version | Change                                                                                                                                                                                    | Reason                                                                                                                                                                                                                                                                                                                                                                 |
| ---------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2026-09-30 | 0.1     | Initial normative protocol semantics produced under STEP-01                                                                                                                               | First PROD-W product artifact; operationalizes D1-D4 with relevant D6 and D8 boundaries                                                                                                                                                                                                                                                                                |
| 2026-09-30 | 0.1     | Added Section 4.1 producing-configuration subsection, Section 6.5, PR-27, PR-28, INV-17, PS-OQ-13; sharpened PS-OQ-02                                                                     | MOD-W Moderator confirmed that controlled re-execution (same prompt, same role, different model) is a deliberate project practice. The protocol had to state what it produces - findings and revisions - and what it cannot produce - independence or acceptance - rather than leave self-verification as an undifferentiated open question                            |
| 2026-09-30 | 0.2     | Status changed to Accepted by MOD-W Moderator (Frank McGuire), conditional on `mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-DEV-TEAM.md` and `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` | STEP-01 gate closed. A scoped Tech Lead review of architecture-level content in this artifact (PR-27 §4.1; AUTH-P/A/V/G taxonomy §4.4) was recommended by the delta review (Section 5) but not commissioned. This acceptance is recorded as an explicit, visible waiver of that review per GR-7 and OBJ-12, not as a finding that no architecture-level content exists |
| 2026-09-30 | 0.2     | Recorded that Phase 3b (QA SubAgent, `qa.md`) and Phase 3c (Product Owner SubAgent sign-off) were also not produced for this artifact                                                     | MOD-W Moderator (Frank McGuire) waived both, on the same terms as the Tech Lead gate, recorded as visible exceptions per GR-7 and OBJ-12 in `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Section 9, not as silent conformance                                                                                                                                     |

**Acceptance status:** Accepted by MOD-W Moderator (Frank McGuire) on 2026-09-30, conditional on the dispositions in `mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-DEV-TEAM.md` and `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md`. Three Phase 3 checkpoints were not run for this artifact and are recorded as explicit, visible waivers per GR-7 and OBJ-12, not as findings that no review was warranted: 3a Tech Lead review of architecture-level content (delta review Section 5), 3b QA SubAgent validation, and 3c Product Owner sign-off (both delta review Section 9).
