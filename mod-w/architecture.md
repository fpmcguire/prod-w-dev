---
artifact:
  type: architecture
  version: 0.3
  created: 2026-09-30
  updated: 2026-10-03
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

| Product requirement                                       | Architecture decision(s) | Notes                                                                                            |
| --------------------------------------------------------- | ------------------------ | ------------------------------------------------------------------------------------------------ |
| FR-1 Roles and authority                                  | D1, D4, D8, D10          | Separates actors, roles, authority grants, and human gate authority.                             |
| FR-2 Governance semantics for progression                 | D1, D2, D5               | Protocol semantics govern actions over time; schemas and state remain subordinate.               |
| FR-3 Evidence requirements                                | D3, D6, D7               | Evidence requirements distinguish checkable presence/provenance from human sufficiency judgment. |
| FR-4 Self-approval invalid                                | D4, D6, D10              | Independent authority identity must be distinguishable from producer identity.                   |
| FR-5 Unresolved disagreement visible                      | D5, D7                   | Disagreement is modeled as an attributable condition, not automatically forced into consensus.   |
| FR-6 Provenance tracking                                  | D3, D6, D7               | Provenance is a conceptual layer attached to claims, evidence, challenges, decisions, and gates. |
| FR-7 Hypothesis validation or visible assumption handling | D3, D5, D7               | Hypotheses remain distinct from assumptions and decisions.                                       |
| Governance requirements                                   | D1-D8                    | Human authority and machine-checkable rules are explicitly separated.                            |
| G-3 Machine-readable protocol                             | D2, D6, D8               | Representation is deferred; semantic contracts come first.                                       |
| Acceptance Criterion 4 MOD-W transferability evidence     | D9                       | Architecture-phase transferability evidence is recorded separately under research governance.    |

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

### D10 - Authority Grants Are Conferred by Human-Held Conferral Scope from a Single Establishing Act

**Status:** Accepted  
**Related Requirements:** FR-1, FR-4

**Context:** D4 separates authority grants from role labels but does not say how grants are created, ended, or chained. STEP-01 (`prod-w/protocol-semantics.md`) defines a grant and defers creation, revocation, and self-conferral. STEP-03 routed them to STEP-04. `prod-w/rule-judgment-boundary.md` declared the choices as UAD4-13, UAD4-14, and UAD4-15, with the revised content of UAD4-27, UAD4-28, and UAD4-30. The MOD-W Moderator promoted them on 2026-10-03.

**Decision:**

- Granting is a recorded, attributable act. Conferral requires a human holding AUTH-G whose conferral scope covers the class and scope conferred. A conferral scope is a scope of AUTH-G and not a fifth authority class. It is not delegation and not class-confers-class, and PR-04 and GCR-08 are read that way. The reading remains Moderator-visible.
- A project has exactly one establishing act for its authority chain, recorded by an identified human, preceding every other recorded act of the project. Root grants are only the grants that act records. A root grant has no conferrer. Every other grant chains acyclically to a root grant, and each link must be effective at the act that relies on the grant. A later act marked establishing or root is not a second root.
- Self-conferral is invalid for every later grant: to the conferring identity, to a role position or collective that includes it, or through a cycle of conferral. The establishing identity may be a root grantee only in the establishing act's own grants. Appointment to a role position that carries grants is a conferral. Work assignment is provenance and confers nothing.
- Grants take effect when recorded, never retroactively. A revocation or narrowing is made by the grantee or by a human whose conferral scope covers the grant. Grants downstream of a revoked or narrowed grant fall prospectively with the chain, to the extent the grant no longer covers what they confer. Acts performed while the whole chain was effective stand. Narrowing is an act on the grant and not a revocation plus a conferral.
- Conferral by a conflicted producer, at any link of the chain, and revocation or narrowing that affects the standing of an actor able to challenge, are flagged and escalation-eligible. They are not invalid in this decision. Whether that handling is strong enough is a pilot question.

**Rationale:** A role label alone cannot say who may create authority. Without a bounded root, a chain rule, and an end rule, self-approval can be routed through grants. Human-only conferral keeps consequential authority decisions explicit and human (HA-1, HA-2).

**Consequences:**

