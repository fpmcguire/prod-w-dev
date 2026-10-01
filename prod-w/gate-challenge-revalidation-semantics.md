---
artifact:
  type: gate-challenge-revalidation-semantics
  id: PROD-W-GCR
  version: 0.1
  created: 2026-10-02
  updated: 2026-10-02
  status: Accepted
  produced_by: Development Team
  produced_under: STEP-03
source:
  step: mod-w/step-03.md
  architecture: mod-w/architecture.md
  domain_language: mod-w/domain-language.md
  product_definition: mod-w/product.md
  protocol_semantics: prod-w/protocol-semantics.md
  evidence_knowledge_model: prod-w/evidence-knowledge-model.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Gate, Challenge, Disagreement, and Revalidation Semantics (Initial Conceptual Semantics)

**Product:** PROD-W - Moderated AI-Assisted Product Development Workflow
**Artifact:** Representation-neutral semantics for independence over accepted items, gates and gate outcomes, challenges, disagreement, escalation, conditional progression, waivers, correction/supersession/withdrawal authority, and revalidation
**Produced under:** STEP-03
**Status:** Accepted by MOD-W Moderator on 2026-10-02. See `mod-w/reviews/MODERATOR-REVIEW-STEP-03.md`.

---

## 1. Purpose and Standing

### 1.1 Purpose

`prod-w/protocol-semantics.md` (STEP-01) says who may act and what makes an action invalid. `prod-w/evidence-knowledge-model.md` (STEP-02) says what knowledge is, how it is related, and what events put a dependent item in question. Both deliberately left the same thing open: **what happens at a gate, when someone disputes something, when someone changes something that was accepted, and when support changes after a decision.**

This artifact supplies that. Its job is the Product Definition's core problem seen from the progression side: plausible ideas, weak evidence, agent agreement, and inherited assumptions must not become unjustified confidence that a product should be built. STEP-02 made the knowledge distinguishable. STEP-03 makes the _moments of reliance_ governable: the acceptance, the challenge, the change to something already relied on, and the reconsideration when support moves.

Three self-approval paths were left open by earlier steps and are closed here before any gate mechanics are stated:

1. A decision cites items its decision-maker produced (EK-OQ-05, Section 4).
2. A producer calls a meaning-changing edit a "correction" and keeps another actor's acceptance (EK-OQ-17, Section 10).
3. A producer withdraws or supersedes its own item, including its own counter-evidence, to shed the opposition recorded against it (D-05b, Sections 6 and 10).

### 1.2 Standing

This is a **product artifact**. It extends the accepted normative core (STEP-01) and the accepted evidence and knowledge model (STEP-02) and, per D1, is normative at the level of _semantics_. Documents, schemas, state records, prompts, and validators are projections of it, not substitutes for it.

It is **conceptual**. Tables, rule identifiers, and the lists of acts are expository devices for human review. They are not a protocol representation, a lifecycle, or a state vocabulary.

It does not describe or alter the governance of the `prod-w-dev` development project (Section 2).

### 1.3 What this artifact deliberately does not select

Operationalizes D2, NG-1, NG-2.

Nothing here selects, favors, prototypes, or assumes:

- a serialization, document format, or metadata model;
- a schema language or structural type system;
- a protocol or transport;
- a workflow engine, state machine, lifecycle graph, or orchestration framework;
- a storage model (document metadata, sidecar files, centralized state, ledger, graph store, or a hybrid);
- a validator, CLI tool, agent harness, prompt format, or runtime integration;
- any condition or state name.

Gate outcomes (acceptance, refusal, deferral, and so on) are described as **recorded acts by an authorized actor**. Conditions such as "open requirement," "exposed," "contested," or "unresolved" are **descriptive prose for what the record shows**. They are not states, no transitions between them are defined, and the order in which acts may occur is limited only by whether each act is valid (EKR-02 carries over unchanged). No `DIVERGENT` state or equivalent is adopted. Product Skeptic, Product Advocate, a Product Knowledge Ledger, a null-hypothesis framing pattern, a document-metadata model, and an external-evaluator contract are not treated as requirements (NG-4).

### 1.4 Limits of what the semantics can do

Three limits are stated rather than implied.

- **Unrecorded things cannot be governed.** A challenge nobody records, a contribution nobody discloses, or a contradicting finding nobody attaches is invisible to any semantics (STEP-02 Section 1.4). These semantics make concealment _invalid to rely on once it surfaces_ (Section 4.7), not impossible.
- **Judgment remains judgment.** Whether a response answers a challenge, whether a residual disagreement is tolerable, and whether a change alters meaning are not decided by this artifact. It says who may decide, who may not, and what must be visible (Section 14).
- **Independence is checkable by identity, not by substance.** Two different identities may still be one person's two accounts. Section 4 states what is checked and what is declared and left open to challenge.

### 1.5 Resolution digest

The open questions this step owns, and where each is resolved. The sections give reasoning; this table gives the answer.

| Question | Resolution in one line | Section |
| --- | --- | --- |
| **EK-OQ-05** What is "the accepted item"? | For a consequential acceptance it is the **accepted set**: the subject, every material basis item followed transitively, the materiality and dependency designations, challenge responses, and verification records relied on. The acceptor must be a producer of none of them. | 4 |
| **EK-OQ-17** Who designates a correction? | A producer may _propose_. For a **standing** item the designation takes effect only on **independent confirmation** by a human with AUTH-G for the scope who is not a producer of the item or the change, with notice to the original acceptor. Unconfirmed means supersession for reliance. | 10 |
| **EK-OQ-17 / D-05b** Withdrawal of own item and own counter-evidence | Valid as a **visible event with a recorded rationale**. It never erases the item, the contradiction, the requirement it created, or its place in decision history. | 10 |
| **EK-OQ-06** Another actor's item | Effective for reliance only through a human with AUTH-G for the item's scope. Anyone else's attempt is recorded as a challenge, counter-evidence, or advisory finding. | 10 |
| **EK-OQ-04 / D-08** Dependent effect | Challenge: contestation and exposure. Source-identified counter-evidence: requirement. Bare contradicting claim or inference: contestation and exposure, with defined promotion paths to a requirement. | 7 |
| **EK-OQ-04** Reliance while exposed or open | Exposure never bars reliance. New reliance on an item with an open requirement needs closure or a recorded reliance authorization by an independent human with AUTH-G. | 7, 9 |
| **EK-OQ-04** Unanswered challenge in a decision basis | Every challenge standing against the basis must receive a recorded **treatment** at the gate: answered, conceded by the challenger, moot, accepted as residual, or covered by an exception against a stricter gate rule. Where the acceptor can do none of these, it refuses or defers and escalates instead. | 6, 8 |
| **EK-OQ-02** Validation of non-gate hypotheses | Always an independent human with AUTH-G. Burden is managed by narrow grant _scope_, not by a lesser acceptance class. | 12 |
| **EK-OQ-03 / PS-OQ-06** Collective identities, delegation | Collectives may be recorded as producers and expand to members for independence. AUTH-G is individual and human. Delegation conveys no authority. | 4 |
| **EK-OQ-07** Disputed materiality | A challenged non-material designation restores the presumption pending resolution by an independent human with AUTH-G. | 7 |
| **EK-OQ-08 / PS-OQ-12** Conditional progression and waivers | Defined as separate instruments with a distinguishing test: does the requirement remain open and tracked afterward? | 9 |
| **EK-OQ-10** Time and evidence age | No direct effect on exposure or requirement. An input to sufficiency, a possible gate-defined recency check, and a stated ground for a request. | 13 |
| **EK-OQ-13 / PS-OQ-03** Disagreement | A **derived condition** over challenges, contradictions, and the absence of an authorized resolution. Not a state, not a stored relationship of its own. | 8 |
| **EK-OQ-16** Non-decision dependents | Two tiers by consequential reach. No lesser acceptance class. | 11 |
| **PS-OQ-02** Verification independence | Required for gate-required formal checks of produced items; not otherwise. Agent-held AUTH-V routed to STEP-04 with an interim constraint. | 4, 5 |
| **PS-OQ-07** Producer set change | Append-only for independence. | 4 |
| **PS-OQ-01 / EK-OQ-11** Explicit or derived conditions | Semantic requirement stated (derivable, enumerable, never cleared except by a recorded act). Representation routed to STEP-05. | 8, 16 |
| **EK-OQ-01** Gate evidence categories | Gate-level semantic slots defined. Category thresholds routed to STEP-06. | 5, 16 |
| **PO A-3** Assumption-rooted support | Defined as a derivable property that gate bases must identify. | 12 |

### 1.6 Reading conventions and identifiers

- "Item," "record," and "relied on" are used as in STEP-02 Section 3.4.
- "Producer," "acceptor," "challenger," and "verifier" are participation capacities (STEP-01 Section 4.5).
- "Human with AUTH-G for the scope" is shortened to **gate authority holder** where the scope is clear.
- "Must" and "may" are used normatively. "Visible" means shown in any view of the item and of its dependents.
- New identifiers avoid collision with earlier steps: `GCR-` rules, `GCO-` objectively checkable conditions, `GCJ-` contextual judgments, `UAD3-` declared choices, `GC-OQ-` routed open questions, `AC3-` acceptance checks. `TRG-6` continues STEP-02's trigger numbering.

---

## 2. Governance Context

### 2.1 Authority

**This artifact is authored under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-03 acceptance for `prod-w-dev` and is the authority for accepting this artifact. The Development Team produced it and may not accept it.

The **PROD-W Product Moderator** referred to here is a _future PROD-W protocol role_. It has no authority in `prod-w-dev`. Where this document says an act requires a "human with AUTH-G," it states a property of the future protocol using STEP-01's authority model unchanged (PR-24). Nothing here grants authority to any actor in `prod-w-dev`.

### 2.2 MW-ADAPT-001

STEP-03 follows the active local adaptation **MW-ADAPT-001**. Section 15 is the Undecided Architecture Declaration. After it, Tech Lead or QA is expected to sample for unlisted choices in authority, independence, evidence standing, and revalidation before acceptance (`research/mod-w-transferability/adaptations.md`, STEP-02 re-evaluation). Section 15.4 gives the sampling targets the Development Team recommends. The Development Team cannot certify that its declaration is complete (Section 15.1).

### 2.3 Review sequence

| Point | Record | Standing for this deliverable |
| --- | --- | --- |
| Setup review (Tech Lead) | `mod-w/reviews/TECH-LEAD-REVIEW-STEP-03-SETUP.md` | Complete. Approved by the Moderator on 2026-10-02 (`mod-w/reviews/MODERATOR-REVIEW-STEP-03-SETUP.md`). This was a review of the work package, not of this artifact. |
| Tech Lead or QA sampling for unlisted choices | Moderator-directed Tech Lead review in chat, recorded by `mod-w/reviews/MODERATOR-REVIEW-STEP-03.md` | Complete. Two findings were returned to the Development Team and fixed before acceptance. |
| Phase 3b QA | Waived by MOD-W Moderator | Waived before final acceptance in `mod-w/reviews/MODERATOR-REVIEW-STEP-03.md`. |
| Phase 3c Product Owner sign-off | Waived by MOD-W Moderator | Waived before final acceptance in `mod-w/reviews/MODERATOR-REVIEW-STEP-03.md`. |
| Final acceptance | `mod-w/reviews/MODERATOR-REVIEW-STEP-03.md` | Accepted on 2026-10-02. |

The MOD-W Moderator approved the Tech Lead review and Development Team work, waived missing Phase 3b QA and Phase 3c Product Owner sign-off before final acceptance, and accepted this artifact on 2026-10-02.

### 2.4 Production note

Produced by the Development Team using Claude Code (model `claude-sonnet-5-5`). The Development Team re-read its own draft against the acceptance checks before submission. That is self-review: it produced revisions and the Section 15 audit pass, and it confers no independence and no verification for gate purposes (PR-27, PR-28).

---

## 3. Relationship to `prod-w/protocol-semantics.md` and `prod-w/evidence-knowledge-model.md`

### 3.1 What is preserved without change

This artifact does not change, weaken, reinterpret, or add exceptions to any of the following:

- the authority model: actors, roles, grants, the four authority classes, and AUTH-G being human-only (PR-01 to PR-05);
- attribution and capacity rules (PR-06 to PR-09);
- action validity and the visibility of invalid actions (PR-10, PR-11) and the action catalog ACT-01 to ACT-07;
- acceptance semantics: sufficiency, not truth; explicit, attributable, human, and independent where consequential (PR-12, PR-13);
- verification as bounded by named criteria (PR-14); advisory findings (PR-15, PR-22, PR-23);
- self-approval invalidity and independence by actor identity (PR-16 to PR-21, PR-27, PR-28);
- the separation of the two Moderator roles (PR-24); representation independence (PR-25);
- STEP-02's knowledge classes, relationships, provenance elements, evidence expectations, and presumed materiality (EKR-01 to EKR-36, EKR-40, EKR-41).

### 3.2 What this artifact adds

| Handed forward | Where addressed |
| --- | --- |
| STEP-01: "gate/challenge/disagreement/revalidation mechanics in full (STEP-03)" | Sections 5 to 11 |
| STEP-01 ACT-03: "answering, routing, and escalating challenges are STEP-03 work" | Sections 6, 8 |
| STEP-01 ACT-05: gate waivers and exceptions (PS-OQ-12) | Section 9 |
| STEP-01 PR-26 minimal revalidation statement | Section 11 |
| STEP-02 Sections 9.4, 9.5, 10.5, 10.7, 10.8: record content stated, gate consequences deferred | Sections 4 to 8, 11 |
| STEP-02 EK-OQ-01 to EK-OQ-08, EK-OQ-10, EK-OQ-11 (part), EK-OQ-13, EK-OQ-16 | Section 1.5 |
| EK-OQ-17 (`mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`, Addendum 2026-10-01) | Section 10 |
| QA D-05b, D-08 and Tech Lead follow-up recommendations | Sections 7, 10 |

### 3.3 Provisions of accepted artifacts this artifact refines

STEP-01 and STEP-02 are accepted and are **not edited**. The following provisions are made more specific, or in one case narrowed, by this artifact. Each is also declared in Section 15.

| Provision | What STEP-03 does | Direction | Declared |
| --- | --- | --- | --- |
| STEP-02 TRG-2 and EKR-37: "a contradicting claim or inference" creates a requirement by itself | A **bare** contradicting claim or inference no longer creates a requirement by itself. It produces contestation and exposure, and reaches requirement status by defined paths (Section 7). Source-identified counter-evidence is unchanged. | **Narrowing** | UAD3-12 |
| STEP-02 EKR-39: "contradiction and challenge take visible effect immediately" | Reads as: challenge produces contestation and exposure; counter-evidence produces a requirement (Section 7.3). | Clarifying | UAD3-12 |
| STEP-02 EKR-37, EKR-38: a requirement "on that dependent" per event | A requirement is a single obligation per dependent carrying every triggering event as a reason (Section 11.2). | Clarifying | UAD3-22 |
| STEP-02 Section 10.5: who may withdraw, supersede, invalidate | Separated into producer-owned acts and authority over another actor's item (Section 10). | Specifying | UAD3-17 |
| STEP-02 EKR-10, Section 6.7: correction versus supersession | Adds designation authority, confirmation, and notice (Section 10). | Specifying | UAD3-15 |
| STEP-02 EKR-38, Section 10.8: closure authority for non-decision dependents (EK-OQ-16) | Two tiers by consequential reach (Section 11.4). | Specifying | UAD3-23 |
| STEP-02 EKR-30: decision record cites opposition | Gate consequence added: an acceptance whose record omits recorded opposition lacks required content and is invalid (Section 5.5). | Specifying | UAD3-09 |
| STEP-02 trigger catalog (non-exhaustive) | Adds **TRG-6**: acceptance found invalid or withdrawn (Section 4.7). | Extending | UAD3-06 |
| STEP-01 ACT-06: request revalidation | A request records its stated basis (Section 7.5). | Clarifying | UAD3-13 |
| STEP-01 ACT-05, ACT-07, PR-16, PR-21: "the accepted item" | Defined (Section 4). | Specifying | UAD3-01 |

### 3.4 How the refinements take effect

On acceptance of this artifact, it is the governing statement for the provisions in Section 3.3, read together with the unedited earlier artifacts. The earlier files remain as accepted. If a reader opens only STEP-02 TRG-2, it will still say that a contradicting claim creates a requirement. **That is a known reading hazard.** Whether to authorize a one-line pointer annotation in `prod-w/evidence-knowledge-model.md` is the MOD-W Moderator's decision. The Development Team has made no edit and requests none.

---

## 4. Independence Basis and "Accepted Item" Semantics

Operationalizes D4, D6; extends FR-4. Resolves **EK-OQ-05** (first-priority work), **PS-OQ-07**, and the identity half of **EK-OQ-03 / PS-OQ-06**. Addresses **PS-OQ-02**.

### 4.1 The gap

STEP-01 invalidates an acceptance where the acceptor is a recorded producer of "the accepted item" (PR-16, PR-21). It never says what that item is when a decision cites claims, evidence, assumptions, and inferences others produced, or the decision-maker produced. STEP-02 keeps every cited item's producers resolvable (EKR-32) and stops there.

