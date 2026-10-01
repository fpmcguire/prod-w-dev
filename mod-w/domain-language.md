---
artifact:
  type: domain-language
  version: 0.1
  created: 2026-09-30
  updated: 2026-10-02
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

## Terms Accepted from STEP-03

These terms were introduced by the Development Team while producing `prod-w/gate-challenge-revalidation-semantics.md` under STEP-03. They are accepted by MOD-W Moderator disposition recorded on 2026-10-02 in `mod-w/reviews/MODERATOR-REVIEW-STEP-03.md`. They remain in this provenance table rather than being merged into the main accepted table so their source step stays visible.

Several are load-bearing for STEP-04 to STEP-06: Accepted set, Standing item, Standing record, Conditional progression authorization, Exception, and Authority gap. Where STEP-03 states a more specific reading of an accepted STEP-02 term (Correction, Withdrawal, Revalidation requirement, Exposure), the accepted governing text is in the STEP-03 artifact (Sections 3.3, 4 to 12).

| Term | Definition | Use | Avoid |
| --- | --- | --- | --- |
| Accepted set | The items over which independence is evaluated for a consequential acceptance: the subject, the material basis followed transitively, the materiality and dependency designations, the challenge responses relied on, and the verification records relied on. | "The acceptor is a producer of no member of the accepted set." | Treating the decision record's own text as "the accepted item." |
| Acceptance-act content | What the acceptor itself contributes in making a determination: the determination, rationale, treatments, conditions, residual-risk statement, and independence declaration. Not production of the accepted set. | "The independence declaration is part of the acceptance-act content." | Using an acceptor's commitment to launder its own earlier recommendation. |
| Standing item | An item that has been validly accepted, or that belongs to the accepted set of a consequential acceptance or decision. | "A correction designation on a standing item needs independent confirmation." | Treating every cited item as standing. |
| Standing record | What is recorded against or around an acceptance's basis at the acceptance act: challenges, contradicting items, exposure, open requirements, reliance marks, earlier refusals and deferrals, and exceptions. | "Every item in the standing record is cited with a treatment." | Omitting opposition because it is unanswered. |
| Treatment | The recorded handling of a standing-record item at an acceptance: answered, conceded or withdrawn by the challenger, moot, accepted as residual, or covered by an exception. | "The challenge was accepted as residual." | Treating an unlisted or omitted item as handled. |
| Gate definition | The recorded definition of a gate before use: progression, scope, acceptor grants, acceptance rule, and the semantic slots. | "The gate definition predates the acceptance." | Amending the definition to fit a basis already refused. |
| Gate basis | The accepted set together with the standing record bearing on it. | "The gate basis includes the open challenges." | Treating the basis as only the favorable items. |
| Refusal | A gate authority holder's determination that sufficiency is not found for the basis as it stands. | "The gate was refused pending independent challenge." | Treating refusal as final or as invalidation. |
| Deferral | A gate authority holder's statement that no determination is made yet, naming what is awaited. | "Acceptance was deferred pending the response." | Treating elapsed time as converting a deferral into acceptance. |
| Conditional progression authorization | An explicit act by an independent human with gate authority to progress or rely while a named condition (unvalidated hypothesis or assumption, or an open revalidation requirement) stays unresolved and tracked. | "The pricing hypothesis is relied on under a conditional progression authorization." | Using it as validation, as ordinary acceptance, or as a waiver. |
| Reliance while open | A dependency mark showing reliance on an item that has an open revalidation requirement, authorized as conditional progression. | "The build decision is relied on while the requirement is open." | Relying silently on an item with an open requirement. |
| Exception | A dispensation, by an independent human with gate authority, from a specific unsatisfied gate requirement for a specific progression, visibly marked. Includes an override. | "The gate was accepted with an exception for the independent-challenge requirement." | Using an exception to cure invalid independence, or presenting it as ordinary conformance. |
| Accepted as residual | A treatment in which the acceptor judges the basis sufficient notwithstanding a named unresolved matter, with rationale and a visible marker. | "The decision was accepted with an unresolved feasibility challenge." | Treating it as an exception or as resolution. |
| Contestation | The visible fact that an item, relationship, or decision is under challenge or contradiction. | "The claim is contested by an unanswered challenge." | Treating contestation as a state name or as invalidation. |
| Challenge closure | The recorded ending of a challenge: challenger resolution, authority closure, or mootness by withdrawal of the target. A response never closes a challenge. | "The challenger recorded resolution." | Treating a producer's response, time, or silence as closure. |
| Escalation | The act of routing an unresolved matter to the authority able to resolve it. It resolves nothing itself. | "The disputed designation was escalated." | Treating escalation as a closure or a decision. |
| Resolving authority | The grant class and scope able to resolve a matter, with its independence condition, determined from grants and not role names. | "The resolving authority for a correction confirmation is a gate authority holder who produced neither item nor change." | Naming a role label as the resolver. |
| Authority gap | A visible condition in which no identity meeting the independence condition can fill the resolving authority for a matter. | "No independent holder exists, so the matter is an authority gap." | Curing it by a conflicted holder's act, a waiver, a collective identity, or time. |
| Reaffirmation | A determination that a dependent, as it now stands and is now supported, remains justified; an acceptance-type act, not validation. | "The decision was reaffirmed on its current basis." | Treating reaffirmation as a trigger or as truth. |
| Revision | A change to a dependent in light of revalidation reasons; a revision that changes meaning is a successor. | "The producer revised the inference." | Treating a producer's revision of a standing item as independent closure. |
| Retirement | A determination or act that a dependent is no longer relied on; it remains recorded. | "The claim was retired." | Deleting the item. |
| Assumption-rooted | Describing a basis item whose every support chain ends only in assumptions or unvalidated hypotheses, with no evidence item. | "The demand inference is assumption-rooted." | Reading a cited, traced chain as evidence-backed. |
| Collective identity | A team, organization, or agent fleet recorded as a producer with recorded membership; it expands to its members for independence. | "Team T is recorded as producer with its members listed." | Treating a collective as one identity for independence or as an acceptor. |
| Assignment | A recorded relation in which one actor assigns work to another. Provenance; conveys no authority. | "The Product Owner assigned the survey analysis to an agent." | Treating assignment as delegation of authority, or as making the assigner a producer without substance or adoption. |

---

## Naming Rules

- Use **protocol**, **schema**, and **state** only with their distinct meanings.
- Use **Product Moderator** only for the future PROD-W product role.
- Use **MOD-W Moderator** only for the human governing this `prod-w-dev` project.
- Use **evidence**, **inference**, **hypothesis**, **assumption**, and **decision** distinctly.
- Use **acceptance** for authorized sufficiency/approval, not for truth.
- Use **external evaluator** generically; do not make DeepPattern a required dependency.
