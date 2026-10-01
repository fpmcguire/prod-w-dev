---
artifact:
  type: research-register
  kind: observations
  version: 0.1
  created: 2026-09-30
  updated: 2026-10-01
  evidence_as_of: 2026-10-01
context:
  project: prod-w-dev
  status: research
  governed_by: MOD-W Moderator
---

# MOD-W Transferability Observations Register

This file records accepted and pending observations about how MOD-W v5.0.1 behaves when used to develop PROD-W, a methodology/protocol rather than a conventional software application.

Observations are maintained chronologically and are identified by ID: `MW-OBS-001`, `MW-OBS-002`, etc.

Each observation is preserved in its original form. Later evidence may refine interpretation or disposition, but the observation itself is not rewritten.

**Path relocation note (2026-09-30):** Early accepted observations refer to architecture-planning artifacts at `prod-w/architecture.md`, `prod-w/domain-language.md`, `prod-w/roadmap.md`, and `prod-w/step-01.md` because that was their location when the observations were recorded. Those MOD-W governance artifacts have since been relocated to `mod-w/architecture.md`, `mod-w/domain-language.md`, `mod-w/roadmap.md`, and `mod-w/step-01.md`; `prod-w/` is reserved for concrete PROD-W product artifacts.

**See `README.md` for governance rules and classification definitions.**

---

## MW-OBS-001 — Product Definition Concept Transfers Naturally

**Date:** 2026-09-30  
**MOD-W area:** Product Definition phase and artifact  
**Project stage:** Product Definition draft review (pre-acceptance)  
**Observed by role:** Moderator  
**Classification:** `TRANSFERS_UNCHANGED`  
**Status:** Accepted  
**Significance:** Medium

### MOD-W Mechanism or Assumption

MOD-W uses a Product Definition artifact early in the workflow to establish what problem the product solves, who the primary users are, what the product delivers, and what success looks like. The Product Definition is authored by the Product Owner and reviewed by the Moderator for coherence, evidence, and appropriate scope before proceeding to architecture.

The underlying assumption is that clarity about what you're building is prior to how you build it, and that an independent review catches gaps or premature conclusions.

### Observation

The initial draft of `mod-w/product.md` successfully used MOD-W's Product Definition structure to define PROD-W even though the product is a protocol/methodology rather than executable application software. The document identified:

- A concrete problem statement (governance gap in AI-assisted product development)
- Primary user roles (Product Owner, Moderator, Tech Lead, Development Team, QA in the context of AI-assisted work)
- Core output (machine-readable protocol specification with supporting guidance)
- Scope boundaries (methodology/protocol vs. complete AI agent framework)
- Success criteria and acceptance gates (evidence quality, human oversight, avoidance of unjustified confidence)
- Assumptions to evaluate (MOD-W transferability itself)

### Evidence

- Repository file: `mod-w/product.md`
- MOD-W template reference: `mod-w/templates/PRODUCT.md`
- Product Definition was structured using MOD-W's prescribed sections and information architecture
- The non-software nature (protocol definition vs. software delivery) did not prevent meaningful use of the Product Definition framework

### Effect on Work

- No friction or reinterpretation was required to apply MOD-W's Product Definition structure
- Moderator review of the Product Definition proceeded using normal MOD-W gates
- Moderator identified content gaps (e.g., premature requirement hardening) using MOD-W review criteria
- The Product Definition accurately captured scope and constraints for a methodology-development project

### Local Adaptation Required

None

### Interpretation

This is evidence that MOD-W's Product Definition concept may be **domain-neutral or at least transferable** to knowledge-development and methodology contexts. The underlying idea—that clarity about what you're building is prior to decisions about how to build it—appears to apply whether the artifact is software or protocol.

This observation does **not** tell us whether later MOD-W phases (architecture, implementation, review, testing) transfer similarly.

### Follow-up

- Observe how architecture work applies to protocol specification
- Observe how "implementation" translates to normative protocol artifacts
- Observe how review and QA work apply to protocol correctness and completeness
- Determine whether role definitions and approval gates remain coherent throughout

### Moderator Disposition

**Accepted.** Evidence is concrete and classification is proportionate to a single phase. Interpretation appropriately limited.

---

## MW-OBS-002 — Moderator Independent Review Catches Premature Requirement Hardening

**Date:** 2026-09-30  
**MOD-W area:** Moderator review gate on Product Definition  
**Project stage:** Product Definition draft review (pre-acceptance)  
**Observed by role:** Moderator  
**Classification:** `TRANSFERS_UNCHANGED`  
**Status:** Accepted  
**Significance:** Medium

### MOD-W Mechanism or Assumption

MOD-W requires that a Product Definition draft authored by the Product Owner be independently reviewed by a Moderator (and in some cases other roles) before proceeding. The Moderator review is designed to catch gaps, unsupported claims, premature hardening of requirements, and insufficient evidence before work proceeds on an unstable foundation.

### Observation

In the initial Product Definition draft, the Product Owner proposed several mechanisms as firm requirements or protocol mechanics before sufficient evidence, design iteration, or Moderator review existed. Examples include:

- Explicit workflow-state commitments (e.g., specific evidence-sufficiency criteria hardcoded as state transitions)
- Enforcement assumptions (e.g., "the protocol must prevent conversion of weak evidence into requirements")
- Lifecycle sequence assumptions (e.g., predetermined phase ordering without flexibility for research feedback)
- Authority role assignments (e.g., who can mark evidence as sufficient) without evaluating alternative role boundaries
- Automated enforceability mechanisms that assumed the protocol could be mechanically validated

The Moderator review process identified these premature mechanizations before Product Definition acceptance. Subsequent Product Owner revision deferred mechanism definition to later stages (roadmap, design, implementation) where sufficient evidence and design thinking can inform the choices.

### Evidence

- Product Definition review comments in project records
- Content changes between draft and revised versions of `mod-w/product.md`
- Moderator feedback that applied standard MOD-W gate criteria (distinguishing problem statement from solution, evidence from assumption, scope from implementation)
- Pattern: Product Owner attempted to solve the "how" in the "what" phase

### Effect on Work

- Prevented premature convergence on protocol mechanics
- Preserved design space for later architecture phase
- Clarified that Product Definition should establish success criteria, not enforce a particular mechanism
- Moderator review was necessary; Product Owner self-review would not have caught the conflation
- Delay was minimal (revisions occurred before formal acceptance gate)

### Local Adaptation Required

None

### Interpretation

This is evidence that **MOD-W's separation between Product Owner proposal and Moderator independent review remains useful in a methodology/protocol-development context.**

The role boundary—between the person closest to the problem (Product Owner) and an independent reviewer (Moderator)—appears to serve the same function in both software and non-software contexts: catching unsupported leaps from problem to solution.

This observation specifically validates the **independence and timing of the review**, not the entire MOD-W role set or later phases.

### Follow-up

- Observe whether Moderator review remains valuable at later gates (architecture, implementation, acceptance)
- Determine whether this role boundary pattern applies to other MOD-W role pairs (e.g., Tech Lead -> QA review)
- Evaluate whether the problem-solution conflation tendency is domain-specific or a general product-development risk

### Moderator Disposition

**Accepted.** Evidence is concrete and tied to actual project events. Classification appropriately limited to the review gate, not extrapolated to entire MOD-W structure.

---

## MW-OBS-003 — Software-Specific Terminology Already Identified for Future Observation

