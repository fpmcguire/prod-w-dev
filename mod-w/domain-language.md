---
artifact:
  type: domain-language
  version: 0.1
  created: 2026-09-30
  updated: 2026-10-01
  status: Accepted
---

# PROD-W Domain Language

**Project:** PROD-W  
**Owner:** Tech Lead  
**Status:** Accepted

---

## Purpose

This file defines domain terms for PROD-W architecture and future implementation work. It is not itself the protocol specification.

Terms should remain stable across product definition, architecture, methodology, schemas, examples, and validation work unless a later accepted change updates this glossary.

---

## Governance Context

**This artifact is authored and reviewed under MOD-W v5.0.1 governance.** The MOD-W Moderator governs this `prod-w-dev` development project and is responsible for acceptance of this glossary.

Terms that describe future PROD-W roles or artifacts are product-domain definitions, not active authority grants inside `prod-w-dev`. In particular, the future Product Moderator role must not be treated as equivalent to the MOD-W Moderator.

---

## Terms

| Term | Definition | Use | Avoid |
| --- | --- | --- | --- |
| Protocol | Normative rules for roles, authority, permitted actions, constraints, gates, challenges, progression, and revalidation. | "Protocol semantics define who may accept a gate." | Treating protocol as a data schema. |
| Schema | Structural definition of valid data fields, types, and constraints. | "The evidence schema requires a source." | Treating schema validity as governance validity. |
| State | Current condition of a claim, artifact, evidence item, challenge, gate, decision, or work item. | "The claim is challenged." | Treating state as the whole protocol. |
| Actor | Identified human, agent, evaluator, or system performing an action. | "The actor produced the artifact." | Using role labels where identity is required. |
| Role | Defined responsibility or authority scope assigned to an actor. | "Product Moderator is a role." | Assuming role name alone proves authority. |
| Authority grant | Explicit permission for a role or actor to perform an action in a scope. | "Gate acceptance requires a human authority grant." | Silent or inherited authority. |
| Product Moderator | Human PROD-W role with consequential gate authority where explicitly assigned. | "The Product Moderator accepts or rejects a gate." | Confusing with the MOD-W Moderator governing `prod-w-dev`. |
| MOD-W Moderator | Human authority governing this development project and research record. | "The MOD-W Moderator accepts transferability observations." | Treating as a future PROD-W product role. |
| Claim | Statement that may require evidence, challenge, acceptance, or qualification. | "Small teams need evidence governance." | Treating every note as a material claim. |
| Material claim | Claim consequential enough to affect product direction, gate decisions, user promises, or investment. | "Material claims require provenance." | Applying equal weight to trivial statements. |
| Evidence | Source-linked information used to support, weaken, or contextualize a claim or decision. | "Interview notes are evidence." | Agent agreement without source evidence. |
| Counter-evidence | Evidence that contradicts, weakens, or complicates a claim, hypothesis, or inference. | "Failed customer interest is counter-evidence." | Burying negative findings in notes. |
| Assumption | Unverified proposition being relied on. | "Assumptions must remain visible." | Treating assumptions as facts. |
| Hypothesis | Testable proposition that can be validated, weakened, or rejected by evidence. | "A hypothesis needs validation criteria." | Calling untestable beliefs hypotheses. |
| Inference | Reasoned interpretation derived from cited evidence, assumptions, or other inferences. | "Evidence X and assumption Y suggest Z." | Presenting inference as observed fact or evidence. |
| Decision | Authorized commitment or selection among alternatives. | "Proceed to prototype is a decision." | Treating a recommendation as a decision. |
| Consequential decision | Decision that commits resources, validates a major claim, changes product direction, or authorizes progression through a gate. | "Go/build/no-build is consequential." | Allowing silent or agent-only acceptance. |
| Gate | Defined decision point requiring specified evidence, checks, challenge, or authority before progression. | "Commercial viability gate." | Generic milestone without governance meaning. |
| Challenge | Attributable act of questioning, testing, disputing, or seeking counter-evidence against an item, relationship, or decision. | "The validator challenged the customer claim." | Informal disagreement with no record. |
| Acceptance | Authorized determination that a defined artifact, evidence condition, or gate is sufficient for its stated scope. | "Gate acceptance is human-authorized where consequential." | Confusing acceptance with truth. |
| Disagreement | Visible unresolved conflict among claims, interpretations, evidence, or role judgments. | "Disagreement remains routable." | Forcing artificial consensus. |
| Provenance | Trace of source, author, time, evidence basis, review/challenge history, and acceptance history. | "Material claims retain provenance." | Anonymous or source-free assertion. |
| Dependency | Relationship showing that one claim, decision, or gate relies on another item. | "Decision D depends on evidence E." | Treating decisions as isolated. |
| Revalidation | Required reconsideration when material supporting evidence, assumptions, upstream claims, or dependencies change. | "Changed evidence triggers revalidation." | Silent continued validity. |
| Objectively checkable rule | Rule that can be mechanically validated from available records. | "Producer cannot be sole approver." | Automating contextual judgment. |
| Contextual judgment | Human decision requiring interpretation of sufficiency, risk, persuasion, or acceptability. | "Evidence is persuasive enough." | Pretending the validator can fully automate it. |
| External evaluator | Advisory actor or system that inspects, challenges, verifies, or produces findings without default gate authority. | "DeepPattern could be an evaluator implementation." | Treating evaluator findings as gate acceptance. |
| Representation adapter | Mapping from protocol semantics into a concrete document format, schema language, validator, prompt, or storage model. | "Markdown metadata may be an adapter." | Treating one adapter as the protocol. |

