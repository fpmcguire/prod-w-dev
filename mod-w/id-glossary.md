# ID Glossary

**Status:** Reference aid. Not normative and not a governance artifact. If this file disagrees with the source named in the "Defined in" column, the source governs.
**Created:** 2026-10-01 at the MOD-W Moderator's request, to explain the identifier prefixes used across `prod-w-dev` artifacts.
**Updated:** 2026-10-03 (Section 1.1 added).
**Coverage:** Prefixes only. For what a specific item says, follow it to its source.

---

## 1. Product Definition (`mod-w/product.md`)

| Prefix   | Meaning                               | Examples                                                                                                                  |
| -------- | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **G-n**  | Primary goal                          | G-3 machine-readable protocol                                                                                             |
| **RG-n** | Research goal                         | RG-1 evaluate MOD-W transferability                                                                                       |
| **NG-n** | Non-goal                              | NG-1 no premature technology selection; NG-4 research hypotheses are not requirements                                     |
| **FR-n** | Functional requirement                | FR-3 evidence requirements; FR-4 self-approval invalid; FR-6 provenance; FR-7 hypothesis validation or visible assumption |
| **GR-n** | Governance requirement                | GR-2 assumptions visible; GR-7 gate exceptions visible                                                                    |
| **RR-n** | Research requirement                  | RR-1 document transferability evidence                                                                                    |
| **PE-n** | Principle: evidence                   | PE-2 agent agreement is not independent evidence                                                                          |
| **HA-n** | Principle: human authority            | HA-1 consequential decisions need an authorized human                                                                     |
| **AH-n** | Principle: assumptions and hypotheses | AH-3 counter-evidence is first-class                                                                                      |
| **WD-n** | Principle: workflow and decisions     | WD-6 dependent decisions need revalidation                                                                                |
| **A-n**  | Key assumption, subject to validation | A-5 material claims are distinct from background knowledge                                                                |
| **OQ-n** | Product-level open question           | OQ-2 what is sufficient customer evidence                                                                                 |
| **E-n**  | Experiment or evaluation area         | E-2 user applicability                                                                                                    |

### 1.1 Requirement identifiers and acceptance criteria

This section records a Moderator decision made on 2026-10-03. The files named here are the sources.

**Requirement identifiers.** The MOD-W templates (`PRODUCT.md`, `ROADMAP.md`, `STEP-XX.md`, `document-lifecycle.md`) call for "R-IDs" (R1, R2 and so on) as stable identifiers for traceability. `prod-w-dev` does not use the literal R1 form. The Moderator accepted this as a reinterpretation of terminology, not as an adaptation. Read the templates' "R-ID" as "stable requirement identifier".

- In `prod-w-dev` the stable identifiers are the typed identifiers of `mod-w/product.md` listed in Section 1. Roadmap "Requirement(s)" columns and step "Related Requirements" lists cite them, for example FR-3, G-3, NG-1 and E-1 to E-9.
- `mod-w/product.md` is not changed, and no crosswalk to R1-style identifiers exists.
- Routed to STEP-06: templates produced there should say "stable requirement identifier". The upstream MOD-W templates are outside this repository.

**Acceptance criteria.** `mod-w/product.md` lists "Acceptance Criterion 1" to "Acceptance Criterion 5" in prose (section "Success Criteria / Acceptance Intent"), not as `AC-n` identifiers. `mod-w/roadmap.md` cites them as AC-2 to AC-5. Read `AC-n` in the roadmap as "Acceptance Criterion n".

Do not confuse these with step-level checks. STEP-02 numbers its own acceptance checks AC-01 to AC-15 (Section 4), and the STEP-04 artifact uses AC4-nn. "AC-4" (product-level, transferability evidence) and "AC-04" (a STEP-02 check) are different items. Check the file where the identifier appears.

## 2. Architecture (`mod-w/architecture.md`)

| Prefix       | Meaning                         | Examples                                                                                                                             |
| ------------ | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **D1 to D9** | Accepted architecture decisions | D3 knowledge classes are first-class; D7 provenance and dependencies support revalidation; D9 product artifacts live under `prod-w/` |

## 3. STEP-01 protocol semantics (`prod-w/protocol-semantics.md`)

| Prefix                 | Meaning                                                                                                                                           | Examples                                                                                                       |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **AUTH-P / A / V / G** | Authority classes: Production, Assessment and challenge, Verification, Gate (human-only)                                                          | AUTH-G accepts gates                                                                                           |
| **ACT-nn**             | Initial protocol action catalog (7 actions: create claim, attach evidence, challenge, verify, accept gate, request revalidation, record decision) | ACT-06 request revalidation                                                                                    |
| **PR-nn**              | Normative protocol rule                                                                                                                           | PR-16 acceptance by a producer is invalid; PR-26 revalidation; PR-27 configuration is provenance, not identity |
| **INV-nn**             | Worked example of an invalid action                                                                                                               | INV-01 producer accepts own gate                                                                               |
| **OBJ-nn**             | Objectively checkable condition                                                                                                                   | OBJ-10 open revalidation is not recorded as current                                                            |
| **HJ-nn**              | Human judgment the protocol will not automate                                                                                                     | HJ-10 whether a change is material enough to revalidate                                                        |
| **PS-OQ-nn**           | STEP-01 open question routed forward                                                                                                              | PS-OQ-06 may a team be one actor                                                                               |