**Date:** 2026-09-30  
**MOD-W area:** Multiple (Development Team role, Tech Lead responsibilities, QA/testing, CI/build, architecture, implementation semantics)  
**Project stage:** Product Definition pre-acceptance  
**Observed by role:** Moderator (in consultation with Product Owner)  
**Classification:** `NOT_YET_TESTED`  
**Status:** Accepted  
**Significance:** Medium (as a tracking mechanism)

### MOD-W Mechanism or Assumption

MOD-W defines several roles and responsibilities with terminology and assumptions that are evidently tied to software development:

- **Development Team:** described as a code-producing role; artifacts assumed to be executable code
- **Tech Lead:** responsibilities include code review, architecture review, and technical approval of implementation
- **QA:** testing responsibilities tied to runtime behavior, build gates, and CI pipelines
- **Architecture:** terminology often assumes deployed software components and runtime interactions
- **Implementation:** equated with code writing, followed by testing against running systems
- **Acceptance:** gates often involve build success, deployment, and runtime verification

### Observation

The Product Definition acknowledges that developing PROD-W (a protocol/methodology) requires observing whether these software-centric mechanisms transfer or require reinterpretation in a knowledge-development context. The Product Definition explicitly lists areas for future observation:

- Development Team as code-producing role (PROD-W produces specification, schemas, and guidance prose, not executable code)
- Tech Lead code review (architecture review of protocol definitions and schemas?)
- QA/testing assumptions (how to validate protocol correctness and completeness?)
- Build/runtime acceptance (what validation gates make sense for protocol artifacts?)
- CI/build-gate assumptions (what continuous integration means for a non-software product?)
- Architecture terminology and concepts (do architectural patterns apply to protocol design?)
- Implementation semantics (does "implementation" mean writing the protocol spec, or implementing it in real projects?)

These observations are **recorded in `mod-w/product.md` as explicit research questions, not as failures**.

### Evidence

- Product Definition section on experimental research goals (see `mod-w/product.md`)
- MOD-W templates under `mod-w/templates/` that use software-centric terminology and examples
- Product Definition explicitly acknowledges that MOD-W was designed for software development
- Research note `research/topics/mod-w-protocol-refactor-hypotheses.md` lists similar terminology concerns

### Effect on Work

- No current effect; these are identified as open questions
- Project is prepared to observe these areas systematically as work proceeds through later MOD-W phases
- This observation prevents treating software-centric terminology as automatic transferability evidence
- Moderator is alerted to watch for terminology drift or forced reinterpretation later

### Local Adaptation Required

None at this stage

### Interpretation

This observation is **NOT** evidence of transferability failure or success. It is evidence that the project recognizes which MOD-W mechanisms are potentially software-coupled and has committed to observing them during the experiment.

**Important distinction:** Identifying a potential domain-coupling issue is not the same as confirming one. The terminology may transfer with minor reinterpretation (see MW-OBS-001 approach), or it may reveal genuine domain coupling. Evidence is insufficient at this stage.

### Follow-up

- Architecture phase: observe how MOD-W architecture concepts and terminology apply to protocol design
- Implementation phase: observe how "implementation" is actually performed and whether Tech Lead code review semantics transfer
- QA/testing phase: observe what validation gates emerge for protocol correctness and how they relate to MOD-W's testing assumptions
- Each phase should produce specific observations (MW-OBS-004, MW-OBS-005, etc.) that replace this placeholder with concrete evidence

### Moderator Disposition

**Accepted as a tracking mechanism.** Classification as `NOT_YET_TESTED` is appropriate. This is a registered research question, not a confirmed finding. Do not allow this observation to be treated as evidence of domain coupling without subsequent concrete observations.

---

## MW-OBS-004 - Architecture Concepts Transfer with Reinterpretation to Protocol Development

**Date:** 2026-09-30  
**MOD-W area:** Architecture phase and Tech Lead responsibilities  
**Project stage:** Architecture planning after Product Definition acceptance  
**Observed by role:** Tech Lead  
**Classification:** `TRANSFERS_WITH_REINTERPRETATION`  
**Status:** Accepted  
**Significance:** Medium

### MOD-W Mechanism or Assumption

MOD-W expects the Tech Lead to produce architecture artifacts that map requirements to decisions, define system structure, record architectural decisions, and guide later implementation.

The canonical templates are software-oriented in places, including sections such as technology stack, components, data flow, implementation files, and tests.

### Observation

During the first PROD-W architecture-planning phase, the architecture mechanism remained useful, but the meaning of "architecture" had to be interpreted around protocol and methodology boundaries rather than runtime software components.

The resulting architecture draft focuses on:

- normative protocol semantics
- distinction among protocol, schema, and state
- authority boundaries
- provenance and dependency concepts
- machine-checkable governance versus contextual human judgment
- staging product artifacts under `prod-w/`

The phase did not require changing canonical MOD-W templates, but the template concepts could not be applied literally as software architecture. Sections such as technology stack and data flow were replaced with semantic components and conceptual flow.

### Evidence

- `mod-w/templates/ARCHITECTURE.md`
- `prod-w/architecture.md`
- `prod-w/domain-language.md`
- `prod-w/roadmap.md`
- `prod-w/step-01.md`
- Accepted Product Definition: `mod-w/product.md`

### Effect on Work

- Tech Lead architecture work proceeded meaningfully without implementation.
- The architecture artifact could map requirements to decisions.
- The useful architectural unit was a governance/domain boundary rather than a deployable software component.
- No local MOD-W adaptation was necessary yet, but terminology required careful interpretation.

### Local Adaptation Required

None proposed at this time.

### Interpretation

This is evidence that MOD-W's architecture phase may transfer to protocol/methodology development when "architecture" is interpreted as the structure of normative semantics, authority, artifacts, and validation boundaries.

The evidence is mixed-positive: the phase transferred, but not literally as software architecture.

### Follow-up

- Moderator should determine whether the proposed classification is appropriate.
- Later implementation and QA phases should test whether reinterpretation remains lightweight or becomes a local adaptation need.
- Watch whether roadmap and step artifacts continue to work cleanly for normative specification deliverables.

### Moderator Disposition

**Accepted.** Evidence is concrete and grounded in specific artifacts. Classification as `TRANSFERS_WITH_REINTERPRETATION` is proportionate: the mechanism transferred, but required semantic reframing rather than tool change. This sets a baseline for observing whether later phases (implementation, QA) require additional adaptation.

---

## MW-OBS-005 - Domain Language Patterns Support Consistent Semantic Boundaries

**Date:** 2026-09-30  
**MOD-W area:** Documentation and terminology governance  
**Project stage:** Architecture planning (parallel to STEP-01 planning)  
**Observed by role:** Moderator  
**Classification:** `TRANSFERS_UNCHANGED`  
**Status:** Accepted  
**Significance:** Medium

### MOD-W Mechanism or Assumption

MOD-W expects roles (Product Owner, Tech Lead, Development Team, QA, Moderator) to have distinct responsibilities and authority. Clear terminology about concepts such as evidence, decision, assumption, claim, and gate is necessary to prevent role confusion and weak governance.

In software contexts, this is often supported by implementation tools (version control, code review systems, build gates) that make role boundaries and decision provenance mechanically visible.

In a protocol/methodology context, these tools may not apply literally. Terminology and documentation conventions must carry more of the responsibility for clarity.

### Observation

The domain language artifact produced during architecture planning (`prod-w/domain-language.md`) establishes working definitions for governance concepts with explicit "use" and "avoid" statements. The language preserves MOD-W's core semantic boundaries:

