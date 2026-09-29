---
artifact:
  type: MOD-W Product Definition
  version: 1.1
  created: 2026-09-29
  updated: 2026-09-30
  date: 2026-09-30
  status: Accepted by Moderator
  accepted_by: Moderator
  accepted_date: 2026-09-30
---

# PROD-W Product Definition

**PROD-W — Moderated AI-Assisted Product Development Workflow**

Working descriptor: *A protocol-first approach to evidence-governed, human-moderated AI-assisted product development.*

---

## Executive Summary

PROD-W addresses a critical governance gap in AI-assisted product development: the tendency for plausible ideas, weak evidence, agent agreement, and inherited assumptions to accumulate into unjustified confidence that a product should be built.

PROD-W is not primarily a prompting or instruction problem. It is an **epistemic and governance problem**: How can authority, evidence quality, assumptions, inference, and human judgment remain explicit and distinguishable throughout AI-assisted product development?

The product will be developed using MOD-W v5.0.1 as a secondary research artifact, to evaluate whether MOD-W's governance model transfers beyond conventional software development to the development of a methodology/protocol itself.

---

## Product Identity

| Attribute | Value |
|-----------|-------|
| **Product name** | PROD-W |
| **Long form** | Moderated AI-Assisted Product Development Workflow |
| **Project scope** | Research, definition, and proof-of-concept of a governance protocol and supporting methodology |
| **Primary output** | Normative governance specification with human-readable methodology, evidence frameworks, role definitions, and a machine-readable representation as a core design goal; exact serialization and implementation remain deferred |
| **Output repository** | `prod-w` (separate from development workspace `prod-w-dev`) |
| **Governance model** | MOD-W v5.0.1 |
| **Experimental frame** | MOD-W transferability evaluation (methodology/protocol development vs. software development) |
| **Start date** | 2026-09-29 |
| **Maturity level** | Pre-alpha research and definition phase |

---

## Problem Statement

### Core Problem

In AI-assisted product development, the combination of:
- plausible problem statements
- plausible customer narratives  
- plausible differentiation claims
- AI validation through agreement and synthesis
- feature elaboration and refinement

...can accumulate into **unjustified confidence that a product should be built**, while:

- evidence remains weak or circumstantial
- assumptions remain invisible
- inference paths remain conflated with facts
- human authority becomes implicit rather than explicit
- alternative hypotheses and counter-evidence disappear
- disagreement is forced into artificial consensus

### Failure Pattern

The typical trajectory is:

```
Idea → plausible problem → plausible customer → plausible differentiation
  → AI validation → feature elaboration → apparent product opportunity
  → DECISION TO BUILD (without justified evidence)
```

At each step, the problem appears more solid, but confidence may outpace evidence quality by a significant margin.

### Root Cause

This is not primarily a problem of weak prompting, insufficient agent diversity, or inadequate model capabilities.

It is a **governance and epistemology problem**: The workflow lacks explicit rules for:
- what constitutes sufficient evidence
- who has authority to accept evidence
- how assumptions and inference remain distinguishable from facts
- what happens when evidence is absent or contradictory
- when human judgment must intervene
- how disagreement surfaces rather than disappears

Natural-language instructions (e.g., "agents should validate assumptions") are weaker than protocol rules that make invalid transitions structurally impossible.

### Impact

Proceeding without justified evidence:
- wastes engineering resources on unvalidated problems
- creates false product narratives in the market
- damages credibility when assumptions prove wrong
- obscures which product decisions were evidence-based
- makes learning from failure difficult

---

## Product Purpose and Intent

### Primary Purpose

PROD-W establishes a **protocol-first governance framework** for AI-assisted product development that:

1. **Makes authority explicit** — defines which decisions require human judgment
2. **Preserves evidence traceability** — connects material claims to their evidence source
3. **Distinguishes classes of knowledge** — separates evidence, inference, hypothesis, assumption, and decision into visible categories
4. **Surfaces disagreement** — keeps unresolved differences visible rather than forcing consensus
5. **Enables challenge** — provides mechanisms to question claims and require defense or revision
6. **Enforces discipline** — expresses governance semantics in forms that can support human review and machine-checkable validation where appropriate

### Secondary Purpose

PROD-W serves as a **research artifact** to evaluate whether MOD-W's governance model transfers to non-software knowledge-development domains (specifically, methodology and protocol development).

