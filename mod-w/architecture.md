---
artifact:
  type: architecture
  version: 0.1
  created: 2026-09-30
  updated: 2026-09-30
  status: Accepted
  governed_by: MOD-W v5.0.1
source:
  product_definition: mod-w/product.md
---

# PROD-W Architecture

**Project:** PROD-W  
**Date:** 2026-09-30  
**Tech Lead:** Codex  
**Status:** Accepted

---

## Overview

PROD-W should be structured as a protocol-first governance system with replaceable technical representations.

The architecture defines semantic boundaries, authority boundaries, and artifact relationships. It does not yet select YAML, JSON, JSON Schema, TypeScript/Zod, a custom DSL, MCP, A2A, an agent framework, a workflow engine, or a document metadata model.

The central architectural goal is to make product-development governance explicit enough that objectively checkable invalid actions can later be detected, while preserving human judgment for contextual sufficiency decisions.

---

## Governance Context

**This artifact is authored and reviewed under MOD-W v5.0.1 governance.** The MOD-W Moderator (who oversees the `prod-w-dev` development project) is responsible for architecture acceptance and coherence review.

The future "Product Moderator" role defined in this architecture is a PROD-W protocol role that does not yet have consequential authority in `prod-w-dev`. Definitions of future PROD-W roles (Product Moderator, Product Owner within PROD-W, etc.) are aspirational and may not be rewritten or overridden without MOD-W Moderator approval.

Future implementations of PROD-W in separate projects will operate under PROD-W governance; this architecture remains under MOD-W control. The separation is intentional and necessary to preserve the experiment's integrity.

---

## Requirement to Architecture Mapping

| Product requirement | Architecture decision(s) | Notes |
| --- | --- | --- |
| FR-1 Roles and authority | D1, D4, D8 | Separates actors, roles, authority grants, and human gate authority. |
| FR-2 Governance semantics for progression | D1, D2, D5 | Protocol semantics govern actions over time; schemas and state remain subordinate. |
| FR-3 Evidence requirements | D3, D6, D7 | Evidence requirements distinguish checkable presence/provenance from human sufficiency judgment. |
| FR-4 Self-approval invalid | D4, D6 | Independent authority identity must be distinguishable from producer identity. |
| FR-5 Unresolved disagreement visible | D5, D7 | Disagreement is modeled as an attributable condition, not automatically forced into consensus. |
| FR-6 Provenance tracking | D3, D6, D7 | Provenance is a conceptual layer attached to claims, evidence, challenges, decisions, and gates. |
| FR-7 Hypothesis validation or visible assumption handling | D3, D5, D7 | Hypotheses remain distinct from assumptions and decisions. |
| Governance requirements | D1-D8 | Human authority and machine-checkable rules are explicitly separated. |
| G-3 Machine-readable protocol | D2, D6, D8 | Representation is deferred; semantic contracts come first. |
| Acceptance Criterion 4 MOD-W transferability evidence | D9 | Architecture-phase transferability evidence is recorded separately under research governance. |

---

## Current Architecture

### Conceptual Components

1. **Normative Protocol Semantics**
   - Defines roles, authority, permitted actions, constraints, gate semantics, challenge requirements, progression rules, and revalidation semantics.
   - Answers: what is allowed to happen, by whom, and under what conditions?

2. **Domain Knowledge Model**
   - Defines conceptual distinctions among claim, evidence, counter-evidence, assumption, hypothesis, inference, decision, challenge, acceptance, disagreement, dependency, provenance, and revalidation.
   - Prevents collapsing materially different knowledge classes into generic notes.

3. **Artifact Schemas**
   - Future structural contracts for product artifacts.
   - Answer: what does valid structured information look like?
   - Schemas may validate required fields but cannot alone decide authority, sequencing, or sufficiency.

4. **Workflow and Artifact State**
   - Records the current condition of claims, evidence items, challenges, gates, decisions, and work items.
   - Answer: where is this thing now?
   - State is governed by protocol semantics but is not itself the protocol definition.

5. **Provenance and Dependency Layer**
   - Records who made, challenged, reviewed, accepted, or changed an item; when; from what source; and what downstream decisions depend on it.
   - Supports revalidation when material support changes.

6. **Validation Boundary**
   - Separates objectively checkable governance rules from contextual human judgments.
   - Later tooling may check missing provenance, missing required artifacts, self-approval, unauthorized role actions, absent challenge events, or broken dependency references.
   - It must not pretend to decide whether market evidence is persuasive enough or whether a product should proceed.

7. **Human Methodology Guidance**
   - Human-readable instructions, examples, role charters, gate guidance, and templates.
   - Should remain aligned with protocol semantics but may be optimized for understanding and adoption.