- **Actor, Role, Authority Grant** are defined separately, not collapsed into role-name shorthand
- **Claim, Evidence, Assumption, Hypothesis, Inference, Decision** remain distinct with operational definitions
- **Protocol, Schema, State** are explicitly separated as per architectural decision D2
- **MOD-W Moderator and Product Moderator** are disambiguated to prevent role confusion
- **Acceptance** is defined as authorized sufficiency judgment, not truth determination
- **External evaluator** is generalized, preventing premature dependency on specific tools

This terminology infrastructure enables consistent governance discourse across documentation, step planning, implementation guidance, and later reviews.

### Evidence

- `prod-w/domain-language.md` with operational definitions and naming rules
- Architecture mapping (D1-D4) between requirements and decisions, using consistent terminology
- Absence of shorthand role references or colloquial substitutions in architecture prose
- Explicit "avoid" patterns in domain language prevent common conflations (e.g., "role name proves authority")

### Effect on Work

- Domain language definitions will guide Development Team writing during STEP-01 and later steps
- Moderator review and acceptance will be able to reference specific terminology standards
- Implementation team and QA can use glossary entries to flag terminology drift
- Terminology consistency reduces risk of silent protocol misunderstanding (e.g., confusing authority grant with role assignment)

### Local Adaptation Required

None

### Interpretation

This is evidence that **MOD-W's use of clear, documented terminology for governance concepts transfers directly to protocol/methodology development.** The glossary serves the same role in both contexts: making role boundaries and conceptual distinctions explicit so that procedures can rely on them.

The mechanism is not software-specific; it is a general best practice for complex governance systems.

### Follow-up

- Monitor whether domain language definitions remain stable through implementation phases
- Observe whether developers consistently use terminology as defined, or whether colloquial drift occurs
- If drift occurs, determine whether it reflects inadequate guidance or genuine need for terminology change
- Assess whether domain language should be embedded in tooling/validators later (e.g., as metadata annotation guidance)

### Moderator Disposition

**Accepted.** Terminology governance is a lightweight, transferable mechanism. The evidence base is clear (the artifact exists and is well-structured). This provides a foundation for ensuring role boundaries and semantic clarity remain enforced throughout the project without requiring tool-specific mechanisms.

---

## MW-OBS-006 - Governance Boundary Between MOD-W and PROD-W Requires Explicit Tracking

**Date:** 2026-09-30  
**MOD-W area:** Moderator role definition and authority scope  
**Project stage:** Architecture planning (pre-acceptance review)  
**Observed by role:** Moderator  
**Classification:** `LOCAL_ADAPTATION_PROPOSED`  
**Status:** Accepted  
**Significance:** High

### MOD-W Mechanism or Assumption

MOD-W defines a Moderator role responsible for gate approval, coherence review, and independent oversight. In a conventional software project, the Moderator role is stable throughout the product lifecycle: one Moderator, one product.

In the PROD-W experiment, there are two Moderators:

1. **MOD-W Moderator:** Governs the `prod-w-dev` repository and the experiment itself. Reviews architecture, step planning, research governance, and local adaptations.
2. **Product Moderator (future PROD-W role):** Will be defined by PROD-W protocol and will govern product decisions within PROD-W-compliant projects. Does not yet exist; cannot review/modify `prod-w-dev` governance.

### Observation

The initial architecture, domain language, and step planning artifacts were authored under MOD-W governance but contain concepts and role definitions (such as "Product Moderator") that belong to PROD-W itself. This is semantically correct but creates a risk of silent authority confusion during implementation and review.

Specifically:

- Architecture defines Product Moderator as a future PROD-W role; it does not yet have consequential authority in `prod-w-dev`
- A reviewer during later implementation phases might mistakenly treat Product Moderator definitions as already-applicable authority
- MOD-W gates (e.g., architecture acceptance) must be explicit about which Moderator is acting

### Evidence

- `prod-w/architecture.md` defines roles but does not clearly state that it is authored under MOD-W governance, not PROD-W governance
- `prod-w/domain-language.md` includes correct role definitions but lacks explicit governance context
- `prod-w/step-01.md` outlines development work but does not clarify which review/acceptance gate applies (MOD-W Moderator, not Product Moderator)
- MOD-W template sections do not have built-in affordance for "Governance Authority" or "Review Audience" that would disambiguate this context

### Effect on Work

- Low risk at this stage (Product Moderator role is not yet assigned)
- Medium risk in implementation phases if reviewers are not clear about which gate authority applies
- High risk if the Product Moderator role is later staffed before governance boundaries are clarified in documentation
- Potential for conflation if both Moderators exist simultaneously without explicit artifact-governance metadata

### Local Adaptation Required

**Proposed:** Add a "Governance Context" section to architecture, domain language, and step artifacts under MOD-W that clarifies:

- This artifact is authored and reviewed under MOD-W v5.0.1 governance
- The MOD-W Moderator is responsible for acceptance/rejection and coherence review
- Definitions of Product Moderator (and other future PROD-W roles) are aspirational and may not be modified without MOD-W Moderator approval
- Future PROD-W implementations must not redefine or override these artifact definitions

### Interpretation

This is evidence that **local adaptation is necessary when MOD-W governs the development of a future governance system (PROD-W) that will itself define a Moderator role.** The adaptation is lightweight (metadata/context markers) but necessary to prevent silent authority confusion.

This is a unique scenario: MOD-W is being used to develop another governance protocol. The risk does not exist in conventional software development.

### Follow-up

- Implement proposed governance-context clarifications in architecture, domain language, and step artifacts
- Review all future `prod-w/` artifacts under MOD-W for similar governance-context clarity
- Determine whether governance-context metadata should be formalized in MOD-W templates for future protocol/methodology experiments

### Moderator Disposition

**Accepted.** Local adaptation is appropriate and necessary. The proposed change is lightweight and adds clarity without disrupting the MOD-W review process. Implement as part of Moderator review feedback.

