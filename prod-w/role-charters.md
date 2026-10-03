---
artifact:
  type: methodology-role-charters
  id: PROD-W-RC
  version: 0.2
  created: 2026-10-04
  updated: 2026-10-04
  status: Draft - Development Team work product for STEP-06. Not reviewed. Not accepted.
  produced_by: Development Team
  produced_under: STEP-06
source:
  step: mod-w/step-06.md
  methodology_guidance: prod-w/methodology-guidance.md
  protocol_semantics: prod-w/protocol-semantics.md
  evidence_knowledge_model: prod-w/evidence-knowledge-model.md
  gate_challenge_revalidation_semantics: prod-w/gate-challenge-revalidation-semantics.md
  rule_judgment_boundary: prod-w/rule-judgment-boundary.md
  representation_options: prod-w/representation-options.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Role Charters

**Status:** Draft v0.2. Development Team work product for STEP-06. Not reviewed. Not accepted.
**Standing:** Methodology guidance. It is subordinate to the accepted protocol artifacts and revises none of them. If this document and an accepted artifact disagree, the accepted artifact governs and this document is wrong.

**Short names used for citations.** PS = `prod-w/protocol-semantics.md`. EK = `prod-w/evidence-knowledge-model.md`. GC = `prod-w/gate-challenge-revalidation-semantics.md`. RJ = `prod-w/rule-judgment-boundary.md`. RO = `prod-w/representation-options.md`. Rule IDs (PR-, EKR-, GCR-, CRC-, BDR-, HJC-) are unique to one artifact, so they are cited without the short name. Section numbers are always given with a short name.

---

## 1. What a Charter Is and Is Not

A charter is a plain-language description of the work a role position usually does, the authority it usually needs, and the traps that usually come with it. It helps a team assign work and notice problems.

**A charter confers nothing.** Authority comes only from a recorded authority grant (PR-01, PR-02). A name in this document, in a byline, or on a project chart is not a grant (PS §4.6). Two positions with the same name in different scopes are different authorities (PR-03).

**A charter is not a role catalog.** The accepted protocol requires exactly one thing of role structure: for each consequential gate, at least one human role position holds AUTH-G (PS §4.7). Everything else in this document is an illustrative composition of the four authority classes that a project may adopt, change, or ignore. Product Skeptic, Product Advocate, and similar positions are open research hypotheses, not accepted roles (PS §4.7). This document therefore describes the **challenge function** as something a project composes from AUTH-A, and does not treat "Skeptic" as a protocol role.

**Two Moderators.** "Product Moderator" in this document means the PROD-W product role, held by a human in a product project. It is not the MOD-W Moderator who governs `prod-w-dev`, and neither inherits the other's authority (PR-24). Nothing in this document grants authority in `prod-w-dev`.

---

## 2. Five Things That Are Kept Apart

The most common failure in practice is to let one of these five stand in for another. A project should be able to point at the separate record of each.

| Thing | What it is | What it is not | Where it is recorded (practice) |
| --- | --- | --- | --- |
| **Actor identity** | A stable, distinguishable identified participant: a human, an AI agent, an external evaluator, or an automated system (PS §4.1; PR-06, PR-07) | A role label, a tool or model name, a session, a byline (PR-07). A producing configuration (PR-27) | Establishment record and any later identity disclosure |
| **Role label / role position** | A name humans use for a bundle of grants and expectations within a scope (PS §4.2; PR-03) | A source of authority. Evidence of independence | The role charter entry for the project, naming the grants it relies on |
| **Authority grant** | Explicit, attributable, scoped permission with grantee, authority class, scope, and granting authority (PR-02) | Seniority, capability, participation, or an appointment that carries no grant | The establishing act for roots; each later conferral act |
| **Participation capacity** | What an actor *did* with respect to a specific item: producer, challenger/reviewer, verifier, or acceptor (PS §4.5; PR-08) | A permanent attribute of the actor. Something merged after the fact | On each act. One capacity per action |
| **Work assignment** | A recorded relation in which one actor assigns work to another. Provenance only (GC §4.6; RJ §10.2.5) | A delegation of authority. A grant-bearing appointment. Automatically production by the assigner | The assignment record, and the acceptor's independence declaration |

Three quick tests that catch most confusions:

1. **"Who is this, really?"** is an identity question. Answer with the actor identity, never the label.
2. **"Where did they get the right to do that?"** is a grant question. Answer with the grant and its chain to the establishing act (CRC-61), never the title.
3. **"What did they do to *this item*?"** is a capacity question. Answer per item, per act.