The project will observe and document:
- which MOD-W concepts transfer unchanged
- which expose software-specific assumptions
- what domain-neutral generalizations are required
- what constitutes "implementation" and "testing" outside software
- whether existing role boundaries remain coherent

This evidence will inform future MOD-W evolution without committing to broad applicability claims yet.

### User Intent

PROD-W is intended primarily for:
- **AI-assisted product development teams** evaluating, defining, and validating product opportunities
- **Product organizations** that need evidence-governed go/build/no-build decisions
- **Governance-conscious teams** that need human-moderated AI collaboration with auditable decision trails

Methodology and protocol-development teams are part of the `prod-w-dev` MOD-W transferability experiment, but they are not treated as a primary PROD-W target audience unless later product evidence justifies that expansion.

---

## Target Users and Stakeholders

The **MOD-W Moderator** governs the `prod-w-dev` development process and MOD-W gates. The **PROD-W Product Moderator** is a role being defined as part of the PROD-W product itself. The future PROD-W role does not govern this repository merely because both roles use the term "Moderator."

| Stakeholder | Primary Interest | Authority Scope |
|-------------|-----------------|-----------------|
| **Product Moderator** | Workflow orchestration; human go/no-go gates; consequence of product decisions | Consequential gate acceptance and final go/build/no-build authority where explicitly assigned |
| **Product Owner / Product Researcher** | What should be built and why; evidence quality; assumption validity | Evidence production, analysis, and recommendation; may not acquire gate authority unless explicitly authorized |
| **Product Skeptic / Validator** (research hypothesis) | Counter-evidence; assumption challenge; failure scenarios | Evidence challenge and gap identification; role remains hypothetical until justified |
| **Product Architect / Tech Lead** | How the product could be built; feasibility assessment; technical risks | Technical feasibility assessment and implementation evidence production/challenge |
| **Implementation Team / Development Team** | How to build the approved product; capability evidence; learning from building | Implementation evidence production and feedback on feasibility constraints |
| **QA / Validator** | Verification against acceptance criteria; evidence collection | Evidence verification against formal criteria and confirmation that required checks occurred; not consequential gate acceptance by default |
| **External Evaluators** (research hypothesis) | Independent validation; pattern-matching to known risks; conformance verification | Advisory findings, challenge, counter-evidence, or conformance verification; not gate authority unless a future approved revision explicitly grants it |

---

## Core Product Principles

These principles guide PROD-W design and are candidates for protocol-level enforcement:

### Evidence and Authority

**PE-1: Material claims require traceable evidence.**  
Every material claim (problem, customer, differentiation, viability) must be connected to its evidence source. Absence of evidence is visible.

**PE-2: Agent agreement is not independent evidence.**  
Multiple agents reaching the same conclusion does not constitute independent validation. Each must show evidence separately.

**PE-3: Inference and fact remain distinct.**  
"We observe X" (fact) is distinguished from "X implies Y" (inference) is distinguished from "Y is desirable" (value judgment).

**PE-4: Evidence quality is not artificial precision.**  
Uncertainty should not be hidden behind false numerical confidence or speculative metrics.

### Human Authority

**HA-1: Consequential decisions require explicitly authorized human judgment.**  
No decision about whether to build a product, validate a market, or commit resources should be silent or implicit.

**HA-2: Human authority is preserved at gates, not compromised by agent capability.**  
Human decision authority at critical transitions is intentional governance, not a limitation to overcome.

**HA-3: Escalation paths are explicit.**  
When evidence is insufficient or disagreement is unresolved, the path to human resolution is clear, not buried in process.

### Assumptions and Hypotheses

**AH-1: Assumptions are surfaced and tracked.**  
Every assumption about customer, problem, market, or technical feasibility is recorded and marked for validation or challenge.

**AH-2: Hypotheses remain testable.**  
A hypothesis that cannot be tested or challenged is classified as assumption, not hypothesis.

**AH-3: Counter-evidence receives first-class treatment.**  
Negative findings, failed searches, contradictory signals are recorded as artifacts with the same formality as positive findings.

### Workflow Discipline

**WD-1: Product intent precedes product evaluation.**  
The statement "We are building X because of Y" must exist before evaluation answers "Does X solve Y?"

