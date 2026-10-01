---
artifact:
  type: roadmap
  version: 0.1
  created: 2026-09-30
  updated: 2026-10-01
  status: Accepted
---

# PROD-W Roadmap

**Project:** PROD-W  
**Date:** 2026-09-30  
**Status:** Accepted

---

## Summary

This roadmap stages PROD-W from semantic architecture to normative protocol, methodology guidance, machine-readable representation, proof-of-concept use, and publication preparation.

The roadmap preserves the Product Definition boundary: do not implement tooling or commit to a representation before the protocol semantics and evidence model justify it.

---

## Governance Context

**This artifact is authored and reviewed under MOD-W v5.0.1 governance.** It plans work in the MOD-W-governed `prod-w-dev` repository.

Roadmap outputs that name `prod-w/` are concrete PROD-W product artifacts to be created by future accepted steps. MOD-W planning, review, and step-control artifacts remain under `mod-w/`.

---

## Steps

| Step    | Title                                                            | Requirement(s)         | Lead interface               | Status   | Notes                                                                                                                                                                                                                                                                      |
| ------- | ---------------------------------------------------------------- | ---------------------- | ---------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| STEP-01 | Define Protocol Semantics and Authority Model                    | FR-1, FR-2, FR-4       | Development Team             | Accepted | Accepted by MOD-W Moderator 2026-09-30 (tag `step-01-complete`); Phase 3a (Tech Lead review), 3b (QA), and 3c (Product Owner sign-off) all waived and recorded as visible exceptions per GR-7/OBJ-12 (`mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Sections 5 and 9). |
| STEP-02 | Define Evidence, Knowledge, and Provenance Model                 | FR-3, FR-6, FR-7       | Development Team             | Accepted | Accepted by MOD-W Moderator 2026-09-30 after Tech Lead approval; completion re-recorded 2026-10-01 after 3b/3c ratification and final D-02 to D-08 dispositions. See `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02.md`, `mod-w/reviews/TECH-LEAD-REVIEW-STEP-02-FOLLOWUP.md`, and `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md` (tag `step-02-complete`). |
| STEP-03 | Define Gate, Challenge, Disagreement, and Revalidation Semantics | FR-2, FR-3, FR-5, FR-7 | Development Team             | Planned  | Defines progression without forcing false consensus. Must resolve open question EK-OQ-17 (authority to designate a correction; producer withdrawal of own counter-evidence), recorded in `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md` (Addendum 2026-10-01).                                                                                                                                                                                                                       |
| STEP-04 | Separate Machine-Checkable Rules from Human Judgment             | FR-3, FR-4, FR-6, G-3  | Development Team             | Planned  | Produces validation boundary and candidate rule catalog.                                                                                                                                                                                                                   |
| STEP-05 | Evaluate Representation Options                                  | G-3, NG-1              | Tech Lead + Development Team | Planned  | Compares YAML, JSON, schemas, metadata, sidecars, centralized state, and hybrids without premature selection.                                                                                                                                                              |
| STEP-06 | Produce Methodology Guidance and Templates                       | G-4, AC-2              | Development Team             | Planned  | Human-usable role charters, evidence guidance, and gate templates.                                                                                                                                                                                                         |
| STEP-07 | Proof-of-Concept Product Opportunity Trial                       | AC-3, E-1-E-9          | Development Team + QA        | Planned  | Runs one small product opportunity through PROD-W.                                                                                                                                                                                                                         |
| STEP-08 | Research Synthesis and Hypothesis Disposition                    | AC-4, AC-5             | Moderator + Tech Lead        | Planned  | Disposes research hypotheses and MOD-W transferability findings.                                                                                                                                                                                                           |
| STEP-09 | Publication Package for Separate `prod-w` Repository             | Output repository      | Development Team             | Planned  | Prepares only accepted artifacts for promotion.                                                                                                                                                                                                                            |

---

## Step Details

### STEP-01

**Goal:** Define the normative protocol semantics for roles, authority, permitted actions, constraints, and self-approval invalidity.  
**Requirements:** FR-1, FR-2, FR-4  
**Output:** `prod-w/protocol-semantics.md`, authority model section, action catalog, invalid-action examples.

### STEP-02

**Goal:** Define the evidence and knowledge model for claims, evidence, counter-evidence, assumptions, hypotheses, inferences, decisions, provenance, dependencies, and revalidation triggers.  
**Requirements:** FR-3, FR-6, FR-7  
**Output:** Knowledge model artifact, provenance requirements, dependency concepts.

### STEP-03

**Goal:** Define gate, challenge, unresolved disagreement, escalation, conditional progression, and revalidation semantics.  
**Requirements:** FR-2, FR-3, FR-5, FR-7  
**Output:** Gate semantics artifact, challenge model, disagreement handling options, revalidation semantics.

### STEP-04

**Goal:** Classify which governance requirements are objectively checkable and which require contextual human judgment.  
**Requirements:** FR-3, FR-4, FR-6, G-3  
**Output:** Rule catalog, human judgment catalog, validation boundary.

### STEP-05

**Goal:** Evaluate candidate technical representations against accepted semantics without treating any one representation as predetermined.  
**Requirements:** G-3, NG-1  
**Output:** Representation decision memo and recommended initial representation experiment, if evidence supports one.

### STEP-06

**Goal:** Produce usable human methodology artifacts aligned with the normative protocol semantics.  
**Requirements:** G-4, AC-2  
**Output:** Role charters, evidence collection guidance, gate templates, examples.

### STEP-07

**Goal:** Run at least one small product opportunity through PROD-W to test coherence, usability, gate behavior, disagreement handling, and protocol feasibility.  
**Requirements:** AC-3, E-1-E-9  
**Output:** Proof-of-concept case record, issues log, validation findings.

### STEP-08

**Goal:** Synthesize research evidence and classify open hypotheses as incorporated, deferred, or rejected.  
**Requirements:** AC-4, AC-5  
**Output:** Research synthesis inputs for Moderator review; hypothesis disposition table.

### STEP-09

**Goal:** Prepare accepted PROD-W artifacts for eventual separate `prod-w` repository publication.  
**Requirements:** Product identity and repository relationship  
**Output:** Publication package, promotion checklist, excluded development/research artifacts list.

---

## Coverage Check

| Requirement                                      | Steps                     | Status  |
| ------------------------------------------------ | ------------------------- | ------- |
| FR-1 Roles and authority                         | STEP-01                   | Planned |
| FR-2 Governance semantics                        | STEP-01, STEP-03          | Planned |
| FR-3 Evidence requirements                       | STEP-02, STEP-03, STEP-04 | Planned |
| FR-4 Self-approval invalid                       | STEP-01, STEP-04          | Planned |
| FR-5 Unresolved disagreement                     | STEP-03                   | Planned |
| FR-6 Provenance tracking                         | STEP-02, STEP-04          | Planned |
| FR-7 Hypothesis validation / visible assumptions | STEP-02, STEP-03          | Planned |
| G-3 Machine-readable protocol                    | STEP-04, STEP-05          | Planned |
| G-4 Usable methodology                           | STEP-06                   | Planned |
| AC-3 Proof of Concept                            | STEP-07                   | Planned |
| AC-4 Transferability Evidence                    | STEP-08                   | Planned |
| AC-5 Hypothesis Disposition                      | STEP-08                   | Planned |