---

## Terms Accepted from STEP-01

These terms were introduced by the Development Team while producing `prod-w/protocol-semantics.md` under STEP-01. They are accepted by MOD-W Moderator disposition recorded on 2026-10-01 in `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`. They remain in this provenance table rather than being merged into the main accepted table so their source step stays visible.

| Term | Definition | Use | Avoid |
| --- | --- | --- | --- |
| Action | Attributable protocol event by which an actor changes the record, carrying actor identity, capacity, target, and time. | "Accepting a gate is an action." | Treating an unattributed record change as an action. |
| Authority class | One of the four separable kinds of authority: production, assessment/challenge, verification, and consequential gate acceptance. | "Verification is a distinct authority class." | Collapsing the classes into generic "permission". |
| Authority scope | Bounded set of items, artifact classes, or gates to which an authority grant applies. | "The grant's scope is the feasibility gate." | Treating a grant as unbounded. |
| Gate authority | Authority to perform consequential gate acceptance; human-only in PROD-W. | "Only a human actor holds gate authority." | Delegating gate authority to an agent or evaluator. |
| Participation capacity | The function in which an actor participated with respect to a specific item: producer, challenger/reviewer, verifier, or acceptor. | "The actor participated in the capacity of challenger." | Inferring capacity from a role label. |
| Producer | Actor recorded as having created or originated an item. | "Every artifact records its producer." | Treating authorship as authority over the item. |
| Independence | Property of an actor relationship in which the acting actor is not a recorded producer of the item acted upon, evaluated by actor identity. | "Acceptance requires an independent acceptor." | Inferring independence from a different role label. |
| Self-approval | Acceptance of an item by an actor who is a recorded producer of it; invalid under PROD-W. | "Self-approval invalidates the acceptance." | Treating self-approval as merely discouraged. |
| Verification | Confirmation that defined formal criteria were satisfied and required checks occurred. | "QA verified the formal criteria." | Using verification as a synonym for acceptance. |
| Advisory finding | Output of an actor lacking gate authority for the matter in question; informs acceptance without performing it. | "The evaluator produced an advisory finding." | Recording an advisory finding as a decision. |
| Producing configuration | Model, reasoning effort, harness, tooling, and instructions that produced an action; part of provenance, not of actor identity. | "The producing configuration is recorded with the action." | Treating a configuration change as a change of actor. |
| Controlled re-execution | Deliberate re-running of the same role on the same inputs under a different model, configuration, or agent instance, in order to compare outputs. | "Controlled re-execution surfaced findings the first pass missed." | Treating the second run as an independent reviewer or acceptor. |

---

## Terms Accepted from STEP-02

