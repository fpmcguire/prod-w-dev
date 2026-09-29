# PROD-W Development Workspace

> Development workspace for PROD-W, using MOD-W to research protocol-first product development and test MOD-W beyond software engineering.

**Status:** Active research and development  
**Primary methodology:** MOD-W v5.0.1  
**Primary output repository:** `prod-w`

---

## Purpose

This repository is the research and development workspace for **PROD-W — Moderated AI-Assisted Product Development Workflow**.

It has two linked objectives:

1. **Develop PROD-W**
   - research the problem space
   - define the product
   - investigate protocol-first architecture
   - evaluate evidence/governance models
   - produce accepted artifacts for the public `prod-w` repository

2. **Evaluate MOD-W beyond software engineering**
   - use MOD-W v5.0.1 to govern the development of a methodology/protocol rather than a conventional software application
   - observe which MOD-W concepts transfer cleanly
   - identify where MOD-W is coupled to software-development assumptions
   - record evidence that may inform future MOD-W evolution

This repository is intentionally separate from the final PROD-W repository so that the research, failed ideas, competing approaches, reviews, decisions, and MOD-W evidence remain distinct from the product itself.

---

## Repository Relationship

```text
mod-w/
  methodology being used and evaluated

prod-w-dev/
  MOD-W-governed research and development workspace

prod-w/
  resulting PROD-W protocol / methodology
```

The intended relationship is:

```text
MOD-W
  │
  │ governs
  ▼
prod-w-dev
  │
  │ produces accepted artifacts
  ▼
PROD-W
```

Not every artifact created in `prod-w-dev` should be promoted into `prod-w`.

The development repository is expected to contain exploratory and historical material that should remain outside the final product.

---

## Research Questions

The project currently explores several related questions.

### PROD-W

- How should AI-assisted product development be governed?
- How can product claims remain traceable to evidence?
- How should assumptions, hypotheses, inference, and decisions be distinguished?
- How should counter-evidence be represented?
- How should unresolved disagreement be surfaced?
- Which decisions must remain under explicit human authority?
- Can product-development governance be expressed as a machine-readable protocol?
- What should be protocol, schema, state, metadata, or human-readable documentation?

### MOD-W Transferability

- Can MOD-W govern disciplined AI-assisted development of a non-software artifact?
- Do the existing MOD-W roles still make sense?
- What does implementation mean when the deliverable is a protocol or methodology?
- What constitutes review, testing, and QA?
- Which MOD-W concepts transfer unchanged?
- Which assumptions are software-specific?
- Which limitations should be adapted locally versus changed in canonical MOD-W?

### Future MOD-W Protocol Research

This project may also provide evidence for a later investigation into whether MOD-W itself would benefit from a protocol-based architecture.

Potential benefits under investigation include:

- governance independence from specific AI models and vendors
- machine-enforceable authority and transition rules
- agent-harness conformance testing
- integration of external evaluators such as DeepPattern
- more systematic revalidation after upstream changes
- portable and resumable workflow state
- improved provenance and auditability
- role-specific human and agent views
- resilience to rapid changes in AI models and agent frameworks

These are research hypotheses, not current MOD-W requirements.

---

## Important Experimental Constraint

This repository should use **MOD-W v5.0.1 as faithfully as reasonably possible**.

If MOD-W creates friction because a rule assumes conventional software development:

> **Record the friction before changing the methodology.**

Do not modify canonical MOD-W merely to make the experiment succeed.

A useful pattern is:

```text
MOD-W assumption:
Development Team produces executable implementation.

Observed problem:
PROD-W deliverables may instead be protocol definitions,
schemas, governance rules, examples, and research artifacts.

Classification:
Potential domain coupling.

Action:
Adapt locally if required.
Record evidence.
Do not change canonical MOD-W yet.
```

The purpose is to generate evidence about MOD-W transferability rather than redesign MOD-W in advance.

---

## Protocol-First Direction

PROD-W is currently expected to be **protocol-first**.

That means the future normative behavior of PROD-W may be represented through machine-readable rules covering concepts such as:

- roles
- authority
- states
- transitions
- evidence requirements
- challenge requirements
- validation
- provenance
- revalidation
- human decision gates

Human-readable documents and agent instructions may eventually become projections of the protocol rather than the sole normative definition.

The exact protocol representation has **not** been selected.