**Appointment versus assignment.** Appointing someone to a role position that carries grants *is a conferral* and is evaluated as one (RJ §10.2.5; CRC-61, CRC-62). Appointing someone to a role position that carries no grants is not a conferral. Assigning someone a piece of work is neither. Do not use the word "assign" for the first two without saying which is meant.

**Configuration is not identity.** Running the same role under a different model, harness, or instruction set is the same accountable actor (PR-27). Record the configuration as provenance. Do not record it as a new reviewer.

---

## 3. Charter Format

Every role position a project adopts is recorded with these entries. The template is `prod-w/templates.md` §2.

- Role position name (a convenience label).
- Actor(s) assigned, by actor identity, and actor kind as designated.
- Grants relied on: for each, class, scope, and the recorded act that conferred it.
- Participation capacities the position is expected to occupy.
- Items the actor has produced or materially influenced (this is what determines the independence limits below).
- Independence limits and known conflicts.
- Escalation route, stated as a grant class and scope (GC §8.4), with the identities holding it now.
- Fallback or substitute actor, if any, and the grant they would need.
- Whether the position may be combined with another, and the recorded limitation if so.

---

## 4. The Charters

Each charter has the same parts: purpose, typical grants, usual work, limits, independence traps, and small-team notes. "Typical" always means "illustrative of PS §4.7". A project records the grants it actually conferred.

### 4.1 Product Moderator

**Purpose.** Hold the consequential gates: decide, in an explicit attributable human act, whether the basis is sufficient for a stated progression.

**Typical grants.** AUTH-G for named gates. Often also AUTH-A (PS §4.7). Possibly the project's gate-definition scope, a validation scope, or a conferral scope, each a *separate* scope of AUTH-G that must be recorded to exist (GC §5.2, §12.2; RJ §10.2.1). One of them does not imply another (PR-04).

**Usual work.**

- Define gates before they are used (GCR-12), when holding the gate-definition scope.
- Accept, refuse, or defer a gate; authorize conditional progression; record exceptions; accept as residual; close challenges by authority closure; reaffirm or retire dependents (GC §5.6, §6.3, §11.4).
- Name and resolve role conflicts where the gate definition designates the position for it (GC §8.4).
- Review standing record and treat each item before accepting (GCR-17).

**Limits.**

- Human only, an individual identity. Not an AI agent, an evaluator, a collective, or a team (PR-05; GCR-08).
- Acts only within the scope of the grant. Authority for one gate does not carry to another (PR-04; INV-09).
- Cannot perform any favorable act over a set of which the holder is a producer (GCR-05). Conservative acts (refusal, deferral, escalation, request for revalidation, challenge, withdrawal or retirement of own item) remain open to the holder.
- Cannot waive independence, human authorization, citation of the standing record, visibility of the exception, the decision record's identification of its nature, or the FR-7 conditions (GC §9.4; GCR-46).

**Independence traps.**

- Drafting the opportunity statement, a recommendation the holder later adopts as a decision, or a materiality designation that keeps something out of the accepted set makes the holder a producer of the accepted set (GCR-02, GCR-03). No contribution is too small to count (GCR-03).
- "I only edited it" and "I only assigned it" are claims about substance, which must be disclosed (GCR-09; GC §4.6). Supplying the conclusion, or adopting or signing an item as one's own, makes the assigner a producer.
- Accepting under a second role label is still self-approval (PR-17; INV-02).

**Small-team notes.** A founder who is both Product Owner and the only AUTH-G holder cannot validly accept anything the founder produced. See guidance §6 (independence practice) and §14 (authority gaps).

### 4.2 Product Owner / Product Researcher

**Purpose.** Frame the opportunity, record claims, gather evidence and counter-evidence, state assumptions and hypotheses, draw inferences, and recommend.

**Typical grants.** AUTH-P, and often AUTH-A (PS §4.7).

**Usual work.**

- Create claims; designate materiality (a recorded judgment, EKJ-01); attach evidence and counter-evidence; record assumptions, hypotheses with validation criteria, and inferences (ACT-01, ACT-02; EKR-21 to EKR-23).
- Record every contradicting item the Owner has obtained, whether or not it favors the Owner's claim (EKR-18).
- Respond to challenges; revise or withdraw own items (GC §6.2, §10).
- Record recommendations. A recommendation by an actor without AUTH-G is a recommendation, not a decision (ACT-07; INV-16).