**WD-2: Unresolved disagreement may remain visible.**  
Forcing false consensus is not progress. Disagreement may be a valid workflow state when evidence is insufficient.

**WD-3: Technical feasibility is distinct from commercial viability.**  
"We can build it" ≠ "We should build it" ≠ "The market will buy it." These remain separate evaluations.

**WD-4: Marketing claims trace to evidence.**  
Any claim made to customers or stakeholders must be traceable to supporting evidence produced in the workflow.

**WD-5: Implementation may trigger reconsideration.**  
Evidence discovered during building (technical constraints, architectural limits, learned customer needs) may legitimately reopen prior decisions.

**WD-6: Dependent decisions require revalidation when material support changes.**  
Product decisions must not remain silently valid when their material supporting assumptions, evidence, or upstream claims are changed, contradicted, or invalidated.

---

## Goals

### Primary Goals

**G-1: Define PROD-W protocol and governance model**  
Produce an authoritative specification of roles, authority, evidence expectations, challenge paths, provenance, and decision gates that can be implemented in various technical representations.

**G-2: Establish evidence and gate framework**  
Define what kinds of evidence are required or expected for different gates (e.g., customer validation, technical feasibility, market viability). Distinguish objectively checkable requirements from contextual sufficiency judgments, and specify who may make consequential acceptance decisions.

**G-3: Design machine-readable protocol**  
Demonstrate that PROD-W governance semantics can be expressed in a form that is:
- independent of any single AI model or vendor
- machine-readable enough to validate objectively checkable rules
- human-reviewable
- auditable for protocol conformance

**G-4: Produce usable methodology**  
Create practical guidance, role definitions, templates, and decision frameworks that product teams can actually use.

### Research Goals

**RG-1: Evaluate MOD-W transferability**  
Document evidence of MOD-W's applicability beyond software development. Identify software-specific assumptions and domain-neutral generalizations.

**RG-2: Characterize non-software development workflow**  
Define what "implementation," "testing," "review," and "acceptance" mean when the primary artifact is a protocol, schema, or specification rather than code.

**RG-3: Test role model coherence**  
Assess whether existing MOD-W roles (Product Owner, Tech Lead, Development Team, QA, Moderator) remain meaningful for protocol/methodology work or require adaptation.

**RG-4: Explore protocol-based governance**  
Evaluate whether expressing governance as protocol (with machine-checkable rules) is more effective than natural-language instruction.

---

## Non-Goals

**NG-1: Do not select implementation technology prematurely**  
PROD-W will not commit to YAML, JSON, JSON Schema, TypeScript/Zod, a DSL, MCP, or any other representation until design decisions justify it.

**NG-2: Do not build tooling yet**  
PROD-W product definition does not include CLI tools, agent harnesses, validators, or integrations. Those belong downstream.

**NG-3: Do not redesign MOD-W**  
Use MOD-W v5.0.1 faithfully. Adapt locally for non-software context only where necessary. Do not infer that canonical MOD-W must change.

**NG-4: Do not assume every research hypothesis is a requirement**  
Ideas about Product Skeptic roles, DIVERGENT states, Product Knowledge Ledgers, or external evaluators remain hypotheses until evidence justifies them.

**NG-5: Do not force consensus on open questions**  
If disagreement about the product approach or research direction is justified, leave it visible rather than papering it over.

---

## Core Requirements

Requirements are stable, justified commitments. Research hypotheses (Appendix A) remain open.

### Functional Requirements

**FR-1: Protocol must define roles and authority**  
PROD-W protocol must specify:
- Which roles exist
- Which roles may produce evidence
- Which roles may assess, challenge, or verify evidence
- Which decisions require explicitly authorized human acceptance
- Which decisions require human authorization
- Authority scope boundaries and conflicts

**FR-2: Protocol must define governance semantics for progression**  
The workflow must define enough product-claim, evidence, challenge, and gate semantics to make valid and invalid governance actions identifiable. Exact lifecycle graphs, state names, transition mechanics, and protocol serialization are downstream design decisions.

**FR-3: Protocol must define evidence requirements**  
Different gates must specify:
- Required evidence categories where applicable
- Objectively checkable evidence conditions, such as source identification, provenance, independent challenge, or required artifact presence
- Contextual sufficiency judgments that remain human-authorized decisions
- Evidence sourcing rules
- Provenance requirements
- Who may accept evidence