- A representation must be able to reconstruct who held what authority as of a point in time, including the chain to a root and which downstream grants have fallen.
- A project has no path to a second establishing act. If every root grant is revoked or renounced, no valid chain can exist again. For a project with one root grantee this is terminal, and a renunciation by that grantee also takes down any successor it conferred. Recovery is by a new project. There is no break-glass, because one would be a way to mint a root. What carries into a new project is not defined here.
- Removal of a grant holder runs one way. Revocation need not come from a holder in the grant's chain. A descendant that revokes an ancestor cuts its own chain. A covering peer can remove a subtree. A rogue sole root grantee cannot be removed without removing its appointees.
- The establishing identity cannot extend its own authority by any route that passes through a grant it conferred. In a project where that identity is the only root grantee, everything it needs for itself must be in the establishing act.
- Root grants are not flagged as conflicted conferral. Authority the establishing identity places in the establishing act is not flagged, even where the grantee later accepts that identity's work. Such a proxy is caught only by challenge, and the pilot is asked for evidence (DP-04).
- This decision does not settle GC-OQ-10 or Product OQ-7 (whether top authority is reviewable or overridable). The removal rule above narrows the space for an answer and does not give one.
- Who holds conferral scopes, and how a project carries out establishment, are methodology and not decided here. Record order and scope containment are representation questions and are not decided here.
- Root legitimacy, and the purpose of a conferral or revocation, are judgments and not checked.

**Detail:** `prod-w/rule-judgment-boundary.md` Sections 10.2 and 10.6, CRC-60 to CRC-64, UAD4-13, UAD4-14, UAD4-15, UAD4-27, UAD4-28, UAD4-30.

---

## Decision Index

| ID  | Title                                                                                       | Status   | Requirements            |
| --- | ------------------------------------------------------------------------------------------- | -------- | ----------------------- |
| D1  | Protocol Semantics Are Normative                                                            | Accepted | FR-1-FR-7               |
| D2  | Protocol, Schema, and State Remain Separate                                                 | Accepted | FR-2, G-3               |
| D3  | Knowledge Classes Are First-Class Domain Concepts                                           | Accepted | FR-3, FR-6, FR-7        |
| D4  | Authority Is Modeled Separately from Role Labels                                            | Accepted | FR-1, FR-4              |
| D5  | Disagreement Is a Preserved Condition, Not Necessarily a State Name                         | Accepted | FR-5, FR-7              |
| D6  | Objectively Checkable Governance Is Separated from Human Judgment                           | Accepted | FR-3, FR-4, FR-6, G-3   |
| D7  | Provenance and Dependencies Support Revalidation                                            | Accepted | FR-6, FR-7, WD-6        |
| D8  | External Evaluators Are Advisory Interfaces Unless Explicitly Granted Authority             | Accepted | FR-1, FR-3, FR-5        |
| D9  | Working Product Artifacts Live Under `prod-w/` in `prod-w-dev`                              | Accepted | Repository relationship |
| D10 | Authority Grants Are Conferred by Human-Held Conferral Scope from a Single Establishing Act | Accepted | FR-1, FR-4              |

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

| Date       | Change                                                                                                                                                                                                                                        | Affected D-IDs          | Reason                                                                                                                                                                      |
| ---------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2026-09-30 | Initial architecture draft                                                                                                                                                                                                                    | D1-D9                   | First Tech Lead architecture-planning phase after Product Definition acceptance.                                                                                            |
| 2026-09-30 | Moderator accepted architecture clarifications and repository staging boundary                                                                                                                                                                | D1-D9                   | MOD-W Moderator approved architecture planning; MOD-W governance artifacts now live under `mod-w/`, while `prod-w/` remains reserved for concrete product artifacts.        |
| 2026-10-03 | Moderator promoted UAD4-13, UAD4-14, UAD4-15 (with UAD4-27, UAD4-28, UAD4-30 and the QA5-02 consequences) from `prod-w/rule-judgment-boundary.md` to an architecture decision, at the Moderator's direction and outside the usual review flow | D10 (new); D4 unchanged | Authority grant creation, chaining, ending, and self-conferral were governed only by a product artifact draft. Record: `mod-w/reviews/MODERATOR-REVIEW-STEP-04-FOLD-IN.md`. |
| 2026-10-03 | Moderator applied Product Owner conditions C-2 and C-3 to D10 Consequences (root grants not flagged; recovery by new project; GC-OQ-10 and Product OQ-7 not settled). Decision text unchanged                                                 | D10                     | Product Owner sign-off, `mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-04.md`. Review of this edit waived. Record: `mod-w/reviews/MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md`.       |