## 4. STEP-02 evidence model (`prod-w/evidence-knowledge-model.md`)

| Prefix                               | Meaning                                                                                               | Examples                                                      |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| **EKR-nn**                           | Rule stated by the model (41)                                                                         | EKR-10 acceptance applies to the item as accepted             |
| **EKO-nn**                           | Objectively checkable condition (20)                                                                  | EKO-04 evidence identifies a source                           |
| **EKJ-nn**                           | Contextual human judgment (14)                                                                        | EKJ-09 whether a revision changes meaning                     |
| **TRG-n**                            | Revalidation trigger type (5)                                                                         | TRG-2 contradiction                                           |
| **UAD-nn**                           | Choice listed in the Undecided Architecture Declaration, Section 12 (16)                              | UAD-04 acceptance applies to the item as accepted             |
| **EK-OQ-nn**                         | Open question routed to a later step, Section 13.1 (16 in the model)                                  | EK-OQ-05 independence set                                     |
| **EK-OQ-17**                         | Recorded outside the model, in `mod-w/reviews/MODERATOR-REVIEW-STEP-02.md`, Addendum 2026-10-01       | Correction authority; producer withdrawal of counter-evidence |
| **AC-01 to AC-15** (in Section 14.3) | The step's 15 acceptance checks, numbered by the model in the order they appear in `mod-w/step-02.md` | AC-13 declaration present                                     |

## 5. Review and QA records

| Prefix                                        | Meaning                                                                                            | Defined in                                                                                                   |
| --------------------------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| **D-01 to D-08** (QA)                         | Defects raised by QA for STEP-02. Local to that report.                                            | `mod-w/reviews/qa.md`                                                                                        |
| **B-1, B-2, R-1, R-2, A-1 to A-9** (sign-off) | Product Owner sign-off blocking conditions, residual risks and advisory items. Local to that file. | `mod-w/reviews/PRODUCT-OWNER-SIGNOFF-STEP-02.md`                                                             |
| **DTD-nn**                                    | Dev Team discrepancy items from STEP-01                                                            | `mod-w/validation/dev-team-step-01-discrepancy-report.md`; `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` |
| **TLR-nnn**                                   | Tech Lead reconciliation findings                                                                  | `mod-w/validation/tech-lead-reconciliation.md`                                                               |
| **TC-nn**                                     | QA test cases                                                                                      | `mod-w/reviews/qa.md`                                                                                        |

Note: "D-nn" (QA defect) is not "Dn" (architecture decision), and "A-n" (product assumption) is not "A-n" (sign-off advisory item). Check the file the ID appears in.

## 6. Research register (`research/mod-w-transferability/`)

| Prefix           | Meaning                                                                                               | Examples                                                                           |
| ---------------- | ----------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **MW-OBS-nnn**   | Observation of how MOD-W behaved here, with a classification and a Moderator disposition. 012 so far. | MW-OBS-010 role separation loses enforcement when both roles write normative prose |
| **MW-ADAPT-nnn** | Moderator-authorized local adaptation of how MOD-W is applied. 001 so far.                            | MW-ADAPT-001 Undecided Architecture Declaration                                    |

Classification vocabulary used by observations: `TRANSFERS_UNCHANGED`, `TRANSFERS_WITH_REINTERPRETATION`, `REQUIRES_LOCAL_ADAPTATION`, `DOMAIN_COUPLED`, `NOT_YET_TESTED`.

## 7. MOD-W workflow points (`mod-w/templates/MOD-W.md`)

| Point             | Meaning                                                                                       |
| ----------------- | --------------------------------------------------------------------------------------------- |
| 1a / 1b           | Tech Lead writes the step / Moderator confirms it                                             |
| 2a / 2b           | Dev Team restates and plans, Moderator approves / Dev Team implements and runs the build gate |
| 3a / 3b / 3c / 3d | Tech Lead review / QA / Product Owner sign-off / Dev Team addresses findings                  |
| 4a                | Moderator final gate: all checks pass, reviews complete, annotated tag, roadmap advanced      |

---

**Not verified:** product-level "AC-n" acceptance criteria (cited by `mod-w/step-02.md` as "AC-4") were not located by ID in `mod-w/product.md` when this file was written. Section 1.1 now records how they are read. MW-OBS-001 to MW-OBS-007 meanings are not summarised here.