**FR-4: PROD-W governance must make self-approval invalid**  
No role may approve its own output or work. PROD-W must not rely solely on natural-language instruction to prevent self-approval; the governance model must make such approval invalid or detectable as invalid. The exact enforcement mechanism is a downstream architecture/design decision.

**FR-5: Protocol must surface unresolved disagreement**  
When evidence is insufficient or roles disagree, the protocol must provide a way to keep disagreement visible and route it for challenge, additional evidence, or authorized human decision. Exact disagreement states or labels remain design questions.

**FR-6: Protocol must track provenance**  
Every material claim must retain traceable provenance sufficient to identify:
- What the claim is
- Who made it
- When
- What evidence supports it
- Who accepted/challenged it
- Current status

The exact metadata model and whether specific items live in document metadata, protocol state, or another representation remain downstream design decisions.

**FR-7: Material hypotheses require validation or visible unresolved-assumption handling**  
A material hypothesis may only be treated as validated when required evidence and challenge criteria are satisfied.

A project may continue while a material hypothesis remains unvalidated only when the appropriate human role explicitly authorizes conditional progression. In that case:
- the hypothesis remains classified as unvalidated
- the assumption remains visible
- dependent decisions remain traceable to the unresolved assumption
- progression under assumption is not represented as validation

### Governance Requirements

**GR-1: Human authority must be explicit**  
Every consequential decision (problem validation, customer validation, market viability, go/build/no-build) must have an explicitly named human decision point.

**GR-2: Assumptions must be visible and reviewable**  
Product assumptions (about customer, market, problem, technical approach) must be collected, documented, and made available for challenge and validation.

**GR-3: Inference paths must be traceable**  
"If X, then Y" claims must be recorded so that if X proves wrong, consequences can be identified.

**GR-4: Confidence must not hide uncertainty**  
Uncertainty about evidence quality, assumption validity, or inference correctness must not be masked by numerical precision or artificial confidence.

**GR-5: Consequential progression must be gated without assuming one universal linear lifecycle**  
Consequential transitions must have explicit gates, clear evidence requirements where gates exist, traceable progression, and revalidation when material upstream assumptions or evidence change. Product development may loop, branch, revisit earlier assumptions, or reopen prior decisions when new evidence warrants it.

**GR-6: Escalation paths must be defined**  
When evidence is disputed, gaps are identified, or roles disagree, the path to resolution must be clear and documented.

**GR-7: Gate exceptions must remain visible**  
Any gate waiver or override must be explicit, identify the authorized human, include rationale, record provenance, identify which requirement or gate was not normally satisfied, and remain visible as an exception rather than ordinary protocol conformance.

### Research Requirements

**RR-1: Document MOD-W transferability evidence**  
As `prod-w-dev` executes, collect evidence of:
- Which MOD-W patterns apply without modification
- Which assumptions are software-specific
- Where local adaptation occurred
- Whether evidence suggests broader applicability

**RR-2: Define non-software "implementation" and "testing"**  
Establish what constitutes implementation work and verification when the deliverable is specification, schema, or protocol rather than code.

**RR-3: Evaluate role model applicability**  
Assess whether MOD-W roles remain coherent for protocol development. Document conflicts or adaptations needed.

**RR-4: Test protocol-based governance hypothesis**  
Evaluate whether expressing governance as machine-checkable protocol is more effective than natural-language instruction for maintaining workflow discipline.

### MOD-W Transferability Research Governance

`prod-w-dev` maintains a dedicated evidence record under `research/mod-w-transferability/` to document how MOD-W v5.0.1 behaves when used for methodology/protocol development rather than conventional software development.

Any active MOD-W role may propose observations based on direct project experience. The MOD-W Moderator owns the transferability research record, reviews and classifies observations, determines whether observations enter the accepted research record, authorizes local adaptations, maintains the cumulative assessment, and ensures supporting, contradictory, mixed, and unresolved evidence are retained.

Observations distinguish among transfer without modification, transfer with reinterpretation, local adaptation, apparent domain coupling, and not-yet-tested questions, using the working classifications defined in `research/mod-w-transferability/README.md`:
- `TRANSFERS_UNCHANGED`
- `TRANSFERS_WITH_REINTERPRETATION`
- `REQUIRES_LOCAL_ADAPTATION`
- `DOMAIN_COUPLED`
- `NOT_YET_TESTED`