**Limits.**

- Cannot determine that its own output is sufficient, and cannot accept any gate (PS §4.4).
- A response never closes a challenge (GCR-25). A Tier 2 revision closes a requirement only as producer-addressed (GCR-61).
- Cannot treat agent agreement as corroboration (PR-20; EKR-17).

**Independence traps.** By definition the main producer of the accepted set. Plan for acceptance by someone else from the start. Delegating drafting to an agent does not remove the Owner as a producer if the Owner supplied the conclusions or adopted the output (GC §4.6).

**Small-team notes.** In a team of one, the Owner's job is to make the opposition as visible as the support, so that an independent gate authority holder can decide quickly when one becomes available.

### 4.3 Challenger (challenge function)

**Purpose.** Look for what the producers did not: counter-evidence, weak inference, mis-classification, missing dependencies, authority and independence defects, and omissions from the basis.

**Not a protocol role.** The challenge function is composed from AUTH-A (PS §4.4, §4.7). Any actor holding AUTH-A may raise a challenge, including AI agents and external evaluators (GCR-24). A project that wants a named "Skeptic" position may create one as a role position over AUTH-A, and records that this is a project convention.

**Typical grants.** AUTH-A for the relevant scopes.

**Usual work.**

- Raise challenges with challenger, target, target scope, and basis (GCR-23). A challenge missing target or basis is recorded as invalid and does nothing.
- Attach counter-evidence with the same elements as supporting evidence (EKR-15).
- Request revalidation with a stated basis, including on age-of-evidence grounds (ACT-06; GCR-32; GC §13.2).
- Escalate (GC §8.4).
- Record challenger resolution when satisfied. That is the challenger's own act and closes only that challenge (GC §6.3).

**Limits.**

- Cannot accept, refuse, defer, close as sufficiently answered, or waive (PS §4.4; GCR-22).
- A challenge has no veto. It is cheap by design. Its control is effect and treatment at the gate (GC §6.1, §5.5).
- A producer who challenges its own item is recorded but is not independent (PR-19; GCR-24).

**Independence traps.**

- Challenger independence from the *challenged item's producers* is what satisfies a gate's independent-challenge requirement (CRC-12). A challenge by a producer does not.
- A challenger who resolves a challenge against a set of which that challenger is a producer is performing a favorable act, which the protocol does not allow (GCR-05; RJ §10.6).

**Small-team notes.** Self-challenge is useful as issue discovery and is recorded. It never counts as the independent challenge a gate requires. See guidance §6.

### 4.4 Product Architect / Tech Lead

**Purpose.** Assess feasibility, constraints, and technical risk, and keep technical feasibility distinct from commercial viability (WD-3; EK §7.3).

**Typical grants.** AUTH-P and AUTH-A for technical scopes (PS §4.7). AUTH-V only if explicitly conferred. AUTH-G for a technical-feasibility gate only if conferred, and then only for that scope (INV-09).

**Usual work.**

- Produce feasibility evidence with basis and limitations stated. Distinguish a prototype working from a product being viable.
- Challenge hidden implementation assumptions in product claims.
- Where holding a narrow validation scope, validate technical hypotheses for a stated scope (GCR-64) provided independent over the validation's accepted set.

**Independence traps.** A Tech Lead who produced the feasibility analysis cannot accept a gate whose accepted set contains it. A Tech Lead who recommended an architecture and then accepts the decision to adopt it has accepted a set it produced (GCR-02).

### 4.5 Implementation Team

**Purpose.** Build what a gate has authorized, and report back what the building showed.

**Typical grants.** AUTH-P (PS §4.7).

**Usual work.**

- Produce artifacts and evidence from implementation work, with producing configuration recorded where AI agents are used (CRC-39).
- Record findings that bear on earlier claims as counter-evidence or as triggers for revalidation (EKR-18; GC §7).

**Limits.** Building under a conditional progression authorization does not validate what was assumed. Dependents carry the reliance mark (GCR-44). Work under way is not halted by the protocol, but *recorded reliance* in gates and commitments is governed (GC §7.6).

### 4.6 QA / Validator

**Purpose.** Confirm that defined formal criteria were checked, and record formal-check results.

**Typical grants.** AUTH-V, often AUTH-A (PS §4.7). AUTH-V may be held by a non-human actor, bounded by decidability (RJ §10.3.1; CRC-15).

**Usual work.**