**Vocabulary normalization note (2026-09-30, appended per DTD-01 disposition, confirmed by Frank McGuire):** This observation's recorded classification `LOCAL_ADAPTATION_PROPOSED` is drawn from `mod-w/step-01.md`'s vocabulary, since superseded. `research/mod-w-transferability/README.md` and the accepted `mod-w/product.md` are the authoritative vocabulary and use `REQUIRES_LOCAL_ADAPTATION` for the same disposition state. The original text and classification label above are preserved unchanged per Historical Integrity. Treat this observation as `REQUIRES_LOCAL_ADAPTATION` going forward. See `mod-w/validation/dev-team-step-01-discrepancy-report.md` DTD-01 and `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Section 1.

---

## MW-OBS-007 - Higher-Depth Review Surfaced Governance-State Drift Missed by Literal Task Execution

**Date:** 2026-09-30  
**MOD-W area:** Tech Lead responsibilities, review depth, cross-artifact governance consistency  
**Project stage:** Post-architecture correction and reconciliation  
**Observed by role:** Tech Lead  
**Classification:** `LOCAL_ADAPTATION_PROPOSED`  
**Status:** Proposed for Moderator review  
**Significance:** Medium

### MOD-W Mechanism or Assumption

MOD-W assigns role responsibilities and review gates intended to separate concerns and prevent self-approval. The Tech Lead role is responsible for architecture coherence, implementation guidance, and technical consistency.

The implicit assumption tested here is that a role prompt plus artifacts may be sufficient to produce consistent review quality across a complex governance correction.

### Observation

The same Tech Lead role produced materially different review quality under different reasoning settings identified in the session as GPT-5.5 Low and GPT-5.5 High.

The lower-depth pass correctly handled the literal file-move instruction but missed several cross-artifact governance consequences, including:

- root-level process artifacts requiring relocation
- accepted artifacts still marked as draft/proposed
- STEP-01 decision coverage mismatch
- risk of silently rewriting accepted transferability observations
- incomplete governance-context propagation
- stale prompt/review instructions after architecture acceptance

The higher-depth review identified these conflicts and required a reconciliation pass.

### Evidence

- `mod-w/validation/tech-lead-reconciliation.md`
- `research/topics/model-depth-tech-lead-self-review.md`
- Corrected MOD-W governance artifacts under `mod-w/`
- Repository-structure correction leaving `prod-w/` reserved for concrete product artifacts

### Effect on Work

- A separate reconciliation artifact was required to preserve findings and correction status.
- Some issues were corrected within Tech Lead authority.
- One Product Definition status inconsistency was returned to Product Owner / MOD-W Moderator rather than silently changed.
- The work is now awaiting MOD-W Moderator review before commit.

### Local Adaptation Required

**Proposed:** Consider an explicit post-change cross-artifact governance consistency check for protocol/methodology development work.

Candidate check:

> If this change is correct locally, what governance records, artifact classifications, review statuses, research evidence, and downstream instructions does it invalidate or make stale?

### Interpretation

This is evidence from one project event. It does not prove that higher reasoning settings are always required or that lower reasoning settings are generally unreliable.

It suggests that MOD-W role definition and governance gates do not fully eliminate variation caused by model/reasoning capability. Model or harness configuration may need to be considered separately from workflow-role conformance when work has high governance complexity.

### Follow-up

- Moderator should determine whether the evidence is sufficient to accept this observation.
- If accepted, classify whether the project needs a local adaptation or simply a stronger Tech Lead review checklist.
- Future steps should observe whether similar cross-artifact drift occurs during Development Team and QA phases.

### Moderator Disposition

Pending Moderator review.

---

## MW-OBS-008 - Development Team "Implementation" Transfers as Normative Specification, but the Blocking Build Gate Has No Instantiation

**Date:** 2026-09-30  
**MOD-W area:** Development Team role, implementation semantics, Phase 2 blocking build gate  
**Project stage:** STEP-01 implementation (first Development Team step)  
**Observed by role:** Development Team  
**Classification (Accepted, mixed):** `TRANSFERS_WITH_REINTERPRETATION` for implementation semantics; `DOMAIN_COUPLED` for the blocking build gate (reclassified from the originally proposed `LOCAL_ADAPTATION_PROPOSED` per the DTD-01/DTD-02 vocabulary correction; see `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Section 3)  
**Status:** Accepted  
**Significance:** Medium

### MOD-W Mechanism or Assumption

MOD-W assigns the Development Team the role of producing "Implementation - code, tests, docs for each Step" (`mod-w/templates/MOD-W.md`, role table). Phase 2 then specifies a blocking gate:

> 2b. **Development Team** implements the approved scope only and runs the blocking build gate (`{{BUILD_COMMAND}}` + `{{TEST_COMMAND}}`).

The underlying assumption is that a Step's output is executable, that correctness is demonstrated mechanically before review, and that the build gate blocks handoff independently of any reviewer's judgment.

This observation supplies the first concrete evidence for two questions registered as open in MW-OBS-003 (Development Team as a code-producing role; build/runtime acceptance assumptions). It does not resolve the remaining questions registered there.

### Observation

STEP-01 was the first Development Team step in `prod-w-dev`. Two distinct things happened.

**1. The implementation concept transferred once "implementation" was read broadly.**

The step's work was recognisably implementation: it took an accepted architecture (D1-D4, with D6 and D8 boundaries), an accepted domain language, and a scoped step artifact, and produced a concrete, traceable deliverable constrained by them. Scope discipline, Reference Implementation disposition, "Expected File Changes", and per-check acceptance criteria all applied literally and usefully. The deliverable was a normative specification (`prod-w/protocol-semantics.md`) rather than executable code, but nothing in the step mechanism required reinterpretation beyond the word "code" in the role table.

**2. The blocking build gate had nothing to instantiate.**

`{{BUILD_COMMAND}}` and `{{TEST_COMMAND}}` remain uninstantiated placeholders. The repository contains no build or test configuration and no CI definition; `.claude/settings.json` is empty (`{}`). There was therefore no mechanical gate to run before handoff, and no automated signal separating "the Development Team believes this is done" from "this is verifiably done".

What substituted for the build gate was entirely documentary: an acceptance-check-to-section traceability table (`prod-w/protocol-semantics.md` Section 12.3) that a human reviewer must read and confirm. That is a reviewer-dependent check, not a blocking one. The difference matters because MOD-W positions the build gate as protection _before_ review, and that protection was simply absent for this step.

### Evidence

- `mod-w/templates/MOD-W.md` line 17 (Development Team role defined as "code, tests, docs") and line 72 (Phase 2b blocking build gate)
- `mod-w/templates/CLAUDE.md` line 52 and `mod-w/templates/ai-agents.md` line 64, which also instruct the Development Team to run the build gate
- `mod-w/step-01.md`: acceptance checks are all statements about the content of a document; none references runtime behavior
- Repository inspection: no `package.json`, no test configuration, no CI workflow; `.claude/settings.json` contains `{}`
- Deliverable produced: `prod-w/protocol-semantics.md`
- Substitute check used: `prod-w/protocol-semantics.md` Section 12.3, acceptance-check traceability table

### Effect on Work

- The step proceeded without friction on scope, inputs, and acceptance-check structure.
- No mechanical pre-review verification occurred, because none exists for this deliverable type.
- The Development Team added a traceability table to make each acceptance check reviewable at a specific location, which is a documentary compensation, not an equivalent to a blocking gate.
- Review burden shifts entirely onto the MOD-W Moderator. For a governance specification this is arguably appropriate, but it is a change in where correctness pressure sits, and it should not be silently absorbed.
- Contradictory evidence worth preserving: the absence of a build gate did not obstruct the step. That may mean the gate is unnecessary for specification work, or it may mean a defect class went undetected. This step alone cannot distinguish those.

### Local Adaptation Required

**Proposed, not authorized.** Two options are offered for Moderator consideration; the Development Team does not select between them and has not applied either.

- **Option A (minimal):** Record that for normative-specification steps in `prod-w-dev`, the Phase 2b blocking gate is deemed not applicable, and the step's acceptance checks plus a required traceability mapping serve as the handoff condition. This is honest about the absence rather than pretending a gate ran.
- **Option B (substantive):** Define a non-code blocking gate for specification steps - for example, a mechanical check that every acceptance check in the active `step-xx.md` maps to a named location in the deliverable, and that no file outside the step's "Expected File Changes" was modified. This preserves the gate's _function_ (mechanical, reviewer-independent, blocking) without assuming executable output.

Either option, if authorized, belongs in `adaptations.md` and not in this observation.

### Interpretation

Separating the two components:

- **Implementation semantics.** This is evidence that MOD-W's Development Team role and step-execution mechanism transfer to protocol/methodology work when "implementation" is read as production of the step's normative deliverable. The reinterpretation required is terminological, not structural - consistent with the pattern MW-OBS-004 recorded for the architecture phase.
- **Build gate.** This is evidence of genuine software coupling in a specific MOD-W mechanism. The gate is not merely worded for software; its defining properties (mechanical, blocking, reviewer-independent) depend on the deliverable being executable. That is a narrower and harder finding than a terminology problem.

**Conclusion (deliberately limited):** one step, one deliverable type, one project. This does not establish that MOD-W's build gate is domain-coupled in general, nor that specification work needs no mechanical gate. It establishes that for this step, the gate had no instantiation and a documentary substitute was used.