Local adaptations are recorded separately from the observations that trigger them. Canonical MOD-W templates under `mod-w/templates/` must not be modified merely to make the experiment succeed, and no canonical MOD-W change is implied unless a separate canonical MOD-W process later authorizes it.

---

## Key Assumptions

Assumptions are treated as subject to validation or challenge during the project:

**A-1: Protocol representation can be made independent of AI model or vendor**  
Assumption: Governance semantics can be expressed in a form that any agent harness (Claude, Codex, OpenAI, LangGraph, local systems) can evaluate correctly. This is not assumed to be trivial but is assumed to be feasible.

**A-2: Evidence requirements can be operationalized**  
Assumption: Criteria like "customer evidence collected with provenance" or "technical feasibility challenged by an appropriate role" can be made specific enough for protocol support while contextual sufficiency judgments remain available for human authority.

**A-3: Unresolved disagreement will occur and must be manageable**  
Assumption: At least some workflow decisions will reveal justified disagreement, such as conflicting evidence or different risk tolerances. PROD-W must preserve unresolved disagreement as a valid condition rather than treating it as an error or forcing artificial consensus. Whether that condition is represented as an explicit protocol state remains an open design question.

**A-4: Product Moderator authority can be defined and enforced**  
Assumption: A human Moderator role with final decision authority can remain meaningful in workflow even with multiple AI agents. This requires clear authority boundaries and escalation paths.

**A-5: Material claims are distinct from background knowledge**  
Assumption: Product workflow can distinguish "claims we are making about this product" (which require evidence) from "background facts we're using" (which may be assumed). This distinction is important for auditing.

**A-6: MOD-W concepts will transfer with some domain adaptation**  
Assumption (research): MOD-W's role model, cross-validation, and gating structure will prove applicable to protocol/methodology development without fundamental redesign of canonical MOD-W. Local adaptation is expected; redesign is not assumed necessary.

---

## Known Risks

| Risk | Impact | Mitigation |
|------|--------|-----------|
| Protocol design becomes too complex to be practical | Users cannot use PROD-W; burden of conformance exceeds value | Start with minimal protocol; expand only when justified by evidence of need |
| Human authority boundaries remain unclear | Authority either dissolves or becomes capricious | Explicitly define Moderator authority and escalation paths early; review with test users |
| Unresolved disagreement becomes stuck state | Product work halts when evidence is inconclusive | Define progression rules for disagreement (escalate, gather more evidence, document and proceed under assumptions) |
| MOD-W assumptions prove too software-specific | Cannot use MOD-W v5.0.1 without major local changes | Document friction carefully; consider forking local adaptation if required; preserve findings as research evidence |
| Implementation phase reveals structural problems | Major rework of protocol semantics | Validate core protocol concepts with small implementation pilots before full build |
| External evaluators (if used) acquire de facto gate authority | Governance model undermined | Define evaluator role explicitly; ensure authority remains advisory unless explicitly changed by an approved PROD-W revision |
| Evidence sufficiency is treated as fully automatable | Contextual judgment is hidden behind false precision | Separate objectively checkable evidence requirements from human-authorized contextual sufficiency decisions |

---

## Key Open Questions

These questions are intentionally left unresolved for Moderator review and research:

**OQ-1: Should PROD-W define specific product roles (e.g., Product Skeptic, Product Advocate)?**  
MOD-W v5.0.1 does not include these roles. If they are valuable, should they be core or optional in PROD-W?

**OQ-2: What constitutes sufficient customer evidence?**  
Different products require different evidence rigor. Which evidence conditions can be objectively checked, and which sufficiency judgments should remain human-authorized?

**OQ-3: Should unresolved disagreement have an explicit protocol state?**  
Can workflow progress with visible disagreement, or does disagreement always require resolution before advancing?

**OQ-4: Which human roles may accept evidence for consequential gates?**  
Product Owner, QA, and evaluator roles may produce, assess, challenge, or verify evidence, but consequential gate acceptance requires explicit human authorization. The exact assignment model remains open.