- Perform and record verification against named criteria (ACT-04). A verification that names no criteria is not a verification (PS §5.3).
- Record formal-check results and findings with the required content (rule, evaluation point, elements examined; CRC-59). See guidance §11.
- Raise revalidation requests (ACT-06).

**Limits.**

- Verification is bounded by its criteria. It is not a sufficiency judgment and never substitutes for acceptance (PR-14).
- A producer's self-verification is recorded and does not satisfy a required check (GCR-10; CRC-13).
- A non-human verifier on an interpretive criterion produces an advisory finding (GCR-11; CRC-15).

**Independence traps.** The acceptor cannot be the verifier whose check it relies on (CRC-07). QA that wrote the template and then checks against it is a producer of the thing checked.

### 4.7 External Evaluator

**Purpose.** Provide an outside view: challenges, counter-evidence, conformance observations, specialist review.

**Typical grants.** None by default. AUTH-A, sometimes AUTH-V (PS §4.7). Never AUTH-G by default (PR-22).

**Usual work.** Challenge, attach sourced counter-evidence, verify within CRC-13 and CRC-15, request revalidation, respond, escalate (GC §5.8).

**Limits.** Findings are advisory. An evaluator never accepts, refuses, defers, authorizes conditional progression, waives, confirms a correction, closes a challenge, reaffirms, or invalidates (GCR-22). Being external, automated, persuasive, independent, or repeated does not change this.

**Practice caution.** "External" does not mean "independent of the accepted set". Independence is evaluated on identity, and substantive independence is a judgment (HJC-12). An evaluator running on the same model family as the producing agents is a separate identity but may share blind spots; record that limit (PR-27; RO §9.5 item 6).

### 4.8 Establishing Identity (a function, not a standing role)

**Purpose.** Perform the single establishing act of a project.

**What this is.** The one human who records the establishing act (CRC-61; D10). After that act the establishing identity has only what the act granted it, and nothing in particular because it was first. The identity may be a root grantee only in the act's own grants, so a founder who needs any authority for themselves must put it in the act (D10; RJ §10.2.2).

**Practice.** See guidance §4. The establishing identity's legitimacy is not checked by anything (HJC-22). A project should state, in the establishment record, why the identity had standing to establish it. A statement is an assertion that can be challenged. It is not proof.

---

## 5. Who Holds the Scopes (DM-02)

DM-02 asks who holds gate-definition, validation, and conferral scopes. The protocol requires that these are *recorded scopes of AUTH-G* held by humans (GC §5.2, §12.2; RJ §10.2.1). It does not say who should hold them. This section gives practice suggestions. It does not make them rules.

### 5.1 Scopes to decide at establishment

| Scope | What it lets the holder do | Practice suggestion |
| --- | --- | --- |
| **Gate acceptance** (per gate or gate class) | Accept, refuse, defer, authorize conditional progression, grant exceptions for that gate | Prefer a holder who is *not* the main producer for that gate's basis. Name more than one holder where the team allows. |
| **Gate definition** | Define and amend gate definitions | Give to a human who is unlikely to produce the basis. A definition is the standard applied, not the item accepted (GC §4.3), but GCR-13 limits post-refusal amendment, so the holder's identity matters less than the discipline of writing definitions before use. |
| **Validation** (per dimension or hypothesis family) | Validate material hypotheses for a stated scope (GCR-64) | Grant narrowly (for example, one evaluation dimension) to the person closest to that dimension *who did not produce the evidence*. Narrow grants are the protocol's own answer to acceptance burden (GC §12.2). |
| **Conferral** (per class and scope) | Confer grants, appoint to grant-bearing positions, revoke and narrow within the covered scope | Keep as small as the team can. Conferral power is the power to change who may accept. Hold it where its use would be least conflicted and most visible. A conferral by a conflicted holder is flagged and escalation-eligible (CRC-64). |
| **Closure authority** (challenges, requirements) | Authority closure and reaffirmation | Same as gate acceptance for the same scope. Spread across at least two holders where possible so one holder's conflict does not create an authority gap. |

### 5.2 Suggested shapes by team size

These are illustrative. They illustrate what is *possible*, not what is allowed or recommended.