### Follow-up

- Moderator determines whether the mixed classification is appropriate or whether this should be split into two observations.
- Moderator determines whether either proposed adaptation is warranted, or whether a stronger Development Team handoff checklist suffices.
- STEP-02 and STEP-03 should observe whether the same gate absence recurs and whether any defect later traces to it.
- The QA phase should be observed specifically: if MOD-W's QA concept also assumes runtime behavior, the two findings together would be stronger evidence than either alone.
- Cross-reference MW-OBS-003, which registered these as open questions; this observation partially answers two of them and leaves the rest open.

### Post-Proposal Note (2026-09-30, added by proposing role)

The proposed classification of the build-gate component is **under question**, and the proposing role flags it rather than changing it.

`LOCAL_ADAPTATION_PROPOSED` was selected from the four-value list in `mod-w/step-01.md` line 133. That list omits `DOMAIN_COUPLED`, which `research/mod-w-transferability/README.md` line 146 and `mod-w/product.md` line 390 both define. The evidence above - that the gate's defining properties depend on the deliverable being executable - is a candidate `DOMAIN_COUPLED` finding under the fuller vocabulary.

The proposed classification is left exactly as first recorded, so that `mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-DEV-TEAM.md` Section 5 item 2, which references it, remains accurate. The Moderator should resolve the vocabulary question before disposing of this observation.

See `mod-w/validation/dev-team-step-01-discrepancy-report.md`, DTD-02.

### Moderator Disposition