Read narrowly ("the item" is the decision record's own text), the rule is trivially met: the decision-maker did not write the record's citations. Read narrowly, a gate authority holder who produced the demand claim, the key inference, and the non-materiality designation can accept the go decision resting on them. That is PR-16 reached through citation.

### 4.2 Vocabulary

| Term | Meaning |
| --- | --- |
| **Acceptance act** | The recorded determination by a gate authority holder that conditions are sufficient (ACT-05), a decision is committed (ACT-07), or another act in Section 4.4 is performed. |
| **Acceptance-act content** | What the acceptor itself contributes in making the determination: the determination, its scope, the stated rationale for sufficiency, the treatment of each challenge (Section 6.6), any conditions, the residual-risk statement, and the independence declaration (GCR-09). |
| **Subject** | What is being accepted or committed to: the proposal, deliverable, or course of action, as it stood at acceptance (EKR-10), **excluding** acceptance-act content. |
| **Material basis** | Every item the subject relies on whose dependency is material or presumed material (EKR-35), followed transitively (the closure defined in 4.3). |
| **Accepted set** | The set of items over which independence is evaluated for a consequential acceptance (4.3). This is the answer to EK-OQ-05. |
| **Standing item** | An item that has been validly accepted, or is a member of the accepted set of any recorded consequential acceptance or decision. Derivable from the record. Used in Sections 10 and 11. |

### 4.3 The accepted set

For a **consequential gate acceptance, a consequential decision, or the validation of a material hypothesis**, the accepted set is the union of:

1. **The subject**, as it stood at the acceptance, excluding acceptance-act content.
2. **The material basis.** Every item cited as basis, and every item reached from it by following material dependency links of any kind (support, derivation, reliance under assumption, upstream decision), through inferences and derived evidence, until the chain ends at evidence, an assumption, or an item with no further material dependency. Items presumed material under EKR-35 are included unless a non-material designation with rationale is recorded and has not been successfully challenged (Section 7.7).
3. **The designations.** Every materiality designation, dependency link, and dependency change that shapes the basis, **including the non-material designations that keep an item out of 2**. The actor who recorded a designation is its producer.
4. **The responses.** Every recorded response to a challenge or contradicting item that the acceptance relies on in treating it (Section 6.6).
5. **The formal-check records the acceptance relies on.** A verification the acceptor treats as satisfying a gate-required formal check is a member. The verifier is its producer.

**Not in the accepted set:**

- **Acceptance-act content.** An acceptor's own determination is not production of the thing accepted. If it were, no acceptance could be valid.
- **The opposition itself.** Challenges and contradicting items recorded _against_ the basis are cited and treated (Section 5.5). Their producers are not producers of the accepted set. An actor who challenged the basis, or recorded counter-evidence against it, is not thereby disqualified from accepting.
- **Items outside the material basis**: background items with a recorded non-material designation that stands.
- **Upstream acceptances as acts.** An actor who accepted an upstream decision has not produced the upstream decision's subject by accepting it. The upstream decision's _basis items_ remain in the closure and count.
- **The gate definition** (Section 5.2). It is the standard applied, not the item accepted. Section 5.3 limits what may be done with it after the fact.

### 4.4 The accepted item for each act

Not every acceptance-type act needs the full set. The set is sized to what is being determined.

| Act | "The accepted item" for independence |
| --- | --- |
| Consequential gate acceptance (ACT-05); consequential decision (ACT-07) | The full accepted set (4.3) |
| Waiver, exception, or conditional progression authorization (Section 9) | The accepted set of the gate or progression it concerns |
| Validation of a material hypothesis (Section 12) | The hypothesis as it stands, its recorded criteria, the evidence and test results bearing on it, challenge responses, and the material basis closure |
| Reaffirmation of a consequential decision, or of a dependent cited by one (Section 11) | A fresh acceptance: the full accepted set over the **current** basis |
| Reaffirmation of any other dependent (Section 11) | The dependent as it stands and its material basis closure |
| Correction confirmation (Section 10) | The item as changed, the change, its rationale, and the earlier acceptance referenced |
| Authority closure of a challenge (Section 6) | The challenged item or determination, and the responses |
| Resolution of a disputed designation (Section 7.7) | The designation, the items whose materiality is at issue, and the dependent |
| Invalidation or withdrawal of reliance (Section 10) | None. These are conservative acts (GCR-05). The _replacing_ item, if any, needs its own acceptance over its own set |

### 4.5 Rules: independence over the accepted set

| ID | Rule |
| --- | --- |
| GCR-01 | For a consequential gate acceptance, consequential decision, or validation of a material hypothesis, **the accepted item is the accepted set** of Section 4.3. Other acts use the sets in Section 4.4. |
| GCR-02 | Acceptance-act content is not production of the accepted set. An acceptor that drafted the subject, including a recommendation it later adopts as a decision, is a producer of the subject. |
| GCR-03 | An acceptance is invalid where the acceptor is a recorded producer of **any member** of the accepted set. No exemption exists for small, late, editorial, or peripheral contributions: how much a contribution mattered is a sufficiency judgment the interested party would be making about itself. |
| GCR-04 | The accepted set is computed from the record as of the acceptance act and is fixed for that acceptance (EKR-31). Later additions to the material basis are events (TRG-5), not retroactive changes to the set. |
| GCR-05 | **Recusal is asymmetric.** A producer of the accepted set may not perform any act whose effect is favorable to the set: acceptance, waiver, conditional progression, correction confirmation, reaffirmation, closure of a challenge in the set's favor, or acceptance of residual risk. A producer who holds the necessary authority **may** perform acts whose direction is conservative: refusal, deferral, escalation, a request for revalidation, a challenge, withdrawal or retirement of its own item, or invalidation. Conservative acts remain challengeable like any other. |
| GCR-06 | **No waiver, exception, deferral, conditional progression, escalation outcome, or relabeling validates an acceptance that PR-16 to PR-21 invalidate.** Independence is a condition of validity, not a gate requirement. It can be satisfied by a different acceptor or by re-basing the subject on independent items (recorded, visible). It cannot be dispensed with. |

### 4.6 Who counts as a producer

**Producer sets are append-only for independence (PS-OQ-07).** An item's recorded producers may be added, never removed or transferred out, for the purpose of evaluating independence. Restating, re-authoring, renaming, or moving an item does not remove a producer (STEP-01 Section 6.3). An omitted contributor may be added by disclosure.

**Collective identities (EK-OQ-03, first half).** A team, organization, or agent fleet may be recorded as a producer if its **membership is recorded**: the individual human and agent identities it comprised at the time of production. For independence, the collective expands to its members. If any member is the acceptor, the acceptor is a producer. Membership changes do not remove earlier producer status. AUTH-G may be held and exercised only by an **individual human identity** (PR-05, PR-06): a collective cannot be an acceptor.

**Agents and assigners (EK-OQ-03, second half).** An AI agent is an actor identity whose configuration is provenance (PR-27). The central PROD-W flow is that agents produce and a human with AUTH-G accepts, so STEP-01's reading stands: the agent is the producer. The remaining risk is a human who supplies the substance and uses the agent as a typist.

- **Assignment** is a recorded relation: who assigned the work to whom. It is provenance. Assignment by itself does not make the assigner a producer.
- A human who **supplies the substance of an item** (its conclusion, its content), or who **adopts, signs, or records an item as their own**, is a producer.
- Whether an assigner supplied substance is a contextual judgment (GCJ-09). The acceptor must **disclose** relevant assignments in its acceptance-act content (GCR-09), and any actor with AUTH-A may challenge a producer attribution. A disputed attribution is resolved by a gate authority holder independent of the disputed item. **Until it is resolved, the disputed actor is treated as a producer for acceptances that actor would perform.**

**Delegation conveys no authority.** Authority is neither transitive nor inheritable (PR-04). "Delegation" in PROD-W is assignment of work, recorded as above. An assignee acts only under grants it holds itself. A grant is a separate act by a granting authority (PS-OQ-05, routed to STEP-04).

| ID | Rule |
| --- | --- |
| GCR-07 | Recorded producers of an item may be added and never removed or transferred out for independence purposes. A disputed producer attribution is treated conservatively against the disputed actor's own favorable acts until a gate authority holder independent of the item resolves it. |
| GCR-08 | A collective identity may be a recorded producer only with recorded membership, and expands to members for independence. AUTH-G is held and exercised only by an individual human. Delegation never conveys authority. Assignment is recorded as provenance and makes the assigner a producer only where the assigner supplied the item's substance or adopted it. |

### 4.7 Invalid acceptances found later

An acceptance that violates GCR-03 or any other validity condition (Section 5.4) has **no intended effect** from the outset (PR-11). It stays recorded and visible as invalid. Discovery is a recorded event.

- The gate was not accepted. Anything that progressed through it did so without valid acceptance.
- **TRG-6 (new).** An acceptance on which a dependent item or progression relied is found invalid, or is withdrawn by its own acceptor (Section 10.7), is a trigger. A requirement arises on every dependent that relied on it (STEP-02 EKR-37 applies).
- The acceptor's validity does not depend on anyone noticing at the time (STEP-01 Section 6.1).

### 4.8 Substantive independence is judgment; declaration is required

Two distinct identities may be one person's two accounts, or may share an undisclosed relationship to the item. That is a contextual judgment (EKJ-04, HJ-07). The semantics do not pretend to check it. They require that it be **stated**.

| ID | Rule |
| --- | --- |
| GCR-09 | The acceptance-act content of every consequential acceptance includes an **independence declaration**: that the acceptor knows of no undisclosed production, assignment, or substantive contribution by itself, or by an identity it controls, to any member of the accepted set, and any assignment relations it knows of. The declaration is an assertion. It is challengeable like any other and is never proof. |

### 4.9 Verification and independence (PS-OQ-02)

PS-OQ-02 asked whether verification needs a normative independence requirement as acceptance does, or whether independent acceptance is enough. Re-execution cannot supply it (PR-27, PR-28).

**Position.** Independent acceptance is _not_ sufficient protection by itself where a gate relies on a **formal check** over a produced item, because the acceptor may reasonably trust a check the producer ran on its own work.

| ID | Rule |
| --- | --- |
| GCR-10 | A formal check that a gate **requires** is satisfied only by a verification whose verifier is not a producer of the verified item (PR-19 generalized). A verification the acceptance relies on is a member of the accepted set (GCR-01), so an acceptor cannot rely on its own. A producer's self-verification is recorded, is not independent, and does not satisfy a required check. Where a gate does not require independent verification of an item, a verification is an ordinary record whose weight is a contextual judgment. |
| GCR-11 | **Interim, routed to STEP-04.** A verification by a non-human actor holding AUTH-V satisfies a gate-required formal check only where the check's named criteria are decidable from the record. Where the criteria require interpretation, the output is an advisory finding. STEP-03 does not decide whether AI agents may hold AUTH-V in general (PS-OQ-08; GC-OQ-03). |

---

## 5. Gate Model and Gate Outcomes

Operationalizes D1, D4, D6; FR-2, FR-3, GR-1, GR-5, HA-1, HA-2. Uses Section 4.

### 5.1 What a gate is

A **gate** is a defined decision point governing a stated **progression** (authorized movement of work, or of reliance, across a boundary) for a stated **scope**. It exists so that consequential transitions are explicit, attributable, and checkable (GR-1, GR-5).

A gate assumes **no universal lifecycle**. Gates may be revisited, may sit in loops and branches, and may be reopened by revalidation (GR-5, WD-5). This artifact defines no order among gates and no transitions between outcomes.

### 5.2 The gate definition and its semantic slots

A gate is defined before it is used. A **gate definition** is a recorded governance act by a human actor holding AUTH-G for the project's gate-definition scope. Who holds that scope in a project is role-assignment work (GC-OQ-06). The definition carries these **slots**. STEP-03 defines the slots. What fills them for a given product category is methodology (STEP-06; EK-OQ-01).

| Slot | What it states | Objectively checkable part | Contextual judgment part |
| --- | --- | --- | --- |
| **Progression and scope** | What may cross the gate, and for what scope | The definition exists and the act falls within it | Whether the scope is the right one |
| **Acceptor grants and acceptance rule** | Which AUTH-G grants may accept, and how many valid independent acceptances are required. The default is one. A gate may require several. Each must satisfy GCR-03. A producer's acceptance is never counted (PR-18) | Grants resolve; independent acceptances are counted | None |
| **Gate basis** | The accepted set (Section 4.3) together with the standing record bearing on it (Section 5.5) | The set and record are computable from links | Whether the basis is the right one |
| **Required evidence** | Slots, each stating: the target to be evidenced, the evaluation dimension (STEP-02 Section 7.3), the acceptable evidence basis kinds, any source-independence expectation (lineage), and optionally a recency criterion (Section 13) | Each slot is filled by present items with the designations STEP-02 requires (EKO-04, EKO-05), or by a visible absence statement. Recency is checked against recorded observation times | Relevance, adequacy, and sufficiency of the evidence for the target (EKJ-02, EKJ-03) |
| **Required challenge criteria** | Which targets must have been challenged, and by whom. Whether challenger independence is required. Whether any response rule is stricter than the default of Section 5.5 | The challenge exists; the challenger is not a producer of the challenged item (OBJ-06); required treatments are recorded | Whether the challenge was adequate; whether a response was adequate (EKJ-12) |
| **Formal checks** | Named criteria whose satisfaction the gate requires, and whether verification must be independent | A verification exists, names its criteria (OBJ-13), and its verifier meets GCR-10 | None. This is the bounded part (PR-14) |
| **Stricter conditions** (optional) | Conditions a project adds, for instance that disagreement on a stated dimension be resolved | Present or absent | Whether satisfied, where the condition is itself a judgment |
| **Contextual sufficiency determination** | The acceptor's judgment that the foregoing is sufficient for the scope | The acceptance act exists and is valid | All of it (HJ-01, HJ-05, HJ-08) |

A required-evidence slot may be filled by a **visible absence statement**: an explicit record that no such evidence exists (PE-1). A visible absence statement makes the absence visible. It does **not** satisfy the slot. The condition stays unsatisfied. The gate can then be accepted only with a recorded exception (Section 9.4) or, where what is missing is validation of a relied-on material hypothesis, only under conditional progression (Section 9.2). An exception alone cannot cover a missing validation (Section 9.4, non-waivable item 6).

### 5.3 Amending a gate definition

A definition applies to an acceptance as it stood at the time of the acceptance act. Amending a definition so that a basis already refused or deferred now passes would let the standard move to fit the item.

| ID | Rule |
| --- | --- |
| GCR-12 | A consequential progression requires a gate definition recorded **before** the act. It identifies progression, scope, acceptor grants, acceptance rule, and the slots of Section 5.2, which may be empty but are present. A consequential decision made without a governing gate definition is recorded as a recommendation (ACT-07), and the missing gate is a visible condition. |
| GCR-13 | A gate definition amended **after a refusal or deferral on the same basis** applies to that basis only as a recorded exception (Section 9), whatever the direction of the amendment. |

### 5.4 Conditions for a valid acceptance

An acceptance (ACT-05, or an ACT-07 that authorizes progression) is valid only if all of the following hold at the acceptance act. Failing any, it is an invalid action with no intended effect and remains visible (PR-10, PR-11).

1. The acceptor is a human identity holding AUTH-G covering the gate's scope (PR-05, OBJ-02, OBJ-04).
2. A gate definition was recorded before the act, and the progression falls within it (GCR-12).
3. The accepted set is computable, and every member's producers are recorded and resolvable (EKR-32).
4. The acceptor is a producer of no member of the accepted set (GCR-03).
5. Each required formal check is satisfied, with independent verification where required (GCR-10), or the shortfall is covered by a recorded exception.
6. Each required-evidence slot and required challenge criterion is satisfied, or the shortfall is covered by a recorded exception. A missing validation of a relied-on material hypothesis is covered only by a conditional progression authorization recorded at or before the acceptance, never by an exception alone (Section 9.4).
7. Every item in the standing record (Section 5.5) is cited with a recorded treatment.
8. Every relied-on unvalidated material hypothesis or assumption is covered by a conditional progression authorization, and every open revalidation requirement on a basis item is covered by a closure or a reliance-while-open authorization (Section 9), recorded at or before the acceptance.
9. The act is explicit and attributable, states the determination, and carries the independence declaration (PR-13, GCR-09).

Authorizations and exceptions have **no retroactive effect**. A conditional progression authorization or waiver recorded after the acceptance does not make the acceptance valid. The acceptance remains invalid and a fresh act is required (GCR-47).

### 5.5 The standing record, opposition, and treatment

This is where STEP-02 Section 9.4 stopped ("stated only as record content"). STEP-03 supplies the gate consequence.

The **standing record** bearing on an acceptance, as of the acceptance act, is:

- every challenge and every contradicting item recorded against any member of the accepted set, or against the decision or gate itself, including those since withdrawn (with the withdrawal and its rationale, Section 10.4);
- the exposure of any basis item: that it depends on an item that is contested, has an open trigger, or has an open requirement (STEP-02 Section 10.7);
- every open revalidation requirement on a basis item, and every reliance under assumption and reliance while open;
- every earlier refusal or deferral recorded on the same gate and basis (Section 8.5);
- every exception already applying to a basis item.

Each is **cited, with a recorded treatment** (EKR-30 extended). One treatment record may address several items. The treatments available:

| Treatment | Meaning | Who determines |
| --- | --- | --- |
| **Answered** | A recorded response exists, and the acceptor judges it adequate for the scope | The acceptor (EKJ-12) |
| **Conceded or withdrawn by the challenger** | The challenger recorded resolution (Section 6.3) | The challenger; the acceptor records it |
| **Moot** | The target was withdrawn, or the matter is superseded and the carried challenge no longer applies | The acceptor, on the record |
| **Accepted as residual** | The matter remains unresolved and the acceptor judges the basis sufficient anyway, with rationale. The decision record carries a marker that it was accepted with that unresolved item (Section 8.5) | The acceptor (EKJ-12, EKJ-14) |
| **Covered by exception** | The gate definition imposed a stricter rule for this matter, and a recorded exception waives it (Section 9) | A gate authority holder independent of the accepted set |

**Default and strictness.** The default requirement of every gate is that each standing-record item has a recorded treatment. That is objectively checkable. Whether the treatment is adequate is judgment. A gate definition may require stronger treatments for stated targets, for example that challenges on the customer-evidence slot be answered. Accepting against such a rule needs an exception.

**Not available:** omitting the item, letting time pass, treating agent agreement as an answer, or having a non-AUTH-G actor determine the treatment.

### 5.6 Gate outcomes

Outcomes are **acts**, not states. The table lists what each is, who may perform it, and what it is not. Conditional progression, waiver or exception, and escalation are defined in Sections 9 and 8.

| Outcome | What it is | Who may perform | Effect on progression | Record must show | What it is not |
| --- | --- | --- | --- | --- | --- |
| **Acceptance** | A determination that the gate's conditions are sufficient for its scope, authorizing progression | A gate authority holder satisfying Section 5.4 | Authorizes progression through this gate for this scope | Acceptor, capacity, grant, scope, accepted set reference, the treatment of each standing-record item, formal-check status, independence declaration, the determination, time | A finding of truth (PR-12). Validation of an unvalidated hypothesis. A waiver. Inherited by a later gate. |
| **Refusal** | A determination that sufficiency is not found for the basis as it stands | A gate authority holder. A producer of the set may refuse (GCR-05) | None | Which conditions are unsatisfied, or why sufficiency was not found, and what would change the determination where known | Final. An erasure of items. An invalidation. A verdict on truth. |
| **Deferral** | A statement that no determination is made yet | A gate authority holder | None | The awaited condition, and the position expected to supply it | Acceptance by lapse. A refusal. A timed process. Time never converts a deferral into anything (PR-13). |
| **Conditional progression** (Section 9) | Authorization to progress or rely while a named condition remains unresolved and tracked | A gate authority holder independent of the accepted set | Authorizes progression for the stated scope, with the condition left open | See Section 9.2 | Validation. Ordinary acceptance. A waiver. |
| **Waiver or exception** (Section 9) | Dispensation from a specific unsatisfied gate requirement for a specific progression | A gate authority holder independent of the accepted set | Together with an acceptance, authorizes progression with a visible exception | See Section 9.4 | Ordinary conformance. Cure of invalid independence. |
| **Escalation** (Section 8) | Routing an unresolved matter to the authority able to resolve it | Any actor holding AUTH-A, AUTH-P, AUTH-V, or AUTH-G | None | See Section 8.4 | A closure, or a resolution of anything. |

An actor lacking AUTH-G for the gate performs none of acceptance, refusal, deferral, conditional progression, or waiver. Its corresponding output is an **advisory finding** that recommends one of them (PR-15, PR-23).

### 5.7 Gate acceptance, decisions, hypothesis validation, and the STEP-01 and STEP-02 records

- **Acceptance and decision.** A consequential gate acceptance is recorded as a **decision** (EKR-29) whose subject is the progression. A consequential decision (ACT-07) is made at a gate (GR-1). EKR-29 and EKR-30 apply in full, and Section 5.5 is their gate consequence. A decision record that omits recorded opposition lacks required content, so the act is invalid (PR-10), not merely incomplete.
- **Acceptance and validation.** A gate acceptance **never validates** a hypothesis. Validation is a separate acceptance-type record (Section 12). A gate may require it as evidence or as a challenge criterion. A gate accepted while a required validation is absent is accepted under conditional progression (Section 9.2), never silently and never by an exception alone.
- **Decision records after the fact.** A decision's basis is preserved as it stood (EKR-31). Later events are not edits to it. They are triggers, handled in Section 11.

### 5.8 External evaluators and gates

Operationalizes D8.

An external evaluator or any actor lacking authority for the matter may, at a gate: raise a challenge (AUTH-A), attach counter-evidence, satisfy the _existence_ of a required independent challenge (OBJ-06), supply a verification where it holds AUTH-V and GCR-10 and GCR-11 are met, request revalidation, respond, and escalate. Its findings enter the standing record and are cited and treated like any other (EKJ-13: weight is the acceptor's judgment).

It **may not** accept, refuse, defer, authorize conditional progression, waive, confirm a correction, close a challenge, reaffirm, or invalidate. Each of those requires AUTH-G, which an evaluator holds only through an explicit grant recorded in an approved PROD-W revision (PR-22). Its recommendation of any of them is an advisory finding. Being automated, persuasive, independent, or repeated does not change this.

### 5.9 Rules

| ID | Rule |
| --- | --- |
| GCR-14 | **Required evidence.** Presence and designation are objectively checkable. Relevance and sufficiency are judgment. A visible absence statement leaves the slot unsatisfied. No score, weight, or grade of sufficiency is defined or required (EKR-19). |
| GCR-15 | **Required challenge criteria.** The existence of a required challenge, and the independence of its challenger from the challenged item's producers, are objectively checkable. Adequacy is judgment. Any actor holding AUTH-A, including an external evaluator, may supply the challenge. A challenge by a producer of the challenged item is recorded and does not satisfy an independent-challenge requirement (PR-19). |
| GCR-16 | An acceptance is valid only if every condition of Section 5.4 holds. An acceptance failing any condition has no intended effect, remains visible as invalid, and gives rise to TRG-6 for anything that relied on it (Section 4.7). |
| GCR-17 | Every standing-record item is cited with a recorded treatment from the list in Section 5.5. The default requirement is that a treatment is recorded. A gate definition may require stronger treatments. Acceptance against a stricter rule requires an exception. Omitting a standing-record item makes the acceptance invalid. |
| GCR-18 | Gate outcomes are acts by a human gate authority holder. Non-AUTH-G actors produce advisory findings recommending them. The artifact defines no order of outcomes and no transitions among them. Acts of conservative direction (refusal, deferral, escalation) may be performed by a producer of the set; acts of favorable direction may not (GCR-05). |
| GCR-19 | A refusal states why. A deferral states what is awaited and from which position. Neither is final, neither erases anything, both remain in the standing record of any later acceptance on the same basis, and no passage of time converts either into acceptance or refusal. |
| GCR-20 | Acceptance concerns sufficiency, not truth. It applies to the subject as it stood (EKR-10), authorizes progression only for the stated scope, and is not inherited by a later gate or by superseding content. |
| GCR-21 | A consequential gate acceptance is recorded as a decision whose subject is the progression. Gate acceptance does not validate a hypothesis. Required validations are separate records (Section 12). |
| GCR-22 | External evaluators and other actors lacking authority may supply challenges, counter-evidence, verifications (within GCR-10 and GCR-11), requests, responses, and escalations. They never accept, refuse, defer, authorize conditional progression, waive, confirm a correction, close a challenge, reaffirm, or invalidate. Their recommendations are advisory findings. |

---

## 6. Challenge Model and Lifecycle

Operationalizes D3, D5; FR-5, WD-2, HA-3, GR-6. Resolves the challenge half of **EK-OQ-04** and part of **D-05b**.

STEP-01 made a challenge a first-class record and left answering, routing, and escalating to this step. STEP-02 extended challenge targets to evidence items and relationships (UAD-03).

The acts and conditions below are **not a sequence**. No state names are assigned. Each act is valid or invalid on its own authority and content, and the conditions are derivable from the record.

### 6.1 Raising a challenge

A challenge is an attributable ACT-03 by an actor holding AUTH-A. To be a valid challenge it records:

- the **challenger** and capacity;
- the **target**: an item, a relationship (including a materiality designation, a dependency link, a producer attribution, or a correction designation), or a decision or other determination (including an acceptance, a waiver, a conditional progression authorization, a closure, or the validity of an act);
- the **target scope**: which aspect is challenged. Examples: the item's content; its source; a relationship; a designation; an omission from a basis; the sufficiency of a basis for a stated purpose or scope; independence or attribution; the validity of an act;
- the **basis**: the stated ground. Examples: a disputed interpretation; an identified gap; an assertion of contradiction that cites recorded counter-evidence; a request to seek counter-evidence not yet found; a question of independence; a question of validity.

A challenge missing target or basis is not a valid challenge. It is recorded and visible as invalid (PR-10, PR-11). A challenge that cites source information not recorded as an evidence item is a challenge with a stated basis only. The counter-evidence must be attached as evidence (EKR-15) to count as such (Section 7.3).

**Who may raise.** Any actor holding AUTH-A, including AI agents and external evaluators. A producer may challenge its own item. That challenge is recorded and is not independent (PR-19). Raising is deliberately cheap (FR-5, WD-2). Control comes through **effects** (Section 7) and through **treatment at gates** (Section 5.5), not through restricting who may raise.

### 6.2 Response

Any actor may record a **response** linked to a challenge. The usual kinds:

| Kind | By | Effect |
| --- | --- | --- |
| Explanation | Anyone | A claim or inference. The respondent's assertion. |
| Evidence | AUTH-P (or AUTH-A for counter-evidence) | Evidence attached under ACT-02; may itself be challenged. |
| Concession through revision, withdrawal, or supersession of the target | The target's producer | Section 10 governs. A concession by the target's producer is not a closure. |
| Dispute of the challenge's standing or target scope | Anyone | A response. It does not close the challenge. |
| Escalation | Any participant | Section 8. |

**A response never closes a challenge**, including a response by the target's producer, and including one that the challenger declines to answer.

### 6.3 Closure

A **closure** is a recorded determination that a challenge no longer stands unresolved. Three kinds exist, and nothing else closes a challenge.

| Kind | By | Notes |
| --- | --- | --- |
| **Challenger resolution** | The challenger, recording withdrawal or satisfaction with a reason | Valid because it is the challenger's own challenge. It ends the challenge's contestation and exposure effect. It stays in the history of the target and of every decision that cited it. Any other AUTH-A actor may raise or adopt the challenge again. |
| **Authority closure** | A gate authority holder, determining that the response is adequate, or that the challenge does not stand or is moot, with rationale | The closer must be independent of the challenged item's accepted set and must not be the author of a challenged determination (Section 4.4). A person cannot close challenges to its own determination. Where only such an actor holds the grant, the matter is an authority gap (Section 8.6). |
| **Mootness by withdrawal** | The target's producer withdraws the target with no successor | The challenge remains in history. Nothing remains to challenge. Dependents receive TRG-1 (Section 10.4). |

**Not closure:** elapsed time, silence, absence of objection, the producer's response, agreement among agents, completion of downstream work, a verification, or a **supersession of the target**. Supersession carries the challenge forward (Section 6.5).

Authority closure is always an AUTH-G act, and AUTH-G scope may be narrow (Section 12.2). No lesser closing authority class exists in PROD-W (PS Section 4.4 admits none and STEP-03 does not create one).

### 6.4 Unanswered and unresolved, without clocks

A challenge is **unanswered** when no response and no closure is recorded. It is **unresolved** when no closure is recorded, whether or not answered. Neither condition has a deadline. Time never answers or resolves a challenge (EKR-05, EKR-38 by analogy).

An unresolved challenge does **not** block progression by itself (WD-2). It blocks only where a gate definition imposes a stricter rule, and then only in the sense that the gate cannot be accepted without an exception. What the protocol forces is **treatment at the gate** (Section 5.5), so that an unresolved challenge cannot stay hidden or stall indefinitely without somebody's recorded determination.

### 6.5 Carry-over on supersession

A producer could shed a challenge by superseding the challenged item. To prevent that:

- A challenge against an item **carries to any item recorded as superseding it**, visibly as carried, and remains unresolved until closed under Section 6.3.
- A contradicting or qualifying relationship recorded against the superseded item likewise attaches to the successor as **carried for re-assessment**. Whether the evidence still bears on the changed content is a judgment. A carried relationship counts as opposition for EKR-30 purposes. It does not create a fresh requirement on the successor's dependents, since the superseding event already did (TRG-1, TRG-4).
- The successor's producer, or anyone else, may ask for closure of a carried challenge. Authority closure may find it moot because the successor addresses it.

### 6.6 Treatment at gates: the answer for unanswered challenges in a decision basis

A challenge standing against a decision's basis at the moment of acceptance must be handled as follows.

| Required | How |
| --- | --- |
| **Recorded** | The decision record cites it and states how it stood: unanswered, answered, resolved, or withdrawn (EKR-30) |
| **Answered** | A response is recorded and the acceptor determines it adequate (treatment "answered") |
| **Escalated** | Where the acceptor does not accept, or cannot judge, it refuses or defers and escalates (Section 8.4). Escalation is an outcome of the act, not a treatment inside an acceptance. |
| **Covered by exception** | Only where the gate definition imposed a stricter response rule, by a recorded exception (Section 9.4). The challenge itself is never waived out of the record. |
| **Accepted as residual** | The acceptor judges the basis sufficient despite the unresolved challenge, records why, and the decision carries a marker that it was accepted with that unresolved challenge. Dependents see the marker. |

### 6.7 Visibility

A challenge is visible, whatever its condition, in every view of its target; in every dependent's exposure; and in every decision record that cites it. A closure is visible with its kind and closer. The challenger's identity is visible. Withdrawal, resolution, and closure are added to history and do not remove the challenge (EKR-09).

### 6.8 Rules

| ID | Rule |
| --- | --- |
| GCR-23 | A valid challenge records challenger, target, target scope, and basis. Absent any, it is an invalid action and remains visible. Targets include items, relationships (including designations, dependency links, attributions, and correction designations), and decisions or other determinations (including acceptances, waivers, authorizations, closures, and the validity of acts). |
| GCR-24 | Any actor holding AUTH-A may raise a challenge. A producer's challenge of its own item is recorded and is not independent. Raising is not restricted beyond AUTH-A. |
| GCR-25 | A response never closes a challenge. |
| GCR-26 | A challenge is closed only by challenger resolution, by authority closure, or by withdrawal of its target with no successor. Authority closure is performed by a gate authority holder independent of the challenged item's accepted set who is not the author of a challenged determination. Nothing else closes a challenge. |
| GCR-27 | Unanswered and unresolved are defined without clocks. An unresolved challenge does not by itself block progression. A gate definition may make it do so. |
| GCR-28 | A challenge, and any contradicting or qualifying relationship, recorded against an item carries to any item recorded as superseding it, visibly as carried. Supersession never closes a challenge. |
| GCR-29 | A challenge is visible in every view of its target, of its dependents, and of every decision citing it, whatever its condition. Closure and withdrawal are history, not deletion. |

---

## 7. Contradiction, Counter-evidence, Bare Contradiction, Exposure, and Requirements

Operationalizes D5, D7; WD-2, WD-6. Resolves **EK-OQ-04 / QA D-08** (widened as the Moderator directed), **EK-OQ-07**, and the reliance questions of EK-OQ-04.

### 7.1 The question

STEP-02 recorded two statements that pulled in different directions. EKR-39 said "contradiction and challenge take visible effect immediately." Section 10.5 said "a challenge alone is not a trigger." TRG-2 let any contradicting claim create a requirement on all dependents by itself. A contradicting claim costs about the same as a challenge, the act Section 10.5 excluded for being too cheap. The result was ambiguity about whether the visible effect was exposure or a requirement, and nothing for contradicting claims or inferences.

The design pressure is two-sided. If every cheap act puts every dependent in doubt, teams learn to ignore requirements, and the protocol fails the burden test (E-2, PO A-5). If cheap dissent has no visible effect, WD-6 ("must not remain silently valid") and WD-2 are defeated. The answer is to give each contribution an effect proportionate to what it puts into the record, and to give cheaper contributions defined routes to a stronger effect.

### 7.2 Terms

| Term | Meaning |
| --- | --- |
| **Contestation** | The visible fact that an item, relationship, or decision is under challenge or contradiction. Not a state name. Derivable from the record. |
| **Exposure** | As defined in STEP-02 Section 10.7: the visible fact that an item depends, directly or through others, on an item that is contested, has an open trigger, or has an open requirement. |
| **Requirement** | As defined in STEP-02 Section 10.4: the obligation on a dependent to remain visibly open to question until an authorized outcome. |
| **Source-identified counter-evidence** | An evidence item meeting the presence conditions of EKO-04 and EKO-05 (source identified, producer, time, target, polarity, category, basis, limitations) whose polarity toward the target is contradicting. |
| **Bare contradicting claim** | A claim in a contradicting relationship to its target that cites no source-identified evidence bearing against the target. |
| **Bare contradicting inference** | An inference in a contradicting relationship to its target, grounded as EKR-26 requires, none of whose cited evidence is itself recorded as counter-evidence to that target. If one is, that evidence item creates the effect (Section 7.4, path P1) and the inference adds nothing. |

### 7.3 The classification

This table is normative. "Direct dependents" means dependents with a material dependency (including presumed material, EKR-35). Indirect dependents are exposed and receive requirements only through outcomes (STEP-02 Section 10.7).

| Contribution | On the target | Direct material dependents | Indirect dependents | Why |
| --- | --- | --- | --- | --- |
| **Challenge** with no recorded counter-evidence | Contestation | **Exposure**. No requirement. | Exposure | It is the cheapest act in the protocol. A requirement would let it put every dependent in doubt. Dissent must not be buried, so it is visible on every dependent. |
| **Source-identified counter-evidence** | Contestation | **Requirement**, by the event (TRG-2, EKR-37). Not waiting for adjudication (EKR-39). | Exposure | It cost the contributor a source, a basis, a limitations statement, and a stated polarity, and it puts information that bears against the basis into the record. The party who benefits from the dependent staying current must not be able to delay the requirement by disputing the evidence. |
| **Qualifying** evidence, claim, or inference | Visible on target | No automatic effect. A request (ACT-06) is available (Section 7.5). | None | It narrows scope without contradicting. Whether it reaches a dependent's scope is judgment (EKJ-11). |
| **Bare contradicting claim** | Contestation | **Exposure**. No requirement by itself. Defined routes to a requirement (7.4). | Exposure | It costs about what a challenge costs and has no source. It is a contradicting item recorded against the basis, so it must be cited and treated at a gate (Section 5.5). It is not evidence (EKR-13). |
| **Bare contradicting inference** | Contestation | **Exposure**. No requirement by itself. Defined routes to a requirement (7.4). | Exposure | An inference is an interpretation and never evidence (EKR-27). Its weight lies in what it cites, and what it cites is handled by P1. Where its support is assumptions only, it is flagged as assumption-rooted (Section 12.4). |
| **Conflicting claims or inferences from different producers**, neither accepted | Contestation on each | Exposure | Exposure | This is disagreement (Section 8). No item is elevated by number or agreement (EKR-06). |
| **Challenge to a relationship, designation, or determination** | Contestation on the relationship or determination | Exposure on what depends on it. Specific effects for designations: 7.6 and Section 10. | Exposure | The target is an assertion by an actor (EKR-03). |
| **Withdrawal of any of the above by its producer** | | Does not undo the effect. Section 10.4. | | |

### 7.4 Routes from exposure to a requirement

A bare contradicting claim, a bare contradicting inference, or a challenge reaches requirement status on a direct material dependent by any of three routes:

| Route | How | Why it is defensible |
| --- | --- | --- |
| **P1. Grounding** | The contradicting item cites an evidence item that is itself recorded as counter-evidence to the target. That evidence item creates the requirement. | The effect arises from the sourced information, not the interpretation |
| **P2. Standing by acceptance** | A gate authority holder independent of the contradicting item's accepted set accepts the contradicting claim or inference as sufficient for its stated scope. The requirement arises on direct material dependents of the target. | An authorized human judged it. It is no longer bare. |
| **P3. Request** | Any actor holding AUTH-A, AUTH-V, or AUTH-G records an ACT-06 request against the dependent, citing the contested item and a stated basis for why it bears on the dependent (7.5). The request creates the requirement (STEP-01 ACT-06). No independence is required of the requester. | It is an identified, reasoned act and not an automatic consequence of someone else's cheapest act. The judgment of HJ-10 sits with an accountable actor. |

P3 is available for every row of the table, including qualifying items, challenges, and evidence age (Section 13).

### 7.5 The request

STEP-01 ACT-06 records that a decision's material support has changed, is contested, or has been withdrawn, and that it may no longer be relied on without reconsideration. This artifact adds only that a request **records its stated basis**: the contested or changed item, the dependent, and why the requester judges that the dependent's standing is in question. The request creates the requirement and concludes nothing. A request by the producer of the dependent, or by the producer of the contradicting item, is valid. Both are exercising authority they hold, and neither is a favorable act (GCR-05).

### 7.6 Exposure, reliance, and open requirements

Answers the reliance questions of EK-OQ-04.

- **Exposure never bars reliance.** A new acceptance may cite an exposed item. The exposure is part of the standing record and must be cited and treated (Section 5.5). The acceptor's ordinary acceptance covers it. No further authorization is required.
- **An open requirement bars _silent_ new reliance.** A dependent with an open requirement is not recorded as current without an authorized outcome (EKR-38, PS OBJ-10). Its **historical** acceptance stands and is never erased (STEP-02 Section 10.9). **New reliance** on it, meaning citing it as basis in a new acceptance, decision, or progression, requires either a **closure** (Section 11) or a **reliance-while-open authorization** by a gate authority holder independent of the _citing_ acceptance's accepted set (Section 9.2, ground G2).
- **Who authorizes.** A human holding AUTH-G for the citing gate, subject to Section 9. Never an agent, an evaluator, or a producer of the citing set.
- **Work under way.** The semantics govern _recorded reliance_: gates, decisions, commitments, and currency marks. They do not halt conduct in the world (Section 1.4).

### 7.7 Disputed materiality and redesignation

Resolves **EK-OQ-07**.

A materiality designation is a recorded judgment by its recorder (EKJ-01, EKJ-10). It is an assertion by an actor, so it can be challenged (EKR-03, ACT-03).

| Dispute | Effect while unresolved | Who resolves |
| --- | --- | --- |
| A **non-material designation** on an item presumed material (EKR-35) is challenged | **The presumption is restored.** The item is treated as material for triggers, for the accepted set, and for gate treatment. | A gate authority holder independent of the designation, the item, and the dependent (authority closure, GCR-26) |
| A **material designation** is challenged as over-broad | The designation stands. Wrongly material costs burden, not independence or silence. | Same |
| A **dependency is alleged to be missing** | A challenge against the decision's basis for omission. Contestation and exposure. | Same. If sustained, the link is recorded as a dependency change and TRG-5 applies. |
| **Redesignation or removal** (EKR-36) on a **standing** dependent | Recorded with rationale. TRG-5 applies at once (the dependent's basis changed). **For triggers and for the accepted set of any later acceptance, the link is treated as still material until confirmed** by a gate authority holder who is a producer of none of the dependent, the upstream item, or the change. | That confirmer |
| Redesignation or removal on a **non-standing** dependent | The recorder's designation stands unless challenged. | Authority closure, as above |

The confirmation requirement keeps a producer from narrowing a basis by redesignation so that someone with an interest in the upstream item can accept (STEP-02 Section 10.3's concern, applied to accepted sets).

### 7.8 Rules

| ID | Rule |
| --- | --- |
| GCR-30 | The classification of Section 7.3 is normative. A challenge, a bare contradicting claim, and a bare contradicting inference each produce contestation and exposure. Source-identified counter-evidence produces a requirement on direct material dependents. Qualifying items have no automatic dependent effect. No contribution has _no_ visible effect. |
| GCR-31 | A bare contradicting claim, a bare contradicting inference, or a challenge reaches requirement status only by P1 (grounding in recorded counter-evidence), P2 (acceptance by an independent gate authority holder), or P3 (a request by an actor holding AUTH-A, AUTH-V, or AUTH-G). |
| GCR-32 | An ACT-06 request records the requester, the dependent, the contested or changed item, and a stated basis. It creates the requirement. It is valid whether or not the requester is independent of the dependent or of the contradicting item. |
| GCR-33 | Exposure never bars reliance and is cited and treated at gates. A dependent with an open requirement may be newly relied on only after a closure (Section 11) or under a reliance-while-open authorization (Section 9). Its historical acceptance is never erased. |
| GCR-34 | A challenged non-material designation restores the presumption of materiality until a gate authority holder independent of the designation, the item, and the dependent resolves it. Redesignation or link removal on a standing dependent takes effect for triggers and later accepted sets only on independent confirmation. |

---

## 8. Disagreement Handling and Escalation

Operationalizes D5; FR-5, WD-2, NG-5, HA-3, GR-6. Resolves **EK-OQ-13 / PS-OQ-03** semantically and states the semantic requirement for **EK-OQ-11 / PS-OQ-01**.

### 8.1 Disagreement is a derived condition

STEP-02 Section 5.4 defined disagreement as a condition the record produces: two or more items in a contradicting or challenging relationship, at least one not withdrawn, and no authorized resolution recorded. EK-OQ-13 asked whether to call it a named condition, a relationship, or an artifact property.

**Position.** Disagreement is a **derived condition over the record**. It is not a named state, not a property carried on an artifact, and not a relationship of its own that someone must record. It exists whenever its sources exist (listed below) and ends only by a recorded act (Section 8.3). This keeps it from becoming a thing that can be forgotten to be recorded, or that can be quietly cleared by editing a label.

Any conforming representation must make the following answerable. Whether the answers are stored or computed is STEP-05's question (EK-OQ-11).

- **Enumerable.** For any item, relationship, decision, or gate: which unresolved disagreements bear on it, directly or through its basis (extends EKR-40).
- **Attributable.** Which actors hold which positions.
- **Evidence-linked.** What each position cites.
- **Routable.** Which resolving authority class and scope can resolve it, and which identities hold it now (Section 8.4).
- **Cleared only by a recorded act** (Section 8.3). Never by time, silence, absence of objection, the number of agreeing actors, agent agreement, or recency (EKR-06, PR-20).

The sources of disagreement are those of STEP-02 Section 5.4, plus **disputed validity or independence of an act** and **conflicting determinations by gate authority holders** (Section 8.5).

### 8.2 What stays visible

While a disagreement exists, and after any resolution, the record keeps: each position and the actors who hold it; what each cites; the challenges, responses, and closures; the treatments at any gate (Section 5.5); and the resolving act and its rationale. A dissenting position is never deleted by being outvoted, answered, or resolved against. The condition ends, not the record (EKR-05, EKR-09).

### 8.3 How a disagreement ends

| Form | How | Notes |
| --- | --- | --- |
| **Challenger resolution** | The challenger records withdrawal or satisfaction (Section 6.3) | Ends that challenge's contribution only |
| **Authority closure** | A gate authority holder closes a challenge as answered, moot, or not standing (Section 6.3) | |
| **Concession** | The target's producer revises, withdraws, or supersedes, **and** the challenge is closed or carried (Section 6.5) | A concession alone is not a closure |
| **Resolution by decision** | A gate authority holder, independent of the accepted set of the determination, decides which position to act on for a stated scope, recorded as a decision (ACT-07) | The decision is a determination of sufficiency for that scope. It is not a finding of truth and not consensus. The position not relied on stays recorded and may be reopened by a new trigger (TRG-2) or a new challenge |

**No consensus is required.** The protocol does not ask disagreeing actors to agree. A disagreement can end with the dissenting position still held by its holder and visibly recorded as such (NG-5, WD-2).

### 8.4 Escalation

Operationalizes HA-3, GR-6.

**Escalation** is the act of routing an unresolved matter to an authority able to resolve it. Any actor holding AUTH-A, AUTH-P, AUTH-V, or AUTH-G may escalate. An escalation records:

- the escalating actor and capacity;
- the **matter**: item, challenge, gate, designation, attribution, or determination;
- the **resolving authority sought**: the grant class and scope that can resolve it, resolved to the identities holding those grants at that time;
- why: insufficient evidence, a conflict of interest, an unresolved disagreement, a disputed designation or attribution, a refused or deferred gate, an authority gap;
- what determination is asked for.

An escalation **never closes or resolves anything**. It stays visible until the addressed authority records a determination: resolve, refuse, or defer. If the addressed authority never responds, the escalation stays visible. Time does not act (Section 8.7).

**The path is explicit because it is derived from grants, not from role names** (D4, PR-01, PR-03). For each kind of matter, the resolving authority is:

| Matter | Resolving authority | Independence condition on the resolver |
| --- | --- | --- |
| A challenge against an item or determination | Challenger resolution, or a gate authority holder in scope | Independent of the challenged item's accepted set; not the author of a challenged determination (GCR-26) |
| A disputed producer attribution | A gate authority holder | Independent of the disputed item (GCR-07) |
| A disputed materiality designation or redesignation | A gate authority holder | Independent of the designation, the item, and the dependent (GCR-34) |
| A correction designation on a standing item | A gate authority holder | A producer of neither the item nor the change (GCR-51) |
| An open revalidation requirement | By tier (Section 11.4) | By tier |
| Authorization of conditional progression, or a waiver | A gate authority holder for the gate | Independent of the accepted set (GCR-43) |
| A refused or deferred gate | Another gate authority holder for the gate; or the position the gate definition designates for role conflicts | Independent of the accepted set |
| Conflicting determinations by gate authority holders | The position the gate definition designates for resolving role conflicts (STEP-01 AUTH-G "resolve role conflicts where assigned"). If none is designated, an authority gap (8.6) | |
| Insufficient evidence | The producer positions (AUTH-P) gather it, and a gate authority holder defers (Section 5.6) | |

A matter whose resolving authority cannot be filled by an identity meeting the independence condition is an **authority gap** (Section 8.6).

### 8.5 Progression under disagreement, and conflicting determinations

**Default.** Disagreement does not by itself block progression (WD-2, NG-5). A gate may be accepted with unresolved challenges and contradictions when each is cited with a recorded treatment (Section 5.5) and the acceptor judges the basis sufficient notwithstanding. That is the treatment **accepted as residual**.

**Who decides whether residual disagreement is acceptable for a gate.** The acceptor: a human gate authority holder satisfying Section 5.4. This is an explicit contextual judgment (GCJ-03; EKJ-12, EKJ-14) and is recorded in the acceptance-act content. It is not decided by a producer of the disputed items in the basis, an agent, an evaluator, or elapsed time.

**Marker.** The decision record and the acceptance carry a marker that they were accepted with the named unresolved items. Dependents see it as part of the standing record. This is ordinary acceptance made with open eyes. It is not an exception (Section 9) and it is not validation.

**Stricter gates.** A gate definition may require resolution on a stated dimension. Accepting against that rule requires an exception.

**Limits.** Residual acceptance cannot cover:

- a dispute about the **validity or independence of an act**, including the acceptor's own independence or a disputed producer attribution of the acceptor. These are resolved only by a determination from an actor independent of the dispute;
- a matter where the acceptor is among the parties whose item is in the accepted set (GCR-03).

**No separate "conditional progression under disagreement" instrument exists.** Sufficiency despite disagreement is acceptance as residual. Where a gate imposes resolution, an exception covers the shortfall. Where the disagreement concerns an unvalidated hypothesis, Section 9 conditional progression applies.

**Conflicting determinations.** Gate authority holders may differ: one refuses or defers, another accepts. The default acceptance rule is that one valid independent acceptance satisfies the gate unless the gate definition says otherwise (Section 5.2). To prevent shopping for a favorable acceptor, **every earlier refusal and deferral on the same gate and basis is part of the standing record of any later acceptance** and must be cited with a treatment, including what changed since. An acceptance that omits them is invalid (GCR-17). The disagreement among holders is itself a disagreement among role judgments (HJ-08). Any actor may escalate it to the position the gate definition designates for role conflicts. The protocol defines **no override hierarchy** among gate authority holders. Whether Product Moderator authority should be reviewable or overridable (product OQ-7) is not decided here (GC-OQ-10).

### 8.6 Authority gap

An **authority gap** exists where the resolving authority for a matter cannot be filled by any identity satisfying the independence condition. For example: the only human holding AUTH-G for the scope produced the whole accepted set; or the only holder authored the determination that is challenged.

- It is a **visible condition**. It is recorded against the matter.
- The matter stays unresolved and visible. Progression that depends on it can occur only through valid acts by other independent holders. If none exist, no valid progression exists.
- It is **not cured** by acceptance by the conflicted holder, by a second role label, by a collective identity, by an agent or evaluator, by a waiver, by time, or by a grant the conflicted actor conferred on itself. Self-conferral is a candidate invalid-action rule for STEP-04 (GC-OQ-02). Until then it is visible and challengeable and is not a valid cure.
- It is cured only by: a grant of the necessary authority to an independent human by a granting authority (PS-OQ-05); or re-basing the subject on independent items, visibly; or substitution of the acceptor.
- A project may stop at an authority gap. The protocol does not require otherwise.

### 8.7 What never resolves disagreement

Elapsed time. Silence. Absence of objection (PR-13). The number or seniority of agreeing actors. Agreement among agents, models, configurations, or evaluators (PR-20, EKR-17). Recency. Persuasiveness or fluency. Completion of downstream work. Only a recorded act of Section 8.3 does.

### 8.8 Rules

| ID | Rule |
| --- | --- |
| GCR-35 | Disagreement is a derived condition over challenges, contradictions, conflicting items and determinations, and the absence of an authorized resolution. A conforming representation must make it enumerable, attributable, evidence-linked, and routable, and must clear it only by a recorded act. |
| GCR-36 | Disagreement ends only by challenger resolution, authority closure, concession combined with closure or carry-over, or resolution by decision. Resolution by decision is a sufficiency determination for a scope. The position not relied on remains recorded. No consensus is required. |
| GCR-37 | An escalation records the escalating actor, the matter, the resolving authority sought (derived from grants), the reason, and the determination asked for. It never closes or resolves anything and remains visible until the addressed authority records a determination. |
| GCR-38 | Disagreement does not by itself block progression. The acceptor judges whether residual disagreement is acceptable. The decision carries a marker. A gate definition may require resolution. Disputes about the validity or independence of an act cannot be accepted as residual by the disputed actor. |
| GCR-39 | Every earlier refusal and deferral on the same gate and basis is cited with a treatment in any later acceptance. The protocol defines no override hierarchy among gate authority holders. |
| GCR-40 | Where no identity meeting the independence condition can fill the resolving authority, an **authority gap** is recorded. It is cured only by a grant to an independent human, by visible re-basing on independent items, or by substitution of the acceptor. |
| GCR-41 | No disagreement is resolved by time, silence, absence of objection, headcount, agent agreement, recency, or downstream completion. |

---

## 9. Conditional Progression, Waivers, and Exceptions

Operationalizes D4, D6; FR-7, GR-7, HA-1. Resolves **EK-OQ-08 / PS-OQ-12**. Uses Sections 4, 5, and 8.

### 9.1 Four things that look alike

Four instruments touch the same moment of progression and are easily confused. Confusing them is how an unresolved assumption becomes "validated," or how an exception becomes "how we do it."

- **Validation** says a hypothesis's criteria are met (Section 12).
- **Acceptance as residual** (Section 8.5) says the gate's sufficiency judgment includes a matter that is still open.
- **Conditional progression** (9.2) says: progress or rely, **while a named condition stays unresolved and tracked**.
- **Waiver or exception** (9.4) says: this specific requirement is **dispensed with** for this specific progression.

**The distinguishing test:** after the progression, does the unmet requirement remain **open and tracked**? Under conditional progression it does. Under a waiver it is dispensed with for that progression and remains visible only as an exception.

### 9.2 Conditional progression

A **conditional progression authorization** is an explicit act by a human gate authority holder, independent of the accepted set, authorizing progression or reliance while a named condition stays unresolved and tracked. It has two grounds.

| Ground | The unresolved condition | Dependency mark produced |
| --- | --- | --- |
| **G1. Assumption** | A relied-on material hypothesis that is unvalidated, or a relied-on assumption (FR-7, EKR-23) | **Reliance under assumption** on each dependency |
| **G2. Open requirement** | A relied-on item with an open revalidation requirement (Section 7.6) | **Reliance while open** on each dependency |

**Complete form.** The authorization records:

1. the **authorizer**: an identified human, capacity, and the AUTH-G grant covering the scope (PR-13);
2. the **independence** of the authorizer from the accepted set of the progression, with the declaration of GCR-09;
3. the **progression** and scope covered;
4. each **item relied on while unresolved**, identified, with its ground (G1 or G2);
5. for each item, **what would resolve it** (validation criteria for G1; the expected outcome for G2) and the **position expected to resolve it**;
6. the **rationale**: why proceeding is warranted. This is a contextual judgment (GCJ-04; HJ-09);
7. the **reliance bound**: which dependents may rely;
8. a statement that the unmet requirement **remains unsatisfied and open**;
9. optionally, a **review event**. It is recorded for visibility and has no automatic effect (Section 13.3).

**Properties.**

- It is **non-delegable**. It cannot be performed by an agent, an evaluator, or a collective (PR-05).
- It takes effect **when recorded**. It never validates earlier progression (GCR-47).
- It is **not inherited**. A later gate or decision that relies on the same unresolved item needs its own authorization (PR-04 by analogy). Reliance does not travel downstream by itself.
- It is **revocable** by any gate authority holder for the scope, as a conservative act. Revocation ends authorization for _new_ reliance. Existing reliance stays visible, marked "no longer authorized," and is part of the standing record of any later acceptance.
- It **ends** when the item is validated (G1), refuted (TRG-2, TRG-3), retired, or its requirement closed (G2), or when it is revoked. It never ends by time (EKR-38).
- It is visible wherever the progression it authorized is cited.

**Reading of "progression" in FR-7.** FR-7 says a project may continue while a hypothesis is unvalidated only when authorized. STEP-03 reads "progression" there as **progression through a gate, or any consequential commitment** (declared, UAD3-18). Ordinary production work that relies on an unvalidated item records its dependency as reliance under assumption (EKR-23), which makes it visible and traceable, and needs no gate authority holder's authorization. The moment the work is cited in a gate acceptance, a consequential decision, or a commitment, the authorization is needed (Section 5.4, condition 8).

### 9.3 Relationship to reliance under assumption

STEP-02 defined **reliance under assumption** as a dependency kind authorized as conditional progression. The two relate as act and mark:

- the **authorization** is the human act (9.2);
- **reliance under assumption** and **reliance while open** are the **marks** it produces on dependency links.

A reliance mark with no authorization behind it, where the reliance is consequential, is an invalid-record condition (Section 5.4, condition 8). The mark makes reliance visible. It does not authorize it.

### 9.4 Waiver or exception

A **waiver or exception** is the dispensation by a human gate authority holder, independent of the accepted set, from a **specific unsatisfied gate requirement** for a **specific progression**. It is performed together with, or as part of, an acceptance. The result is an **acceptance with exception**. A waiver with no acceptance authorizes no progression.

**Record content** (GR-7, OBJ-12), all required:

- the authorized human, capacity, and grant;
- the rationale;
- the **unsatisfied requirement**, identified: the gate definition slot, or the stricter rule;
- the progression and scope;
- provenance (the common elements of STEP-02 Section 6.2);
- the marker identifying it as an **exception**.

**Visibility.** The exception marker is part of the acceptance and appears in the standing record wherever the acceptance is cited, including by dependents. It is not erased by reaffirmation: a reaffirmation is a fresh acceptance (Section 11.4) and, if the requirement is still unmet, needs its own exception. An exception can be challenged (GCR-23).

**Override.** GR-7 names "waiver or override." STEP-03 treats an **override**, an acceptance despite a standing refusal, a failing formal check, or a contrary determination of another holder, as a form of exception. It uses the same record content, with the overridden determination or check named as the unsatisfied requirement.

**Not waivable.** None of these can be dispensed with by any act:

1. independence over the accepted set (PR-16 to PR-21; GCR-06);
2. human, explicit, attributable authorization by an actor holding AUTH-G (PR-05, PR-13);
3. citation of the standing record and recording of treatments (GCR-17). A stricter _response_ rule may be waived. The visibility of what exists may not;
4. the visibility of the exception itself;
5. the decision record's identification of its nature and authority basis (EKO-16);
6. the FR-7 conditions where a material hypothesis is relied on. A requirement that such a hypothesis be validated cannot be waived into silence. It is handled by conditional progression (G1), which keeps the hypothesis unvalidated, visible, and traceable.

### 9.5 The distinctions side by side

| | **Validation** | **Ordinary acceptance** | **Acceptance as residual** | **Conditional progression** | **Waiver or exception** |
| --- | --- | --- | --- | --- | --- |
| What it says | A hypothesis's criteria are satisfied for a stated scope | The gate's conditions are sufficient | Sufficiency, despite a named unresolved matter | Proceed or rely while a named condition stays unresolved | This requirement is dispensed with for this progression |
| Does the unmet requirement stay open and tracked? | Not applicable | Not applicable | The matter stays open and visible | **Yes** | **No.** It stays visible as an exception |
| What it authorizes | Reliance on the hypothesis as validated | Progression | Progression | Progression or reliance with the condition open | Progression with a visible exception |
| Marker | Validation record | Acceptance record | "Accepted with unresolved..." | Reliance under assumption or while open | Exception |
| Who | Human holding AUTH-G, independent (Section 12) | Human holding AUTH-G, independent | The acceptor | Human holding AUTH-G, independent | Human holding AUTH-G, independent |
| It is not | Truth | Validation | An exception | Validation, reaffirmation, or a waiver | Ordinary conformance, or a cure of invalid independence |

### 9.6 Rules

| ID | Rule |
| --- | --- |
| GCR-42 | A conditional progression authorization has ground G1 (a relied-on unvalidated material hypothesis or relied-on assumption) or G2 (a relied-on item with an open revalidation requirement) and records the nine elements of Section 9.2. It is revocable by any human holding AUTH-G for the scope, as a conservative act. It ends by validation, refutation, retirement, closure of the requirement, or revocation, never by time. |
| GCR-43 | A conditional progression authorization or a waiver is an explicit act by a human holding AUTH-G for the scope and independent of the accepted set of the progression. It is non-delegable and is not inherited by later gates. (The ending conditions of GCR-42 apply to conditional progression only. The record requirements of GCR-45 apply to waivers and exceptions only.) |
| GCR-44 | Conditional progression is not validation, ordinary acceptance, reaffirmation, or a waiver. The relied-on hypothesis stays classified as unvalidated, stays visible with unresolved assumptions, and every dependency on it carries the reliance mark (EKR-23). Progression under assumption is never represented as validation. |
| GCR-45 | A waiver or exception records the authorized human, grant, rationale, unsatisfied requirement, scope, and provenance, and is marked as an exception. The marker travels with the acceptance and is visible wherever it is cited. It is not erased by reaffirmation, validation, closure, or the passage of time, and it has no ending condition of its own: it is history attached to that acceptance, and only withdrawal of the acceptance (GCR-57, TRG-6) changes the acceptance's own standing. It takes effect only as GCR-47 allows. An override is an exception naming the overridden determination or check. |
| GCR-46 | The six items listed as non-waivable in Section 9.4 cannot be dispensed with by any waiver, exception, authorization, deferral, or escalation outcome. |
| GCR-47 | Authorizations, waivers, exceptions, confirmations, and closures take effect when recorded and **never retroactively**. One recorded after an act does not make that act valid. |
| GCR-48 | The distinguishing test of Section 9.1 is normative: an instrument that leaves the unmet requirement open and tracked is conditional progression. One that dispenses with it for a stated progression is a waiver or exception. A project may not record one under the other's name. |

---

## 10. Correction, Supersession, Withdrawal, and Invalidation Authority

Operationalizes D4, D7; FR-4, FR-6. Resolves **EK-OQ-17** (all four questions), **EK-OQ-06 / PS-OQ-07**, and **QA D-05b**. Uses Sections 4, 6, and 7.

### 10.1 The separation

STEP-02 placed three kinds of act in one paragraph (Section 10.5): a producer retracting its own item, a producer replacing its own item, and a determination that another actor's item must stop being relied on. They are different kinds of authority, and the distinction is what keeps self-approval from entering through an edit.

| Layer | What it concerns | Authority |
| --- | --- | --- |
| **Producer-owned acts** | A producer's own item: revise, withdraw, supersede, retire its own dependent, propose a designation | AUTH-P. Valid on its own. Always a visible event. Never an erasure. Effects flow through triggers |
| **Designations that control whether acceptance carries** | Whether a change to a standing item is a correction | A producer may only **propose**. Effect requires independent confirmation (10.3) |
| **Authority over another actor's item** | Whether another actor's item may continue to be relied on, or be replaced | A human gate authority holder for the scope (10.6). Everyone else records a challenge, counter-evidence, or an advisory finding |

### 10.2 Revision, designation, and standing

A producer may always revise its own item (STEP-01 Section 6.5). A revision is recorded as an event. Its **designation** is one of: correction (meaning unchanged), supersession (meaning changed), or withdrawal. Designation matters only once there is something to protect: an acceptance to inherit, or dependents to trigger.

An item is **standing** if it has been validly accepted, or is a member of the accepted set of any recorded consequential acceptance or decision (Section 4.2). Before an item is standing, a producer's changes are revisions and their designations carry no protocol effect on acceptance. For dependents of a non-standing item, the producer's designation stands unless challenged (Section 10.3).

### 10.3 Correction designation (EK-OQ-17, questions 1 to 3)

**The risk (R-1).** Acceptance carries across a correction and does not carry across a supersession (EKR-10). If the producer decides which it is, a meaning-changing edit to an independently accepted item can keep that acceptance and trigger nothing. That is PR-16 reached through item identity.

**Who may designate.** Any actor may record a designation. A producer records its own as a **proposal** with rationale. Anyone with AUTH-A may challenge a designation (GCR-23).

**When a designation takes effect.**

| Item | Producer's correction designation |
| --- | --- |
| **Not standing** (never accepted, not in a consequential accepted set) | Stands unless challenged. A challenge produces contestation and exposure on dependents and no other automatic effect |
| **Standing** | Takes effect **only on independent confirmation** by a human holding AUTH-G for the item's scope who is **a producer of neither the item nor the change** (the person who made the change is a producer of the change) |

**The original acceptor** of a standing item must be **notified**: a recorded notice addressed to the original acceptor's identity, or, if unavailable, to the holders of the AUTH-G grants covering the item's scope. Consultation is **not** required. Three consequences:

- The original acceptor **may** be the confirmer, if independent. Having accepted the item does not make it a producer of it.
- The original acceptor may **challenge** the designation, as any AUTH-A holder may. A pending challenge blocks effectiveness until closed under Section 6.3.
- **Non-response never confirms** (PR-13).

**May the producer retain acceptance by its own designation? No.** Acceptance continues across a change to a standing item only if the correction designation is effective.

**Unconfirmed means supersession.** A change to a standing item with no effective correction designation is treated, **for reliance purposes**, as a supersession: the acceptance is not inherited (EKR-10), the replaced content remains recorded, TRG-1 and TRG-4 apply to dependents, and challenges and opposition carry to the new content (Section 6.5). It is not an invalid action. It is the conservative default.

**Later confirmation.** If confirmation comes later, the change is reclassified as a correction from that point. Requirements that arose from the conservative treatment remain open until closed under Section 11. The confirmer may close them in the same act where it holds closure authority for those dependents.

**Overturned designation.** If an effective correction designation is later overturned (a challenge is closed against it, or the confirmation is found invalid), the change is treated as supersession **as of the change**. The triggers arise at the overturning record. The interval during which the item was treated as accepted stays visible in history.

**Changes that are never corrections.** Whether a change alters meaning is judgment (EKJ-09). Some changes are recognizable from the record and force the answer:

1. a change to a hypothesis's validation criteria after test results have been recorded (Section 12.3);
2. a reclassification between knowledge classes (EKR-01);
3. a change to the polarity or target of an evidence item, or substitution of a different source;
4. a change to the stated scope of an acceptance, validation, or decision;
5. a change to the dependency links or materiality designations of the item (a dependency change, TRG-5).

Each is recorded as a supersession whatever it is called.

**Burden.** One confirmation act may confirm a stated set of changes, each identified. Pilot evidence on confirmation overhead is routed to STEP-07 (GC-OQ-08).

### 10.4 Withdrawal (EK-OQ-17, question 4)

A producer may withdraw **its own item** at any time without independent review (AUTH-P). Withdrawal is valid as a **visible historical event**. It records the item, the withdrawing actor, the time, and a **rationale** (recorded in error; source retracted or discredited; replaced by a corrected item; other, with explanation).

**Effects.**

- The item **remains recorded and visible**, marked as withdrawn by its producer (EKR-09).
- Dependents receive **TRG-1** and a requirement (Section 11).
- Challenges against it become moot with no successor, and remain in history (Section 6.3).
- Earlier acceptances of the item stay as **historical acceptance**. Withdrawal does not make them never have happened, and does not make them current.
- It does not remove the item from the standing record of earlier decisions, whose bases are preserved as they stood (EKR-31).

**Withdrawing own counter-evidence.** A producer may record counter-evidence against its own claim (EKR-18 requires it where it holds the information) and later withdraw that counter-evidence. The withdrawal is allowed and subject to the following, so that it cannot cleanse the record:

1. The counter-evidence **remains recorded and visible**, marked "withdrawn by its producer on <date> for <rationale>."
2. The **requirement** it created on dependents **remains open**. Withdrawal is a reason an authorized actor may weigh in closing it, never a closure itself (Section 11.3).
3. **Decisions made while it stood** keep citing it as part of their preserved basis (EKR-30, EKR-31). **Decisions made afterward** cite it as a **withdrawn contradicting item**, with its rationale. It cannot be omitted from a basis that cites the item it contradicted.
4. **Any actor holding AUTH-A** may attach the same _source_ information as its own counter-evidence. The source never depended on the producer's assertion (EKR-13). A producer's withdrawal does not make the information unrecordable.
5. The **rationale is challengeable**. Whether it is genuine (for example, that a source was discredited) is a contextual judgment (GCJ-10).

**Co-produced items.** If an item has several recorded producers (PR-21) and fewer than all withdraw, the withdrawal is of **that producer's endorsement of the item**. The item remains. The withdrawal is visible, and any actor may request revalidation on its basis (Section 7.5). TRG-1 applies automatically only where all recorded producers withdraw, or where a gate authority holder invalidates the item (10.6).

**A producer cannot withdraw another actor's item.** Its attempt to do so is recorded as a challenge, counter-evidence, or an advisory finding (EKR-04).

### 10.5 A producer's supersession of its own item

A producer may replace its own item with one that changes meaning. The replaced item remains recorded (TRG-4). Acceptance is not inherited (EKR-10). Challenges and opposition carry to the successor (Section 6.5). Requirements arise on material dependents (TRG-1, TRG-4). A producer cannot designate its own supersession a correction, and cannot use supersession to shed opposition.

### 10.6 Authority over another actor's item (EK-OQ-06, D-05b)

Whether another actor's item may continue to be relied on is a judgment about **reliance**, not about the producer's own work. It requires the acceptance authority for the item's scope.

- **Invalidation.** A human gate authority holder for the item's scope determines that the item can no longer be relied on, with rationale. This is a **conservative act** (GCR-05): it needs no independence from rival items. If the invalidator is itself a producer of the item, the act is a withdrawal (10.4). The item remains recorded. Dependents receive TRG-3. Historical acceptance stays history, and current validity ends. An invalidation is **reversed** only by a **fresh acceptance** of the item as it then stands (EKR-10) by a gate authority holder who is a producer of none of it (GCR-03). It is never erased.
- **Supersession of another actor's item.** The same human determines that the item is replaced for purposes of reliance. The **replacing item must itself be accepted** by a gate authority holder who is a producer of none of the replacing item's accepted set. A holder who produced the replacing item cannot accept it, and one person can both determine and accept only if independent of the replacement.
- **Everyone else.** Any actor without that authority (a non-producer holding AUTH-A, an agent, an evaluator) who proposes that another actor's item be superseded or invalidated records a **challenge, counter-evidence, or an advisory finding**, according to what it is authorized to make (EKR-04). Its effect is that of Section 7.3, no more.

### 10.7 An acceptor's own acceptance

An acceptor may **withdraw its own acceptance**. This is a conservative act. It is visible, with rationale. It gives rise to **TRG-6** on everything that relied on the acceptance (Section 4.7). It does not withdraw any item.

### 10.8 Authority summary

| Act | Who | Independence or confirmation | Effect on reliance | Visibility |
| --- | --- | --- | --- | --- |
| Revise own item | Its producer | None | Event. Section 10.2 | History |
| Withdraw own item | Its producer | None | TRG-1 on dependents. Never an erasure | Visible event with rationale |
| Withdraw own counter-evidence | Its producer | None | Requirement it created stays open. Cited as withdrawn | Visible event, marked on the item and on later decisions |
| Supersede own item | Its producer | None | TRG-1, TRG-4. Acceptance not inherited. Opposition carries | Visible |
| Propose a correction designation | Its producer | None | None until effective | Visible |
| Correction effective, **non-standing** item | Producer's designation | Stands unless challenged | None | Visible |
| Correction effective, **standing** item | Gate authority holder for the scope | **A producer of neither the item nor the change.** Original acceptor notified. No pending objection | Acceptance carries. No trigger | Visible with confirmer |
| Supersede another actor's item | Gate authority holder for the scope | Plus independent acceptance of the replacing item | Replaces for reliance. TRG-4 | Visible |
| Invalidate another actor's item | Gate authority holder for the scope | None (conservative) | TRG-3 | Visible |
| Withdraw own acceptance | The acceptor | None (conservative) | TRG-6 | Visible |
| Reinstate an invalidated item | Gate authority holder for the scope | Fresh acceptance. A producer of none of it | Reliance resumes for the item as it stands | Visible, invalidation retained |
| Confirm a redesignation on a standing dependent | Gate authority holder for the scope | A producer of none of dependent, upstream item, or change | Link treated as redesignated | Visible |
| Retire own dependent | Its producer | None (conservative) | TRG-1 on its dependents | Visible |
| Any of the above attempted without authority | Anyone else | | Recorded as challenge, counter-evidence, or advisory finding | Visible |

### 10.9 Rules

| ID | Rule |
| --- | --- |
| GCR-49 | A producer's revision, withdrawal, supersession, and retirement of its own item are valid without independent review. Each is a visible event with a recorded designation and rationale. None erases an item, a contradiction, or a requirement. Effects reach dependents only through triggers. |
| GCR-50 | An item is **standing** if it has been validly accepted or belongs to the accepted set of a recorded consequential acceptance or decision. Correction versus supersession has protocol effect only for standing items and for items with material dependents. |
| GCR-51 | A producer's correction designation on a **standing** item is a proposal. It takes effect only on confirmation by a human holding AUTH-G for the scope who is a producer of neither the item nor the change, with notice recorded to the original acceptor and no pending objection. Non-response never confirms. A producer cannot retain acceptance by its own designation. |
| GCR-52 | A change to a standing item with no effective correction designation is treated as a supersession for reliance purposes. Later confirmation reclassifies it from that point and does not close requirements that already arose. An overturned designation is treated as supersession as of the change. |
| GCR-53 | The five kinds of change listed in Section 10.3 are never corrections. |
| GCR-54 | Withdrawal of a producer's own counter-evidence is valid as a visible event with a rationale. The counter-evidence stays recorded and cited as withdrawn. The requirement it created stays open. Any AUTH-A actor may attach the same source information as its own counter-evidence. |
| GCR-55 | Withdrawal by fewer than all recorded producers of an item withdraws that producer's endorsement and not the item. TRG-1 applies automatically only if all withdraw, or on invalidation. |
| GCR-56 | Supersession or invalidation of **another actor's** item is effective for reliance only through a human holding AUTH-G for the item's scope. Supersession also needs independent acceptance of the replacing item. An attempt by anyone else is recorded as a challenge, counter-evidence, or advisory finding. Reinstatement of an invalidated item requires fresh independent acceptance. |
| GCR-57 | An acceptor may withdraw its own acceptance as a visible conservative act. It gives rise to TRG-6. |

---

## 11. Revalidation Requirement and Closure Semantics

Operationalizes D7; FR-2, WD-6, GR-5. Extends STEP-02 Section 10 and PR-26. Resolves **EK-OQ-16**, the closure half of **EK-OQ-04**, and addresses **PO A-5** (burden).

### 11.1 What STEP-02 supplied and what this section adds

STEP-02 defined the trigger (an event), the requirement (an obligation on a dependent), exposure (a derivable fact), and that a requirement ends when an authorized actor reaffirms, revises, or retires the dependent. It left open _who_ for non-decision dependents (EK-OQ-16), whether reliance may continue (EK-OQ-04), and what the three outcomes mean in operational terms. This section adds the following; the vocabulary is that of STEP-02 Sections 10.4 to 10.8.

### 11.2 The requirement

A revalidation requirement is a **single standing obligation per dependent**, not one obligation per event.

- A requirement exists on a dependent from the first trigger event on a material dependency of it (EKR-37).
- Each further trigger event, from any of its material dependencies, adds a **reason** to the same requirement. Reasons are visible.
- It remains until a **closure** (11.3) that **addresses every reason present at the closure**. A trigger recorded after a closure creates a requirement again.
- It is not closed by elapsed time, silence, absence of objection, agreement among agents, completion of downstream work, or the withdrawal of the thing that caused it (EKR-38; Section 10.4).
- While it is open, the dependent is **not recorded as current**. Its historical acceptance stands (STEP-02 Section 10.9). New reliance is governed by Section 7.6.

**Why per dependent.** A hundred counter-evidence items against one supporting claim would otherwise mean a hundred obligations to close. One dependent has one standing question, "is it still justified?", with a hundred reasons attached. This is the principal burden control for the all-dependents scope of STEP-02 UAD-06 (Section 11.7).

**Indirect dependents** receive no requirement from the original trigger. They are exposed. Consequences propagate **through outcomes**: the revision, supersession, retirement, or invalidation of a dependent is a trigger for _its_ dependents (TRG-1, TRG-3, TRG-4), and an acceptance found invalid or withdrawn is TRG-6. A reaffirmation is not a trigger (STEP-02 Section 10.7).

### 11.3 Outcomes and closure

| Outcome | What it is |
| --- | --- |
| **Reaffirmation** | A determination that the dependent, **as it now stands and is now supported**, remains justified. It addresses each reason, for example "survives on other support," "the counter-evidence does not reach this scope," "the withdrawn evidence was not load-bearing." It is an acceptance-type act: sufficiency, not truth, applying to the dependent as it stands after the change (EKR-10, EKR-38). It is not validation and not a waiver. |
| **Revision** | The dependent is changed in light of the reasons. A revision that changes meaning is a **successor** of the dependent (Section 10.5). The requirement **carries forward** to the successor until the successor has the outcome required in 11.4. |
| **Retirement** | The dependent is no longer relied on. It remains recorded. Its own dependents receive triggers. |
| **Closure** | A recorded outcome that meets the authority conditions of 11.4 and addresses every reason. A purported closure that does not meet them is an invalid action with no effect (PR-11). The requirement stays open and the attempt stays visible. |

### 11.4 Who may close

**D-05c** (human closer where the dependent is a consequential decision or is cited by one) was confirmed as operationalization by the Tech Lead and the Moderator. STEP-03 keeps it and answers **EK-OQ-16** for the remainder.

| | **Tier 1. Consequential reach**: the dependent is a consequential decision, or a member of the accepted set of one | **Tier 2. All other non-decision dependents** (claim, hypothesis, or inference not in any consequential accepted set) |
| --- | --- | --- |
| **Reaffirmation** | A **fresh acceptance** by a human holding AUTH-G, independent over the full accepted set computed on the **current** basis (Section 4.4). The new reasons are in the standing record and are treated (Section 5.5). Prior acceptance stays as history. | Only by a human holding AUTH-G for the scope (which may be narrow) who is a producer of neither the dependent nor its material basis closure |
| **Revision** | For a non-decision dependent: its producer revises, and the requirement carries to the successor until it is independently reaffirmed. For a decision: a human holding AUTH-G records a new decision (ACT-07), independent over its own accepted set, and the requirement carries until that decision is accepted. | The dependent's producer revises. The requirement closes as **producer-addressed**. |
| **Retirement** | The dependent's producer, or any human holding AUTH-G for the scope. For a decision, a human holding AUTH-G. | The dependent's producer, or a human holding AUTH-G |
| **Others** (AUTH-A, AUTH-V, evaluators, agents) | May request, challenge, and escalate. May not close. | May request, challenge, and escalate. May not close. |

**Standing transition.** If a Tier 2 dependent later becomes standing (enters the accepted set of a consequential acceptance), any closure that was only producer-addressed is **not counted as independent closure**. It is part of the standing record of that acceptance and must be treated there (Section 5.5). This keeps a producer from clearing a requirement on its own draft and carrying the clearance into a gate.

**EK-OQ-16: why no lesser authority class.** Reaffirmation is a determination of sufficiency for the dependent as supported. Sufficiency determinations are what AUTH-G exists to make (PR-12, PR-13), and the producer cannot make them about its own item (PR-16). Creating a weaker class of acceptor would create a fifth authority class and is an architecture-level step STEP-03 does not take. The cost is managed three ways: producers may revise or retire their own non-consequential dependents cheaply; grants may be narrow in scope (Section 12.2); and requirements on non-consequential dependents only restrict _silent new reliance_ (Section 7.6), so one that stays open for a while costs visibility, not progress. Whether pilot evidence warrants a lesser class is routed (GC-OQ-08).

A closure by an actor who is not independent is invalid (GCR-03 and PR-16 apply to every acceptance-type act). Where the only available holder is a producer of the dependent's accepted set, the matter is an **authority gap** (Section 8.6).

### 11.5 Reliance, revisited

The rules of Section 7.6 apply. Summarized: exposure never bars reliance. New reliance on a dependent with an open requirement needs a closure or a reliance-while-open authorization (Section 9.2, ground G2). Historical acceptance is not erased. These govern recorded reliance and not conduct in the world.

### 11.6 Escalation within revalidation

A producer who will not revise, a closure authority who is conflicted, a disputed designation, or a requirement nobody is positioned to close is routed under Section 8.4. A requirement that stays open for a long time **blocks nothing except silent new reliance** and is a visible condition on every item that depends on the dependent. That is deliberate. The protocol applies no clock because a clock would manufacture closures nobody decided (EKR-38).

### 11.7 Burden controls

STEP-02 applied revalidation to every dependent item with a material dependency (UAD-06) and presumed materiality for items cited by a consequential decision (UAD-05). The Product Owner and Tech Lead both flagged the burden as an untested risk (PO A-5; Tech Lead follow-up). STEP-03 treats this as a burden to manage and measure, not as a reason to weaken the intent.

Controls this artifact adds or relies on:

1. **One requirement per dependent**, with reasons (11.2).
2. **Direct dependents only**. Indirect dependents are exposed, and consequences travel through outcomes.
3. **Challenges and bare contradictions produce exposure, not requirements** (Section 7.3). Only sourced counter-evidence creates a requirement by itself.
4. **One closure act may close the requirements on several dependents**, if its author holds the required authority for each.
5. **Tier 2**: cheap producer revision or retirement for non-consequential dependents (11.4).
6. **Narrow-scope grants** make human acceptance cheap to assign (Section 12.2).
7. **Batch confirmation** of corrections (Section 10.3).
8. **Time never creates requirements** (Section 13).

Measures proposed for the proof-of-concept (STEP-07), recorded as pilot evidence and not as protocol requirements (GC-OQ-08): open requirements per consequential decision; the share of requirements closed by retirement, revision, and reaffirmation; effort to close; how often authority gaps occur; how often requests (P3) are filed; confirmation overhead for corrections; and whether teams begin to ignore requirements. Friction is evidence for narrowing the mechanism, not for dropping the intent of WD-6.

### 11.8 Rules

| ID | Rule |
| --- | --- |
| GCR-58 | A revalidation requirement is a single obligation per dependent. Each trigger event on a material dependency adds a visible reason. It remains until a closure addresses every reason present. A later trigger creates a requirement again. It is not closed by time, silence, absence of objection, agreement, withdrawal of the cause, or downstream completion. |
| GCR-59 | The outcomes are reaffirmation, revision, and retirement. A closure is an outcome that meets the authority conditions of Section 11.4 and addresses every reason. A purported closure that does not has no effect, and the requirement stays open. |
| GCR-60 | **Tier 1** (consequential decision, or member of the accepted set of one): reaffirmation is a fresh acceptance by an independent human holding AUTH-G over the accepted set on the current basis. Revision carries the requirement to the successor until independently reaffirmed or accepted. Retirement is by the producer or any gate authority holder. |
| GCR-61 | **Tier 2** (other non-decision dependents): the producer may revise or retire. Reaffirmation requires a human holding AUTH-G who is a producer of neither the dependent nor its material basis closure. No lesser authority class exists. A producer-addressed closure is not independent closure and is part of the standing record if the dependent later becomes standing. |
| GCR-62 | Revision, retirement, supersession, and invalidation of a dependent are triggers for its dependents. Reaffirmation is not. An acceptance found invalid or withdrawn is TRG-6. |
| GCR-63 | Only a human holding AUTH-G may close a requirement by reaffirmation or by recording a decision. A producer may also retire its own dependent (a conservative act), and may revise its own Tier 2 dependent, which closes the requirement as producer-addressed only. Actors holding AUTH-A, AUTH-V, evaluators, and agents may request, challenge, and escalate. They may not close. |

---

## 12. Hypothesis Validation and Assumption-Rooted Support

Operationalizes FR-7, AH-1, AH-2, GR-2. Resolves **EK-OQ-02 / PS-OQ-09** (in part) and addresses **PO A-3**.

### 12.1 Validation is an acceptance

STEP-02 defined validation as authorized acceptance that a hypothesis's required evidence and challenge criteria are satisfied for a stated scope (EKR-24, EKR-25). It left open who may validate a hypothesis not tied to a consequential gate (EK-OQ-02) and what the gate relationship is.

### 12.2 Who may validate (EK-OQ-02)

**Resolution.** Validation is **always** an explicit act by a **human holding AUTH-G** for the hypothesis's scope, who is independent over the validation's accepted set (Section 4.4). This holds whether or not a consequential gate is involved.

**No lesser acceptance class.** STEP-01 has four authority classes and no weaker acceptor. Creating one would be an architecture-level choice (declared as UAD3-24, level A). It is also unnecessary for burden control, because **AUTH-G is scoped** (PR-02, PR-04). A project may grant AUTH-G with a narrow scope, for example "validation of hypotheses on the technical-feasibility dimension," to a person who is not the Product Moderator. That is cheap and keeps acceptance human, attributable, and independent.

**If validation is absent.** A hypothesis that cannot yet be validated may be relied on only as an unresolved assumption under conditional progression (Section 9.2, ground G1) when the reliance is consequential. Before that, ordinary work records reliance under assumption.

**Gate-tied validation.** A validation relied on by a gate is a separate acceptance-type record that the gate cites as a required evidence or challenge criterion. Its accepted set joins the gate's accepted set (Section 4.3, item 2). The same human may perform the validation and the gate acceptance only if independent of the union.

### 12.3 Scope, criteria, and results

- A validation states the **scope** it validates the hypothesis for (EKR-25).
- It cites the **criteria** recorded with the hypothesis (EKR-21), the **evidence and test results** relied on, whether favorable or not (EKR-18), and the **challenge responses** relied on.
- **Criteria amended after test results are recorded are a supersession of the hypothesis, never a correction** (Section 10.3). Without this rule, criteria could be redrawn around the results.
- A validated hypothesis can lose that standing. Triggers apply (EKR-25, Section 11).

### 12.4 Assumption-rooted support (PO A-3)

A basis item is **assumption-rooted** when **every** support or derivation chain beneath it ends only in assumptions or unvalidated hypotheses, and none reaches an evidence item. It is derivable from the record (EKO-10 already requires chains to ground).

An inference grounded wholly in an assumption is permitted (EKR-26). The risk the Product Owner named is that such support reads as evidence-backed because it is cited and traced. STEP-03 answers: a gate basis must **identify** its assumption-rooted items, and they are included among the unresolved assumptions relied on (Section 9.2, ground G1). No new class is created. The identification is a property of the record and not evidence, and it is a candidate rule for STEP-04 (GC-OQ-11).

### 12.5 Rules

| ID | Rule |
| --- | --- |
| GCR-64 | Validation of a material hypothesis is an explicit act by a human holding AUTH-G for the scope, independent over the validation's accepted set, whether or not a consequential gate is involved. Grants may be narrow in scope. No lesser acceptance class exists. |
| GCR-65 | A validation states its scope and cites the criteria, results (favorable or not), and challenge responses relied on. Criteria amended after results are recorded are a supersession of the hypothesis. |
| GCR-66 | A gate basis identifies its assumption-rooted items. They are among the unresolved assumptions covered by a conditional progression authorization where reliance is consequential. |

---

## 13. Time and Evidence-Age Effects

Resolves **EK-OQ-10**.

### 13.1 The question

Can the passage of time, or the age of evidence, itself create exposure, a request, a requirement, or nothing?

### 13.2 Position

| Candidate effect | Result | Why |
| --- | --- | --- |
| **Exposure** | **No direct effect** | Exposure is derived from an item being contested or having an open trigger or requirement. Age is neither |
| **A revalidation requirement** | **No direct effect** | A trigger is an _event on an item_ (STEP-02 Section 10.4). A clock is not an event. A clock-driven requirement would make every dated item a standing obligation: it would flood (E-2) and put the creation of obligations in the hands of nobody who decided |
| **A revalidation request** (ACT-06, route P3) | **Permitted, by an identified actor with a stated basis** | An actor holding AUTH-A, AUTH-V, or AUTH-G may judge that the age of evidence matters and say why (EKJ-02, EKJ-11). The judgment sits with an accountable actor |
| **An input to sufficiency** | **Yes** | Evidence age is relevant to sufficiency (STEP-02 Section 7.2). The acceptor judges it |
| **A gate-time formal check** | **Yes, where the gate definition defines it** | A required-evidence slot may carry a **recency criterion** (Section 5.2). It is evaluated at the acceptance act against recorded observation times. Failing it leaves the slot unsatisfied, so an exception is needed. It is checked at a point in time and is not a continuing clock |
| **Closing or ending anything** | **Never** | Time never validates, accepts, closes a requirement, resolves a disagreement, or ends an authorization (PR-13, EKR-38, GCR-41) |

### 13.3 Stated review events

An authorization may state a **review event** (Section 9.2, element 9). It is recorded for visibility. It has no automatic effect. Whether authorizations may carry **protocol-effective terms** (for example, "lapses on a stated date") is not decided here. It would create a time-driven effect by an authorizer's own act, which is different from elapsed time acting alone. It is routed (GC-OQ-09).

### 13.4 Rules

| ID | Rule |
| --- | --- |
| GCR-67 | Elapsed time and evidence age have no direct effect on exposure or on any requirement and never validate, accept, close, resolve, or end anything. They are inputs to sufficiency judgment and may be the stated basis of a request (ACT-06). |
| GCR-68 | A gate definition may state a recency criterion as part of a required-evidence slot. It is evaluated at the acceptance act against recorded observation times. A shortfall is an unsatisfied requirement. |

---

## 14. Objectively Checkable Conditions and Contextual Human Judgments

Operationalizes D6 and E-9. Extends STEP-01 Section 9 and STEP-02 Section 11. It is an initial classification of this artifact's own conditions and does **not** replace STEP-04's rule catalog (PS-OQ-10).

### 14.1 The boundary

A check is **objectively checkable** when it can be decided from the record alone, without interpreting the world the record describes. Everything else is a **contextual judgment** reserved to an appropriately authorized human (STEP-02 Section 11.1). The same limit applies: the semantics can require that a challenge exists; they cannot check that it was good.

### 14.2 Objectively checkable conditions (initial set)

Each is checkable **given a record that carries the elements STEP-02 Section 6 and this artifact require**. Each is a candidate for STEP-04. None specifies how it is checked or whether a violation is blocked or flagged.

| ID | Condition | Rule |
| --- | --- | --- |
| GCO-01 | The accepted set is computable: basis links resolve, the closure is computed, and every member has recorded, resolvable producers | GCR-01, GCR-04; EKR-32; OBJ-08 |
| GCO-02 | The acceptor is a human identity holding an AUTH-G grant covering the scope at the act | GCR-16; OBJ-02, OBJ-04 |
| GCO-03 | The acceptor, with collective identities expanded to members, is a producer of no member of the accepted set | GCR-03, GCR-08; OBJ-03 generalized |
| GCO-04 | A gate definition was recorded before the act and the progression is within it; no amendment after a refusal or deferral on the same basis is applied except as a recorded exception | GCR-12, GCR-13 |
| GCO-05 | Each required-evidence slot is filled by present items with the required designations. A visible absence statement does not fill it. A recency criterion is checked against recorded observation times | GCR-14, GCR-68; EKO-04, EKO-05 |
| GCO-06 | A required challenge exists, its challenger is not a producer of the challenged item, and required treatments are recorded | GCR-15; OBJ-06 |
| GCO-07 | A required formal check has a verification that names its criteria, whose verifier is a producer of nothing verified, and which the acceptor did not itself perform | GCR-10; OBJ-13 |
| GCO-08 | Every standing-record item, including earlier refusals and deferrals, is cited with a recorded treatment | GCR-17, GCR-39; EKO-17 |
| GCO-09 | Every relied-on unvalidated hypothesis or assumption is covered by a conditional progression authorization, and every open requirement on a basis item by a closure or a reliance-while-open authorization, recorded at or before the acceptance | GCR-16, GCR-42, GCR-47 |
| GCO-10 | Every unsatisfied gate requirement is covered by an exception with the required content and independence. No non-waivable condition is waived | GCR-45, GCR-46; OBJ-12 |
| GCO-11 | The acceptance-act content carries an independence declaration and the determination. The act is explicit and attributable and precedes the progression | GCR-09; OBJ-11 |
| GCO-12 | A valid challenge records challenger, target, target scope, and basis. A closure is of a recognized kind and a closer meets its authority conditions | GCR-23, GCR-26 |
| GCO-13 | A challenge or relationship recorded against an item is carried to its recorded successor | GCR-28 |
| GCO-14 | Each contribution has its Section 7.3 effect: contestation and exposure for challenges and bare contradiction; a requirement for source-identified counter-evidence on a material dependency | GCR-30, GCR-31; EKO-19 |
| GCO-15 | A request records its stated basis | GCR-32 |
| GCO-16 | A withdrawal records producer, time, and rationale. A withdrawn item remains recorded and cited. A requirement from withdrawn counter-evidence remains open | GCR-49, GCR-54 |
| GCO-17 | A correction designation on a standing item has an independent confirmation by a producer of neither item nor change, a recorded notice to the original acceptor, and no pending objection. Otherwise the change is treated as a supersession | GCR-51, GCR-52 |
| GCO-18 | A change of any of the five kinds in Section 10.3 is recorded as a supersession | GCR-53 |
| GCO-19 | Supersession or invalidation of another actor's item is recorded only by a human holding AUTH-G for its scope. Attempts by others are recorded as challenge, counter-evidence, or advisory finding | GCR-56; EKO-12 |
| GCO-20 | A dependent has a single requirement record with its reasons. A closure addresses every reason and meets the authority conditions of Section 11.4 | GCR-58, GCR-59, GCR-60, GCR-61 |
| GCO-21 | A conditional progression authorization records its nine elements | GCR-42 |
| GCO-22 | Exposure is derivable: dependents of contested items and of items with open triggers or requirements are identifiable as exposed | GCR-30; EKR-40 |
| GCO-23 | Producer sets are append-only | GCR-07 |
| GCO-24 | Assumption-rooted basis items are identified in the gate basis | GCR-66 |
| GCO-25 | Where no identity can meet the independence condition for a matter, an authority gap is recorded, and no act by a conflicted holder purports to cure it | GCR-40 |
| GCO-26 | An escalation records the actor, matter, resolving authority sought, reason, and determination asked for | GCR-37 |
| GCO-27 | An output of an evaluator or other non-AUTH-G actor is typed as advisory and is not recorded as acceptance, refusal, deferral, authorization, waiver, closure, or confirmation | GCR-22; EKO-20 |
| GCO-28 | A trigger event of any kind on a material dependency has a corresponding open requirement on the dependent, including TRG-6 | GCR-58; EKO-19 |

### 14.3 Contextual human judgments (initial set)

For each judgment, the **paired objective check** is the mechanical fact that can support it. It never decides it.

| ID | Judgment | Extends | Paired objective check |
| --- | --- | --- | --- |
| GCJ-01 | Whether the evidence and basis are sufficient for the gate's scope | HJ-01; EKJ-02 | GCO-05, GCO-06 (presence only) |
| GCJ-02 | Whether a response adequately answers a challenge, and whether a challenge stands | HJ-04; EKJ-12 | GCO-08 (a treatment is recorded) |
| GCJ-03 | Whether residual disagreement or residual risk is acceptable for the gate | HJ-05, HJ-08; EKJ-12, EKJ-14 | GCO-08 |
| GCJ-04 | Whether conditional progression is warranted | HJ-09 | GCO-21 (the authorization is complete) |
| GCJ-05 | Whether a waiver or exception is warranted | new | GCO-10 (the exception record is complete) |
| GCJ-06 | Whether a change alters meaning: correction or supersession (outside the five never-correction cases) | EKJ-09 | GCO-17, GCO-18 |
| GCJ-07 | Whether a dependency is material or missing, and whether a redesignation is warranted | EKJ-01, EKJ-10 | GCO-14 |
| GCJ-08 | Whether a trigger, a bare contradiction, or evidence age undermines a dependent, and whether the outcome is reaffirmation, revision, or retirement | HJ-10; EKJ-11 | GCO-20, GCO-28 |
| GCJ-09 | Whether identities are substantively independent, including whether an assigner supplied substance and whether undisclosed relationships exist | HJ-07; EKJ-04 | GCO-03, GCO-11 (identity distinctness and a declaration) |
| GCJ-10 | Whether a withdrawal's rationale is genuine | new | GCO-16 (a rationale is recorded) |
| GCJ-11 | What weight an advisory finding or evaluator output deserves | EKJ-13 | GCO-27 |
| GCJ-12 | Whether a hypothesis's criteria are adequate and satisfied, and what scope a validation covers | EKJ-06, EKJ-07 | GCO-05; EKO-09, EKO-11 |
| GCJ-13 | Whether evidence age matters for the target | EKJ-02 | GCO-05 (recorded observation times) |
| GCJ-14 | Whether a gate definition's slots are adequate for the product category | new | GCO-04 (a definition exists) |

### 14.4 Rules about the boundary

STEP-02's EKR-41 stands unchanged and applies to this artifact's tables. An implementation **may** block or flag a GCO-class violation. It **must not** decide a GCJ-class question, present one as decided, or convert one into a score or grade that implies it was decided (GR-4). The absence of a mechanical check never implies that a requirement does not apply. The rules of this artifact that are hard to check remain binding.

Whether each GCO condition is blocked, flagged, or escalated on detection is STEP-04's question (PS-OQ-10; GC-OQ-01).

---

## 15. Undecided Architecture Declaration

Required by **MW-ADAPT-001** (`research/mod-w-transferability/adaptations.md`). Routes to the Tech Lead in addition to MOD-W Moderator review. After this declaration, Tech Lead or QA is expected to sample for unlisted choices in authority, independence, evidence standing, and revalidation (Section 15.4).

### 15.1 How this declaration was compiled

The declaration was compiled by an **audit pass over the finished draft**, against accepted upstream artifacts (`mod-w/product.md`, `mod-w/architecture.md`, `mod-w/domain-language.md`, `prod-w/protocol-semantics.md`, `prod-w/evidence-knowledge-model.md`, and `mod-w/step-03.md` with its carry-forward and review inputs).

**Working test.** A choice is declared if a reasonable alternative reading of the upstream artifacts would have produced a materially different semantics, **or** if the choice touches authority, actor identity, independence, evidence standing, disagreement, gates, correction or supersession, withdrawal, or revalidation. Choices that only restate or organize what upstream artifacts already state are treated as operationalization and are not declared.

**What the audit pass added.** The Development Team's drafting plan covered the questions in `mod-w/step-03.md`. Re-reading the finished text against the working test added UAD3-33 (non-retroactivity) and UAD3-34 (challenge targets extended to determinations), and made explicit that the **standing item** concept inside UAD3-15 is itself a choice. The plan had treated it as notation.

**Limits, stated plainly.** The working test is this team's judgment. MW-OBS-010 and MW-OBS-011 show that architecture-level choices are hard to see from inside the artifact that contains them, and STEP-02's re-evaluation found that choices touching authority and revalidation still slipped past a self-audit. The Development Team **cannot certify** that it has found every such choice, **cannot classify its own choices as lower-level**, and cannot show that nothing slipped past, because it is the same actor as the producer. The **level** column is a proposal. The Tech Lead or QA determines both the completeness and the levels.

### 15.2 Declared decisions

Level scale as in STEP-02: **A** = architecture-level candidate (touches identity, authority, independence, evidence standing, or revalidation; recommend Tech Lead review before acceptance); **M** = model-level (a choice within a defined space; recommend confirmation); **L** = low (organizing or completing an accepted principle; listed for visibility).

| ID | Decision made | What upstream left open | Reasoning, and input derived from | Level |
| --- | --- | --- | --- | --- |
| UAD3-01 | For a consequential acceptance, decision, or validation, **"the accepted item" is the accepted set**: subject, material basis followed transitively across support, derivation, assumption, and upstream-decision links, the designations (including non-material ones), the challenge responses relied on, and the verification records relied on. Opposition, acceptance-act content, upstream acceptances as acts, and the gate definition are outside it. Other acts use sized sets (Section 4.4) | PR-16, PR-21 say "the accepted item" and STEP-02 EKR-32 only keeps producers resolvable. EK-OQ-05 | A narrow reading (the record's own text) makes the rule trivially met. A producer of the key inference could accept the decision. Transitive closure follows the material dependency links STEP-02 already requires. Excluding opposition keeps challengers eligible to accept. From: PR-16 to PR-21, EKR-32, EKR-35, Tech Lead follow-up (EK-OQ-05), PO A-1 | **A** |
| UAD3-02 | **Acceptance-act content is not production.** An acceptor that drafted the subject, including a recommendation later adopted as a decision, is a producer of it | PR-16 does not distinguish a decision-maker's commitment from the item committed to | Without the carve-out no acceptance could be valid. With it, "I decided" cannot be used to launder "I proposed" | **A** |
| UAD3-03 | **Recusal is asymmetric.** A producer of the set may not perform favorable acts over it (accept, waive, authorize, confirm, reaffirm, close in its favor, accept residual). It may perform conservative acts (refuse, defer, escalate, request, challenge, withdraw or retire its own, invalidate) | PR-16 speaks only to acceptance | Independence matters where an act benefits the producer. Conservative acts cannot manufacture progression and should not be blocked. Needed to say who may raise requests and invalidate | **A** |
| UAD3-04 | **Independence cannot be waived or cured by any gate outcome.** It is satisfied only by a different acceptor or by visible re-basing on independent items | PS Section 5.3 says waivers must remain visible but does not say what cannot be waived | A waiver by the self-approving party is the self-approval it would excuse. FR-4 forbids relying on instruction alone. From: PR-16 to PR-21, FR-4, GR-7 | **A** |
| UAD3-05 | **Producer sets are append-only** for independence. Omitted contributors are added by disclosure. A disputed attribution is treated conservatively against the disputed actor's favorable acts until an independent gate authority holder resolves it | PS-OQ-07 | STEP-01 Section 6.3 already holds that restatement does not remove a producer. Conservative treatment makes disputing cheap and bounded to the disputed actor | **A** |
| UAD3-06 | New trigger **TRG-6**: an acceptance found invalid, or withdrawn by its acceptor, is a trigger for everything that relied on it | STEP-02 catalog is "initial and non-exhaustive." It lists no trigger for acceptance invalidity | An invalid acceptance means progression without authorization. Dependents must not stay silently valid. From: PR-11, PR-26, WD-6 | **A** |
| UAD3-07 | **Identity.** A collective identity may be a recorded producer only with recorded membership and expands to members for independence. AUTH-G is individual and human. Delegation conveys no authority and is recorded as **assignment**, which makes an assigner a producer only if it supplied the item's substance or adopted it. Every consequential acceptance carries an **independence declaration** | EK-OQ-03, PS-OQ-06 | Collective-as-unit would let a member accept the team's work. Treating every assigner as producer would make the central PROD-W flow (agents produce, a human accepts) impossible for small teams. The substance test and the declaration give a challengeable boundary. From: PR-04, PR-05, PR-06, PR-27 | **A** |
| UAD3-08 | A **gate-required formal check** is satisfied only by a verification whose verifier produced nothing verified. The acceptor cannot rely on its own verification. A non-human AUTH-V verification satisfies a required check only if the criteria are decidable from the record. AI-held AUTH-V in general is routed | PS-OQ-02, PS-OQ-08 | Independent acceptance alone would let an acceptor trust a producer's self-check. Keeping non-required verification as an ordinary record avoids over-requiring | **A** |
| UAD3-09 | **Gate consequence of EKR-30.** Every standing-record item (opposition, exposure, open requirements, reliance marks, earlier refusals and deferrals, exceptions) must be cited with a recorded treatment. Omission makes the acceptance invalid. Five treatments are available | STEP-02 Section 9.4 states record content only and leaves gate consequences to STEP-03 | The failure pattern is decisions made as though opposition did not exist. Treating omission as invalid (missing required content, PR-10) makes it checkable. Default requires a treatment, not an answer, so disagreement does not block (WD-2). From: EKR-30, PR-10, FR-5, HA-3 | **A** |
| UAD3-10 | A **gate definition must precede** a consequential progression, with its slots (which may be empty). A consequential decision without one is a recommendation. A definition amended after a refusal or deferral on the same basis applies only as an exception. Gate definition is an act of a human holding AUTH-G for the gate-definition scope. The default acceptance rule is one valid independent acceptance | GR-1 and GR-5 require explicit gates and named decision points. Nothing says what "no gate" yields, or who defines gates, or whether a standard can move after a refusal | Moving the standard to fit a refused basis defeats the gate. A recommendation is the existing STEP-01 outcome for an unauthorized decision. From: GR-1, GR-5, GR-7, ACT-07 | **A** |
| UAD3-11 | **Challenge closure.** Only challenger resolution, authority closure (a gate authority holder independent of the item's accepted set and not the author of the challenged determination), or mootness by withdrawal closes a challenge. A response never does. Challenger resolution ends the challenge's exposure effect but stays visible and may be re-raised. A challenge carries to the successor on supersession | STEP-01 ACT-03 and STEP-02 EKR-05 defer closure. AUTH-A "may not close a challenge as sufficiently answered where reserved to a gate authority" | Closing a challenge to one's own determination is self-approval. Carry-over blocks shedding by supersession. Challenger resolution can be coerced: it stays visible and re-raisable, and the acceptor still decides at a gate. From: PS Section 4.4, EKR-05, D-05a | **A** |
| UAD3-12 | **Dependent-effect classification (D-08).** Challenge: contestation and exposure. Source-identified counter-evidence: requirement. Bare contradicting claim or inference: contestation and exposure, with routes to a requirement (P1 grounding, P2 acceptance, P3 request). Qualifying items: no automatic effect. **This narrows STEP-02 TRG-2 and EKR-37 as to bare contradicting claims and inferences** | EK-OQ-04; QA D-08; Moderator direction | A bare contradiction costs about what a challenge costs. Making it a trigger reintroduces the flooding STEP-02 excluded for challenges and risks teams ignoring requirements. Exposure keeps it from being silent. The routes keep the effect available. This is a change to an accepted reading, so it is declared at level A and flagged in Section 3.3. From: Tech Lead follow-up, PO A-2, WD-2, WD-6 | **A** |
| UAD3-13 | An ACT-06 request **records its stated basis** | STEP-01 describes ACT-06 and leaves content open | Makes the HJ-10 judgment attributable | L |
| UAD3-14 | **Disputed materiality (EK-OQ-07).** A challenged non-material designation restores the presumption of materiality until an independent gate authority holder resolves it. Redesignation or link removal on a standing dependent takes effect for triggers and later accepted sets only on independent confirmation | EK-OQ-07; STEP-02 EKR-36 requires a rationale and no more | Presumption restoration is conservative. Without confirmation, a producer and an interested party could narrow a basis so the interested party can accept it. From: EKR-35, UAD-05 | **A** |
| UAD3-15 | **Correction designation (EK-OQ-17).** A producer's designation on a **standing** item is a proposal. It takes effect only on confirmation by a human holding AUTH-G for the scope who produced neither item nor change, with notice to the original acceptor and no pending objection. Unconfirmed means supersession. Five kinds of change are never corrections. **"Standing item"** (accepted, or a member of a consequential accepted set) is introduced as the dividing concept | EK-OQ-17; PO R-1; EKR-10, EKJ-09 | Otherwise PR-16 is reached through item identity. The standing concept lets non-consequential work stay light. The never-correction list gives objective tripwires without deciding EKJ-09. From: Tech Lead follow-up, PR-16, UAD-04 | **A** |
| UAD3-16 | **Withdrawal.** A producer may withdraw its own item as a visible event with rationale. Withdrawing own counter-evidence does not erase it, close the requirement it created, or remove it from later decision bases, and any AUTH-A actor may re-attach the source. Withdrawal by fewer than all co-producers withdraws only that producer's endorsement | EK-OQ-17 question 4; D-05b | Preserves the producer's legitimate retraction while preventing cleansing. The co-producer rule is needed because PR-21 recognizes multiple producers. From: EKR-09, EKR-18, EKR-30, EKR-31 | **A** |
| UAD3-17 | **Own item versus another actor's.** Producer-owned acts are valid without independent review and always visible. Supersession or invalidation of another actor's item needs a human holding AUTH-G for the scope. Invalidation is a conservative act needing no independence from rivals. Supersession also needs independent acceptance of the replacing item. Reinstatement needs fresh independent acceptance. Others' attempts are recorded as challenge, counter-evidence, or advisory finding | EK-OQ-06 (PS-OQ-07); D-05b | The Tech Lead confirmed the split and asked that STEP-03 declare it. From: PR-10 to PR-16, EKR-04, TRG-1, TRG-3, TRG-4 | **A** |
| UAD3-18 | **Conditional progression.** Two grounds (G1 assumption, G2 open requirement). Nine-element form. Non-delegable, effective when recorded, not inherited by later gates, revocable by any gate authority holder for the scope as a conservative act. FR-7's "progression" is read as progression through a gate or consequential commitment. Ordinary work relying on an unvalidated item records reliance under assumption and needs no authorization | EK-OQ-08; FR-7 says "project may continue" without defining the unit | A broader reading would require authorization for every draft. A narrower one lets reliance slide into commitments unmarked. From: FR-7, EKR-23, PR-04, PR-05 | **A** |
| UAD3-19 | **Waivers and exceptions.** Defined with required content. The marker travels with the acceptance and is not erased by reaffirmation. An override is an exception. Six conditions are non-waivable, including independence and FR-7's conditions. A requirement that a hypothesis be validated is not waivable into silence | PS-OQ-12; GR-7 | Visibility that disappears when an acceptance is cited downstream is not visibility. Letting a waiver stand in for conditional progression would drop FR-7's four conditions. From: GR-7, OBJ-12, FR-7 | **A** |
| UAD3-20 | **Disagreement is a derived condition** over the record, not a named state, a property, or a relationship of its own. It ends by challenger resolution, authority closure, concession with closure, or **resolution by decision** (a sufficiency determination for a scope with dissent preserved) | EK-OQ-13 / PS-OQ-03; D5 leaves it to STEP-03 | A recorded label can be forgotten or quietly cleared. Derivation matches D5 and defers storage to STEP-05. From: D5, WD-2, EKR-05 | M |
| UAD3-21 | **Progression under disagreement.** Permitted by default. The acceptor decides whether residual disagreement is acceptable and marks the decision. Disputes about the validity or independence of an act cannot be accepted as residual by the disputed actor. Earlier refusals and deferrals on the same gate and basis are cited in any later acceptance. No override hierarchy is defined among holders | FR-5, WD-2, NG-5 leave how to proceed; product OQ-7 | Closes acceptor shopping without a veto. Leaves a reviewable-authority question open and routed. From: WD-2, GR-6, OQ-7 | **A** |
| UAD3-22 | A revalidation requirement is **one obligation per dependent** carrying a visible reason per trigger. **Exposure never bars reliance.** An open requirement bars _silent new_ reliance and not historical acceptance. New reliance needs a closure or a reliance-while-open authorization | STEP-02 EKR-37: "creates a requirement on that dependent"; EK-OQ-04 | Per-dependent collapses flooding. Barring silent reliance gives requirements force without clocks. From: EKR-37, EKR-38, PR-26, WD-6 | **A** |
| UAD3-23 | **Closure authority tiers (EK-OQ-16).** Tier 1 (consequential reach): reaffirmation is a fresh acceptance by an independent human holding AUTH-G. Tier 2 (other non-decision dependents): the producer may revise or retire; reaffirmation needs a human holding AUTH-G who produced neither the dependent nor its basis. No lesser authority class. Producer-addressed closure is not independent closure if the dependent later becomes standing | EK-OQ-16; PS-OQ-09 | A weaker acceptor class would be a fifth authority class. Tiering and narrow-scope grants contain burden. The standing-transition clause stops carrying a producer's self-clearance into a gate. From: D-05c, PR-12, PR-13, PR-16 | **A** |
| UAD3-24 | **Validation (EK-OQ-02)** is always an explicit act by an independent human holding AUTH-G, whether or not a consequential gate is involved. Scope may be narrow. No lesser acceptance class | EK-OQ-02 | Reuses STEP-01. Scope is how burden is managed. From: FR-7, PR-02, PR-04, PR-13, UAD-15 | **A** |
| UAD3-25 | Criteria amended after test results are recorded are a **supersession** of the hypothesis, never a correction | Nothing in STEP-02 addresses post hoc criteria | Closes the redrawn-criteria route. From: EKR-21, EKR-18, UAD-04 | M |
| UAD3-26 | A gate basis must **identify assumption-rooted** items, which are among the unresolved assumptions relied on | PO A-3 | Makes visible what is already derivable. No new class | L |
| UAD3-27 | **Time and evidence age** (EK-OQ-10): no direct effect on exposure or requirements. An input to sufficiency, a possible stated ground for a request, and a gate-defined recency criterion evaluated at the acceptance act. Never closes or ends anything | EK-OQ-10 | A clock is not an event on an item. Clock-driven requirements flood and hide who judged. Gate-time recency keeps a legitimate use. From: PR-13, EKR-38, EKJ-02 | **A** |
| UAD3-28 | **Escalation and authority gap.** Escalation names the resolving authority, derived from grants, never closes anything, and stays visible until a determination. An **authority gap** is a visible condition cured only by a grant to an independent human, visible re-basing, or substitution. It is not cured by a self-conferred grant, a collective, an agent, a waiver, or time | HA-3, GR-6; PS-OQ-05, PS-OQ-09 | Paths must be explicit without a role catalog (STEP-06). A gap that can be waived away is the self-approval it describes. Self-conferral is routed to STEP-04 | **A** |
| UAD3-29 | External evaluators may satisfy the _existence_ of a required independent challenge and may supply verifications within UAD3-08. They never accept, refuse, defer, authorize, waive, confirm, close, reaffirm, or invalidate | D8 and STEP-02 EKR-20 | Operationalizes D8 at gates | L |
| UAD3-30 | **Reaffirmation of a consequential decision is a fresh acceptance** of the full accepted set on the current basis | PR-26, EKR-38 say "reaffirms" | Reuses independence rules. Reaffirming on the old basis would ignore what changed | M |
| UAD3-31 | **Gate outcomes are acts**, not states, with no defined order. Refusal and deferral are defined (reasons, awaited condition, no time effect) and remain in the standing record | STEP-01 names acceptance and waiver only | Keeps D2 and GR-5. Needed for UAD3-21 | M |
| UAD3-32 | **Gate definition slots.** A visible absence statement does not satisfy a required-evidence slot. A required formal check is bounded and non-judgmental. A stricter-conditions slot is optional | FR-3 says gates specify categories "where applicable" | Gives FR-3 a representation-neutral shape while leaving contents to STEP-06. From: FR-3, PE-1, GR-4 | M |
| UAD3-33 | Authorizations, waivers, exceptions, confirmations, and closures take effect when recorded and **never retroactively** | STEP-01 does not address timing of authorizing acts | Retroactive authorization would cure unauthorized progression by paperwork. From: PR-11, PR-13 | M |
| UAD3-34 | **Challenge targets extend** from STEP-02's items, relationships, and decisions to determinations (acceptances, waivers, authorizations, closures) and to the validity of acts, including producer attributions and correction designations | STEP-02 UAD-03 | A determination that cannot be challenged cannot be reviewed. No authority is added (AUTH-A). From: UAD-03, EKR-03 | M |

### 15.3 Recommended Tech Lead priority

If review time is limited:

1. **Independence and the accepted item:** UAD3-01, UAD3-02, UAD3-03, UAD3-04, UAD3-05, UAD3-07. These decide whether self-approval can enter through citation, identity, or an agent.
2. **Authority over change:** UAD3-15, UAD3-16, UAD3-17. These decide whether it can enter through an edit.
3. **Effect on dependents and burden:** UAD3-12 (which narrows an accepted STEP-02 reading), UAD3-22, UAD3-23.
4. **Closure and instruments:** UAD3-11, UAD3-18, UAD3-19, UAD3-21.
5. Then UAD3-24, UAD3-27, UAD3-28.

Options for each, offered without preference: confirm as operationalization; promote to an architecture decision; return for revision. Several of these (notably UAD3-01, UAD3-12, UAD3-15, UAD3-22) govern behavior that `mod-w/architecture.md` does not state. As with STEP-02's UAD-04 to UAD-07, the rules would then live only in this product artifact. Whether any should be promoted is a Tech Lead and Moderator question.

### 15.4 Sampling targets for the independent pass

For the Tech Lead or QA sampling that MW-ADAPT-001 now expects. These are where the Development Team believes unlisted choices are most likely to remain, and what to look for.

| Area | Probe |
| --- | --- |
| **Authority** | For every "may" and every recorded act in Sections 5 to 11: which authority class and grant does it need? Find any act that appears to need none. Find any place a grant is assumed to be narrow, collective, or delegated |
| **Independence** | Find any act whose beneficiary could also perform it. Check the accepted-set closure for a path through which a producer reaches a decision it cannot accept. Check the agent-and-assigner boundary (GCR-08): can a human supply substance through an agent and escape producer status? |
| **Evidence standing** | Check what the routes P1 to P3 let a cheap contributor do. Check the withdrawal rules for any way counter-evidence can disappear from view. Check whether "assumption-rooted," "visible absence," or "withdrawn contradicting item" can be read as lending standing |
| **Revalidation** | Check the per-dependent requirement for any reason that can be dropped. Check Tier 2 and the standing transition for a route by which a producer's self-clearance reaches a gate. Check whether time acts anywhere (it should not) |
| **Gates** | Check whether any outcome can be reached without a human holding AUTH-G. Check whether the standard can move after a refusal |

**Known soft spots the Development Team can name.**

- **Challenger resolution can be coerced.** A challenger pressured to withdraw ends the challenge's exposure effect. It stays visible and may be re-raised, and the acceptor still judges. It is not otherwise guarded.
- **P3 makes requirements cheap for any actor holding AUTH-A, AUTH-V, or AUTH-G.** This follows STEP-01's ACT-06. The per-dependent requirement contains the cost, and it is untested.
- **Authority gaps may be common in small teams.** Independence requires at least two distinct humans with the relevant scope. The artifact makes the gap visible and does not solve it.
- **The assigner-versus-producer boundary is a judgment** (GCJ-09) the interested party makes first.
- **Closure computation cost.** Accepted-set closure and standing transitions are mechanical, but may be heavy on a real record. They are untested (GC-OQ-08).
- **Original-acceptor notice** is a recorded event. Receipt is not checkable.

### 15.5 Decisions considered and not made

The following were considered and deliberately left open. This is not a declaration that nothing else was decided.

- Condition or state names, including for disagreement, contested, exposed, open requirement, or current validity; lifecycle graphs, transition mechanics, or the sequence of acts.
- Any representation, schema, storage model, or serialization; whether conditions are stored or computed (EK-OQ-11, EK-OQ-12).
- Which evidence categories and thresholds a gate requires for any product category (EK-OQ-01, product OQ-2).
- A role catalog, or which people hold AUTH-G, gate-definition, or narrow validation scopes in any project (PS-OQ-09 remainder; product OQ-4).
- How grants are created, scoped, changed, revoked, and audited, including self-conferral (PS-OQ-05).
- Whether AI agents may hold AUTH-V in general (PS-OQ-08).
- Whether, on detection, an invalid action is blocked, flagged, or escalated (PS-OQ-10).
- Whether Product Moderator authority is reviewable or overridable (product OQ-7).
- Whether a lesser acceptance class should exist (rejected for now, UAD3-23, UAD3-24; routed to pilot evidence).
- Whether authorizations may carry protocol-effective terms (GC-OQ-09).
- Granularity of producing-configuration and lineage recording (EK-OQ-09).
- Anything about external evaluator contracts (PS-OQ-11), the agent-skills research hypotheses, or speed-versus-rigor tradeoffs (product OQ-6).

### 15.6 Note for the MW-ADAPT-001 re-evaluation

MW-ADAPT-001's STEP-02 re-evaluation concluded that a self-audit alone is insufficient and that independent sampling should follow the declaration. This step is the first to apply that expectation. The Development Team's report on the first half (did the declaration produce findings) is that the audit pass produced thirty-four declared choices, of which twenty-four are self-assessed level A. The second half (did anything slip past) the Development Team cannot answer, for the reason in Section 15.1. See accepted observation MW-OBS-015.

---

## 16. Open Questions Routed to Later Steps

STEP-03 resolves the questions in Section 1.5. The following remain, and are routed without duplicating the ownership of the step they belong to.

### 16.1 New questions arising from STEP-03

| ID | Question | Routed to | Notes |
| --- | --- | --- | --- |
| GC-OQ-01 | For each GCO condition: is a violation blocked, flagged, or escalated? Which become the machine-checkable rule catalog? | STEP-04 | PS-OQ-10, EK-OQ-14. Section 14.2 is an initial classification only |
| GC-OQ-02 | How are authority grants created, scoped, changed, revoked, and audited? Is self-conferral of AUTH-G over a scope an invalid action? | STEP-04 | PS-OQ-05. STEP-03's interim position: self-conferral is not a valid cure for an authority gap (Section 8.6) |
| GC-OQ-03 | May AI agents hold AUTH-V, and what rule form carries verifier independence? | STEP-04 | PS-OQ-08, PS-OQ-02 remainder. Interim: GCR-10, GCR-11 |
| GC-OQ-04 | How are the derived conditions (contested, exposed, open requirement, current validity, disagreement) and item identity across change represented, and how are accepted-set closure and enumeration computed? | STEP-05 | EK-OQ-11, EK-OQ-12, EK-OQ-13 representation; PO A-6: do not treat EKR-09, EKR-33, EKR-40, or GCR-35 as selecting a ledger or central state model |
| GC-OQ-05 | How are collective identities, their membership over time, and assignment relations represented? | STEP-05 | EK-OQ-03 representation |
| GC-OQ-06 | Which evidence categories and thresholds does each gate require, by product category? Who holds AUTH-G, gate-definition, and narrow validation scopes? Which role positions exist? | STEP-06 | EK-OQ-01, product OQ-2, OQ-4, PS-OQ-09 remainder. Gate templates and role charters |
| GC-OQ-07 | How should teams of one or two practice independence, assignment disclosure, and the substance test? | STEP-06 | Guidance on GCR-08, GCR-09 and authority gaps |
| GC-OQ-08 | **Burden and friction.** Open requirements per consequential decision; closure effort and path; frequency of authority gaps and of P3 requests; correction-confirmation overhead; accepted-set closure cost; whether teams begin to ignore requirements; whether a lesser acceptance class is warranted; whether background knowledge collides with EKR-22 (PO A-4) | STEP-07 (pilot) | PO A-4, A-5; Tech Lead burden risk. Record as pilot evidence, not as requirements |
| GC-OQ-09 | May authorizations carry protocol-effective terms, such as a lapse date set by the authorizer? | STEP-04 / STEP-05 / pilot | Section 13.3 |
| GC-OQ-10 | Should Product Moderator authority be reviewable or overridable, and by whom? Is there a terminus above AUTH-G holders? | MOD-W Moderator / STEP-06 | Product OQ-7. STEP-03 defines no override hierarchy (Section 8.5) |
| GC-OQ-11 | Should the "assumption-rooted" identification (Section 12.4) and the "never a correction" tripwires (Section 10.3) become catalog rules? | STEP-04 | PO A-3 |
| GC-OQ-12 | Do the transferability observations from STEP-03 change the standing of MW-ADAPT-001 or of the plan and build gates for specification work? | STEP-08 / MOD-W Moderator | MW-OBS-015, MW-OBS-012 |

### 16.2 Upstream questions that remain with their steps and are not duplicated here

| ID | Question | Routed to |
| --- | --- | --- |
| EK-OQ-09 / PS-OQ-13 | Granularity of producing-configuration and lineage recording; does insufficient provenance invalidate or only weaken | STEP-04 |
| EK-OQ-12 | Realization of item identity across change (representation only; the authority question was EK-OQ-17 and is resolved in Section 10) | STEP-05 |
| EK-OQ-14 | Which EKO conditions become machine-checkable rules | STEP-04 |
| EK-OQ-15 | Separating role-specific and machine views | STEP-05 |
| PS-OQ-11 | External evaluator contract | Deferred (D8) |
| Agent-skills hypotheses H-A, H-B, H-C | Disposition of skills as producing configuration or protocol projections | STEP-05 (H-C), STEP-04 (producing-configuration granularity), STEP-08 (disposition). Non-normative. Not used by this artifact |
| Product OQ-1, OQ-6 | Product Skeptic and Advocate roles; speed versus rigor | Not addressed; NG-4 |

---

## 17. Traceability

### 17.1 Requirements

| Requirement | Where addressed |
| --- | --- |
| **FR-2** Governance semantics for progression | Sections 5, 9, 11; GCR-12 to GCR-22, GCR-42 to GCR-48, GCR-58 to GCR-63 |
| **FR-3** Evidence requirements | Section 5.2 (gate slots), 5.5, 12, 13.2; GCR-14, GCR-15, GCR-68; GCO-05, GCO-06 |
| **FR-4** Self-approval invalid | Sections 4, 9.4, 10.3, 11.4; GCR-01 to GCR-11, GCR-46, GCR-51, GCR-61 |
| **FR-5** Unresolved disagreement surfaced | Sections 6, 7, 8; GCR-23 to GCR-41 |
| **FR-6** Provenance for decisions, challenges, correction, withdrawal, revalidation | Sections 4.3, 5.5, 6.7, 10.4, 10.8, 11.2; GCR-07, GCR-17, GCR-29, GCR-49, GCR-54, GCR-58 |
| **FR-7** Hypothesis validation or visible assumption handling | Sections 9.2 to 9.4, 12; GCR-42 to GCR-44, GCR-64 to GCR-66 |
| **HA-3** Escalation paths explicit | Section 8.4, 8.6, 11.6; GCR-37, GCR-40 |
| **WD-2** Unresolved disagreement may remain visible | Sections 6.4, 8.1, 8.5; GCR-27, GCR-35, GCR-38 |
| **WD-6** Dependent decisions require revalidation | Sections 7.3, 7.6, 10, 11; GCR-30 to GCR-33, GCR-58 to GCR-63 |
| **GR-7** Gate exceptions visible | Section 9.4; GCR-45, GCR-46; GCO-10 |
| GR-1, GR-5, GR-6 Human authority, gating without a universal lifecycle, escalation | Sections 5.1, 5.2, 8.4; GCR-12, GCR-37 |
| HA-1, HA-2 Human consequential judgment | Sections 5.6, 5.8; GCR-18, GCR-22 |
| AH-1, AH-2, GR-2 Assumptions and hypotheses | Sections 9.2, 12 |
| PE-1, PE-2 Absence visible, agent agreement is not evidence | Sections 5.2, 8.7; GCR-14, GCR-41 |
| NG-1, NG-2, NG-4, NG-5 | Sections 1.3, 8.3, 15.5 |

### 17.2 Architecture decisions

| Decision | Where operationalized |
| --- | --- |
| D1 Protocol semantics are normative | Sections 1.2, 3 |
| D2 Protocol, schema, state separate | Sections 1.3, 5.6, 8.1 (derived, not named); GCR-18, GCR-35 |
| D3 Knowledge classes first-class | Sections 6.1, 7.2, 7.3; no class added |
| D4 Authority separate from role labels | Sections 4, 8.4, 10.8, 11.4; GCR-03, GCR-08, GCR-49 to GCR-57 |
| D5 Disagreement is a preserved condition | Section 8; GCR-35 to GCR-41 |
| D6 Objective checks separate from judgment | Section 14; GCO-01 to GCO-28; GCJ-01 to GCJ-14 |
| D7 Provenance and dependencies support revalidation | Sections 7, 10, 11; TRG-6; GCR-58 to GCR-63 |
| D8 Evaluators advisory unless granted authority | Sections 5.8; GCR-22; GCO-27 |
| D9 Working artifacts under `prod-w/` | This artifact lives under `prod-w/` (Section 18) |

### 17.3 Carry-forward items

| Item | Where addressed |
| --- | --- |
| **EK-OQ-05** (A-1) | Section 4; GCR-01 to GCR-06 |
| **EK-OQ-17** (R-1 / B-1) | Section 10; GCR-49 to GCR-55 |
| **EK-OQ-04**, QA **D-08** (A-2), Tech Lead widening | Sections 6, 7; GCR-23 to GCR-34 |
| **EK-OQ-06 / PS-OQ-07**, QA **D-05b** | Sections 4.6, 10.6; GCR-07, GCR-49, GCR-56 |
| QA D-05a, D-05c, D-05d | D-05a: Sections 5.8, 6.3 (AUTH-A attaches counter-evidence and cannot close). D-05c: Section 11.4 Tier 1. D-05d: Sections 10.4, 7.3 (EKR-18 carried as a conformance duty, with the detection limit in Section 1.4) |
| EK-OQ-02 / PS-OQ-09 | Section 12.2; GCR-64 |
| EK-OQ-03 / PS-OQ-06 | Section 4.6; GCR-08, GCR-09 |
| EK-OQ-07 | Section 7.7; GCR-34 |
| EK-OQ-08 / PS-OQ-12 / GR-7 | Section 9; GCR-42 to GCR-48 |
| EK-OQ-10 | Section 13; GCR-67, GCR-68 |
| EK-OQ-11 / PS-OQ-01 | Section 8.1 (semantic requirement); representation to STEP-05 (GC-OQ-04) |
| EK-OQ-13 / PS-OQ-03 | Section 8.1; GCR-35 |
| EK-OQ-16 | Section 11.4; GCR-60, GCR-61 |
| EK-OQ-01 | Section 5.2 (slots); content to STEP-06 (GC-OQ-06) |
| PS-OQ-02 | Section 4.9; GCR-10, GCR-11 |
| PS-OQ-05, PS-OQ-08 | Routed (GC-OQ-02, GC-OQ-03) with interim constraints |
| QA D-02, D-06 (terms) | Pending terms appended to `mod-w/domain-language.md`. Challenge and Inference were already corrected by the Moderator |
| PO A-3 | Section 12.4; GCR-66 |
| PO A-4, A-5 | Section 11.7; GC-OQ-08 |
| PO A-6 | GC-OQ-04 |
| Section E passages: EKR-30, EKR-41, EKR-35, EKR-37, UAD-04 to UAD-07 | EKR-30: Section 5.5. EKR-41: Section 14.4 (confirmed unchanged). EKR-35: Sections 4.3, 7.7. EKR-37: Sections 7.3, 11.2 (burden controls in 11.7). UAD-04 to UAD-07: Section 15.3 notes that the rules live only in the product artifacts |
| Section F process items | MW-ADAPT-001 applied (Section 15). Plan and build gate observation: MW-OBS-015. Carry-forward consolidation observed as an input (MW-OBS-015) |

### 17.4 STEP-03 acceptance checks

The checks in `mod-w/step-03.md` are unnumbered. They are numbered here in the order they appear there.

| # | Acceptance check | Where satisfied |
| --- | --- | --- |
| AC3-01 | Defines gate, gate basis, required evidence, required challenge criteria, acceptance, refusal, deferral, conditional progression, waiver/exception, escalation, unresolved disagreement, exposure, revalidation requirement, revalidation closure, correction, supersession, withdrawal, reaffirmation, revision, and retirement | Gate, gate basis, required evidence, required challenge criteria: 5.2. Acceptance, refusal, deferral: 5.6. Conditional progression, waiver/exception: 9. Escalation: 8.4. Unresolved disagreement: 8.1. Exposure: 7.2. Requirement, closure, reaffirmation, revision, retirement: 11.2, 11.3. Correction, supersession, withdrawal: 10 |
| AC3-02 | EK-OQ-05 resolved first | Section 4 (first substantive section); GCR-01 to GCR-06 |
| AC3-03 | EK-OQ-17 resolved: correction authority, original-acceptor notice, acceptance inheritance, producer designation, producer withdrawal, without self-approval through item identity | Sections 10.3, 10.4; GCR-49 to GCR-55 |
| AC3-04 | D-05b resolved: producer-owned versus another actor's item, with visibility of withdrawn own counter-evidence | Sections 10.1, 10.4, 10.6, 10.8; GCR-54, GCR-56 |
| AC3-05 | EK-OQ-04 / D-08 resolved for challenges, source-identified counter-evidence, bare contradicting claims, and bare contradicting inferences | Section 7.3; GCR-30, GCR-31 |
| AC3-06 | Reliance while exposure exists or a requirement is open, and who may authorize it | Sections 7.6, 9.2 (ground G2); GCR-33, GCR-42, GCR-43 |
| AC3-07 | Unanswered challenges cited in a decision basis: recorded, answered, escalated, covered by exception (the work package says "waived"; a challenge itself is never waived out of the record, only a stricter gate response rule is, Section 5.5), or accepted as residual | Sections 5.5, 6.6; GCR-17 |
| AC3-08 | Challenge lifecycle: target scope, basis, response, closure, escalation, unresolved visibility, without forcing consensus | Section 6; GCR-23 to GCR-29 |
| AC3-09 | Disagreement preserved visibly; whether conditional progression can occur under it | Sections 8.2, 8.5; GCR-36, GCR-38 |
| AC3-10 | Conditional progression distinguished from validation, ordinary acceptance, waiver or exception, and reliance under assumption | Sections 9.1, 9.3, 9.5; GCR-44, GCR-48 |
| AC3-11 | Revalidation closure authority for consequential decisions and non-decision dependents (EK-OQ-16) | Section 11.4; GCR-60, GCR-61 |
| AC3-12 | Validation authority for material hypotheses not tied to a consequential gate (EK-OQ-02) | Section 12.2; GCR-64 |
| AC3-13 | Disputed materiality and dependency redesignation (EK-OQ-07) | Section 7.7; GCR-34 |
| AC3-14 | Time and evidence-age effects (EK-OQ-10) | Section 13; GCR-67, GCR-68 |
| AC3-15 | Actor identity, collective identity, and delegation, to the extent needed | Section 4.6; GCR-07, GCR-08, GCR-09 |
| AC3-16 | Verification independence, or routing with a safe interim constraint | Section 4.9; GCR-10, GCR-11; GC-OQ-03 |
| AC3-17 | External evaluator outputs advisory unless authority is explicitly granted | Section 5.8; GCR-22; GCO-27 |
| AC3-18 | Objectively checkable conditions separated from contextual judgments at an initial level | Section 14 |
| AC3-19 | Undecided Architecture Declaration applying MW-ADAPT-001 | Section 15 (thirty-four declared choices) |
| AC3-20 | Declaration followed by Tech Lead or QA sampling before acceptance | Section 15.4 gives targets. Moderator-directed Tech Lead review sampled the declaration, found two issues, and the Development Team fixed both before acceptance (`mod-w/reviews/MODERATOR-REVIEW-STEP-03.md`). |
| AC3-21 | Open questions routed to STEP-04, STEP-05, STEP-06, pilot, or later work without duplicating ownership | Section 16 |
| AC3-22 | No implementation technology, schema language, storage model, transport, validator, workflow engine, lifecycle graph, or final state vocabulary selected | Sections 1.3, 5.6, 8.1, 15.5 |
| AC3-23 | Transferability evidence encountered is proposed under the research governance process | MW-OBS-015 in `research/mod-w-transferability/observations.md`; accepted by Moderator disposition on 2026-10-02 |
| AC3-24 | Final acceptance not recorded before Phase 3a, 3b, and 3c, or a Moderator waiver | Section 2.3. Phase 3b QA and Phase 3c Product Owner sign-off were waived by the Moderator before final acceptance. |

---

## 18. Change Notes

| Date | Version | Change | Reason |
| --- | --- | --- | --- |
| 2026-10-02 | 0.1 | Initial gate, challenge, disagreement, and revalidation semantics produced under STEP-03 | Third PROD-W product artifact; extends `prod-w/protocol-semantics.md` and `prod-w/evidence-knowledge-model.md` without modifying them. Thirty-four decisions beyond accepted upstream artifacts are declared in Section 15 under MW-ADAPT-001 and routed to the Tech Lead. One is a narrowing of an accepted STEP-02 reading (UAD3-12) and is flagged in Section 3.3. |
| 2026-10-02 | 0.1 | Accepted by MOD-W Moderator | Tech Lead review approved; Development Team work approved; Phase 3b QA and Phase 3c Product Owner sign-off waived before final acceptance. |

**Files changed in this delivery:**

- `prod-w/gate-challenge-revalidation-semantics.md` (added).
- `mod-w/domain-language.md`: a pending STEP-03 terms section appended. The accepted terms tables are untouched.
- `research/mod-w-transferability/observations.md`: MW-OBS-015 appended and accepted by Moderator disposition.

No accepted Product Definition, Architecture, STEP-01 deliverable, STEP-02 deliverable, or MOD-W template was modified. Moderator-owned status and review records were updated for STEP-03 acceptance. `prod-w/protocol-semantics.md` and `prod-w/evidence-knowledge-model.md` are unchanged.

**Acceptance status:** Accepted by MOD-W Moderator on 2026-10-02. See `mod-w/reviews/MODERATOR-REVIEW-STEP-03.md`.