Possible representations remain research questions.

---

## Human Authority

A core design direction is that consequential product judgments remain under explicit human authority.

AI may:

- research
- propose
- compare
- challenge
- synthesize
- identify uncertainty
- search for counter-evidence
- generate experiments
- analyze results

AI should not silently decide that:

- a problem is real
- evidence is sufficient
- a customer segment is validated
- a product is commercially viable
- a product should be built
- a claim is true
- disagreement has been resolved

The responsible human role is currently described as the **Product Moderator**.

---

## Evidence and Divergence

PROD-W research is based on the principle that repeated AI agreement is not equivalent to independent evidence.

> **Agent agreement is not evidence.**

The project is expected to distinguish among concepts such as:

- FACT
- EVIDENCE
- INFERENCE
- HYPOTHESIS
- ASSUMPTION
- DECISION

Counter-evidence and disagreement are expected to remain visible.

A disagreement may be a legitimate state rather than an error that must be automatically resolved.

This reflects a broader principle also seen in CAV and MOD-W:

> **Surface consequential differences rather than prematurely resolving them.**

---

## Document Metadata Research

One research direction is whether document metadata or related structured representations can help separate:

- human-readable working content
- machine-readable governance state

Possible approaches include:

- metadata embedded in Markdown
- sidecar metadata
- centralized protocol state
- hybrid approaches

This is currently **only a research idea**.

PROD-W has not committed to document metadata as its protocol-state mechanism.

---

## Research Artifact Freshness

Because AI tooling and the surrounding ecosystem evolve rapidly, `prod-w-dev` is experimenting with lightweight research-artifact freshness metadata.

A current candidate pattern is:

```yaml
artifact:
  id: RESEARCH-007
  version: 0.1
  created: 2026-09-29T09:37:00+02:00
  updated: 2026-09-29T09:37:00+02:00
  evidence_as_of: 2026-09-29T09:37:00+02:00
```

The important distinction is:

```text
updated != evidence_as_of
```

A document may be edited without its external research being refreshed.

This convention is experimental and currently applies only to `prod-w-dev` research artifacts.

---

## Research Structure

Current research material is expected to live under:

```text
research/
├── conversations/
├── topics/
└── comparators/
```

### `research/conversations/`

Raw conversation/source archives.

These should remain unchanged once captured.

### `research/topics/`

Derived topic-specific research notes.

Examples:

- protocol-first rationale
- MOD-W protocol-refactor hypotheses
- external evaluators
- harness conformance
- document metadata
- research freshness/versioning
- CAV surfacing vs. monitoring

### `research/comparators/`

Research into adjacent systems and precedents.

Examples include:

- Grove
- Herdr Flow
- SMALL Protocol
- FCoP
- MCP
- A2A
- ADL
- other workflow/governance protocols

---

## MOD-W Artifacts

As the project begins formal MOD-W execution, the repository is expected to contain the normal MOD-W project artifacts, including:

```text
mod-w/
  product.md
  roadmap.md
  step-*.md
  validation/
```

and review/QA artifacts where required by MOD-W.

The exact structure should follow MOD-W v5.0.1 rather than assumptions in this README.

---

## Promotion to `prod-w`

Artifacts should move from this repository into the public `prod-w` repository only after they have reached an appropriate accepted state.

Examples may eventually include:

```text
prod-w/
├── protocol/
├── schemas/
├── docs/
├── examples/
└── conformance/
```

The final structure of `prod-w` has not yet been fixed.

---

## Non-Goals

This repository is not intended to be:

- the final PROD-W distribution
- a polished public specification
- a production agent runtime
- an autonomous product manager
- a generic orchestration framework
- a place to rewrite MOD-W prematurely
- proof that MOD-W is universally domain-independent
- proof that protocol-first architecture is inherently superior

The purpose is to **investigate, build, test, and preserve evidence**.

---

## Working Principle

The current direction can be summarized as:

> **Use MOD-W to develop PROD-W, observe where the methodology transfers or breaks, preserve the evidence, and let those findings inform both PROD-W and any future evolution of MOD-W.**

---

## License

This repository is licensed under the MIT License. See [LICENSE](LICENSE).

---

**`prod-w-dev` is an active research and development workspace. Its terminology, structure, artifacts, and conclusions are expected to change as the experiment progresses.**