**Accepted**, per `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Section 3, confirmed by Frank McGuire (MOD-W Moderator) 2026-09-30. Implementation semantics: `TRANSFERS_WITH_REINTERPRETATION`. Blocking build gate: `DOMAIN_COUPLED` — the gate's mechanical, blocking, reviewer-independent properties depend on the deliverable being executable, and none of that was available to substitute for this step. This does not foreclose a local adaptation; Option A/B remain open, deferred pending STEP-02/03 recurrence evidence.

---

## MW-OBS-009 - Controlled Re-Execution Is in Deliberate Use, and MOD-W's Independence Model Does Not Describe It

**Date:** 2026-09-30  
**MOD-W area:** Role independence and cross-validation; tooling assumptions; Development Team role  
**Project stage:** STEP-01 implementation  
**Observed by role:** Development Team  
**Classification (Accepted):** `TRANSFERS_WITH_REINTERPRETATION`  
**Status:** Accepted  
**Significance:** Medium  
**Related:** MW-OBS-007 (same phenomenon, Tech Lead role, still Proposed)

### Scope caveat, stated first

This register exists to record evidence about MOD-W's transferability to **non-software** development. The finding below may not be a non-software finding at all: it may be an **AI-assistance** finding that would arise equally in a conventional software project run with AI agents. The Development Team cannot resolve that, and flags it so the Moderator can decide whether this observation belongs in this register, in a separate record, or in both. It should not be counted as non-software transferability evidence unless the Moderator determines that it is.

### MOD-W Mechanism or Assumption

MOD-W builds independence out of **role separation**: Tech Lead plans and reviews, a different Development Team role implements, QA verifies, Moderator holds the final gate. `mod-w/templates/MOD-W.md` line 40 calls the Tech Lead to Development Team boundary "the single most-protected boundary". The assumption is that assigning work to a different role is what makes a second look independent.

MOD-W does not describe a second dimension that exists in AI-assisted work: the same role, with the same prompt and the same inputs, can be executed by different models or reasoning configurations, producing materially different output.

### Observation

Controlled re-execution is in deliberate use in this project, and is now confirmed as intentional Moderator practice rather than incidental.

Two instances are on record:

1. **Tech Lead, prior stage.** Initial Tech Lead work produced under one configuration was re-reviewed under a higher-effort configuration, which surfaced 15 findings the first pass had missed - repository-structure errors, stale status metadata, a decision-coverage mismatch, and a risk of rewriting accepted transferability observations. Recorded as MW-OBS-007 and `mod-w/validation/tech-lead-reconciliation.md`.

2. **Development Team, this step.** The STEP-01 prompt was re-issued unchanged, in the same Development Team role, after a model change. The Moderator has confirmed that this was requested specifically to compare different models against the same prompt and the same role.

The disposition pattern in instance 1 is the important part of the evidence. Of 15 findings, 13 were corrected within the role's own authority, 1 was returned to the Product Owner, and 1 to the Moderator. The reconciliation artifact closes: "No implementation, QA, or self-approval has been performed." The re-execution fed **revision and escalation**, and fed acceptance nowhere.

### Evidence

- `mod-w/templates/MOD-W.md` line 40 (role separation as the protected boundary) and the Phase 1-4 role sequence
- `mod-w/validation/tech-lead-reconciliation.md`, including the finding table, the authority column, and the stop condition
- `research/topics/model-depth-tech-lead-self-review.md`
- MW-OBS-007 in this register
- This session: the STEP-01 prompt re-issued verbatim, same role, different model configuration
- Moderator confirmation that the re-execution was requested for model comparison

### Effect on Work

- The practice produced real defect detection in instance 1, at a stage where no other mechanism would have caught the issues before Moderator review.
- It created a classification question the Development Team could not answer from MOD-W alone: is a second run by a different model an independent review, or the same actor looking twice? MOD-W's role-based independence model does not address the question, because the role is identical in both runs.
- The question had to be settled inside the product artifact, since PROD-W must state when acceptance is valid. `prod-w/protocol-semantics.md` now settles it: producing configuration is provenance and not actor identity (PR-27), and re-execution yields revisions, advisory findings, escalations and research evidence but never independence or acceptance (PR-28, Section 6.5).
- No local MOD-W adaptation was required to proceed. The existing disposition pattern from instance 1 was already correct; it simply was not described anywhere in MOD-W.

### Local Adaptation Required

None proposed. The project's existing behaviour already matches the rule the product artifact now states. What is arguably missing is documentation, not mechanism.

Offered for Moderator consideration only: MOD-W role prompts and review artifacts could record the producing configuration alongside the role, so that a later reader can distinguish two runs of one role from two roles. The Development Team does not propose this as an adaptation and has not applied it.

### Interpretation

MOD-W's cross-validation concept **transfers, but is under-specified for AI-assisted execution**. Role separation remains the right primitive, and nothing observed suggests it should be replaced. What MOD-W does not say is that varying the configuration of a single role is not a substitute for varying the role - a gap that only becomes visible when a project deliberately varies configuration, as this one does.

Evidence both ways is preserved. _For_ configuration variance being valuable: instance 1 caught 15 real findings. _Against_ it being independence: both runs shared prompt, inputs and accountability, so any defect originating in the prompt or the inputs would be invisible to both, and agreement between them would be agreement rather than corroboration.

**Conclusion (deliberately limited):** two instances, one project, one methodology. This does not establish how MOD-W should handle configuration variance generally, and as noted in the scope caveat, it may not be a non-software finding at all.

### Follow-up

- Moderator determines whether this belongs in this register, given the scope caveat.
- Moderator determines whether MW-OBS-007 and this observation should be considered together, since they record the same phenomenon in two different roles.
- Later steps should observe whether controlled re-execution continues to find issues as the artifacts mature, or whether its yield falls off.
- Watch for the failure mode this observation predicts but has not seen: a defect originating in a step prompt or its inputs, missed identically by every configuration.

### Moderator Disposition

**Accepted** as `TRANSFERS_WITH_REINTERPRETATION`, confirmed by Frank McGuire (MOD-W Moderator) 2026-09-30. Kept in this register with the scope caveat intact; whether this is non-software transferability evidence or a general AI-assistance finding remains open. No adaptation authorized — none was proposed, and PR-27/PR-28 already state the substantive rule this observation asked for.

---

## MW-OBS-010 - The Tech Lead to Development Team Boundary Loses Its Enforcement Mechanism When Both Roles Produce Normative Prose

**Date:** 2026-09-30  
**MOD-W area:** Tech Lead and Development Team role separation; the Phase 1 to Phase 2 boundary  
**Project stage:** STEP-01 implementation, post-delivery, post-Moderator-review  
**Observed by role:** Development Team (reporting on its own output)  
**Classification (Accepted):** `REQUIRES_LOCAL_ADAPTATION`  
**Status:** Accepted  
**Significance:** High  
**Related:** MW-OBS-003 (registered this area as `NOT_YET_TESTED`), MW-OBS-008 (implementation semantics)

### Vocabulary note

This observation uses `REQUIRES_LOCAL_ADAPTATION` from `research/mod-w-transferability/README.md` line 142, not `LOCAL_ADAPTATION_PROPOSED` from `mod-w/step-01.md` line 133. The two vocabularies conflict; see `mod-w/validation/dev-team-step-01-discrepancy-report.md`, DTD-01. The Moderator should normalize the value when disposing of this observation.

### MOD-W Mechanism or Assumption

`mod-w/templates/MOD-W.md` line 40: "The single most-protected boundary is Tech Lead to Development Team: Codex plans and reviews; a different implementation role executes the approved Step."

The stated assumption is that **role assignment** is what separates planning from implementation.

There is an unstated second mechanism. In conventional software development the boundary is also enforced by **medium**: architecture is prose, implementation is code, and the two are not interchangeable. A developer cannot accidentally emit an architectural decision from a compiler-checked artifact. The decision would have nowhere to live. Role separation and media separation reinforce each other, and MOD-W only names the first.

### Observation

In `prod-w-dev`, both sides of the boundary produce normative prose in markdown, in the same register, in the same repository. The Tech Lead produced `mod-w/architecture.md` and `mod-w/domain-language.md`; the Development Team produced `prod-w/protocol-semantics.md`. The media separation is gone. Enforcement collapses onto role discipline and reviewer attention alone.

**The boundary was crossed, in this step, by the reporting role.**

The clearest instance is **PR-27** in `prod-w/protocol-semantics.md`: "producing configuration is part of provenance and is not part of actor identity." That is a decision about the identity model. Architectural decision D4 requires actor identity to be separated from role labels; it does not decide whether configuration belongs to identity. The Development Team decided it, inside an implementation deliverable, during a mid-step correction, and stated a rationale for it (that the alternative would let an actor manufacture independence by switching configurations).

A milder instance is the four-class authority taxonomy AUTH-P / AUTH-A / AUTH-V / AUTH-G. It is traceable to the "Authority Types" section of the accepted `mod-w/product.md`, so it is grounded, but D4 does not enumerate it. The Development Team structured the authority model.

**The review did not catch it.** `mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-DEV-TEAM.md` Section 2 passes acceptance check 3 citing Section 4.1 of the deliverable, which is where PR-27's rationale sits, and Section 3 concludes "No defects found." This is not a criticism of the review: PR-27 reads as protocol semantics, which it also genuinely is. An architecture-level decision expressed in the same medium and register as implementation output is difficult to see.

**A secondary conformance note.** MOD-W Phase 2a requires the Development Team to restate the step, propose a plan, and wait for Moderator approval before implementing. That did not occur in this step; implementation began directly from the briefing. The briefing was detailed enough - scope, constraints, acceptance checks, required report format - that it arguably pre-empted the plan gate, and the prior Moderator feedback had already recorded STEP-01 as unblocked. Recorded as a deviation rather than an accusation, because a skipped restate-and-plan gate is one of the few places where a boundary crossing would have surfaced before the work was written.

### Evidence

- `mod-w/templates/MOD-W.md` line 40 (boundary statement), lines 70-72 (Phase 2a and 2b)
- `mod-w/architecture.md` D4 and its Consequences paragraph
- `prod-w/protocol-semantics.md` PR-27, Section 4.1 subsection "Producing configuration is provenance, not identity", and the Section 13 change note recording that it was added mid-step
- `prod-w/protocol-semantics.md` Section 4.4 (authority class taxonomy) against `mod-w/product.md` "Authority Types"
- `mod-w/reviews/MODERATOR-REVIEW-FEEDBACK-DEV-TEAM.md` Sections 2 and 3
- Absence of any Tech Lead review artifact for `prod-w/protocol-semantics.md` in `mod-w/reviews/`, confirmed by the Moderator review Section 4

### Effect on Work

- An architecture-level decision entered a product artifact without Tech Lead review, and passed Moderator review unflagged.
- The outcome was not bad. PR-27 was judged sound, and the Development Team believes it is correct. **The defect is procedural, not substantive**, and the distinction matters: the boundary did not fail by producing a wrong decision, it failed by producing a decision at the wrong level for the wrong reviewer. A boundary that only fails visibly when the output is also wrong is not a boundary.
- The absence of a Tech Lead review artifact compounds it. Per the Moderator review Section 4, Moderator review is currently standing in for both Tech Lead review and the build gate, so the one gate designed to catch architecture-level drift in implementation output did not run at all.

### Contradictory Evidence, Preserved

The separation earned its keep in this same step. Executing against the governance artifacts closely enough to implement them, the Development Team found four inconsistencies in them, including one that materially affected its own output - the omission of `DOMAIN_COUPLED` from the classification vocabulary handed to evidence-producing roles. A single merged planning-and-implementing role would have written both the instruction and the evidence, and would have had no occasion to read the instruction adversarially.

Recorded in `mod-w/validation/dev-team-step-01-discrepancy-report.md`.

So the evidence is genuinely mixed: the boundary is **valuable and under-enforced at the same time**. Neither half should be dropped.

### Local Adaptation Required

**Proposed, not authorized.** Restore the boundary's enforcement with an explicit declaration, since the medium no longer supplies it:

> Every Development Team deliverable in `prod-w-dev` declares the decisions it had to make that the accepted architecture did not decide, with the reasoning and the input each was derived from. That list routes to the Tech Lead.

Properties: cheap, produced by the role best placed to know, and it targets the specific failure rather than the general one. It converts an invisible crossing into a visible, reviewable list.

This is offered as **Option C for MW-OBS-008**, and the proposing role considers it stronger than its own Options A and B. Those address the build gate that vanished; this addresses the risk that took its place. A mechanical check that every acceptance check maps to a location (Option B) would not have caught PR-27, because PR-27 does map to a location and is well-traced.

### Interpretation

MOD-W's role-separation concept **transfers**; its implicit enforcement does not. The mechanism relies on a property of software development that MOD-W never had to state, because in software it is free.

The generalization worth testing: MOD-W boundaries that are enforced by artifact type in software may need explicit substitutes wherever every role's output is prose. If that holds, it applies to the Tech Lead to Development Team boundary, and likely to any other boundary where planning and output share a medium.

**Conclusion (deliberately limited):** one step, one deliverable, one crossing with a benign outcome, in a project whose subject matter is authority boundaries and is therefore unusually likely to notice its own. This does not establish that the boundary fails generally, nor that the proposed adaptation is the right one.

### Follow-up

- Moderator determines whether the classification, and the vocabulary it is drawn from, are appropriate.
- Moderator determines whether Option C is authorized, and whether it supersedes or complements the MW-OBS-008 options.
- Moderator determines whether a Tech Lead review of `prod-w/protocol-semantics.md` should be run now, specifically for architecture-level content, or whether the gate is formally waived and recorded as a visible exception per the Moderator review Section 5 item 4.
- STEP-02 should be observed with this specifically in mind: whether crossings recur, and whether a declaration list surfaces them.
- Watch for the harder version of this failure: a boundary crossing whose outcome is also wrong, which is the case this step did not produce and therefore did not test.

### Moderator Disposition

**Accepted** as `REQUIRES_LOCAL_ADAPTATION`, Significance High, confirmed by Frank McGuire (MOD-W Moderator) 2026-09-30 — on the strength of an independent re-read of `prod-w/protocol-semantics.md` Section 4 against `mod-w/architecture.md` D4 (`mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Section 0), not on the strength of this self-report alone. PR-27 is confirmed architecture-level content that entered without Tech Lead review.