| Team | Possible shape | What it does not give you |
| --- | --- | --- |
| **One human plus AI agents** | The human is establishing identity and holds every root grant. Agents hold AUTH-P, AUTH-A, and possibly bounded AUTH-V. | Any valid consequential acceptance of items the human produced or supplied substance to. Agent review is not independent (PR-27, PR-28). See guidance §6.4. |
| **Two humans plus AI agents** | One human (A) is Owner and holds production grants. The other (B) holds AUTH-G for the gates and is not a producer of their bases. B is named in the establishing act. | Anything where B produced the basis. B cannot accept B's own work. For B's work, A is the only possible acceptor, and A must not have produced it. |
| **Three or more humans** | Separate producers, a challenge function, a verifier, and at least two AUTH-G holders with disjoint production sets. | Freedom from authority gaps in every case. A gap can still arise when all holders contributed to a basis. |

---

## 6. Combining Roles

A project may combine roles for one actor. The combination must be recorded so that independence can be evaluated. Practical rules:

1. **Record the combination, not the label.** "Alex holds AUTH-P and AUTH-A for Discovery scope, and AUTH-G for Discovery gate" is a statement about grants. "Alex is Owner and Moderator" is not.
2. **Combinations restrict, not expand.** Holding AUTH-G and AUTH-P together means the holder can accept only what they did not produce (PR-16). Combining never gives the holder any ability to accept their own work.
3. **A combination that makes a gate unfillable is an authority gap**, and is recorded as one (GC §8.6). Do not hide it behind an acceptor who is a producer.
4. **Nothing is gained by splitting a person across identities.** Two accounts for one person is a substantive-independence failure (HJC-12) that the acceptor's independence declaration exists to surface (GCR-09).

---

## 7. Independence Declaration Practice

Every consequential acceptance carries an independence declaration (GCR-09; CRC-11). Presence is checked. Truth is not, so the declaration is only as good as the acceptor's care.

**Practice.** Before accepting, the acceptor works through, and records the answer to, these questions:

1. Did I, or any identity I control, create, edit, restate, summarize, rename, or adopt any item in the accepted set?
2. Did I supply the substance (the conclusion or key content) of any item, even where someone or something else typed it?
3. Did I assign any item in the accepted set to another actor? If so, to whom, and did I specify its conclusions?
4. Did I record any materiality designation, dependency link, or non-material designation that shapes the basis?
5. Did I perform any verification that I am relying on?
6. Did I confer any grant that a favorable act in this set relies on, at any link of the chain (CRC-64)?
7. Is there any relationship between me and a producer, or between me and the matter, that a reasonable reviewer would want to know about, even if it is not production?

The declaration states "I know of none" or lists what was found. It is an assertion and can be challenged. It is never proof of independence (GCR-09). Template: `prod-w/templates.md` §16.

---

## 8. Escalation Routes by Role

Any actor holding AUTH-A, AUTH-P, AUTH-V, or AUTH-G may escalate (GC §8.4). The route is derived from grants (GC §8.4 table). Role positions in practice:

| If the matter is... | The route runs to... | Typical position |
| --- | --- | --- |
| A challenge against an item or determination | Challenger resolution, or a gate authority holder independent of the challenged item's accepted set | Product Moderator, if independent |
| A disputed producer attribution | A gate authority holder independent of the disputed item | Product Moderator or other AUTH-G holder |
| A disputed materiality designation | A gate authority holder independent of the designation, item, and dependent | As above |
| An open revalidation requirement | By tier (GC §11.4) | Tier 1: independent AUTH-G for a fresh acceptance. Tier 2: AUTH-G who produced neither the dependent nor its basis closure |
| A refused or deferred gate | Another gate authority holder for the gate, or the role-conflict position the gate definition designates | As designated |
| Conflicting determinations by gate authority holders | The position the gate definition designates. If none, an authority gap | As designated, or none |
| Insufficient evidence | Producers gather more. A gate authority holder defers | Owner and Moderator |

An escalation records its elements (GCR-37) and **resolves nothing**. It stays visible until the addressee records a determination. Time does not act (GCR-41).

---

## 9. Change Notes

| Date | Version | Change | Reason |
| --- | --- | --- | --- |
| 2026-10-04 | 0.1 | Initial draft | STEP-06 Development Team work product |
| 2026-10-04 | 0.2 | Rewritten against the accepted artifacts. Removed "Product Skeptic" as a role and replaced it with a challenge function composed from AUTH-A (PS §4.7). Added the five-things table, DM-02 scope guidance, independence-declaration practice, and escalation routes. Corrected authority statements to match PS §4.7, GC §5.2, §11.4, and RJ §10.2. | Draft v0.1 misstated accepted semantics in several places |

MOD-W v5.0.1