**OQ-5: How should advisory external evaluation be incorporated?**  
External evaluators may provide independent findings, challenge claims, identify evidence gaps, provide counter-evidence, or perform conformance/verification work. They do not automatically acquire gate authority; any change to that model would require a future explicitly approved PROD-W revision.

**OQ-6: How should PROD-W handle speed vs. rigor tradeoffs?**  
Is lightweight PROD-W (minimal gates) appropriate for low-risk products? Or should rigor remain consistent?

**OQ-7: Should Product Moderator authority be reviewable/overridable?**  
If Moderator decisions are final, what prevents moderator bias? Does governance require independent review?

**OQ-8: What metadata belongs in protocol state vs. documentation?**  
Should provenance, confidence, and evidence links be protocol state or artifact metadata?

---

## Evidence Expectations

The project will collect evidence of:

**E-1: Protocol feasibility**  
Can core governance semantics be expressed in machine-readable form without becoming unmaintainably complex?

**E-2: User applicability**  
Can real product teams use PROD-W workflow without excessive overhead?

**E-3: Discipline enforcement**  
Does protocol-based governance actually prevent invalid transitions, or do natural-language workarounds emerge?

**E-4: MOD-W transferability**  
Which MOD-W patterns transfer unchanged? Where does local adaptation occur? Is domain coupling found?

**E-5: Role model coherence**  
Do existing MOD-W roles remain meaningful for protocol development? Are software-specific assumptions identified?

**E-6: Evidence quality**  
Does PROD-W governance improve evidence quality and traceability relative to an identified baseline product-development process, comparison case, or prior workflow? The comparison basis must be explicitly documented before drawing conclusions.

**E-7: Authority clarity**  
Does explicit authority definition prevent role confusion and silent decision-making?

**E-8: Workflow progression semantics**  
Do the defined progression, challenge, and gate semantics match the actual workflow of product development, or do gaps emerge?

**E-9: Automated enforceability boundary**  
Which governance checks can be automatically validated because they are objective, and which should be surfaced for human interpretation or gate decision?

---

## Human Authority Boundary

### Authority Types

PROD-W distinguishes authority to produce evidence, authority to assess or challenge evidence, authority to verify formal criteria, and authority to accept consequential gates.

**Evidence production** may include gathering evidence, producing evidence artifacts, and documenting sources.

**Evidence assessment and challenge** may include analyzing evidence, identifying gaps, disputing interpretation, searching for counter-evidence, or verifying whether required evidence exists.

**Evidence verification** may include confirming that defined formal criteria were satisfied and that required checks were performed.

**Consequential gate acceptance** may only be performed by the explicitly authorized human decision role. This includes accepting evidence as sufficient for a consequential product gate, authorizing progression through that gate, or making final go/build/no-build decisions where defined.

### Product Moderator Authority

The **PROD-W Product Moderator** (human only) retains consequential gate authority only where explicitly assigned by the PROD-W workflow. That authority may include:

- Final go/build/no-build decision authority
- Authority to accept evidence as sufficient for a consequential gate or demand additional evidence
- Authority to escalate unresolved disagreement
- Authority to authorize conditional progression under unresolved assumptions
- Authority to resolve role conflicts

Any future gate override or waiver must be explicit, identify the authorized human, include rationale, record provenance, identify the unsatisfied requirement or gate, and remain visible as an exception rather than ordinary protocol conformance.

### AI Agent and Non-Gate Role Authority

AI agents and non-gate roles may:

- Research and propose within evidence constraints
- Produce or document evidence
- Identify gaps and ask for evidence
- Challenge claims and demand justification
- Synthesize findings and present conclusions
- Verify formal criteria when assigned
- Implement or apply approved decisions
- Propose alternative approaches

### Restrictions

No AI agent or non-authorized role may:

- Silently decide that evidence is sufficient for a consequential gate
- Declare a hypothesis validated without required evidence and authorized acceptance
- Override Product Moderator gates
- Approve its own work
- Make final go/build/no-build decisions
- Accept or close disagreement without the required human authority

---

## Success Criteria / Acceptance Intent

Initial PROD-W development is complete and ready for initial release, publication, controlled trial use, or pilot evaluation when:

**Acceptance Criterion 1 — Protocol Definition**  
PROD-W protocol is documented and specifies:
- Role definitions and authority boundaries (no silent roles or implicit authority)
- Governance semantics sufficient to distinguish valid from invalid actions
- Evidence requirements and contextual sufficiency decision points for each consequential gate
- Challenge and escalation procedures
- Provenance and tracking requirements
- Self-approval prevention rules

**Acceptance Criterion 2 — Methodology Guidance**  
Practical guidance is produced:
- Role charters and responsibilities
- Decision workflow with examples
- Evidence types and collection procedures
- Gate criteria with worked examples
- Escalation procedures
- Templates for key artifacts

**Acceptance Criterion 3 — Proof of Concept**  
At least one small product opportunity is taken through PROD-W workflow to demonstrate:
- Protocol rules can be followed without breaking
- Evidence requirements can be operationalized
- Roles remain coherent and non-overlapping
- Unresolved disagreement, if it occurs, can remain visible and be handled without forcing false resolution
- Moderator authority is sufficient to resolve conflicts

One successful proof of concept may provide evidence of feasibility, coherence, usability, gate behavior, role interaction, and protocol execution. It does not prove broad product effectiveness, general commercial value, universal domain applicability, or robustness across product categories.

**Acceptance Criterion 4 — MOD-W Transferability Evidence**  
Documentation of:
- MOD-W concepts that transferred unchanged
- Software-specific assumptions identified
- Local adaptations and their justification
- Whether role model remained coherent
- Whether review and testing concepts adapted meaningfully
- Recommendations for future MOD-W evaluation

**Acceptance Criterion 5 — Research Hypotheses Disposition**  
Each research hypothesis (Appendix A) is classified as:
- Incorporated into PROD-W (with evidence)
- Deferred (with rationale)
- Rejected (with evidence)

---

## Relationship to MOD-W and Product Repositories

### Repository Structure

```text
mod-w/
  MOD-W v5.0.1 (methodology being used and evaluated)
  
prod-w-dev/
  MOD-W-governed development workspace (this project)
  Outputs: PROD-W specification, methodology, evidence, research findings
  
prod-w/
  Published PROD-W protocol and methodology (clean public repository)
  Contains only accepted artifacts
  No development history, failed ideas, or research debate
```

### Artifact Flow

Not every artifact in `prod-w-dev` is promoted to `prod-w`:

- **Promoted**: Protocol specification, role definitions, decision frameworks, evidence templates, successful examples
- **Retained in development workspace**: Research notes, failed approaches, technical disagreements, exploratory artifacts, full decision history

### Governance Relationship

```text
MOD-W v5.0.1
  │
  │ governs (faithfully)
  ▼
prod-w-dev project
  │
  │ produces evidence about MOD-W transferability AND
  │ develops
  ▼
PROD-W protocol and methodology
  │
  │ published in
  ▼
prod-w repository
```

---

## Current Product Status

| Component | Status | Notes |
|-----------|--------|-------|
| Problem definition | Drafted for review | Core problem and failure pattern documented; not yet accepted by MOD-W Moderator |
| Purpose and intent | Drafted for review | Primary and secondary objectives defined; not yet accepted by MOD-W Moderator |
| Core principles | In progress | Candidate principles documented; Moderator review needed |
| Requirements | In progress | Functional, governance, and research requirements drafted; Moderator review needed |
| Protocol concept | In progress | Protocol-first direction stated; detailed specification deferred |
| Methodology concept | In progress | Role framework sketched; detailed guidance deferred |
| MOD-W transferability experiment | In progress | Research governance referenced; evidence record governed separately by MOD-W Moderator |
| Implementation (code/tooling) | Not started | Not in scope for Product Definition phase |

---

## Version and Change History

| Version | Date | Status | Changes |
|---------|------|--------|---------|
| 1.1 | 2026-09-30 | Draft for Moderator Review | Incorporates Moderator review; separates product outcomes from premature protocol mechanics; clarifies authority boundaries; distinguishes MOD-W Moderator from PROD-W Product Moderator; fixes FR-7; removes premature linear lifecycle commitment; formalizes MOD-W transferability research governance; preserves research hypotheses as hypotheses; corrects internal inconsistencies; does not begin architecture or implementation. |
| 1.0 | 2026-09-29 | Draft for Moderator Review | Initial Product Definition. Ready for Moderator review and adjustment before proceeding to next MOD-W phases. |

---

## Next Steps (Deferred)