These terms were introduced by the Development Team while producing `prod-w/evidence-knowledge-model.md` under STEP-02. They are accepted by MOD-W Moderator disposition recorded on 2026-10-01 in `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`. They remain in this provenance table rather than being merged into the main accepted table so their source step stays visible.

Several STEP-02 terms are load-bearing for STEP-03, especially Validation, Invalidation, Material dependency, Correction, Supersession, Withdrawal, Revalidation trigger, Revalidation requirement, and Exposure. They are accepted as the STEP-02 vocabulary baseline; STEP-03 may revise them through a later accepted change if gate, challenge, disagreement, or revalidation semantics require it.

| Term | Definition | Use | Avoid |
| --- | --- | --- | --- |
| Knowledge item | Attributable, recorded unit belonging to exactly one knowledge class at a time. | "Every knowledge item records its producer." | Treating a generic note as a knowledge item without a class. |
| Negative finding | Evidence that a defined search, test, or attempt to observe something did not find or confirm it, or found the opposite; recorded with its attempt record. | "The failed competitor search is a negative finding with a stated scope." | Treating absence of discovered evidence as evidence without a recorded attempt. |
| Source | Where information came from; need not be an actor in the protocol. | "The interview subject is the source; the interviewer is the producer." | Confusing source with the actor that produced the evidence item. |
| Source lineage | Identification of the items an evidence item is derived from, making shared sources visible. | "Three articles share one lineage." | Counting items that share a source as independent sources. |
| Material dependency | Dependency whose upstream item, if changed, contradicted, or withdrawn, would put the dependent's standing in question. | "The decision has a material dependency on the demand claim." | Assuming every citation is material, or that a producer alone decides non-materiality of support for a consequential decision. |
| Reliance under assumption | Dependency on a hypothesis or assumption that remains unvalidated, authorized by an identified human as conditional progression. | "The plan relies on the pricing hypothesis under assumption." | Representing reliance as validation. |
| Validation | Recorded acceptance that a hypothesis's required evidence and challenge criteria are satisfied for a stated scope; acceptance of sufficiency, not truth. | "The hypothesis was validated for the pilot scope." | Using validation as a synonym for verification or truth. |
| Invalidation | Authorized determination that an item can no longer be relied on; distinct from being contested. | "The claim was invalidated after the retest." | Treating a challenge or counter-evidence as invalidation. |
| Withdrawal | Producer's retraction of its own item; the item remains recorded. | "The producer withdrew the claim." | Deleting or overwriting an item. |
| Supersession | Replacement of an item by another for purposes of reliance; the replaced item remains recorded. | "The revised finding supersedes the earlier one." | Treating a meaning-changing edit as a correction. |
| Correction | Change to an item that leaves its meaning unchanged, visible in history, and not a trigger. | "The typo was recorded as a correction." | Using correction for a change that alters meaning. |
| Revalidation trigger | Recorded event affecting an upstream item that, through a dependency, means a dependent item may no longer be justified. | "Recorded counter-evidence is a revalidation trigger." | Treating a trigger as the outcome of revalidation. |
| Revalidation requirement | Obligation created on a dependent item by a trigger, visible until an authorized actor reaffirms, revises, or retires it. | "The decision has an open revalidation requirement." | Treating silence or elapsed time as closing it. |
| Exposure | Visible fact that an item depends, directly or indirectly, on an item that is contested or has an open trigger or requirement. | "The go decision is exposed through the demand inference." | Treating exposure as a requirement, or as nothing. |
| Evaluative claim | Claim whose content is a value judgment, identified as such; not established by evidence or inference alone. | "That the product is desirable is an evaluative claim." | Presenting a value judgment as observation or inference. |

---

## Naming Rules

- Use **protocol**, **schema**, and **state** only with their distinct meanings.
- Use **Product Moderator** only for the future PROD-W product role.
- Use **MOD-W Moderator** only for the human governing this `prod-w-dev` project.
- Use **evidence**, **inference**, **hypothesis**, **assumption**, and **decision** distinctly.
- Use **acceptance** for authorized sufficiency/approval, not for truth.
- Use **external evaluator** generically; do not make DeepPattern a required dependency.