The proposed adaptation (Option C: every Development Team deliverable declares the decisions it had to make that the accepted architecture did not decide, routed to Tech Lead) is **authorized**. Recorded as `MW-ADAPT-001` in `adaptations.md`.

A scoped Tech Lead review of `prod-w/protocol-semantics.md` for architecture-level content (PR-27 §4.1; AUTH-P/A/V/G taxonomy §4.4) was recommended but not commissioned. The Moderator approved STEP-01 without it. This is recorded as an explicit, visible waiver of that review, per GR-7 and OBJ-12 — not as a finding that no architecture-level content exists. See `prod-w/protocol-semantics.md` Section 13 and `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Section 5.

---

## MW-OBS-011 - First Application of MW-ADAPT-001: The Declaration Is Operable, but "Did Not Already Decide" Has No Criterion and the Producer Is the Only Auditor

**Date:** 2026-09-30  
**MOD-W area:** Tech Lead to Development Team boundary (Phase 1 to Phase 2); MW-ADAPT-001  
**Project stage:** STEP-02 implementation (second Development Team step)  
**Observed by role:** Development Team (reporting on its own output)  
**Classification (Proposed):** `REQUIRES_LOCAL_ADAPTATION`  
**Status:** Proposed for Moderator review  
**Significance:** Medium  
**Related:** MW-OBS-010, MW-ADAPT-001, MW-OBS-009

### MOD-W Mechanism or Assumption

`mod-w/templates/MOD-W.md` line 40 relies on role separation to keep planning and implementation independent. MW-OBS-010 recorded that this loses its enforcement when both roles produce normative prose. MW-ADAPT-001 (authorized 2026-09-30) responds by requiring every Development Team deliverable to list the decisions it had to make that accepted upstream artifacts did not decide, routed to the Tech Lead. Its re-evaluation condition: "at the STEP-02 gate: did the declaration section produce any findings, and did any architecture-level content still slip past it?"

### Observation

`prod-w/evidence-knowledge-model.md` Section 12 is the first deliverable produced under MW-ADAPT-001. Three things occurred.

**1. The declaration was operable and produced a list.** An audit pass over the finished draft identified sixteen choices not settled by accepted upstream artifacts. The Development Team self-assessed four as architecture-level candidates (UAD-04 item identity across change; UAD-05 presumed materiality; UAD-06 the layered reading of PR-26 with ACT-06/HJ-10; UAD-07 the trigger set and exposure). In the case of UAD-06 the choice arose from an apparent tension between two accepted STEP-01 provisions, not from a gap.

**2. MW-ADAPT-001 gives no criterion for "did not already decide."** To compile the list the Development Team had to write its own working test (Section 12.1 of the deliverable): declare a choice if a reasonable alternative reading of upstream artifacts would have produced a materially different model, or if it touches authority, actor identity, independence, revalidation semantics, or what counts as evidence. Another producer could have drawn the line elsewhere and produced a shorter or longer list. The boundary between "operationalizing an accepted principle" and "making a new decision" is itself a judgment, and MW-ADAPT-001 leaves it to the producer.

**3. The audit was performed by the producer.** The list was compiled after drafting rather than kept as a running record, which means choices made in the flow of writing had to be recognized in retrospect. The deliverable states that it cannot show nothing was missed (Section 12.5). This is the same limitation MW-OBS-009 identifies for controlled re-execution: the producing actor cannot supply independence over its own output.

### Evidence

- `prod-w/evidence-knowledge-model.md` Section 12 (declaration, working test, self-assessed levels) and Section 12.5
- `research/mod-w-transferability/adaptations.md` MW-ADAPT-001, including its re-evaluation condition
- `research/mod-w-transferability/observations.md` MW-OBS-010 (the failure mode addressed) and MW-OBS-009 (the independence limit)
- `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Sections 0 and 4 (the precedent that PR-27 was architecture-level and passed review unflagged)

### Effect on Work

- Architecture-adjacent choices were made visible in one reviewable list rather than left inside the model text.
- The list is only as complete as the producer's judgment. No independent check of its completeness exists yet. The Tech Lead review is what would provide one, and has not occurred.
- Compiling the list added a bounded amount of work at the end of the step.

### Local Adaptation Required

None proposed by the Development Team as authorized action. Offered for Moderator consideration only: MW-ADAPT-001 could state a criterion for "did not already decide," or require the Tech Lead to review a sample of the deliverable's unlisted choices in addition to the declared ones, so that completeness is checked by someone other than the producer. The Development Team does not select between these and has applied neither.

### Interpretation

This is evidence that MW-ADAPT-001 can be executed and does surface architecture-adjacent choices. It is also evidence that the adaptation's effectiveness depends on the level-of-decision judgment that MW-OBS-010 showed to be hard to make from inside the producing artifact.

Evidence both ways is preserved. For the adaptation working: the list exists and includes choices, notably UAD-04 to UAD-07, that would not otherwise be labeled as decisions. Against it being sufficient: the same actor drew its boundary, and an omitted architecture-level choice would be invisible to it.

**Conclusion (deliberately limited):** one deliverable, one producer, one project. This does not establish that the adaptation is sufficient or insufficient. Whether any architecture-level content slipped past it can only be determined by an actor other than the producer.

### Follow-up

- At the STEP-02 gate, the Tech Lead reviews Section 12 and, at the Moderator's discretion, a sample of unlisted choices, so the re-evaluation condition can be answered by someone other than the producer.
- Observe whether STEP-03 produces a comparably sized list, or whether the list shrinks as upstream artifacts accumulate.
- Watch for an architecture-level choice found in a deliverable that the declaration did not list.

### Moderator Disposition

Pending Moderator review.

---

## MW-OBS-012 - The Blocking Build Gate and the Restate-and-Plan Gate Are Again Not Instantiated at STEP-02