After MOD-W Moderator approval of this Product Definition:

1. **Architecture Phase** — Tech Lead (Codex) produces `architecture.md`, `domain-language.md`, `roadmap.md`, and first `step-xx.md` based on accepted Product Definition.

2. **Implementation** — Development Team produces PROD-W specification, templates, and proof-of-concept demonstration.

3. **Research Evaluation** — Collect and document MOD-W transferability evidence as work progresses.

4. **Publication** — Accepted artifacts are promoted to `prod-w` repository.

---

## Appendix A: Candidate Principles Not Yet Classified

The following statements from project research are recorded as candidates for further classification:

- **Research Hypothesis: Document Metadata Model** — Document metadata (id, version, created, updated, evidence_as_of) may help separate human-readable working views from machine-readable governance state. Current use in `prod-w-dev` is experimental only; not yet a product requirement.

- **Research Hypothesis: Hybrid Architecture** — A hybrid metadata + central protocol-state architecture may be useful. Deferred to architecture phase.

- **Research Hypothesis: External Evaluators** — External evaluators (e.g., DeepPattern) may benefit from a standardized verification contract. Deferred; not assumed to be core to initial PROD-W.

- **Research Hypothesis: Agent Harness Conformance** — Agent harnesses may eventually be testable for PROD-W conformance (e.g., "Can Claude Code implement this protocol correctly?"). Interesting but deferred; not core to product definition.

- **Research Hypothesis: Protocol-Based MOD-W** — MOD-W itself may eventually benefit from protocol-based architecture. Outside scope; deferred to future MOD-W evolution.

- **Research Hypothesis: Role-Specific Projections** — Role-specific human/agent projections may reduce cognitive load. Interesting design direction; deferred.

- **Research Hypothesis: DIVERGENT State** — DIVERGENT may become a legitimate protocol state for unresolved disagreement. Open question (OQ-3); not yet a requirement.

- **Research Hypothesis: Product Skeptic Role** — Product Skeptic and Product Advocate may be useful roles. Open question (OQ-1); not core to initial PROD-W.

- **Research Hypothesis: Product Knowledge Ledger** — A Product Knowledge Ledger (structured record of all claims, evidence, and decisions) may be valuable. Interesting; deferred to implementation.

- **Research Hypothesis: Null Hypothesis** — A null hypothesis like "This product should not be built" may be useful framework. Open question; deferred.

---

## Appendix B: MOD-W Software-Specific Assumptions to Observe

During `prod-w-dev` execution, the following aspects of MOD-W v5.0.1 will be observed for software-specific coupling:

1. **Development Team role** — MOD-W defines Development Team as writing code. What does implementation mean for a protocol/specification deliverable?

2. **Tech Lead review of code** — MOD-W positions Tech Lead reviewing implementation code. Can Tech Lead meaningfully review protocol semantics and normative language?

3. **QA/Testing framework** — MOD-W emphasizes code testing and build gates. What constitutes testing for a protocol or specification?

4. **Acceptance checks** — MOD-W acceptance criteria often reference runtime behavior. What are equivalent criteria for non-software deliverables?

5. **Architecture role** — MOD-W Tech Lead produces architecture for code organization, patterns, and system boundaries. Does this transfer to protocol/methodology architecture?

6. **Repository structure** — MOD-W recommends specific file layouts and tool configurations. Are these software conventions or methodology fundamentals?

7. **CI/CD and build gates** — MOD-W emphasizes build passes and automated testing. What automation makes sense for protocol development?

These observations will inform the `prod-w-dev` research report and may (but do not necessarily) suggest changes to canonical MOD-W.

---

## References

- README.md — Project purpose and research questions
- research/topics/prod-w-protocol-first-rationale.md — Protocol-first direction and invariants
- research/topics/protocol-schema-state-distinction.md — Core conceptual distinctions
- research/topics/mod-w-beyond-software-experiment.md — MOD-W transferability experiment framing
- research/mod-w-transferability/README.md — Project-level MOD-W transferability research governance
- research/topics/agent-harness-conformance.md — Research hypothesis on protocol-based governance testing
- research/conversations/2026-09-29-prod-w-origin-protocol-research-conversation.md — Research discussion that informed this definition
- mod-w/templates/MOD-W.md — MOD-W v5.0.1 reference methodology