8. **Representation Adapters**
   - Future mappings from protocol semantics into concrete formats such as markdown metadata, sidecar files, centralized state, schemas, validators, or agent prompts.
   - These are replaceable implementation choices, not the architecture's foundation.

### Conceptual Flow

```text
Product intent
  -> material claims and hypotheses
  -> evidence, counter-evidence, assumptions, and inferences
  -> challenge and verification
  -> gate decision by authorized human where consequential
  -> dependent decisions and preserved history
  -> revalidation if material support changes
```

---

## Architectural Decisions

### D1 - Protocol Semantics Are Normative

**Status:** Accepted  
**Related Requirements:** FR-1, FR-2, FR-3, FR-4, FR-5, FR-6, FR-7

**Context:** The Product Definition requires a protocol-first approach but explicitly defers representation choices.

**Decision:** PROD-W architecture treats protocol semantics as the normative layer. Human-readable documents, schemas, state records, prompts, and validators are projections or implementations of those semantics.

**Rationale:** Self-approval prevention, authority boundaries, challenge requirements, and gate conditions are behavioral rules. They cannot be fully captured by document prose or structural schemas alone.

**Consequences:** Downstream work must define protocol concepts before choosing serialization or tooling. A schema can support the protocol but cannot replace it.

---

### D2 - Protocol, Schema, and State Remain Separate

**Status:** Accepted  
**Related Requirements:** FR-2, G-3

**Context:** Existing research identifies a recurring risk of conflating protocol, schema, and state.

**Decision:** PROD-W artifacts must preserve the distinction:

- Protocol: allowed actions, authority, constraints, gates, and progression rules.
- Schema: valid structure, fields, and types.
- State: current condition of a claim, artifact, evidence item, gate, or work item.

**Rationale:** This separation keeps future technical representations replaceable and prevents false assumptions that structural validity equals governance validity.

**Consequences:** Later schema work must identify which rules are merely structural and which require protocol validation.

---

### D3 - Knowledge Classes Are First-Class Domain Concepts

**Status:** Accepted  
**Related Requirements:** FR-3, FR-6, FR-7

**Context:** PROD-W exists to prevent weak evidence, inference, assumptions, and agent agreement from hardening into unjustified product confidence.

**Decision:** The domain model must preserve distinct concepts for claims, evidence, counter-evidence, assumptions, hypotheses, inferences, decisions, challenges, acceptances, provenance, dependencies, and revalidation triggers.

**Rationale:** Collapsing these into generic notes would erase the product's core governance value.

**Consequences:** Later templates, schemas, and examples must use these distinctions consistently.

---

### D4 - Authority Is Modeled Separately from Role Labels

**Status:** Accepted  
**Related Requirements:** FR-1, FR-4

**Context:** The Product Definition distinguishes evidence production, challenge, verification, and consequential gate acceptance.

**Decision:** Architecture separates actor identity, role assignment, artifact authorship, review/challenge participation, and authority grants.

**Rationale:** A role label alone is insufficient to detect self-approval or unauthorized gate acceptance. The system must know who produced an artifact, who reviewed or challenged it, and who has authority to accept it.

**Consequences:** Future representations must include enough identity and authority information to make self-approval invalid or detectable.

---

### D5 - Disagreement Is a Preserved Condition, Not Necessarily a State Name

**Status:** Accepted  
**Related Requirements:** FR-5, FR-7

**Context:** The Product Definition requires unresolved disagreement to remain visible but does not require a literal `DIVERGENT` state.

**Decision:** PROD-W architecture must support disagreement as an attributable, evidence-linked, routable condition. The exact representation may later become a state, artifact, property, relationship, or other mechanism.

**Rationale:** The semantic requirement is visibility and routing without false consensus, not a specific serialized label.

**Consequences:** Downstream design should compare representation options before hardening state names.

---

### D6 - Objectively Checkable Governance Is Separated from Human Judgment

**Status:** Accepted  
**Related Requirements:** FR-3, FR-4, FR-6, G-3

**Context:** PROD-W must support machine-readable governance without pretending contextual sufficiency can always be automated.

**Decision:** Architecture defines two validation categories:

- Objectively checkable governance rules, such as missing provenance, self-approval, absent required artifact, missing challenge, unauthorized actor, or absent evidence-category metadata.
- Contextual human judgments, such as whether customer evidence is persuasive, whether commercial risk is acceptable, or whether disagreement is sufficiently resolved.

**Rationale:** This boundary prevents both under-governance and false automation.

**Consequences:** Later validators may block or flag objective invalidity. They may support, summarize, or route contextual decisions, but consequential acceptance remains human-authorized where required.

---