**Date:** 2026-09-30  
**MOD-W area:** Development Team role, Phase 2a and Phase 2b, Phase 3 gates  
**Project stage:** STEP-02 implementation (second Development Team step)  
**Observed by role:** Development Team  
**Classification (Proposed):** `DOMAIN_COUPLED` for the blocking build gate (recurrence of MW-OBS-008's accepted classification); no new classification proposed for the plan gate  
**Status:** Proposed for Moderator review  
**Significance:** Low to Medium  
**Related:** MW-OBS-008, MW-OBS-010

### MOD-W Mechanism or Assumption

Phase 2a (`mod-w/templates/MOD-W.md`) has the Development Team restate the Step and propose a plan for Moderator approval before implementing. Phase 2b has it run a blocking build gate (`{{BUILD_COMMAND}}` + `{{TEST_COMMAND}}`). MW-OBS-008 recorded that the build gate had no instantiation for a specification deliverable and asked that STEP-02 and STEP-03 observe whether that recurs and whether any defect later traces to it.

### Observation

**Build gate.** At STEP-02 the repository still has no build or test configuration, no CI definition, and no package manifest, and `.claude/settings.json` still contains `{}`. The STEP-02 deliverable is again a normative specification. No mechanical pre-review gate existed to run.

**What substituted for it.** As in STEP-01, an acceptance-check-to-section traceability table (`prod-w/evidence-knowledge-model.md` Section 14.3), plus a manual cross-reference and forbidden-term scan by the Development Team. The scan is by the producer and is not independent verification.

**Plan gate.** The STEP-02 briefing directed direct implementation of the accepted step. The Development Team read the inputs and proceeded; no separate restate-and-plan checkpoint was held for Moderator approval. This is the deviation MW-OBS-010 recorded for STEP-01, occurring again. The briefing was detailed and the step file was already Moderator-accepted, which arguably pre-empts the plan gate, as MW-OBS-010 noted.

**Review gates.** No Phase 3a, 3b, or 3c has been run for this deliverable and none has been waived. The STEP-01 waiver was stated to be specific to STEP-01 (`mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Section 9).

### Evidence

- Repository inspection at STEP-02 start: no `package.json`, no test or CI configuration; `.claude/settings.json` = `{}`; `prod-w/` contained only `protocol-semantics.md`
- `mod-w/step-02.md`: acceptance checks are all statements about document content
- `prod-w/evidence-knowledge-model.md` Section 14.3 (substitute traceability)
- `research/mod-w-transferability/observations.md` MW-OBS-008 (follow-up asking for recurrence evidence) and MW-OBS-010 (secondary conformance note on the plan gate)
- `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Sections 3 and 9

### Effect on Work

- The step proceeded without friction from the absence of a build gate, as in STEP-01. As in STEP-01, that may mean the gate is unnecessary for specification work or that a defect class goes undetected; this step cannot distinguish the two.
- No defect has been traced to the gate's absence at this point. That is a statement about the time of writing, not a finding, and nothing here shows it will stay true.
- Correctness pressure again rests on Moderator review, and on a Tech Lead review that has not yet happened.

### Local Adaptation Required

None proposed. MW-OBS-008 Options A and B remain open as the Moderator left them; this observation adds recurrence evidence only.

### Interpretation

This is evidence that the STEP-01 finding was not a one-time artifact: a second specification deliverable met the same absence in the same way. It is consistent with the accepted `DOMAIN_COUPLED` classification of the build-gate component, and it does not extend it. Recurrence of a gate's absence is weaker evidence than a defect traced to that absence, and none has been observed.

**Conclusion (deliberately limited):** two steps, one deliverable type, one project. This does not establish that specification work needs a mechanical gate, or that it does not.

### Follow-up

- Moderator determines whether recurrence changes the standing disposition of MW-OBS-008 Options A and B.
- Moderator decides whether Phase 3a, 3b, and 3c are run or waived for STEP-02, as the STEP-01 waiver did not carry over.
- STEP-03 should be observed for the same pattern, and for the first defect, if any, that traces to the missing gate or the missing plan checkpoint.

### Moderator Disposition

Pending Moderator review.

---

## MW-OBS-013 - "Tests Not Run" Close-out Language Exposes Software-Centric Verification Defaults

**Date:** 2026-10-01  
**MOD-W area:** Tech Lead review, QA/testing terminology, verification reporting  
**Project stage:** STEP-02 follow-up review  
**Observed by role:** Tech Lead (self-observation after Moderator correction)  
**Classification (Proposed):** `TRANSFERS_WITH_REINTERPRETATION` for verification reporting; `DOMAIN_COUPLED` for executable-test wording when used without qualification  
**Status:** Proposed for Moderator review  
**Significance:** Low to Medium  
**Related:** MW-OBS-003, MW-OBS-008, MW-OBS-012

### MOD-W Mechanism or Assumption

MOD-W's software-project defaults treat "tests" as executable verification: unit tests, build checks, CI, lint, or runtime validation. In `prod-w-dev`, the product is document-only and the verification artifacts are review records, QA reports, traceability checks, term comparisons, and Moderator dispositions.

The implicit software assumption is that a delivery close-out should report whether "tests were run." In a document-governed methodology project, that phrase is ambiguous: it may refer to executable tests that do not exist, or it may appear to discount document-native validation that did occur.

### Observation

After producing `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02-FOLLOWUP.md`, the Tech Lead close-out said: "No tests were run since this was a documentation-only review file."

The Moderator corrected the framing: because `prod-w-dev` is a document-only project, similar to MOD-W but not for coding projects, flagging that "tests have not been run" is itself an observation to record. The correction distinguishes executable code tests from document-native validation and review.

This shows that even when the working role understands the project as document-only, its default completion language can still import software-project verification expectations. The issue is not that review was absent: the follow-up relied on `qa.md`, Product Owner sign-off, Moderator review addenda, the model, protocol semantics, domain language, and transferability records. The issue is that the word "tests" was used without saying "executable tests" or naming the document validation that did happen.

### Evidence

- `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02-FOLLOWUP.md` was produced as a Markdown review artifact, not executable code.
- The Tech Lead close-out for that work stated that no tests were run because the file was documentation-only.
- The Moderator correction on 2026-10-01 stated that, in this document-only project, flagging tests as not run is an observation to record.
- `mod-w/reviews/qa.md` shows that document-native QA did run for STEP-02, including full reading of cited artifacts, git-history checks, forbidden-term scan, and comparison of accepted terms with model usage.
- MW-OBS-008 and MW-OBS-012 already record that executable build/test gates have no instantiation for specification deliverables.

### Effect on Work

- The close-out could be read as saying verification was absent, even though document-native review and QA artifacts were central inputs.
- The project now has additional evidence that MOD-W's testing vocabulary needs explicit reinterpretation in methodology/protocol work.
- The distinction matters for future reviews: "no executable tests were run" is not equivalent to "no validation occurred."

### Local Adaptation Required

None authorized here. Offered for Moderator consideration: review and delivery close-outs in `prod-w-dev` should distinguish:

1. executable/build tests;
2. document-native QA or review checks;
3. artifact rendering or formatting checks, where applicable;
4. checks not run because no corresponding gate exists.

This could be handled as a wording convention rather than a new workflow gate.

### Interpretation

This is small but concrete evidence that MOD-W's verification concept transfers better than its software-test vocabulary. The validation function still exists: review artifacts, QA reports, traceability tables, and Moderator dispositions perform it. The unqualified term "tests," however, remains domain-coupled enough to mislead when the deliverable is prose.

**Conclusion (deliberately limited):** one close-out, one review artifact, one correction. This does not show that QA itself failed to transfer. It shows that verification reporting needs more precise language in document-only projects.

### Follow-up

- Use "executable tests" when referring to code/build/CI checks.
- Name document-native validation explicitly when it is performed.
- Observe STEP-03 close-outs for whether the distinction is maintained without prompting.
- Consider whether `mod-w/templates/REVIEW.md` or role prompts should include the distinction if the pattern recurs.

### Moderator Disposition

Pending Moderator review.

---

## Open Observation Log

Future observations will be added to this register as they occur. Each will follow the template structure above, be assigned a sequential ID (`MW-OBS-014`, etc.), include concrete evidence, and use an appropriate classification.

The register is append-only; accepted observations are not removed or rewritten, though disposition may be updated based on new evidence.