### D7 - Provenance and Dependencies Support Revalidation

**Status:** Accepted  
**Related Requirements:** FR-6, FR-7, WD-6

**Context:** Dependent product decisions must not remain silently valid when material support changes.

**Decision:** PROD-W architecture includes a provenance and dependency layer connecting decisions to supporting claims, evidence, assumptions, hypotheses, challenges, and upstream decisions.

**Rationale:** Revalidation requires knowing what depended on what, what changed, and who is authorized to reaffirm, revise, or retire the affected decision.

**Consequences:** Future state design must preserve prior decision history and distinguish current validity from historical acceptance.

---

### D8 - External Evaluators Are Advisory Interfaces Unless Explicitly Granted Authority

**Status:** Accepted  
**Related Requirements:** FR-1, FR-3, FR-5

**Context:** External evaluators may inspect, challenge, verify, and produce counter-evidence, but the Product Definition does not grant automatic gate authority.

**Decision:** Architecture may define an evaluator interface for advisory findings and conformance evidence, but no evaluator receives consequential gate authority by default.

**Rationale:** This preserves explicit human authority and avoids making DeepPattern or any other evaluator a required dependency.

**Consequences:** Later evaluator contracts must distinguish findings from decisions.

---

### D9 - Working Product Artifacts Live Under `prod-w/` in `prod-w-dev`

**Status:** Accepted  
**Related Requirements:** Product repository relationship, product artifact staging

**Context:** The Product Definition says the final output repository is separate (`prod-w`) and asks architecture to decide how artifacts should be staged in `prod-w-dev`.

**Decision:** Working PROD-W product artifacts should live under `prod-w/` inside `prod-w-dev`.

**Rationale:** This keeps MOD-W governance artifacts (`mod-w/`), transferability research (`research/`), and product artifacts (`prod-w/`) visibly separate while preserving the eventual promotion path to the separate public repository.

**Consequences:** Draft product artifacts are not automatically accepted for publication. Promotion requires MOD-W acceptance and later copying or publishing to the separate `prod-w` repository.

---

## Decision Index

| ID | Title | Status | Requirements |
| --- | --- | --- | --- |
| D1 | Protocol Semantics Are Normative | Accepted | FR-1-FR-7 |
| D2 | Protocol, Schema, and State Remain Separate | Accepted | FR-2, G-3 |
| D3 | Knowledge Classes Are First-Class Domain Concepts | Accepted | FR-3, FR-6, FR-7 |
| D4 | Authority Is Modeled Separately from Role Labels | Accepted | FR-1, FR-4 |
| D5 | Disagreement Is a Preserved Condition, Not Necessarily a State Name | Accepted | FR-5, FR-7 |
| D6 | Objectively Checkable Governance Is Separated from Human Judgment | Accepted | FR-3, FR-4, FR-6, G-3 |
| D7 | Provenance and Dependencies Support Revalidation | Accepted | FR-6, FR-7, WD-6 |
| D8 | External Evaluators Are Advisory Interfaces Unless Explicitly Granted Authority | Accepted | FR-1, FR-3, FR-5 |
| D9 | Working Product Artifacts Live Under `prod-w/` in `prod-w-dev` | Accepted | Repository relationship |

---

## Deferred Decisions

These remain deliberately open:

- Exact protocol serialization.
- Schema language.
- Workflow engine or state-machine implementation.
- Document metadata vs. centralized state vs. hybrid state.
- Whether disagreement becomes a formal state name.
- Whether Product Skeptic or Product Advocate become core roles.
- Whether a Product Knowledge Ledger is an artifact, database, state model, or methodology concept.
- Whether a null hypothesis becomes a required framing pattern.
- Whether evaluator interfaces become core product scope.
- Whether agent harness conformance tooling is part of initial PROD-W.

---

## Constraints

- Do not modify accepted Product Definition without Moderator/Product Owner review.
- Do not modify canonical MOD-W templates under `mod-w/templates/`.
- Do not treat agent agreement as evidence.
- Do not grant AI agents consequential gate authority.
- Do not treat technical feasibility as commercial viability.
- Do not hard-code representation choices before architecture/design evidence supports them.
- Record transferability evidence under `research/mod-w-transferability/`.

---

## Change Log

| Date | Change | Affected D-IDs | Reason |
| --- | --- | --- | --- |
| 2026-09-30 | Initial architecture draft | D1-D9 | First Tech Lead architecture-planning phase after Product Definition acceptance. |
| 2026-09-30 | Moderator accepted architecture clarifications and repository staging boundary | D1-D9 | MOD-W Moderator approved architecture planning; MOD-W governance artifacts now live under `mod-w/`, while `prod-w/` remains reserved for concrete product artifacts. |

