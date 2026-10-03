---
artifact:
  type: representation-options
  id: PROD-W-RO
  version: 0.1
  created: 2026-10-03
  updated: 2026-10-03
  status: Draft - Development Team work product for STEP-05. Not reviewed. Not accepted.
  produced_by: Development Team
  produced_under: STEP-05
source:
  step: mod-w/step-05.md
  setup_review: mod-w/reviews/MODERATOR-REVIEW-STEP-05-SETUP.md
  step_04_acceptance: mod-w/reviews/MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md
  step_04_post_acceptance: mod-w/reviews/MODERATOR-REVIEW-STEP-04-POST-ACCEPTANCE-TECH-LEAD.md
  architecture: mod-w/architecture.md
  domain_language: mod-w/domain-language.md
  product_definition: mod-w/product.md
  roadmap: mod-w/roadmap.md
  protocol_semantics: prod-w/protocol-semantics.md
  evidence_knowledge_model: prod-w/evidence-knowledge-model.md
  gate_challenge_revalidation_semantics: prod-w/gate-challenge-revalidation-semantics.md
  rule_judgment_boundary: prod-w/rule-judgment-boundary.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Representation Options (Evaluation Memo)

**Product:** PROD-W - Moderated AI-Assisted Product Development Workflow
**Artifact:** Evaluation of candidate technical representations against the accepted protocol semantics, evidence model, gate semantics, and rule/judgment boundary
**Produced under:** STEP-05
**Status:** Draft v0.1. Development Team work product (MOD-W point 2b). Tech Lead review, QA, and Product Owner sign-off have not occurred. Not accepted.

---

## 1. Purpose and Standing

### 1.1 Purpose

STEP-01 to STEP-04 say what the protocol means, what knowledge is, what gates and challenges do, and where objective checking ends and human judgment begins. They deliberately selected no representation (NG-1, D2). This memo asks the next question: **if the accepted semantics were carried by a concrete technical representation, which kinds of representation could carry which parts, what would each need a second mechanism for, and what would choosing one now decide without anyone having decided it?**

It does four things.

1. It defines criteria and applies them to the nine representation families named in `mod-w/step-05.md` (Sections 5 to 8).
2. It tests the families against authority, evidence, challenge, gate, disagreement, exposure, and revalidation semantics (Sections 9 to 11).
3. It disposes of the representation-owned items STEP-04 routed here, including QA5-03 and F-5 (Sections 9.5, 10.2, 12).
4. It says what is rejected for now, whether a later experiment is supported, and what is routed onward (Sections 13 to 15).

### 1.2 Standing

This is a **product artifact** under `prod-w/`. It is an **evaluation only (ROR-01)**. It extends STEP-01 to STEP-04 without editing them. It is not protocol semantics and not a representation. Its tables, identifiers, and labels are expository devices for human review. They are not a schema, a rule language, a state vocabulary, or a lifecycle (ROR-09).

### 1.3 Standing rules of this memo

These rules state the posture of the whole memo. Each restates an accepted rule or follows from one. None adds protocol semantics.

| ID | Rule | Source |
| --- | --- | --- |
| ROR-01 | STEP-05 is evaluation only. It selects no final representation, schema language, storage model, workflow engine, validator, lifecycle graph, serialized state vocabulary, protocol transport, CLI, prompt format, agent harness, runtime integration, database, API, or publication package. | `mod-w/step-05.md`; NG-1, NG-2; D2 |
| ROR-02 | **Schema validity does not equal governance validity.** A record that satisfies every structural requirement may be the product of an invalid action. | PR-25; INV-13; BDR-07 |
| ROR-03 | **Recorded state does not equal protocol authority.** State is an effect of valid actions, not a source of authority. A condition reached by an invalid action does not become legitimate because it is recorded. | `prod-w/protocol-semantics.md` Section 3; PR-11; BDR-09 |
| ROR-04 | **A representation adapter is replaceable and subordinate to accepted protocol semantics.** Replacing the schema, storage model, or tooling must not change which actions are valid. | D1; PR-25; `mod-w/architecture.md`, Representation Adapters |
| ROR-05 | Validator findings, evaluator outputs, and formal-check results are advisory formal-check results. They become consequential only where accepted protocol semantics grant the producing actor the relevant authority. | BDR-13, BDR-17; PR-15, PR-22, PR-23; D8 |
| ROR-06 | Nothing here is scored, weighted, graded, or given a confidence value. The fit labels in Sections 5 and 8 describe how a family relates to a requirement. They are not summed, ranked, or weighted. | BDR-14; EKR-19; `mod-w/step-05.md` Out of Scope |
| ROR-07 | A representation may carry or support the checks that are objectively checkable. The contextual judgments stay with an authorized human. Nothing in any family decides sufficiency, relevance, persuasion, risk, materiality, acceptability, warrant, or substantive independence. | D6; BDR-01, BDR-05, BDR-14 |
| ROR-08 | Where this memo says a representation "must" do something, it means: to carry the accepted requirement cited beside it. Where such a consequence is not a verbatim reading of the accepted text, it is declared in Section 15.3 (UAD5) and is Moderator-visible. | MW-ADAPT-001 |
| ROR-09 | Record elements are defined by semantic role, not by field name, column, key, edge label, or state value. No serialized name or vocabulary is selected. | BDR-11, BDR-18 |
| ROR-10 | The absence of a check in a representation does not relax a requirement. Where a representation cannot compute a condition, the condition falls to human review until a computation exists, and the representation must say so. | BDR-07; `rule-judgment-boundary.md` Section 9.5 |

### 1.4 Limits stated plainly

- **This is desk analysis by one producer.** It is the Development Team's reading of the accepted artifacts. No family was built, run, or tried on a record. Every fit label is a judgment a reviewer can sample (Section 2.4).
- **The comparison is not exhaustive.** Families are classes. Named products, libraries, and languages are not evaluated individually. Where a class has well-known members (for example, structural schema languages), they appear only as examples of the class.
- **Absence of a favorite is a finding, not a gap.** No family carries the accepted semantics alone. Section 7 and Section 13 say what that implies.

---

## 2. Governance Context

### 2.1 Authority

**This artifact is authored under MOD-W v5.0.1 governance.** The MOD-W Moderator governs STEP-05 acceptance for `prod-w-dev`. The Development Team produced this memo and may not accept it. The future **PROD-W Product Moderator** is a protocol role being defined by the product and has no authority over STEP-05 (`mod-w/step-05.md`, Governance Context). Where this memo says an act requires "a human holding AUTH-G", it states a property of the future protocol (PR-24).

### 2.2 MW-ADAPT-001

The STEP-05 work package does not restate MW-ADAPT-001, but `rule-judgment-boundary.md` Section 14.4 listed "hidden representation choices" as a sampling area for STEP-04, and `mod-w/step-05.md` asks the Tech Lead to sample this memo for hidden representation selection. This memo therefore (a) lists, option by option, the hidden decisions that selecting the option now would make (Sections 6 and 13.2), and (b) declares its own choices in Section 15.3. As in STEP-04, the Development Team cannot certify that it found every hidden choice.

### 2.3 Review sequence

| MOD-W point | Expected handling per `mod-w/step-05.md` | Standing for this deliverable |
| --- | --- | --- |
| 2a Plan approval | Development Team may proceed directly unless the Moderator requests a checkpoint | Not held. The setup review authorizes direct implementation |
| 2b Development Team work product | Development Team drafts the artifact | This artifact (v0.1) |
| 3a Tech Lead review | Expected before final acceptance. Samples for hidden representation selection, protocol/schema/state collapse, loss of STEP-04 boundaries | Pending |
| 3b QA | Expected before final acceptance unless the Moderator waives it beforehand. Samples option coverage, traceability, criteria, carry-forward routing | Pending |
| 3c Product Owner sign-off | Expected before final acceptance unless waived beforehand | Pending |
| 4a Moderator acceptance | Only after required reviews or recorded waivers | Pending. Not recorded by this memo |

### 2.4 Production note and reading coverage

Produced by the Development Team using Claude Code (model `claude-sonnet-5-5`). Every check in Section 18.2 was run by the producer. That is self-review: it confers no independence and no verification for gate purposes (PR-27, PR-28). Any reviewer who is also a Claude-family model is not independent of this producing configuration.

**Reading coverage.** The accepted inputs total roughly 980 KB, and one of them (`rule-judgment-boundary.md`) is about 528 KB, which is more than a single read of the file allows. The Development Team did not read every input in full. What was read:

- Read in full: `mod-w/step-05.md`; the STEP-05 setup review; the STEP-04 acceptance and post-acceptance records; `mod-w/architecture.md`; `mod-w/roadmap.md`; `prod-w/protocol-semantics.md` Sections 3 to 11; the research notes on document metadata, agent skills, and protocol/schema/state.
- Read in full from `rule-judgment-boundary.md`: Sections 1 to 6.2 (all catalog entries CRC-01 to CRC-64), 6.5, 6.6, 9, 10.1, 10.2 (through item 6 of 10.2.2), 10.4 to 10.6, 11, 12, 13.8 to 13.10, and 14.1, 14.4 to 14.6.
- Read by search or row extraction only: `rule-judgment-boundary.md` Sections 6.3, 7, 8 (selected rows), 10.2.3 to 10.3, 13.1 to 13.7, 14.2 (rows truncated), 15, 16, 17; STEP-02 and STEP-03 (selected rules, definitions, and open-question rows, and STEP-03 Section 8); `mod-w/product.md` (selected requirements and open questions); `mod-w/domain-language.md` (naming rules and selected terms).
- Not read: `research/topics/agent-harness-conformance.md`, `product-definition-skill.md`, and `prod-w-compliance-skills-pattern.md`; `mod-w/step-04.md`; the STEP-04 Tech Lead and QA review records (except the QA5-03 entry of `QA-REVIEW-STEP-04-REVISION.md`); `research/mod-w-transferability/adaptations.md` and `assessment.md` (found by search only); and most of `research/mod-w-transferability/observations.md` (MW-OBS-016 and the register header were read).

A statement in this memo about an accepted rule that was read only by extraction is a statement about the extracted text. Reviewers should sample those first (Section 16).

### 2.5 Declared choices

This memo makes choices that a reasonable alternative reading would not have made. They are listed in Section 15.3 (UAD5-01 to UAD5-17) with proposed levels, and each is cited from where it is applied. Level scale as in STEP-04: **A** architecture-level candidate; **M** model-level; **L** low. ROR-08 governs how a consequence read from the accepted text is distinguished from a new rule.

---

## 3. Relationship to Accepted Architecture D1 to D10

| Decision | How this memo uses it |
| --- | --- |
| **D1** Protocol semantics are normative | Every option is evaluated as a projection of the semantics. Where an option would silently redefine a semantic (for example, a state field that reads as authority), the memo records it as a hazard (ROR-03, ROR-04) |
| **D2** Protocol, schema, and state remain separate | The core evaluation boundary. Section 7 evaluates protocol, schema, and state support separately for every option. Section 12.5 and 12.6 apply D2 to lifecycle graphs and state vocabulary |
| **D3** Knowledge classes are first-class | Options are tested for carrying claim, evidence, assumption, hypothesis, inference, decision, challenge, dependency, provenance, and revalidation as distinct (Sections 10, 11) |
| **D4** Authority is modeled separately from role labels | Section 9 tests identity, capacity, grants, scope, and independence. No option may resolve authority from a role name or a document byline |
| **D5** Disagreement is a preserved condition, not necessarily a state name | Section 11.3 and 12.6. No option is required to make disagreement a fixed serialized state, and none is selected |
| **D6** Objective checks are separated from human judgment | Section 8. The memo distinguishes what a representation can check from what an authorized human must judge (Section 8.6) |
| **D7** Provenance and dependencies support revalidation | Sections 10 and 11. Version-binding, as-of reconstruction, and derived conditions are tested per option |
| **D8** External evaluators are advisory | ROR-05. Section 12.7 (formal-check result form) keeps results distinguishable from acts |
| **D9** Working artifacts live under `prod-w/` | This memo lives at `prod-w/representation-options.md`. Promotion to a separate `prod-w` repository is a publication matter. Portability is criterion RC-14 |
| **D10** Authority grants, single establishing act | Section 9. The D10 consequence "a representation must be able to reconstruct who held what authority as of a point in time" is tested per option (Section 9.3) |

---

## 4. Representation-Neutral Vocabulary

These definitions are for this memo. They are proposed for the Moderator's later glossary disposition and are not edited into `mod-w/domain-language.md`.

| Term | Definition in this memo |
| --- | --- |
| **Protocol representation** | Any encoding of the protocol's rules (the catalog, handling categories, authority conditions) in a machine-readable form. Two degrees are distinguished: (1) **catalog metadata** (rule identity, sources, evaluation kind, handling, judgment pair) and (2) **executable rule logic**. This memo evaluates degree 1 and treats degree 2 as an evaluator question that is not selected. The semantics remain normative either way (D1) |
| **Schema representation** | A statement of valid structure: fields, types, required elements, the shape of references. It answers "what does a valid record look like". It cannot decide authority, sequencing, independence, or sufficiency (`protocol-semantics.md` Section 3) |
| **State representation** | A way of showing the current recorded condition of an item. Accepted semantics make the conditions derivable from the record (GCR-35, EKR-40; Section 12.1). A state representation is therefore a projection or cache of the record unless a later accepted revision says otherwise (UAD5-04) |
| **Record element** | A unit of information defined by its semantic role, which a rule, a visibility requirement, or a record form reads or carries: for example, the acting identity of an action, the recorder of a relationship, the conferrer of a grant, the basis-presentation designation of a claim (Section 10.2). It is not a field name, column, key, edge label, or state value (ROR-09) |
| **Adapter** | A mapping from record elements and semantics into a concrete carrier, including view generators and the binding of an evaluator to a carrier. Replaceable and subordinate to the semantics (ROR-04). It holds no authority |
| **Carrier** | The data holder an adapter maps into (a document, a file of records, a store). The family names in Section 6 are carriers or carrier conventions |
| **Evaluator** | A mechanism that applies rule logic to a record at an evaluation point and produces formal-check results. It is not a representation. Its form is not selected. Every family in Section 6 needs one for any rule beyond single-record presence (Section 8.2) |
| **Formal-check result** | As in `rule-judgment-boundary.md` Section 4.10: the record of applying a named rule at a named evaluation point to named record elements, with an outcome. This memo adds only its recording form (Section 12.7) |
| **Machine view** | A projection of the record arranged for machine reading or enforcement. Non-normative. It names the record and the evaluation point it projects (UAD5-09) |
| **Human view** | A projection of the record arranged for a human reader. Non-normative. It must preserve the visibility invariants of Section 12.4 |
| **Hybrid design** | A defined arrangement of two or more families with a stated source of truth for acts and relationships (Section 6.8). It is a design with tradeoffs, not a compromise between families |
| **Experiment** | A bounded, later, separately authorized task that tests a stated representation question with named inputs and signals and produces findings, not decisions. Its encodings are not accepted architecture (Section 14) |

### 4.1 Layers used in the analysis

The Tech Lead recommended keeping the analysis layered. The layers used are: **L1** protocol semantics (normative, outside every family), **L2** structural schema, **L3** state record (acts and recorded conditions), **L4** human document, **L5** machine view, **L6** agent-facing instructions. A family is evaluated for each layer it could occupy. The same technology can occupy several layers, and the memo keeps them apart.

### 4.2 Demand classes

To compare families against the 64 catalog entries without evaluating each entry per family, this memo groups the questions the catalog asks of a record into seven **demand classes** (CD-1 to CD-7). The classes are an analytic device of this memo (UAD5-02). They are not a rule language, a taxonomy of rules, or a classification of any STEP-04 entry. The mapping from catalog entries to classes (Section 8.1) is a reading a reviewer can sample.

| Class | The record must support | Examples (entries) |
| --- | --- | --- |
| **CD-1** | **Presence of required elements in one record** (including that a required designation or rationale exists) | CRC-01, 05, 11, 23, 25, 26, 30, 34, 37, 39, 43, 45, 48, 60 |
| **CD-2** | **Reference and identity resolution**: a link, identity, or source resolves to a recorded item | CRC-01, 36, 38, 40, 49 |
| **CD-3** | **Relation and set data**: producer sets, citation chains, dependency links, grant chains, as inputs to a computation | CRC-06, 07, 08, 12, 13, 27, 44, 53, 61, 62 |
| **CD-4** | **Order, history preservation, and as-of reconstruction** | CRC-14, 16, 21, 24, 41, 42, 55, 56, 61, 63 |
| **CD-5** | **Derived conditions**: contested, exposed, open requirement, current validity, disagreement, assumption-rooted | CRC-18, 19, 28, 29, 32, 33, 47, 50, 51, 52, 54 |
| **CD-6** | **Attribution and actor-kind integrity**: that the recorded identity and kind are the ones that acted | CRC-01, 03 |
| **CD-7** | **Visibility in views**: a condition, flag, marker, or challenge appears wherever the item appears | CRC-18, 28, 47; `rule-judgment-boundary.md` Section 9.2 (F, X); GCR-29 |

### 4.3 Fit labels

Fit labels say how a family relates to a demand. They are descriptive, they are not scores, and they are never summed or ranked (ROR-06).

| Label | Meaning |
| --- | --- |
| **Nat** | Native. The family's data model gives the needed access without a project-specific convention. Rule logic is still applied by an evaluator |
| **Con** | Convention. Possible only through a project-specific convention that is itself undeclared structure. Nothing in the family checks it. A tool that interprets the convention is a hidden schema |
| **2nd** | Needs a second mechanism, named in the cell or note. The family holds inputs but the demand needs something it does not contain |
| **Can't** | The family cannot carry the demand, with or without convention |
| **Nat†** | Native to the data model, but the authority that assigns record position (who says what came first, and when) is a separate mechanism no family supplies (Section 10.4) |

For comparison criteria (Section 5) the labels are **Strong**, **Partial**, **Weak**, and **n/a**, with **Low / Moderate / High risk** for RC-15. **The weakest cell governs** when a question needs several classes (UAD5-03).

---

## 5. Evaluation Criteria

The criteria below are applied to every family and every hybrid design. They are **not weighted** and not equally important. No total, ranking, or average is computed. A Strong cell is not a recommendation (ROR-06).

| ID | Criterion | The question | Source |
| --- | --- | --- | --- |
| RC-01 | **Protocol/schema/state separation** | Can the layers stay distinguishable when this family is used? Does the family invite merging them (for example, a status field read as authority, or a schema constraint read as a governance rule)? | D2; PR-25 |
| RC-02 | **Semantic coverage** | How much of the accepted record vocabulary can the family carry without a second mechanism? | D3; Sections 8 to 11 |
| RC-03 | **Authority, identity, and D10 reconstruction** | Can it carry identity, capacity, grants, conferral scope, the establishing act, chains, revocation cascade, and as-of reconstruction? | D4; D10 |
| RC-04 | **Provenance and version-binding** | Can it carry producing configuration, source lineage, evidence basis, and bind a reference to the version in force at an act? | D7; CRC-38, 39, 42 |
| RC-05 | **Independence support** | Can it support identity-based independence over producer sets, append-only for independence? | PR-17; CRC-07, 14 |
| RC-06 | **Challenge, disagreement, gate, and exception support** | Can it carry challenge, closure, disagreement answerability, gate basis, standing record, and visible exception? | D5; STEP-03 |
| RC-07 | **Revalidation and derived-condition support** | Can derived conditions be obtained from the record, not stored, and do triggers and open requirements follow? | D7; GCR-35; CRC-51 |
| RC-08 | **Rule/judgment boundary preservation** | Does the family keep checkable elements checkable and judgment-bearing content from being checked, scored, or reported as decided? | D6; BDR-05, BDR-14 |
| RC-09 | **Auditability** | Order, history preservation, as-of reconstruction, and visibility of invalid acts | CRC-41; EKR-09; PR-11 |
| RC-10 | **Tamper locality** | Can the producer of an item alter records about that item (challenges, acceptances, grants) as a side effect of editing it? | BDR-09, BDR-10; CRC-41 |
| RC-11 | **Human readability and review ergonomics** | Can a reviewer read and challenge the record without tooling or the author? | G-4; HA-1 |
| RC-12 | **Diffability** | Do changes show up as reviewable differences? | MOD-W review practice |
| RC-13 | **View derivability** | Can human and machine views be generated from it while preserving the visibility invariants? | EK-OQ-15; OQ-8 |
| RC-14 | **Portability** | Can it move into a separate `prod-w` repository and across tools and agent harnesses without lock-in? | D9 |
| RC-15 | **Premature-selection risk** | How many decisions does choosing it now make that no accepted artifact has made? | NG-1, NG-2 |

**Not evaluated: burden.** The effort of recording, flag volume, and false-positive cost are pilot evidence (DP-01, STEP-07). The memo notes direction only where an option plainly adds or removes recording work.

---

## 6. Option Comparison

Nine families (RO-01 to RO-09). Each entry uses the same headings. "Cannot carry alone" lists the accepted semantics the family cannot carry without something outside it. "Hidden decisions" lists what choosing the family now would decide without a decision being made.

### 6.1 RO-01 Markdown body conventions and tables

- **What it is.** Prose, headings, tables, lists, and identifiers by convention. The working medium of the accepted artifacts and of MOD-W.
- **Natural layer.** L4 human document; methodology; the expository catalog form used in STEP-01 to STEP-04.
- **Strengths.** Best human readability and review ergonomics (RC-11, RC-12). Judgment-bearing content (rationales, limitations, declarations) belongs in prose, and prose does not pressure it into a score. Reviewers already work in it.
- **Limits.** The accepted artifacts state that their tables and identifiers are expository devices and not a protocol representation (`protocol-semantics.md` Section 10; `rule-judgment-boundary.md` Section 1.2). Nothing checks an identifier pattern, link, or table convention. A hyperlink or an ID in a table cannot carry the recorder, time, kind, materiality designation, and removal rationale a relationship must have (CRC-49; EKR-33, EKR-36). Edits are in place. History exists only through an outside mechanism. The STEP-04 catalog tables are already at the edge of what a reviewer can hold at once.
- **Cannot carry alone.** CD-3 to CD-6 (Section 8.2); version-binding; tamper locality; derived conditions (a human can derive them by reading, no mechanism can).
- **Second mechanism needed.** A parser for the conventions (a hidden schema), an evaluator, and an order source.
- **Hidden decisions if selected now.** Table columns and ID patterns become an undeclared schema; headings become item boundaries; link syntax becomes the relationship record; version control becomes the order source (and with it the meaning of "recorded").
- **Suitable only as.** Human document, human view, methodology support, and report format for advisory output.

### 6.2 RO-02 YAML frontmatter

- **What it is.** A structured metadata block at the head of a document.
- **Natural layer.** L3 for item-level identity and provenance; L5 machine-readable part of a human document. Not a schema, not a rule carrier.
- **Strengths.** Provenance and identity stay with the artifact, which is the stable-identity half of the hybrid the research note proposes to investigate. Line-based diff (RC-12). Visible to a human opening the file. Compact for item-level elements: class, producers, time, producing configuration facets, derived-from links.
- **Limits.**
  - *Granularity.* One frontmatter per document gives one record per document. Claims, evidence entries, and challenges inside a document need their own identity, which the family does not provide.
  - *Write control.* Acts by others on the item (a challenge, an acceptance, a revocation) either sit in the target's frontmatter, under the producer's edit control, or live elsewhere. The first is a tamper-locality failure (RC-10): the producer can alter or remove records about its own item, against CRC-41 and BDR-10.
  - *In-place mutation.* A `status` field is stored state (D2 hazard, Section 12.1).
  - *Parse variance.* Implicit typing, duplicate keys, and dialect differences mean the same text can parse to different records. That is a threat to the agreement corollary (`rule-judgment-boundary.md` Section 4.3).
  - A bare list of IDs cannot carry the recorder and time of a relationship.
- **Cannot carry alone.** Acts by other actors safely (CD-4, RC-10); order; as-of; chains; derived conditions; attributed relationships without nested records.
- **Hidden decisions if selected now.** Item equals document; field names and placement; where acts go; nesting depth; whether a `status` field exists (a state vocabulary); the YAML dialect or safe subset.
- **Suitable only as.** Item-level identity and provenance metadata (conditional). Stored condition fields are a hazard, not a role.

### 6.3 RO-03 JSON documents

- **What it is.** Structured data documents, including line-delimited streams of records as an arrangement variant.
- **Natural layer.** L5 machine view; L3 record-per-act data; interchange.
- **Strengths.** Unambiguous parse and a strict data model; suitable for machine views and for one-record-per-act arrangements; easy to apply a structural schema to (RO-04); an append convention is possible with line-delimited streams.
- **Limits.** Poor for human review of reasoning content. No comments. No native references, identity, or order. The data model forces conventions for time, large numbers, and absent values. Diff noise unless a canonical formatting is fixed (itself a decision).
- **Cannot carry alone.** CD-2 to CD-6 beyond holding data; human readability; order authority.
- **Hidden decisions if selected now.** Key names and nesting; one document per record or an aggregate; stream or document; canonical form (needed for stable diff or any hash); time encoding.
- **Suitable only as.** Machine view, record-of-acts data (conditional), advisory tool output, cache of derived conditions.

### 6.4 RO-04 Structural schemas (JSON Schema or equivalent)

- **What it is.** A statement of valid structure applied to a carrier: required elements, types, conditional presence, reference shape. "Or equivalent" names the class of structural definition languages (declarative, type-system-based, or grammar-based). None is selected and none is evaluated individually.
- **Natural layer.** L2 only.
- **Strengths.** The one family built for CD-1. Conditional presence ("if X then Y") fits record forms such as the four elements of a challenge (CRC-26), the nine elements of a conditional progression authorization (CRC-23), and the four elements of a grant (CRC-60). A closed shape can keep accidental score or verdict fields out of a record. Machine-checkable and versionable.
- **Limits.**
  - *Reach.* A schema checks one record. Cross-record resolution, sets, chains, order, and "acceptor is not in the producer set of the closure" are outside it.
  - *Rule creep.* Encoding governance conditions as conditional constraints invites reading a schema pass as governance validity, which is INV-13 (ROR-02).
  - *False adequacy.* A required non-empty string satisfies "a rationale is present" and says nothing about adequacy. Presence only is the correct report (handling N, `rule-judgment-boundary.md` Section 9.7).
  - *Vocabulary lock-in.* An enumerated list in a schema becomes a de facto state or value vocabulary (BDR-11).
  - A schema revision is not a protocol revision. Classification of a condition changes only by an accepted revision of the boundary artifact (BDR-16).
- **Cannot carry alone.** Everything but CD-1; it also holds no data.
- **Hidden decisions if selected now.** Language, dialect, and version; open or closed objects; use of enumerations; extension policy; cross-file references; ID patterns.
- **Suitable only as.** Schema support (L2). Its output is an advisory structural finding.

### 6.5 RO-05 Markdown plus sidecar files

- **What it is.** A human document with a separate machine metadata file bound to it.
- **Natural layer.** L4 document plus L3/L5 metadata.
- **Strengths.** Keeps the human view uncluttered, which is the human/machine split the research note proposes. A sidecar can be a separate write domain, so a challenger can record in its own file (RC-10 improved). One sidecar can hold metadata for several items in a document.
- **Limits.** Two sources of truth. Which governs when they disagree? The binding mechanism (name, path, content hash, or ID) is a design decision and also the weak point: a rename or move breaks identity, and acceptance "as the item stood" (CRC-42) needs a binding to a specific version. A reviewer reads two files. Orphaned and stale sidecars are likely.
- **Cannot carry alone.** CD-3 to CD-6; binding integrity; the content format of the sidecar (it pulls in a choice among RO-02, RO-03).
- **Hidden decisions if selected now.** Pairing rule; sidecar granularity (per document, per item, per act); sidecar format; drift handling; who may write a sidecar.
- **Suitable only as.** Human document with attached machine metadata; methodology support. Record-of-acts role is conditional on the binding and write-control decisions.

### 6.6 RO-06 Centralized protocol-state or registry file

Two subfamilies are kept apart because the accepted semantics treat them differently.

- **RO-06a Registry.** A central list of identities, actors, grants, sources, and item identifiers.
- **RO-06b Stored condition state.** A central record of each item's current condition as a stored value.
- **Natural layer.** RO-06a: L3 records and a resolution namespace. RO-06b: L3 state, which is where D2 and the accepted semantics both warn.
- **Strengths.** A single namespace makes reference and identity resolution easy (CD-2). A grant register makes the D10 chain easy to traverse if each grant records its conferrer. Good machine view.
- **Limits.**
  - *Stored authority.* RO-06b is the pattern ROR-03 warns about: a stored value can look like authority.
  - *Stored derived conditions go stale.* Contested, exposed, open requirement, current validity, and disagreement are derived conditions (GCR-35, EKR-40). A stored "current" mark is invalid while a requirement is open (CRC-51).
  - *Overwrite.* Updating a state value in place violates CRC-41 and EKR-09 unless every change is kept.
  - *Single write domain.* One file or store is one tamper surface (RC-10) and a merge-conflict site.
  - *Vocabulary.* Stored values are a state vocabulary (D5, BDR-11). The Product Owner's note on GC-OQ-04 says EKR-09, EKR-33, EKR-40, and GCR-35 must not be read as selecting a ledger or central state model.
- **Cannot carry alone.** History (RO-06b); derived conditions without staleness; attribution truth; a human view.
- **Hidden decisions if selected now.** What the registry holds (identity or condition); the state vocabulary; the write protocol and locking; format; single store or one per project; who may write.
- **Suitable only as.** RO-06a: resolution namespace and machine view, if every change is kept as a record. RO-06b: a cache or projection only, never a source.

### 6.7 RO-07 Graph or ledger-style relationship records

Two ideas are separated because only the first is already implied by accepted semantics.

- **Relationship records.** Each relationship (derives-from, supports, contradicts, depends-on, produced-by, conferred-by, member-of, successor-of) is a first-class record with its recorder, time, kind, and designations. Accepted semantics require relationships to be assertions by exactly one identity (CRC-01), dependency links to carry a materiality designation with recorder and time (CRC-49; EKR-33), and removal to carry a rationale (EKR-36). A bare link cannot do that (UAD5-05).
- **Ledger-style properties.** Append-only, ordered, attributable records of acts, with history preserved (CRC-41; EKR-09; CRC-14).
- **Neither idea implies** a graph database, a distributed ledger, hash chains, signatures, or a Product Knowledge Ledger. That last item is a deferred decision (`mod-w/architecture.md`, Deferred Decisions; NG-4), and this memo does not decide it.
- **Natural layer.** L3.
- **Strengths.** Closest data-model fit to the accepted notion of "the record". Chains, cycles, closure, and producer sets are relation queries. As-of reconstruction follows from ordered records. Derived conditions are computed, not stored. Views can be projected from it.
- **Limits.**
  - *Readability.* Needs projection for a human (RC-11 weak).
  - *Infrastructure creep.* A store, a ledger technology, tamper evidence, and identity binding (keys) can each enter unnoticed, against NG-2.
  - *Order is not truth.* A ledger preserves order. It does not say an appended act was valid. An unauthorized act can still be appended and is invalid (BDR-09; ROR-03).
  - *Order authority.* Position in the record must be assigned by something other than the actor claiming it (Section 10.4).
  - Recording every act as a separate record raises recording burden (DP-01).
- **Cannot carry alone.** Attribution truth (CD-6); the evaluator; scope containment; a human view.
- **Hidden decisions if selected now.** Events or states as the record; ID scheme; whether relationships are reified; store technology; tamper evidence; canonical serialization; the granularity of "an act"; whether the Product Knowledge Ledger question is thereby decided.
- **Suitable only as.** Record of acts and history (the role it fits best) and the basis for generated views. Not a human document and not a state store.

### 6.8 RO-08 Hybrids

Hybrid is a family of designs with tradeoffs, not an automatic compromise. Combining families does not inherit each one's strengths. It adds a **binding problem** (keeping the parts consistent) and a **hidden decision** (which part is the source of truth when parts disagree). The designs below differ in where **acts and relationships** live.

| Design | Source of truth for acts and relationships | Composition | What it buys | What it costs |
| --- | --- | --- | --- | --- |
| **H-1 Item-embedded** | The target item's own frontmatter | RO-01 + RO-02, optionally RO-04 | Co-location; cheapest; readable | Producer controls records about its item (RC-10). In-place edits. No order, no as-of. Stored fields tempt derived conditions |
| **H-2 Record-per-act, reference-inward** | Small records for each act, relationship, and designation. Each references what it concerns, so the referencing record holds the assertion. Item content stays in documents | RO-01 + RO-02 for items, RO-03 or RO-02-style data for acts, RO-04 for shape, an evaluator, generated views | Tamper locality improves (a challenge is the challenger's record). Derived conditions are computed. As-of and chains follow. Views are generated | Many small records. Human reading needs generated views. Order authority needed. More hidden decisions at once (RC-15 High) |
| **H-3 Central record-first** | One consolidated structured record (registry plus events) | RO-06a + RO-07, documents as views or attachments | One namespace. Strong machine view. Easy resolution | One write domain (RC-10 weak). Human reading is of generated views only. Merge friction. Risk of drifting into RO-06b if it stores conditions |
| **H-4 Embedded identity, central mutable state** | Identity and provenance in frontmatter. Current conditions in a central stored file | RO-02 + RO-06b | Familiar split between "document" and "workflow state". The hybrid the research note proposes to investigate | Stored conditions are the form ROR-03 and Section 12.1 warn against. Overwrite loses history. A stored condition can diverge from the record |

**For every hybrid, the unresolved question is the same:** where is a disagreement between parts decided? Accepted semantics give one answer: the record of acts governs, and any projection, cache, or document that disagrees with it is wrong (UAD5-04). A hybrid that cannot say which part is the record has not answered the question.

### 6.9 RO-09 Agent instructions and skill/prompt conventions

These are **representation-adjacent**. They do not hold a record. They tell actors how to produce one.

- **Natural layer.** L6.
- **What accepted semantics already say.** Instructions are part of producing configuration (PR-27; UAD4-11 holds that skills are instructions, covered when the instruction statement resolves to what was given). A skill is not an actor and holds no authority. A skill's output must not be read as verification or acceptance (PR-14, PR-15). Shared skills used by producer and challenger reduce *substantive* independence while identity independence stands (HJC-12; `research/topics/agent-skills-and-protocol-relationship.md`).
- **What they cannot do.** Carry a record element, check anything, enforce anything, or authenticate anyone. Instruction text may be dropped later in a session. For a rule that must hold every time, the documentation directs authors to a hook, not a skill. The pattern of a boundary held only as prose against prose is MW-OBS-010.
- **H-C (skills as generated projections of the protocol).** The hypothesis depends on a normative machine-readable source existing, which is what this step evaluates and does not select. This memo can say: H-C is not testable until a representation exists; if ever tried, a generated instruction set is a non-normative projection that names the protocol version it projects, holds no authority, and is not an enforcement mechanism. Disposition of H-A, H-B, H-C is STEP-08.
- **Hidden decisions if selected now.** A skill file format, the harness that reads it, a trigger policy, and the assumption that instructions reliably persist. All are agent-harness and prompt-format decisions (out of scope).
- **Suitable only as.** Methodology support and, in the form of agents producing advisory findings, advisory tooling support. Not a representation of protocol, schema, or state.

### 6.10 Comparison against the criteria

**Families RO-01 to RO-07 and RO-09.** † Strong for the schema layer only. RO-09 is not a record representation, so record-bound criteria are n/a.

| Criterion | RO-01 Markdown | RO-02 YAML FM | RO-03 JSON | RO-04 Schema | RO-05 Sidecar | RO-06 Central | RO-07 Graph/ledger | RO-09 Agent instr. |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| RC-01 Separation | Partial | Partial | Partial | Strong† | Partial | Weak | Partial | n/a |
| RC-02 Coverage | Weak | Partial | Partial | Weak | Partial | Partial | Strong | n/a |
| RC-03 Authority / D10 | Weak | Weak | Partial | Weak | Weak | Partial | Strong | n/a |
| RC-04 Provenance, version-binding | Partial | Partial | Partial | Partial | Partial | Partial | Strong | n/a |
| RC-05 Independence | Weak | Partial | Partial | Weak | Partial | Partial | Strong | n/a |
| RC-06 Challenge, gate, exception | Partial | Weak | Partial | Weak | Partial | Partial | Strong | n/a |
| RC-07 Revalidation, derived | Weak | Weak | Weak | Weak | Weak | Weak | Strong | n/a |
| RC-08 Rule/judgment boundary | Partial | Partial | Partial | Partial | Partial | Partial | Partial | Weak |
| RC-09 Auditability | Weak | Weak | Weak | Weak | Weak | Weak | Strong† | n/a |
| RC-10 Tamper locality | Weak | Weak | Partial | n/a | Partial | Weak | Partial | n/a |
| RC-11 Readability | Strong | Partial | Weak | Partial | Partial | Weak | Weak | Strong |
| RC-12 Diffability | Strong | Strong | Partial | Strong | Strong | Partial | Partial | Strong |
| RC-13 View derivability | Weak | Partial | Strong | n/a | Partial | Strong | Strong | n/a |
| RC-14 Portability | Strong | Partial | Strong | Partial | Partial | Partial | Partial | Partial |
| RC-15 Premature-selection | Moderate risk | Moderate risk | Moderate risk | High risk | Moderate risk | High risk | High risk | High risk |

† Strong for RC-09 in RO-07 means native to the data model. The authority that assigns record position is a separate mechanism (Section 10.4).

**Reading notes.**

- **RC-08 does not discriminate among record families.** Every family is Partial, because the boundary between checkable elements and judgment-bearing content is kept by how an evaluator and the handling categories are designed, not by the carrier. That is a finding: no family protects the boundary by itself.
- **RO-07 has the most Strong cells and the most High-risk and Weak ones where cost shows up** (RC-11, RC-15). The count of Strong cells is not a recommendation. The criteria are not equally important, and this memo assigns them no weights.
- **RO-04's Strong separation is only for its own layer.** A schema keeps L2 distinct. It does nothing for L1 or L3.

**Hybrid designs.**

| Criterion | H-1 Item-embedded | H-2 Record-per-act | H-3 Central record-first | H-4 Embedded + central state |
| --- | --- | --- | --- | --- |
| RC-01 Separation | Partial | Strong | Partial | Weak |
| RC-02 Coverage | Partial | Strong | Strong | Partial |
| RC-03 Authority / D10 | Weak | Strong | Strong | Partial |
| RC-04 Provenance, version-binding | Strong | Strong | Strong | Strong |
| RC-05 Independence | Partial | Strong | Strong | Partial |
| RC-06 Challenge, gate, exception | Weak | Strong | Strong | Partial |
| RC-07 Revalidation, derived | Weak | Strong | Strong | Weak |
| RC-08 Rule/judgment boundary | Partial | Partial | Partial | Partial |
| RC-09 Auditability | Weak | Strong† | Strong† | Weak |
| RC-10 Tamper locality | Weak | Partial | Weak | Weak |
| RC-11 Readability | Strong | Partial | Weak | Partial |
| RC-12 Diffability | Strong | Strong | Partial | Partial |
| RC-13 View derivability | Partial | Strong | Strong | Partial |
| RC-14 Portability | Strong | Partial | Partial | Partial |
| RC-15 Premature-selection | Moderate risk | High risk | High risk | High risk |

**Reading notes.** H-2 and H-3 fit alike on the semantic criteria because both keep acts as records and compute derived conditions. They differ on tamper locality, readability, and the source of truth. H-2 is not preferred because it has more Strong cells. Its costs (readability, many records, High risk) are exactly what an experiment would need to test before anything is decided (Section 14).

### 6.11 Suitable roles

S Suitable. C Conditional on the restriction or second mechanism noted. X Not suitable. Hybrids are not listed: a hybrid's suitability is that of its parts plus its binding mechanism (Section 6.8).

| Family | Protocol catalog metadata | Schema support | State support | Record of acts and history | Human document | Machine view | Methodology support | Advisory tooling output |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| RO-01 Markdown | C (expository only, as in STEP-04) | X | X | X | S | X | S | S (reports) |
| RO-02 YAML frontmatter | X | X | C (item-level provenance and identity; a stored condition field is a hazard) | C (item level only) | C | C | X | X |
| RO-03 JSON | C (catalog metadata as data) | X | C (cache or projection) | C (record-per-act files) | X | S | X | S |
| RO-04 Structural schema | C (shape of catalog entries only) | S | X | X | X | X | X | C (structural findings) |
| RO-05 Sidecar | X | X | C (projection beside a document) | C | S | C | S | X |
| RO-06 Central | C (registry of catalog entries) | X | C (cache only. X as an authoritative source) | C (only if every change is kept) | X | S | X | X |
| RO-07 Graph/ledger | X | X | X (derive instead) | S | X | C (basis for generated views) | X | X |
| RO-09 Agent instructions | X | X | X | X | C (agent-facing guide) | X | S | C (agents producing advisory findings) |

**Suitable only as** (the Scope's request):

- **Schema support only:** RO-04.
- **State support:** no family is suitable as an authoritative source. RO-03 and RO-06 are suitable as caches or projections.
- **Methodology support:** RO-09, and RO-01 as a human document.
- **Advisory tooling support:** RO-04 output, RO-03 output, and RO-09 (agents producing advisory findings).

---

## 7. Protocol / Schema / State Fit Table

D2 requires that protocol, schema, and state be evaluated separately for every option. Each cell says what the family can do for that layer, and the last column says what it cannot carry alone.

| Family | Protocol layer (rule catalog and rule logic) | Schema layer (valid structure) | State layer (records of acts and recorded conditions) | Cannot carry alone |
| --- | --- | --- | --- | --- |
| **RO-01 Markdown** | Catalog metadata only, as prose and tables. Not machine-readable. No rule logic | None. Conventions are an undeclared schema | Prose accounts of acts and conditions. Not mechanically readable | CD-3 to CD-6; version-binding; tamper locality; derived conditions; visibility invariants beyond convention |
| **RO-02 YAML FM** | Not a catalog carrier | None. Holds fields; nothing defines required ones | Item-level provenance and identity. Acts by others only under the producer's edit control. Stored conditions are a hazard | Safe acts by others; order and as-of; chains; attributed relationships; derived conditions |
| **RO-03 JSON** | Catalog metadata as data. No rule logic | None alone. Pairs naturally with RO-04 | Record-per-act data possible; no order or identity of its own | CD-2 to CD-6; human readability; order authority |
| **RO-04 Schema** | Shape of catalog entries only. Cannot carry rule logic that crosses records | **The schema layer.** Presence, types, conditional presence, reference shape | None. It holds no data and checks nothing about acts | Everything except CD-1. Authority, sequencing, independence, sufficiency (`protocol-semantics.md` Section 3) |
| **RO-05 Sidecar** | Not a catalog carrier | None alone | Metadata beside a document, as a second source of truth | Binding integrity; order; as-of; derived conditions; attribution |
| **RO-06 Central** | Registry of catalog entries is possible. No rule logic | None alone | **RO-06a:** identity, grant, and source registries. **RO-06b:** stored conditions (hazard: derived values stored as authority) | History (RO-06b); derived conditions without staleness; attribution; human view |
| **RO-07 Graph/ledger** | Not a catalog carrier. Rule logic runs as an evaluator over it | Typed record kinds are a structural definition, written in whatever language | **Records of acts and relationships with order.** Derived conditions are computed from it, not stored | Attribution truth; order authority; scope containment; the evaluator; human readability |
| **RO-09 Agent instructions** | None. Instructions are not the protocol | None | None | Everything. It carries no record element, checks nothing, enforces nothing, authenticates no one |
| **H-1 to H-4** | See Section 6.8. A hybrid adds an evaluator to every design. The evaluator's form is not selected | RO-04 can be a component | H-2/H-3 hold records of acts. H-1 and H-4 hold conditions in documents or a stored file | See 6.8. H-4 cannot carry history of its stored state |

**Reading.** No family and no hybrid carries the accepted semantics alone. The only layer a family is built for is RO-04 for L2. The protocol layer's logic belongs to an evaluator in every design. The state layer's best fit is a record of acts with derived conditions (RO-07 properties, H-2, H-3). The hybrid that stores conditions (H-4, RO-06b) is the one ROR-03 and Section 12.1 warn against.

---

## 8. Rule/Judgment Boundary Fit

This section shows how the STEP-04 candidate rules, recorded-judgment checks, contextual judgments, and violation-handling categories would be supported, or not supported, by each family. It reclassifies nothing (BDR-16). It adds no rule.

### 8.1 Catalog entries by demand class

The mapping is the Development Team's reading of the CRC entries. Where an entry needs several classes, each is listed. A reviewer can sample any row.

| Family of entries | Dominant demands | Notes |
| --- | --- | --- |
| **A. Attribution and authority** CRC-01 to 05 | CD-1; CD-2; CD-3 and CD-4 for authority at the act; CD-6 for attribution and actor kind | CRC-02 needs the grant chain as of the act. CRC-01 and 03 check a recorded designation (HJC-21) |
| **B. Independence** CRC-06 to 14 | CD-3 (closure, producer sets); CD-2; CD-4 for append-only producers (CRC-14) | CRC-07 is set difference over the accepted set. No schema can compute it |
| **C. Gate acts** CRC-15 to 25 | CD-1 (required elements); CD-4 (definition before act; effective when recorded; not backdated); CD-5 for CRC-18, 19 | CRC-22 is a composite over other entries |
| **D. Challenge, disagreement** CRC-26 to 33 | CD-1 (CRC-26, 30, 31); CD-3 (closer qualification); CD-5 (CRC-28, 29, 32, 33) | |
| **E. Provenance, evidence** CRC-34 to 41 | CD-1; CD-2 (CRC-36, 38, 40); CD-4 (CRC-41) | CRC-36's concurrence limb applies only where the record distinguishes sourced evidence from concurrence |
| **F. Knowledge classes, dependencies, revalidation** CRC-42 to 54 | CD-1; CD-3 (grounding, assumption-rooted); CD-4 (CRC-42); CD-5 (CRC-47, 50 to 54) | CRC-54 is deferred (DR-04). CRC-45: Section 10.2 |
| **G. Correction, supersession, withdrawal** CRC-55 to 59 | CD-4 and CD-2 (identity across change, CRC-55, 56); CD-1 (CRC-59 content); CD-5 | CRC-56 needs polarity, target, source, scope, and dependency links as discrete fields to compare versions |
| **H. Authority grants** CRC-60 to 64 | CD-1 (CRC-60); CD-3 and CD-4 (CRC-61 to 63); CD-5 (CRC-64) | CRC-61 needs the establishing act first in the record. CRC-63 needs as-of reconstruction |

### 8.2 Fit by demand class

For CD-3 and CD-5 the label means the family gives the **inputs** natively. The rule logic is applied by an evaluator in every case, and no family supplies one.

| Demand | RO-01 | RO-02 | RO-03 | RO-04 | RO-05 | RO-06 | RO-07 | RO-09 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **CD-1** Presence in one record | Con | Con | Con | Nat | Con | Con | Nat | Can't |
| **CD-2** Reference and identity resolution | Con | Con | Con | Can't | Con | Nat | Nat | Can't |
| **CD-3** Relation and set data | Con | Con | Con | Can't | Con | Con | Nat | Can't |
| **CD-4** Order, history, as-of | 2nd (order source, history) | 2nd | 2nd | Can't | 2nd | 2nd | Nat† | Can't |
| **CD-5** Derived conditions | 2nd (inputs not machine-reachable) | 2nd | 2nd | Can't | 2nd | Con (stores rather than derives) | Nat (inputs and order) | Can't |
| **CD-6** Attribution and actor-kind integrity | Can't | Can't | Can't | Can't | Can't | Can't | Can't | Can't |
| **CD-7** Visibility in views | Con | Con | 2nd (view generator) | Can't | Con | 2nd | 2nd | Con (unenforced) |

Notes.

- **CD-1 for RO-07 is Nat** because typed act and relationship records are themselves a structural definition. Whether that definition is written in a schema language (RO-04) is a separate choice.
- **CD-6 is Can't for every family.** This is not a gap in any family. No representation can establish that the identity recorded is the one that acted, or that a human acted. Section 9.5.
- **Hybrids.** H-2 and H-3 take Nat or Nat† in CD-2 to CD-5. H-1 and H-4 take Con or 2nd. All hybrids add an evaluator.

### 8.3 Recorded-judgment checks

A recorded-judgment check confirms only the eight facets of `rule-judgment-boundary.md` Section 4.5. It never decides the judgment's substance (BDR-05). The facet is supportable for a family to the extent of the **weakest** demand class it involves.

| Facet | Demand classes involved | What bounds it |
| --- | --- | --- |
| **Existence** (a judgment record exists where required) | CD-1 | Presence only. A non-empty string is not an adequate rationale |
| **Recorder identity** (an identified actor of the required kind) | CD-2, CD-6 | The recorded kind is checked. Whether the identity is who acted is HJC-21 (Section 9.5) |
| **Authority** (the recorder held a covering grant at the act) | CD-2, CD-3, CD-4 | Needs the grant chain as of the act. Only the Nat† cells reach it without extra machinery |
| **Capacity** (acted in the recorded capacity) | CD-1 | One capacity per action (PR-08) |
| **Required elements** (the elements the form requires are present) | CD-1 | A schema (RO-04) is the natural check. It reports presence, not adequacy |
| **Timing** (the record precedes the act; not backdated) | CD-4 | Needs an order the recorder does not control (Section 10.4) |
| **Independence** (recorder is not a producer of the set favored) | CD-2, CD-3 | Identity-based only. Substantive independence is HJC-12 |
| **Direction** (the act is favorable or conservative, read from a closed list) | CD-1, CD-3 | The act kind must be a discrete element. An unrecorded kind is unresolved (CRC-09; UAD4-31) |

### 8.4 Contextual judgments

For every contextual judgment (HJC-01 to HJC-26), every family has the same relationship: **it can hold the recorded judgment** with recorder, time, and rationale, **it can surface the residue** for a human, **and it cannot decide, prefill, score, or summarize the substance** (BDR-14). The derived judgments at the edge of a check (HJC-21 to HJC-26) are the ones most likely to be mistaken for checkable.

| Judgment at the edge of a check | Why a representation cannot take it |
| --- | --- |
| HJC-21 Attribution and actor-kind accuracy | Any credential or recorded identity can be used by an actor who is not its holder (Section 9.5) |
| HJC-22 Legitimacy of the establishing act | The record shows an establishing act exists, first. It does not show real-world standing |
| HJC-23 Purpose of a conferral or revocation | Only the chain and the producer-of-set relation are in the record |
| HJC-24 Decidability of a criterion or rule | A checkability designation is recorded. Whether it is right is judgment |
| HJC-25 Containment of a scope stated by description | Containment is decidable only where scopes are references (Section 9.4) |
| HJC-26 Adequacy of configuration and lineage | Presence and "not determinable" are recorded. Adequacy is the acceptor's |

### 8.5 Violation-handling categories

Handling categories are semantic effects, not state names, values, or mechanisms (BDR-11). The table says what a representation has to provide for the effect to be carryable at all.

| Category | What a representation must provide | Where families fall short |
| --- | --- | --- |
| **I** Invalidating | The invalid act or ineffective designation stays recorded and visible as invalid. Check results are distinct from acts. Recorded as the event the source names (a CRC-59 finding for an invalid acceptance) | Families that overwrite in place (RO-01 to RO-03, RO-05, RO-06) can delete the attempt. Only append-only arrangements keep the attempt |
| **B** Blocking candidate | An evaluation point between recording an act and reliance on it, with inputs available. Blocking may never prevent the *record* (BDR-09, BDR-10) | Blocking is not a property of any family. It needs an enforcement point outside the representation. The representation's job is to keep the attempt recorded and to make the evaluation point identifiable (F-5; Section 9.5) |
| **F** Flagging | The flag appears wherever the item appears and in the standing record of any acceptance citing it. Cleared only by a recorded act | CD-7. Hand-authored views drop flags |
| **E** Escalating | An escalation record (CRC-31) and the resolving authority derived from grants | Needs current grants (CD-3, CD-4) |
| **U** Recorded as unresolved | An "unresolved" outcome that is distinct from "satisfied" and from "no result", and that no clock clears | A family where "no check ran" and "satisfied" look the same fails BDR-06 |
| **X** Visible exception | An exception record with the CRC-20 content, a result "satisfied under exception" distinct from "satisfied", and a marker that travels with the acceptance (CD-7) | Hand-authored views can drop the marker |
| **N** No automated conclusion | Presence-or-absence reporting only. No verdict, score, grade, weight, or confidence field | A closed shape (RO-04) can refuse stray score fields. Nothing prevents an evaluator writing prose that reads as a verdict |

### 8.6 What a representation can check, what an authorized human must judge

This is the distinction ROR-07 requires, drawn from the tables above.

| A representation, with an evaluator, can help check | An authorized human must judge | No one can determine from the record |
| --- | --- | --- |
| That an element is present, in the required form, from a recorded kind | Whether the element is adequate, warranted, or sufficient | Whether the record is complete (BDR-06, HJC-21) |
| That the acceptor is not a recorded producer of any member of the accepted set (identity only) | Whether two distinct identities are substantively independent (HJC-12) | An undisclosed contribution or relationship nobody recorded (Section 1.4 of the boundary artifact) |
| That a grant chain reaches a root and is acyclic, as of an act | Whether the establishing act is legitimate (HJC-22); the purpose of a conferral (HJC-23) | That an identity recorded as human is a human (Section 9.5) |
| That a derived condition follows from recorded links and acts | Whether a change undermines a dependent; whether a disposition adequately addresses its reason (HJC-16) | Whether the record's attributions match what happened |
| That a result names its rule, evaluation point, and elements examined (CRC-59) | Whether the rule asserted violated is decidable (HJC-24) and whether the acceptance should be reaffirmed | |
| That a closure names every open reason with a disposition | Acceptance, refusal, deferral, validation, waiver: any gate-class determination (PR-13) | |

---

## 9. Authority and Identity Analysis

### 9.1 What the accepted semantics require

- **Identity.** One acting identity per action; stable and distinguishable; a role label, tool, model, session, or byline is not an identity (PR-06, PR-07). Configuration is provenance and not identity (PR-27).
- **Capacity.** Exactly one participation capacity per action; not merged retroactively (PR-08).
- **Grants.** Each grant records grantee, authority class, scope, granting authority, and a time. Absent any, it is not a grant (PR-02; CRC-60). A grant takes effect when recorded (CRC-24, CRC-60).
- **D10 chain.** Conferral requires a human holding AUTH-G whose **conferral scope** covers what is conferred. A project has exactly one establishing act, first in the record; root grants come only from it; every other grant has an acyclic chain to a root; each link is effective at the relying act; self-conferral is invalid; revocation or narrowing is by the grantee or a covering human holder and cascades prospectively; narrowing is an act on the grant (CRC-61 to CRC-63).
- **Independence.** By identity. Producer sets are append-only. Collectives expand to recorded members (GCR-08; CRC-07, CRC-14).
- **D10 consequence.** A representation must reconstruct who held what authority **as of a point in time**, including the chain to a root and which downstream grants have fallen.

### 9.2 Requirements used for the per-option test

R1 Identity recorded and resolvable, kind recorded. R2 One capacity per action. R3 Grant recorded with its four elements and its conferrer. R4 Scope containment decided where scopes are references. R5 Establishing act first, root grants only from it. R6 Acyclic effective chain to a root as of the relying act. R7 Self-conferral and cycle detection. R8 Revocation or narrowing as an act on the grant, with prospective cascade. R9 Producer sets append-only, with the acceptor outside the producer set of the accepted set. R10 Collective membership and work-assignment relations recorded. R11 Conflicted-chain flag (CRC-64). R12 As-of reconstruction of authority.

### 9.3 Fit by option

| Req. | RO-01 | RO-02 | RO-03 | RO-04 | RO-05 | RO-06 | RO-07 | H-1 | H-2 | H-3 | H-4 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| R1 | Con | Con | Con | Can't | Con | Nat | Nat | Con | Nat | Nat | Nat |
| R2 | Con | Con | Con | Nat | Con | Con | Nat | Con | Nat | Nat | Con |
| R3 | Con | Con | Con | Nat | Con | Con | Nat | Con | Nat | Nat | Con |
| R4 | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | Con | 2nd | Con | Con | 2nd |
| R5 | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | Nat† | 2nd | Nat† | Nat† | 2nd |
| R6 | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | Nat† | 2nd | Nat† | Nat† | 2nd |
| R7 | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | Nat† | 2nd | Nat† | Nat† | 2nd |
| R8 | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | Nat† | 2nd | Nat† | Nat† | 2nd |
| R9 | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | Nat† | 2nd | Nat† | Nat† | 2nd |
| R10 | Con | Con | Con | Can't | Con | Con | Nat† | Con | Nat† | Nat† | Con |
| R11 | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | Nat† | 2nd | Nat† | Nat† | 2nd |
| R12 | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | Nat† | 2nd | Nat† | Nat† | 2nd |

RO-09 is Can't for every row.

**Reading notes.**

- **Only record-of-acts arrangements (RO-07 properties, H-2, H-3) reach R5 to R12 without a second mechanism.** Every other cell says the same thing: grants and revocations can be written down, but "who held what, as of when" is a computation over ordered history, and that history comes from somewhere else (a version-control history, a log). Where that source is a version-control history, "recorded" acquires the version-control meaning of the term (Section 10.4).
- **R4 is Con even for the best fit.** Scope containment needs a recorded scope vocabulary and a containment relation. No family supplies either (Section 9.4).
- **R11 (the conflicted-chain flag) is an evaluator output** in every column. The Nat† cells mean only that the chain and producer-of-set data are natively reachable.
- **H-4 loses R12.** If current grants are held as stored state and overwritten, the as-of chain is gone, which fails the D10 consequence.
- **Tamper locality shapes R3 and R8.** A grant or revocation recorded in a file the grantee or the revoked holder can edit is not safely recorded (RC-10). Write control is environment, not representation (RQ-17).

### 9.4 Scope vocabulary, containment, collectives, and work assignment

**Scope vocabulary and containment (DR-08, RJ-OQ-04).** `rule-judgment-boundary.md` Section 10.2 says containment is decided where scopes are references, and that a scope stated by description is a designation with a judgment residue (HJC-25). This memo adds three representation-level points (UAD5-15).

- A containment decision is mechanical only where a grant's scope refers to an identifier in a recorded scope vocabulary and a recorded containment relation says one scope covers another.
- The containment relation is itself an assertion by an identity, and a wider relation widens every grant that refers to it. **Who may record it, and under what grant, is not answered by any accepted artifact.** A relation recorded by an actor with no applicable authority would be a route to extend scope. This is not a representation question. It is routed (RQ-03).
- A project may state scopes by description. Then containment is HJC-25 judgment and the representation must say so and not guess.

**Collective identities and work assignment (GC-OQ-05).** A collective can be a recorded producer only with recorded membership and expands to its members for independence (GCR-08). The representation needs: an identity record for the collective, membership records that carry their own recorder and time, and assignment relations recorded as provenance (a work assignment confers no authority). Membership must be reconstructable **as of** the evaluation point, which is the same machinery as grants (CD-4). The accepted text does not say at which point a collective is expanded when membership changes after an act. That is routed (RQ-09).

### 9.5 Actor-kind authentication (STEP-04 F-5, DR-07, RJ-OQ-02)

STEP-04 routed to this step: "STEP-05 answers DR-07 (authentication of actor kind). Any conformance definition requires B-eligible rules to be evaluated at or before reliance. No claim may say the protocol alone guarantees that a human acted."

**Four things that are easily run together** (UAD5-12).

| Thing | What it is | What can carry it |
| --- | --- | --- |
| **Kind designation** | A recorded statement that an identity is human, AI, evaluator, or automated | Any family can hold it. CRC-03 checks the recorded kind of an AUTH-G act. Whether the designation was authorized and by whom is itself a record |
| **Attribution integrity** | That the act recorded under an identity was written by or for that identity | No family. Any file-based record, including a version-control author or a field naming the acceptor, is self-assertable |
| **Authentication** | A binding between an act and a credential presented at the time | A mechanism outside the record: access control, credentials, signatures, platform attestation. A representation can record that a binding method was used. It cannot make the binding true |
| **Human-presence assurance** | That a human, not an agent holding the human's credential or session, performed the act | **Nothing.** No representation, schema, signature, or record can establish this. A credential can be used by whoever holds it. A signature proves a key was used, not who used it |

**Consequences.**

1. **No claim, in this memo or in any later artifact, may say that the protocol, a schema, a record, or a signature guarantees that a human acted.** The accurate statement is: a record of an AUTH-G act is *designated* human-held and is checked against that designation (CRC-03). Whether the designation is accurate is HJC-21, challengeable by an AUTH-A actor and closed only by an independent human with authority.
2. **What a representation can do** is make the weak point visible and auditable: record the kind designation with its recorder, time, and grant; record the method by which the act was bound to the identity, as descriptive provenance; keep the record of the attempt even when blocked; and make the evaluation point before reliance identifiable (consequence 4).
3. **Descriptive categories of what a project might record** about the binding are: none stated; access-control placement only; a credential presented; an out-of-band confirmation by a second identity; a third-party attestation. These are descriptive categories, not strengths. This memo does not order them, does not say any is sufficient, and makes none required (that would be a new rule, RQ-05).
4. **At or before reliance (F-5, second sentence).** A rule tagged blocking-eligible (B) only protects if it is evaluated between the recording of an act and reliance on that act (`rule-judgment-boundary.md` Section 9.4.4). A conformance definition therefore needs the representation to make three things identifiable: the act, the formal-check result for the act, and the first reliance on the act, with an order among them. A representation that cannot order those three has no "at or before reliance" and any conformance claim built on it is a claim about detection after the fact. That is routed to the conformance and publication work (RQ-06).
5. **Both directions matter.** An agent presenting as a human to hold AUTH-G, and an agent acting through a human-designated credential, are both outside what any check can see. An AI actor holding AUTH-V is a recorded non-human identity, and CRC-15 and CRC-59 bound what it may assert.
6. **Same-vendor review.** Review of this and other artifacts by Claude-family models is not independent corroboration (PR-27, PR-28). This is a limit on the process, not a representation property (RQ-16).

**Routing for F-5.** STEP-06: what a project records about the binding and the practice of out-of-band confirmation. STEP-07: pilot evidence on whether the weak point is exploitable and at what cost (F-2, F-5). Publication (STEP-09): the claim wording above. Later architecture: identity and credential integration, which is out of scope here.

---

## 10. Evidence and Provenance Analysis

### 10.1 Which record elements must be discrete for the catalog's checks to exist

A check can only read what is separately identifiable. Where a catalog entry needs an element, the element must be a discrete, referable part of the record, not only a sentence in prose. Where the content is judgment-bearing, it stays prose and is paired with a judgment. The table is an inventory by family of entries. It is not exhaustive, defines no field, and selects no serialization (ROR-09).

| Family | Must be discrete (checkable) | Stays prose (judgment-bearing) |
| --- | --- | --- |
| A Attribution, authority | Acting identity, capacity, target, time, action kind; recorded actor kind; the grant relied on | Accuracy of attribution and actor kind (HJC-21) |
| B Independence | Producer identities per item; acceptor identity; accepted-set basis links; act kind (favorable or conservative); presence of the independence declaration | Content of the declaration; substantive independence (HJC-12) |
| C Gate acts | Gate definition reference; slot fillers; treatment designations from the recognised list; the nine authorization elements; exception elements and marker; determination stated; times | Sufficiency; adequacy of the gate definition; warrant of an exception or authorization |
| D Challenge, disagreement | Challenger, target, target scope, basis (four elements); closure kind and closer; escalation elements | Whether an answer is adequate; whether a challenge stands |
| E Provenance, evidence | Class; producer; time; source reference; target and polarity; attempt record elements; derived-from references; configuration facet statements; observation time; limitations statement present | Reliability and relevance of a source; adequacy of configuration and limitations |
| F Knowledge classes, dependencies | Validation criteria present; inference citations; evaluative designation; basis-presentation designation (Section 10.2); dependency link kind, recorder, time, materiality designation; reason per trigger event | Testability of criteria; warrant of an inference; materiality; whether content is evaluative |
| G Correction, supersession | Correction designation and its recorder; confirmation and notice; the polarity, target, source, scope, and dependency-link fields compared across versions; successor link; withdrawal elements | Whether a revision alters meaning (HJC-13); genuineness of a rationale |
| H Grants | Grantee, class, scope reference, conferrer, conferral scope, time; the establishing-act mark; revocation and narrowing acts | Legitimacy of the establishing act; purpose of a conferral |

**Consequence.** CRC-56 (never-a-correction changes) cannot be checked in any family where polarity, target, source, scope, and dependency links of an item are only prose, because the check compares versions of discrete elements. The same holds for CRC-36's "target and polarity" and CRC-49's link designations. In a prose-only family those conditions are unresolved, and the requirement still stands (ROR-10).

### 10.2 QA5-03: the record element behind "evidence-only form"

**The issue.** CRC-45 (v0.5) checks (a) the recorded evaluative designation of a claim and (b) whether the record carries, for the same claim, a recorded observed-fact designation or a recorded basis statement that the claim is established by evidence alone. STEP-02 defines no such record element. EKR-28 says an evaluative claim "is not established by evidence or inference alone and is not presented as observed fact." QA5-03 recorded that whether a claim citing evidence items is "established by evidence alone" remained an interpretation, so two evaluators could reach different presence results. The Moderator's record: "Define the record element that 'evidence-only form' refers to. CRC-45 is unresolved where none exists."

**Definition proposed (representation-neutral; UAD5-01).**

> A **basis-presentation designation** is a recorded designation, attributable to one identity with a time, attached to a claim, by which the recorder states **how the claim is presented with respect to its basis**. For CRC-45 two presentations matter: *presented as observed fact* and *presented as established by evidence alone*. A claim with no such designation recorded has no basis-presentation designation.

**Properties.**

1. **Recorded, not inferred.** The element exists only where an identity recorded it. A checker must not derive "established by evidence alone" from a claim citing evidence items and no inference, and must not treat the lack of a citation as absence of the element. This closes QA5-03's failure scenario: evaluators A and B reading the same record find the element present or absent, and reading style no longer decides it.
2. **Distinct from support structure.** Evidence links, inference citations, and the class of the item are recorded under their own entries (CRC-44; EKR-26, EKR-27). A claim that cites evidence may or may not be *presented* as established by it alone. The designation records the presentation, and the structure records the support.
3. **Any identity may record it.** The recorder is part of the element. A decision record that cites a claim as established is a recorder of that presentation.
4. **Attributable and challengeable.** It takes effect when recorded (CRC-24). Changing it is a recorded revision, not an overwrite (EKR-09). Whether the content is evaluative, and whether an evaluative claim is warranted, stays HJC-18.
5. **No vocabulary is selected.** Two distinctions are named because CRC-45 names them. How they are labeled, and whether other presentations exist, are not decided (BDR-11).

**What the definition does and does not do.**

- It does **not** edit CRC-45, UAD4-32, or EKR-28. It does **not** change CRC-45's classification or handling (N, U). It fixes what "the record carries" means, so the agreement corollary can be met.
- With the element defined, the outcomes under the accepted text are unchanged: an evaluative designation recorded together with one of the two presentations is reported as present (handling N, no verdict). An evaluative designation with neither is **unresolved and not read as satisfied**. A representation that provides no such element leaves limb (b) unresolved for every claim.
- **Honest consequence.** Unless a recorder states a basis presentation, limb (b) of CRC-45 stays unresolved. The check's protective effect against an evaluative claim being presented as fact then rests on challenge, which CRC-45 already names as the remedy. Making the designation required for evaluative claims would be a new rule. It is not made here (RQ-02).

**Disposition options for the Moderator.**

| Option | Effect | Cost |
| --- | --- | --- |
| (i) Accept the definition as STEP-05's answer; CRC-45 text unchanged | Smallest change. QA5-03 closes at the STEP-05 level | CRC-45 and the memo are cited together. The pair is a reading |
| (ii) As (i), and cite the element in a later accepted revision of the boundary artifact | Aligns the text with the definition (BDR-16) | A revision of an accepted artifact |
| (iii) Do not define an element; mark limb (b) as unresolved by design wherever no element exists | No new element; limb (b) is a standing "unresolved" | The check's second limb has no mechanical content |
| (iv) Require the designation for evaluative claims | Limb (b) becomes decidable | A new protocol rule. Out of STEP-05's authority; Moderator-visible and a STEP-06 practice question |

This memo recommends (i), with (ii) taken up when the boundary artifact is next revised. The disposition is the Moderator's.

### 10.3 Producing configuration, source lineage, and evidence basis

**Producing configuration (CRC-39; `rule-judgment-boundary.md` Section 11.2).** The five facets (model, reasoning effort, harness, tooling, instructions) are stated per facet; "not determinable" is a permitted statement; the instruction statement is "by content or by a reference that resolves to what was in force at the act, not to a later version."

- **Representation implication (UAD5-06).** A reference to instructions must be **version-bound**: it resolves to the version in force at the act. A bare path to a mutable file does not. No family supplies version-binding by itself (Section 10.5, P2). Version-binding needs a revision identifier, a content hash, or an immutable record. This applies equally to a skill file used as instructions.
- Recording configuration confers no independence (CRC-39, PR-27).
- Absence of a statement is flagged and does not invalidate (UAD4-11). A gate may require named facets.

**Source lineage (CRC-38; DR-06, RJ-OQ-10).** Derived evidence names the items it derives from. Transitive lineage is computed from recorded links (DR-01). Evidence items sharing an identified source must be identifiable as sharing it.

- **Source comparability (UAD5-14).** A representation can support declared source identity: a source record with an identifier, which evidence items reference. Two evidence items that reference the same source record share a source. **Two descriptions that do not reference the same source record are not determined to be the same by any check.** Whether they are the same is judgment (HJC-12, HJC-26), and the lineage gap is flagged (CRC-38, F). A registry (RO-06a) or relationship records (RO-07) carry declared source identity natively. Document-based families carry it by convention.
- Unrecorded lineage cannot be found by any check (HJC-12).

**Evidence basis and class (CRC-34 to 37, 44; D3).** The class, source, target and polarity, and attempt record of a negative finding are class-defining and must be discrete elements. The distinction between sourced evidence and a concurrence or agreement record (CRC-36; PR-20) is checkable only "where the record distinguishes" them. That requires a discrete **source-kind** element, recorded by an identity and challengeable. If a family lacks it, agent agreement is not detectable as non-evidence by the check, and the remedy is challenge (`rule-judgment-boundary.md` Section 12.1).

### 10.4 Record order (DR-03, DR-10, RJ-OQ-01)

**What the accepted rules need from order.**

| Need | Source |
| --- | --- |
| The establishing act precedes every other recorded act | CRC-61 |
| A gate definition precedes the act; an authorization precedes the acceptance; effective-from-recording; "not backdated" | CRC-16, CRC-24; GCR-47 |
| Notice precedes confirmation; exception precedes reliance | CRC-55, CRC-20, CRC-24 |
| Nothing overwritten; producers added, never removed | CRC-41, CRC-14; EKR-09 |
| Act-time evaluation uses the record as of the act | Section 5.4 of the boundary artifact; DR-10 |
| Reliance and check results ordered relative to the act | F-5 (Section 9.5) |

**Properties record order must have (UAD5-07).**

- **O1 Position.** Every record has a position relative to others sufficient to decide before and after for the pairs the rules compare.
- **O2 Not self-assertable.** Position, and the time of recording, must not be established solely by the recorder's assertion. A timestamp written by the actor claiming it can be written backwards, and CRC-24's "not backdated" cannot then be checked. Something other than the recorder must assign or witness the position.
- **O3 History preserved.** Nothing is overwritten or removed. A removal is a new record.
- **O4 As-of reconstruction.** The record at an evaluation point can be reconstructed.
- **O5 Total enough.** CRC-61 needs the establishing act to precede *every* other act, so the order must be total at least with respect to it. Where an arrangement allows concurrent writers or branches, two acts can be incomparable. The conservative reading (BDR-06, BDR-12) is that an incomparable pair is **unresolved**, not "before".

**Three things that are easily confused.** *Record order* (position in the record), *recorded time* (a timestamp element on the act), and *observation time or period* (a descriptive element of an evidence item, CRC-37). They are different elements. Time never acts as a clock in the protocol (GCR-67). Ordering does the work.

**Order sources, described without selection.**

| Source | O1 | O2 | O3 | O4 | O5 | Note |
| --- | --- | --- | --- | --- | --- | --- |
| Version-control history | Yes | Partly: authors and times are self-assertable; rewriting history is possible | Only if history is never rewritten | Yes | Only along one line of history. Branches are incomparable until merged | Makes "recorded" mean "present in the shared line of history". The meaning of "recorded" for a local draft is a hidden decision (RQ-04) |
| Sequence number in each record | Yes | No, if the writer assigns it | Not by itself | Not by itself | Yes if one writer | A convention |
| Timestamp in each record | Partly | No | No | No | No | Self-assertion |
| Append-only log with a position assigned by the log | Yes | Yes, in the log's terms | Yes | Yes | Yes for one log | A log is a store. Choosing one is NG-2 |
| Hash-linked records | Yes | Tamper-evident, not witnessed | Evident | Yes | One chain | Detects change after the fact. Does not say who wrote it or whether it was valid |
| External witness (a timestamp authority or equivalent) | Yes | Yes | n/a | n/a | n/a | Out of scope. Named only as the kind of thing O2 refers to |

**What this memo does not decide.** It does not choose an order source. It states the five properties and the hazard that every self-assertion-only source fails O2.

### 10.5 Provenance and version-binding by option

| Need | RO-01 | RO-02 | RO-03 | RO-04 | RO-05 | RO-06 | RO-07 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| P1 Configuration facets stated, "not determinable" allowed | Con | Con | Con | Nat (presence) | Con | Con | Nat |
| P2 Instructions referenced as in force at the act | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | 2nd |
| P3 Item as it stood; basis preserved as of the decision | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | Nat (records are immutable) |
| P4 Class-defining evidence elements | Con | Con | Con | Nat (presence) | Con | Con | Nat |
| P5 Descriptive elements; limitations statement | Con | Con | Con | Nat (presence) | Con | Con | Nat |
| P6 Derived-from links; transitive lineage | Con | Con | Con | Can't | Con | Con | Nat |
| P7 Source comparability by reference | Con | Con | Con | Can't | Con | Nat | Nat |
| P8 Class and basis-presentation designation | Con | Con | Con | Nat (presence) | Con | Con | Nat |
| P9 References resolve | Con | Con | Con | Can't | Con | Nat | Nat |
| P10 Append-only; invalid acts visible | 2nd | 2nd | 2nd | Can't | 2nd | 2nd | Nat† |

Hybrids follow the same logic: H-2 and H-3 take the RO-07 column; H-1 and H-4 take the RO-02 column. P2 is **2nd for every family, including the best fit**, because a reference to an external document (instructions, a skill file) must be bound to a version, and no family contains that binding.

---

## 11. Challenge, Disagreement, Gate, Exception, Exposure, and Revalidation Analysis

### 11.1 What the accepted semantics need from the record

| Semantic | Needs (source) | Demand classes |
| --- | --- | --- |
| Challenge | Challenger, target, target scope, basis; recorded whatever its condition; visible in every view of its target, its dependents, and every decision citing it (CRC-26; GCR-29) | CD-1, CD-7 |
| Closure | Only by challenger resolution, authority closure, or withdrawal of the target with no successor; closer qualified; act kind read from a closed list (CRC-27, CRC-09; UAD4-31) | CD-1, CD-3 |
| Gate basis and accepted set | Basis links resolve; closure computed under the effective designations as of the act; fixed for that acceptance (CRC-06; GCR-04) | CD-2, CD-3, CD-4 |
| Standing record | Each item cited with a recorded treatment; earlier refusals and deferrals; applying exceptions (CRC-18) | CD-5 |
| Exception | Authorized human, grant, rationale, requirement, scope, provenance, marker; result "satisfied under exception" distinct; marker travels (CRC-20; `rule-judgment-boundary.md` Section 9.6) | CD-1, CD-7 |
| Disagreement | Derived. Enumerable, attributable, evidence-linked, routable, cleared only by a recorded act (GCR-35) | CD-3, CD-4, CD-5 |
| Exposure | Derived. An item depends, directly or through others, on an item that is contested or has an open trigger or requirement (EKR-40) | CD-3, CD-5 |
| Revalidation | One open requirement per trigger event, with a reason per event; a dependent with an open requirement is not recorded as current; closure names each reason and records a disposition (CRC-51, CRC-52) | CD-1, CD-5 |
| Finding of an invalid acceptance | A formal-check result with rule, evaluation point, and elements examined (CRC-59) | CD-1, CD-2, CD-4 |

### 11.2 Fit by option

Composed from Section 8.2 by the weakest cell. The prose below gives the reading per family.

- **RO-01 Markdown.** A human can record challenges, treatments, exceptions, and dispositions as prose and tables, and can derive exposure and disagreement by reading. No check can. Visibility in every view is a convention. A marker copied into a summary by hand can be dropped.
- **RO-02 YAML frontmatter.** Item-level facts fit. Challenges, closures, exceptions, and requirements are acts by others and sit in a producer-controlled file (RC-10) or elsewhere.
- **RO-03 JSON.** Challenge, closure, exception, and requirement records fit as discrete records. The family contributes nothing to order, derivation, or views.
- **RO-04 Schema.** Checks that a challenge has four elements, an exception has its content, and a closure lists a disposition for each reason, as presence. Nothing else in this section.
- **RO-05 Sidecar.** Records in sidecars can be separate write domains, which helps challenges. Visibility in the document view depends on the document's author keeping up with the sidecars.
- **RO-06 Central.** Easy to hold challenge and requirement records and resolve references. Stored conditions are the hazard of Section 12.1.
- **RO-07 Graph/ledger.** The fit is best: challenge, closure, treatment, exception, requirement, and finding are records; exposure and disagreement follow from relation queries; the standing record is a query over what existed at the act. Views must be generated.
- **RO-09 Agent instructions.** Can ask agents to show markers. Cannot ensure they do.

### 11.3 Disagreement (D5, GCR-35)

D5 requires disagreement to be an attributable, evidence-linked, routable condition and does not require it to be a state name. GCR-35 makes it a **derived condition**: not a named state, not a property carried on an artifact, and not a relationship someone must remember to record. Any conforming representation must make five things answerable: enumerable, attributable, evidence-linked, routable, and cleared only by a recorded act.

- *Routable* requires current grants, so it carries the as-of machinery of Section 9.
- A representation that **stores** a disagreement flag fails "cleared only by a recorded act" if the flag can be edited without an act.
- No option is required to give disagreement a fixed serialized state, and this memo selects none.

### 11.4 Gate basis, standing record, and exception visibility

- **Gate basis.** The basis is explicit citations recorded at the act. The accepted set is derived from them and the links as of the act, and is fixed for that acceptance (GCR-04). A stored copy of the computed set is a **formal-check result**: a record of applying CRC-06 at an evaluation point with named inputs. It is a reproducibility aid, advisory and challengeable (Section 12.3), not the authority.
- **Standing record.** The items a gate must cite (opposition including withdrawn, exposure, open requirements, earlier refusals and deferrals, applying exceptions) are derived conditions. CRC-18's blocking eligibility holds only where the representation makes them available at the evaluation point (UAD4-23).
- **Exception.** The result "satisfied under exception" must be distinct from "satisfied", and the marker must be visible wherever the acceptance is cited (CD-7). A family whose views are hand-authored cannot ensure this.

### 11.5 Exposure and revalidation

- **Triggers and requirements.** A trigger event on a material dependency has one open requirement with a reason per event (CRC-51). A **stored "current" mark** over a dependent with an open requirement is invalid. A representation that stores a currency or status value therefore creates a field that is wrong exactly when the protocol most needs it right.
- **Exposure** follows dependency links. It needs both directions of every link (EKR-33), designations with recorder and time, and the as-of rule for removals. A link that is only a bare reference cannot support it (UAD5-05).
- **Closure of a requirement** names each open reason and records a disposition for each (CRC-52). That is CD-1 presence of a mapping from reasons to dispositions. Adequacy is HJC-16.
- **TRG-6.** The finding of an invalid acceptance is a recorded formal-check result. It creates a requirement on dependents only if it meets CRC-59 and is recorded by an AUTH-V holder or a human AUTH-G holder. A pending challenge does not suspend it (Section 9.4.3 of the boundary artifact).

---

## 12. Derived Conditions, Item Identity, Closure, Machine Views, Lifecycle Graphs, State Vocabulary, and Formal-Check Result Form

For each item the memo states what accepted semantics fix, what a representation must make answerable, and what is deliberately left unselected.

### 12.1 Derived conditions (DR-04, GC-OQ-04, EK-OQ-11, PS-OQ-01)

**Conditions.** Contested, exposed, open requirement, current validity, disagreement, assumption-rooted, and the unresolved assumptions a dependent relies on.

**What the accepted semantics fix.** They are derivable from the record, enumerable, attributable, and cleared only by a recorded act (CRC-54; GCR-35; EKR-40). Effect follows from the source rule whether or not the condition is shown (`rule-judgment-boundary.md` Section 12.6). Visibility of unresolved assumptions on the dependent is a semantic requirement on any conforming representation (CRC-47).

**Three realizations.**

| Realization | Description | Reading |
| --- | --- | --- |
| **D-a** Computed on demand | Derived from the record at the evaluation point each time | Never stale. Needs an evaluator and the as-of record |
| **D-b** Materialized cache | A stored result regenerated from the record | Acceptable as a projection (Section 12.4). Stale if not regenerated |
| **D-c** Stored as authoritative state | A stored value that is the source | The pattern ROR-03 warns about. Diverges from the record. Overwrites history |

**Position (UAD5-04).** Accepted semantics require *derivability*. They do not forbid a cache. They do mean that any stored value is a **projection**, never the source, and that if a stored value and the derivation from the record disagree, the derivation governs. This follows from GCR-35 (cleared only by a recorded act), CRC-51 (a currency mark over an open requirement is invalid), and the Product Owner's note on GC-OQ-04. It is a reading of those rules, declared, and not a new one.

**Availability statement.** For each blocking-conditional rule (CRC-18 and CRC-19, whose blocking eligibility depends on exposure, open requirements, and assumption-rooted status), a representation must say whether it makes the derived condition available at the evaluation point. A representation that does not is not blocking-eligible for those rules there, and a violation is still a violation (UAD4-23; BDR-07). A written availability statement is an output a later experiment would produce (RQ-06).

**Not selected.** Whether any condition is computed, cached, or materialized; any condition name.

### 12.2 Item identity across change (DR-02, EK-OQ-12, GC-OQ-04)

**What the accepted semantics need.**

- Acceptance applies to the item **as it stood** (EKR-10; CRC-42). A decision's basis is preserved **as of the decision** (EKR-31).
- Post-acceptance change is a correction or a supersession (CRC-55, CRC-56). Challenges and relationships carry to a recorded successor and are shown as carried (CRC-28).
- Producers are added, never removed, **including when an item is restated, renamed, or moved** (`protocol-semantics.md` Sections 6.2 and 6.3; CRC-14).
- Five kinds of change are never corrections. The check compares a change with the item it changes (CRC-56; Section 12.7 of the boundary artifact).

**Representation implications (UAD5-16).** Two things are needed and they are different.

1. **Version-binding.** A way to refer to a specific state of an item (a revision identifier, a content hash, or an immutable record). Without it, "as it stood" cannot be reconstructed.
2. **Continuity link.** A recorded relation saying that this version continues, corrects, or supersedes that one. The link is an **assertion by one identity** and can be disputed. An unlinked restatement by another actor is not detectable as the same item by any check. That case is a disputed attribution and substantive independence (HJC-12), and the remedy is challenge.

**Identity bases, without selection.**

| Basis | Version-binding | Continuity | Hazard |
| --- | --- | --- | --- |
| Stable identifier plus version designator | Yes | Needs successor links | The identifier is assigned by someone. Collisions and reuse need a rule |
| Content hash only | Yes | None. Continuity is only by explicit link | Any change is a new identity. Fine for versions, silent on continuity |
| Path or name | No | Fragile | Rename and move break identity. Acceptance "as it stood" is lost. Incompatible with "renaming or moving does not remove a producer" unless history is consulted |

A representation needs both version-binding and a continuity link. Which basis is used is not selected here.

### 12.3 Accepted-set closure computation (DR-01, GC-OQ-04)

**What is fixed.** The accepted set is computed from the record as of the act and is fixed for that acceptance (GCR-04). It follows the material basis transitively, with the materiality and dependency designations, the challenge responses relied on, and the verification records relied on (`mod-w/domain-language.md`, Accepted set). An unresolvable link means the acceptance is invalid (CRC-06; BDR-06). Citation-chain grounding (CRC-44) and assumption-rooted derivation (CRC-53) are computed over the same links.

**Representation needs.** Typed links carrying a recorder, a time, and a materiality designation with its effectiveness conditions (CRC-49, CRC-50); both directions (EKR-33); the record as of the act (CD-4); an evaluator that follows the links.

**Approaches.**

| Approach | Reading |
| --- | --- |
| Compute at the act from links | The accepted semantics' own description. Needs the link records as of the act |
| Compute on demand later from links and history | Gives the same result if history is complete and as-of reconstruction is reliable |
| Store the computed set as a formal-check result | A reproducibility aid. Advisory and challengeable. Not the authority. A stored set that disagrees with the computation loses |

No approach is selected. A family that cannot give typed attributed links (RO-01, RO-02 by bare lists) cannot support CRC-06 mechanically, and the condition falls to human review with the shortfall stated (ROR-10).

### 12.4 Machine views and human views (EK-OQ-15, Product OQ-8)

**Position.** A view is a projection of the record. It is non-normative. If a view disagrees with the record, the view is wrong (UAD5-09). Role-specific views are permitted, and a view may layer (a summary with expandable detail) to reduce the burden on a human. A view may **not** omit what accepted semantics require to be visible.

**Visibility invariants.** Any view that shows an item must preserve these:

| ID | Invariant | Source |
| --- | --- | --- |
| VI-1 | A challenge is visible in every view of its target, of its dependents, and of every decision citing it, whatever its condition | GCR-29 |
| VI-2 | Invalid acts remain visible as invalid | PR-11; EKR-09 |
| VI-3 | A dependent shows its unresolved assumptions wherever it appears | CRC-47 |
| VI-4 | A flag is shown wherever the item appears, and in the standing record of any acceptance citing it, until a recorded act cures it | `rule-judgment-boundary.md` Section 9.2 (F) |
| VI-5 | An exception marker travels with the acceptance and is visible wherever it is cited | `rule-judgment-boundary.md` Section 9.6; GCR-45 |
| VI-6 | A dependent with an open requirement is not shown as current | CRC-51; OBJ-10 |
| VI-7 | A withdrawn item is cited as withdrawn in later decision bases | CRC-58 |
| VI-8 | A view names the record and the evaluation point it projects | Added by this memo for reproducibility (UAD5-09) |

**Answer to Product OQ-8 (metadata in protocol state versus documentation), as a criterion, not an allocation.** A piece of information belongs with the record if a catalog entry reads it, or if its absence would break a visibility invariant. It belongs in the document if only a human reasons from it. The OQ-8 text lists "confidence" as an example of metadata. This memo does not adopt confidence as a record element (BDR-14). The remaining allocation questions go to STEP-06 and the Product Owner (RQ-14).

**Views by family.** RO-03, RO-06, and RO-07 give the best base for generation (RC-13). RO-01 is the human view. A hybrid that generates human views from the record can preserve the invariants in one place, and a hybrid that hand-authors them cannot.

### 12.5 Lifecycle graph questions

**What the accepted semantics say.** They describe acts, valid and invalid, and derived conditions. They deliberately name no states and no transitions (`protocol-semantics.md` Section 10). The research note's phrase "allowed transitions" is a hypothesis. It is not a requirement (NG-4).

**Why a lifecycle graph is not required, and the risks of adopting one now (UAD5-11).**

1. **One item has several simultaneous conditions.** An item can be accepted, contested, exposed, carry an open requirement, and be superseded all at once. A single-valued state enumerates combinations or hides them, and invites a `DIVERGENT`-style name that D5 declined.
2. **Legality is not a function of previous state.** Whether an act is valid depends on grants, independence, and the accepted set (CRC-02, CRC-07), not on which node the item sits at. A transition table cannot express "the acceptor is not in the producer set of the closure". Its guard conditions would be the protocol, and then the graph is not the protocol layer.
3. **A graph can be mistaken for authority** (ROR-03).

**What would be admissible.** A graph or diagram as a **non-normative orientation aid** for humans, showing act kinds and typical order. It would be a methodology artifact (STEP-06). A state view would be admissible if it is made of orthogonal derived facets and not a single status, is a projection, and selects no names. No lifecycle graph is defined here.

### 12.6 Serialized state vocabulary

**What the accepted semantics say.** No vocabulary is selected. Handling categories and check outcomes are not value sets (BDR-11). `DIVERGENT` is not adopted (D5; `protocol-semantics.md` Section 10). Disagreement is derived.

**Admissibility tests for any vocabulary proposed later (UAD5-10).**

| Test | Requirement |
| --- | --- |
| S1 | Each term names a derived condition that accepted semantics define |
| S2 | Vocabulary for check results (violated, satisfied, satisfied under exception, unresolved) is kept apart from vocabulary for item conditions |
| S3 | No term merges an item condition with an authority fact. "Approved" or "accepted" is not an item condition. Acceptance is an act. "Currently accepted" is a derived condition |
| S4 | No term makes disagreement a state that can be set or cleared outside a recorded act |
| S5 | Terms are labels on a projection and can change without changing semantics |
| S6 | A vocabulary change does not change classification or validity (BDR-16; ROR-04) |

**Not selected.** Any term. The vocabulary question is raised again after STEP-06 (users' words) and STEP-07 (use) and is the Moderator's (RQ-11).

### 12.7 Formal-check result form (DR-09, RJ-OQ-03a)

**What is fixed.** A formal-check result records the rule applied, the evaluation point, the record elements examined (by reference), and the outcome (satisfied, violated, satisfied under exception, unresolved). A CRC-59 finding adds that it names the rule or rules violated, states the evaluation point, and identifies the record elements examined. Standing is advisory, challengeable, record-relative, confers no independence, and does not suspend a trigger it creates (Section 9.4.3 of the boundary artifact). How a result is recorded and attributed is DR-09.

**Representation requirements (UAD5-08).**

| ID | Requirement | Reason |
| --- | --- | --- |
| RF-1 | A result is a **record in its own right**, distinguishable from an act and from an item's condition | A "violated" result must not itself change protocol effect, and a "satisfied" result must not grant any (BDR-08, BDR-13) |
| RF-2 | It is **attributed** to a producing identity with a capacity. Where an AI actor produced it, its producing configuration is recorded (CRC-39) | A tool or model is an actor in the record. An AI AUTH-V holder is bounded by CRC-15 and CRC-59 |
| RF-3 | The elements examined are referenced **version-bound**, so the basis is reproducible | Section 9.4.5 of the boundary artifact: "the reproducible basis" |
| RF-4 | The rule applied is identified together with the version of the semantics it was applied under | Reproducibility, and BDR-16 (classification changes only by accepted revision) |
| RF-5 | The outcome set is the four above and is not a value set. "Unresolved" is distinct from "satisfied" and from "no result" | BDR-11, BDR-06 |
| RF-6 | A result is **never written into the item's recorded condition**. A validator writing "valid" into an artifact is a state write-back (Z-5) | ROR-03, ROR-05 |
| RF-7 | A result relied on to satisfy a gate-required formal check, or recorded as a CRC-59 finding, carries the authority conditions of CRC-13, CRC-15, and CRC-59 | ROR-05 |
| RF-8 | A result's link to the requirement it creates on dependents (TRG-6) is recorded | CRC-51, CRC-59 |

**Reading by family.** RO-04 can check that a result record has the elements, as presence, and cannot check that the rule named was violated or that the elements examined are the right ones. Document-based families can hold a result as prose with no guarantee of RF-1, RF-3, or RF-6. An arrangement that stores results as separate attributed records (RO-07 properties, H-2, H-3) can satisfy RF-1 to RF-8 with an evaluator. None of this gives a result consequential authority (ROR-05).

---

## 13. Representation Options Explicitly Rejected for Now

"Rejected for now" means: not to be selected on the evidence available, with the condition under which it would be reconsidered. It does not say never. It is the Development Team's recommendation, and the Moderator decides.

### 13.1 Rejections

| ID | Rejected for now | Rationale | Reconsider when |
| --- | --- | --- | --- |
| Z-1 | Markdown conventions and tables as the **sole machine-readable record** | Nothing checks the conventions. They become an undeclared schema. Relationship attribution, version-binding, order, and derived conditions are not carried (Section 6.1) | Never as the sole record. It stays the human document and methodology medium |
| Z-2 | **Acts and relationships stored in the target item's own frontmatter** (H-1 for acts) | The producer controls records about its own item (RC-10). In-place edit. No order, no as-of (Sections 6.2, 6.8) | A write-control arrangement shows the producer cannot alter those records, and an order source exists |
| Z-3 | **Stored authoritative item condition** in a central state file (RO-06b; the state half of H-4) | A stored value reads as authority (ROR-03). Derived conditions go stale. Overwrite loses history. Locks in a state vocabulary (D5) (Sections 6.6, 12.1) | A later accepted revision makes a condition a primary record. The record would still govern when the two disagree |
| Z-4 | Selecting a **graph store, distributed ledger, hash-chained or signed log infrastructure** | NG-2. Pre-empts the deferred Product Knowledge Ledger decision. Pulls identity binding and key management in | A pilot or experiment shows an order and as-of need no simpler arrangement meets. Infrastructure is separate from the record properties of Section 6.7, which are not rejected |
| Z-5 | **Governance rules encoded as schema constraints and presented as protocol validation**; validator write-back into artifacts | INV-13, ROR-02. A schema pass reads as governance validity. A written-back "valid" reads as authority | Never as presented. A schema may remain a structural check with its output typed advisory |
| Z-6 | **Skill, prompt, or agent-instruction conventions as protocol representation, enforcement, or a source of authority** | They carry no record element, check and enforce nothing (Section 6.9). Prose against prose (MW-OBS-010) | Never as enforcement. H-C remains a hypothesis for STEP-08, testable only after a representation exists |
| Z-7 | A **custom rule language or executable rule encoding** (protocol representation degree 2) | No evidence yet that the catalog's rules can be encoded without becoming unmaintainably complex (E-1). Selecting one decides evaluator, schema, and state at once | An experiment (Section 14) shows which rules are encodable from which record forms |
| Z-8 | A **lifecycle graph or state machine as protocol or state representation** | Section 12.5 | The orientation use in STEP-06; or derived orthogonal facets with no single status |
| Z-9 | Any **numeric, graded, or weighted** field for evidence strength, sufficiency, or judgment quality | BDR-14, EKR-19, ROR-06 | Never |
| Z-10 | Any representation or claim that **proves a human acted** | Section 9.5. No representation can | Never. A stronger binding of act to identity may be recorded. It is still a recorded claim |

### 13.2 Hidden architecture decisions, by option, if selected now

This restates the "hidden decisions" of Section 6 in one view for the Tech Lead's sampling.

| Option | Decisions the choice would make without anyone deciding them |
| --- | --- |
| RO-01 | Schema (conventions); item boundary (headings); relationship record (link syntax); order source (version control) and the meaning of "recorded" |
| RO-02 | Item = document; field names and placement; where acts go; whether `status` exists (a state vocabulary); YAML dialect |
| RO-03 | Key names, nesting, canonical form, time encoding, stream or document; record = file or aggregate |
| RO-04 | Schema language and version; open or closed shape; enumerations (a value vocabulary); extension policy; cross-file references |
| RO-05 | Pairing rule; sidecar granularity and format; drift policy; write control |
| RO-06 | Registry or state; state vocabulary; write protocol and locking; store; who writes |
| RO-07 | Events or states; ID scheme; reified relationships; store; tamper evidence; canonical form; the Product Knowledge Ledger question |
| RO-08 | The source of truth among parts (the most consequential hidden decision in any hybrid); the binding mechanism; whether views are generated |
| RO-09 | A skill file format; the harness; trigger policy; the assumption instructions persist |

---

## 14. Recommended Next Experiment

### 14.1 Recommendation

**A narrow hybrid experiment, RX-1, as later work, entered only after the prerequisites in Section 14.3 are disposed.** If the Moderator does not dispose the prerequisites or does not authorize an experiment, the recommendation falls back to **prerequisites before experimentation**, and Sections 13 and 15 stand without it. The recommendation is severable from the rest of the memo (UAD5-13).

It is a recommendation to consider. It does not select a representation, does not make any arrangement in it accepted architecture, and is not implemented in STEP-05.

### 14.2 Why this, and why not the others

- **Why an experiment.** The desk analysis leaves four questions open that reasoning cannot settle, because each is empirical: (1) whether record-per-act arrangements with computed derived conditions can be reviewed by a human without losing the visibility invariants; (2) whether the discrete-element inventory (Section 10.1) is sufficient for the fixture questions or names elements missing from the semantics; (3) what a backdated act, a forged attribution, and a validator write-back look like in each arrangement and whether the arrangement overclaims; (4) the readability and recording cost of the arrangement that fits the semantics best.
- **Why a hybrid, with a control.** No single family carries the semantics (Section 7). The arrangement that fits best on semantic criteria (H-2) is also the one with the costs that matter (RC-11, RC-14, RC-15). A single-family experiment would confirm limits already visible. The experiment therefore compares an H-2-style arrangement against a **document-only baseline**, the way the skills note uses a no-skill baseline: if the baseline answers the fixture questions as well, the extra mechanism added nothing for them.
- **Why not "no experiment yet".** It is a coherent option if the Moderator prefers to wait for STEP-06 and STEP-07. It leaves unanswered the questions that STEP-07 would otherwise meet unprepared (E-1: can core semantics be expressed in machine-readable form without unmaintainable complexity?).
- **Why not a single-family experiment.** It would test a family against questions the memo already answers (Section 7), and risks hardening that family by being the only one tried.
- **Why not a prototype or pilot.** NG-2. The pilot is STEP-07.
- **A limit on the evidence.** The case for this experiment rests on one producer's reading and on no independent corroboration. The experiment cannot repair that on its own (Section 14.4, review gate).

### 14.3 Prerequisites

These are Moderator-visible decisions. None needs the experiment to run first.

| ID | Prerequisite | Why |
| --- | --- | --- |
| P-1 | The Moderator disposes the QA5-03 element definition (Section 10.2; RQ-01), or confirms the routing | The fixtures include CRC-45. Without a disposition the experiment would be testing a definition no one has accepted |
| P-2 | The Moderator decides where the experiment sits: an authorized task, or a roadmap step (RQ-18). The roadmap has no experiment step, and a roadmap change is the Moderator's | Authorization and review gates depend on it |
| P-3 | The Moderator decides whether throwaway scripts may be run in this repository, which has no build or test configuration (MW-OBS-008, MW-OBS-012, MW-OBS-015) | Derivation of conditions may be done by hand or by throwaway scripts |
| P-4 | Tech Lead review of the fixture list for source and scope: accepted artifacts only, no pilot content, no methodology templates | Tech Lead Recommendation 6 |

### 14.4 RX-1 definition

**RX-1: Record-element coverage and derivation probe.**

**Purpose.** To find out, on fixed fixtures drawn from accepted material, which catalog questions can be answered from the record in each of two arrangements, which need a second mechanism, which are judgment, and what each arrangement costs a human reviewer. It produces **findings**, not a representation decision.

**Scope.**

- Two arms. **Arm A (baseline):** items, acts, and relationships recorded in Markdown documents and tables, evaluated by a human reader. **Arm B:** an H-2-style arrangement: items as documents with item-level metadata; each act, relationship, and designation as a separate small record that references what it concerns; derived conditions computed; human views generated from the records.
- The encodings are **throwaway** and unnamed in any recommendation. If a structural check is used, it is a measuring instrument for the experiment, its choice is declared throwaway, and its output is typed advisory.
- Each fixture is a small, self-contained record with a list of questions drawn from the catalog.

**Inputs (accepted material only).**

- The 17 invalid action examples of STEP-01 Section 8 and their handling (`rule-judgment-boundary.md` Section 15.4).
- D10 scenarios: a later act marked establishing; self-conferral through a role position and through a cycle; revocation with cascade and as-of reconstruction; a root grant that is not flagged (the proxy case, DP-04).
- CRC-45 with a basis-presentation designation present, present with the other presentation, and absent.
- A backdated authorization and an authorization recorded after the act (CRC-24).
- A correction versus the five never-correction kinds, with a successor link and with an unlinked restatement (CRC-55, CRC-56).
- A derived-condition case: counter-evidence creating a requirement; a currency mark placed over an open requirement; a stored cache that has gone stale.
- A forged attribution of an AUTH-G act to a human identity.
- A validator that writes "valid" into an artifact.
- A disagreement case tested against the five answerable properties.
- The criteria of Section 5 and the discrete-element inventory of Section 10.1.

**Success signals (qualitative; no thresholds).**

1. Every fixture question is classified as answered-from-record (with named inputs), unresolved (with the reason), or judgment (with the HJC named). None is skipped.
2. For questions classified checkable, two evaluators (the Arm A human reader and the Arm B derivation) reach the same result. A disagreement is evidence for the agreement corollary, not a reclassification (BDR-16, DP-05).
3. Derived conditions in Arm B reproduce from the record. Deleting the cache changes nothing.
4. Every generated human view preserves VI-1 to VI-8. Arm A's hand-authored views are checked against the same list.
5. The forged attribution is reported by both arms as **not detectable from the record**, and neither arm claims otherwise.
6. The element inventory proves sufficient for the fixtures, or the experiment names the missing elements and routes them to the semantics owners.

**Failure signals.**

1. A structural pass is reported anywhere as governance validity (ROR-02).
2. A stored value diverges from the derivation and the divergence is not noticed.
3. A backdated act is accepted under "effective when recorded" in an arm that claims to detect it.
4. A view omits a visibility invariant.
5. A formal-check result is written into an item's recorded condition.
6. Any output contains a score, grade, weight, confidence value, or verdict on a judgment (BDR-14).
7. A human reviewer cannot trace a derived result to its inputs without asking the producer.
8. A fixture needs an element no accepted artifact defines. This is a **finding for the semantics owners**, not a failure of the experiment.

Recording and review effort is noted qualitatively. Deciding whether it is acceptable is STEP-07 (DP-01).

**Exclusions.** No schema language selected or promoted. No validator, CLI, or tool packaged. No database, graph store, ledger, MCP server, A2A integration, or API. No identity or authentication integration. No agent harness, prompt format, or skill format. No pilot (STEP-07). No methodology templates, worked examples, or role charters (STEP-06). No state vocabulary and no lifecycle graph. No edit to any accepted STEP-01 to STEP-04 artifact. The encodings and any scripts are experiment artifacts and are not accepted architecture. The output is a findings memo.

**Required review gate.**

1. The Moderator authorizes the task and its placement (P-2).
2. Tech Lead review of the experiment design **before** it runs, sampling for hidden representation selection and for protocol, schema, and state collapse.
3. QA sample of fixture coverage and traceability to the catalog.
4. A review of the findings by a role outside the producing configuration where one is available. Where none is, the limitation is recorded (PR-27, PR-28; RQ-16).
5. Product Owner sign-off on what the findings may be used for.
6. Moderator acceptance of the findings memo. The findings are input to later steps and are not a representation decision. A representation decision needs its own accepted artifact.

### 14.5 What the recommendation is not

It is not a selection. It does not make H-2 the preferred hybrid. It does not make any record property of Section 6.7 required. It does not authorize implementation. Its success would not select a representation, and its failure would not reject one. It could change the memo's labels in Sections 6 to 8. Those labels are a reading and can be revised.

---

## 15. Open Questions and Routing

### 15.1 Routed questions

| ID | Question | Routed to | Notes |
| --- | --- | --- | --- |
| RQ-01 | Does the Moderator accept the basis-presentation designation definition as STEP-05's answer to QA5-03, and does a later revision cite it? | MOD-W Moderator | Section 10.2. A revision of the boundary artifact is under BDR-16 |
| RQ-02 | Should a project be required to record a basis-presentation designation for evaluative claims? | MOD-W Moderator (a new rule is Moderator-visible); STEP-06 (practice) | Without it, CRC-45 limb (b) stays unresolved and the protection rests on challenge |
| RQ-03 | Who may record a scope vocabulary and a containment relation, and under what grant? | MOD-W Moderator (protocol question); STEP-06 (DM-02 practice) | Section 9.4. A containment relation recorded without authority widens scopes |
| RQ-04 | What does "recorded" mean at a project boundary and between branches or local drafts? What is the recording authority for record order and time? | Later architecture; STEP-06 (DM-03 practice); STEP-07 (backdating evidence) | Section 10.4. Interacts with DM-03, DR-03, and "project" (Section 4.11 of the boundary artifact) |
| RQ-05 | What do projects record about the binding of an act to an identity, and should the protocol ever require it? | STEP-06 (practice); STEP-07 (F-5, F-2); MOD-W Moderator (any rule); STEP-09 (claim wording); later architecture (identity integration) | Section 9.5 |
| RQ-06 | What form does a representation's conformance statement take: availability of derived conditions at the evaluation point for CRC-18 and CRC-19, the limbs left unresolved (for example CRC-45), the rules left to human review, and the ordering of act, check, and reliance? | Later architecture; STEP-09; RX-1 output if run | Sections 9.5, 12.1. F-5, second sentence |
| RQ-07 | What source-comparability practice should projects use? | STEP-06; RX-1 if run | DR-06; RJ-OQ-10. Section 10.3 |
| RQ-08 | How is instruction content bound to a version in producing configuration? | STEP-06 (DM-05); RX-1 if run | UAD5-06 |
| RQ-09 | At what point is a collective's membership expanded for independence when membership changes after an act? | MOD-W Moderator (the accepted text is silent); RX-1 if run | GC-OQ-05. Section 9.4 |
| RQ-10 | Is an orientation diagram of act kinds helpful to humans, and is a single status or a set of facets preferable to a reader? | STEP-06; STEP-07 | Sections 12.5, 12.6 |
| RQ-11 | Is a serialized state vocabulary wanted, and which? | MOD-W Moderator, after STEP-06 and STEP-07 | S1 to S6, Section 12.6 |
| RQ-12 | Disposition of agent-skills hypotheses H-A, H-B, H-C. H-C can be tested only after a representation exists | STEP-08 | Section 6.9 |
| RQ-13 | Burden of recording acts as separate records, of generating views, and of flag volume | STEP-07 (DP-01) | |
| RQ-14 | What metadata belongs in the record versus the document, beyond the criterion of Section 12.4? | STEP-06; Product Owner | Product OQ-8 |
| RQ-15 | Recovery by a new project, with carry-over undefined. The representation must make a project boundary explicit | STEP-06 (DM-07); MOD-W Moderator | TLR5-01 kept visible |
| RQ-16 | Standing of review by Claude-family models of this and later artifacts, and of any experiment's findings | MOD-W Moderator | PR-27, PR-28 |
| RQ-17 | Who controls writes to the record store, and how are records by one actor kept from edit by another? | STEP-06 (practice); later architecture; STEP-07 | Tamper locality (RC-10) is an environment property |
| RQ-18 | Where does RX-1 sit: an authorized task or a roadmap step? | MOD-W Moderator | P-2 |
| RQ-19 | External evaluator contract, agent-harness conformance, transport and interchange (MCP, A2A) | Deferred. Not addressed (D8; PS-OQ-11; NG-4) | |

### 15.2 Ownership preserved

STEP-06 owns methodology guidance, templates, role charters, evidence worksheets, gate templates, examples, and practitioner guidance. This memo states none. STEP-07 owns the pilot and its evidence. This memo describes no pilot, and RX-1 is not a pilot. STEP-08 owns research synthesis and hypothesis disposition. This memo disposes of none. Publication work (STEP-09) owns promotion to the separate repository and the claim wording of Section 9.5.

### 15.3 Declared choices (UAD5)

Level scale in Section 2.5. The levels are the Development Team's proposals. The Tech Lead or QA determines completeness and levels.

| ID | Decision made | Alternative reading | Where applied | Level |
| --- | --- | --- | --- | --- |
| UAD5-01 | Define the **basis-presentation designation** as the record element behind CRC-45's "evidence-only form", recorded and not inferred | Leave limb (b) unresolved by design (option iii); or require the designation (option iv, a new rule) | 10.2; 8.1; 14.4 | A |
| UAD5-02 | Group catalog questions into demand classes CD-1 to CD-7, as an analytic device | Evaluate each CRC entry per family | 4.2; 8.1; 8.2 | M |
| UAD5-03 | Use qualitative fit labels, with the weakest cell governing a multi-class question, and no totals or ranking | A weighted matrix (barred by BDR-14) | 4.3; 5; 6.10 | L |
| UAD5-04 | Read GCR-35, EKR-40, CRC-51, and the Product Owner's GC-OQ-04 note together: stored conditions are projections or caches, and the record governs when they disagree | Permit a stored condition as the source in some arrangements | 6.6; 6.8; 12.1; 13.1 (Z-3) | A |
| UAD5-05 | Relationships must be carried as attributable records, not bare links, because CRC-01, CRC-49, EKR-33, and EKR-36 attach a recorder, time, designation, and rationale | Treat links as sufficient and carry the rest in prose | 6.7; 10.1; 11.5 | A |
| UAD5-06 | References to instructions, to an item as it stood, and to elements examined by a result must be version-bound | Accept references that resolve to the latest version | 10.3; 10.5; 12.2; 12.7 | A |
| UAD5-07 | Record order and recorded time must not be established solely by the recorder's assertion (O2), and incomparable pairs are unresolved | Treat a recorder's timestamp as the recording time | 10.4; 8.3 | A |
| UAD5-08 | A formal-check result is a distinct record that is never written into an item's recorded condition (RF-1 to RF-8) | Permit a validator to store a result as item state | 12.7; 13.1 (Z-5) | A |
| UAD5-09 | Views are non-normative projections that must preserve VI-1 to VI-8 and name the record and evaluation point | Allow hand-authored summaries without the invariants | 12.4 | A |
| UAD5-10 | Admissibility tests S1 to S6 for any later state vocabulary | Defer all constraints on a vocabulary to STEP-06 | 12.6 | M |
| UAD5-11 | A lifecycle graph is not required by the accepted semantics, and is admissible only as an orientation aid or as orthogonal derived facets | Treat a lifecycle graph as part of the protocol layer | 12.5; 13.1 (Z-8) | A |
| UAD5-12 | Separate kind designation, attribution integrity, authentication, and human-presence assurance, and state that no representation establishes the last | Treat a strong authentication method as proof a human acted | 9.5 | A |
| UAD5-13 | Recommend RX-1 as severable, entered after prerequisites; fall back to prerequisites only | Recommend no experiment, or a single-family experiment | 14 | L |
| UAD5-14 | Source comparability is by reference to a source record; unreferenced descriptions are undetermined, and the gap is flagged | Define a comparison method for unregistered sources | 10.3 | M |
| UAD5-15 | Scope containment is decidable only where scopes are references to a recorded vocabulary with a recorded containment relation, and who may record that relation is open | Treat containment as a representation computation only | 9.4 | M |
| UAD5-16 | Item identity across change needs both version-binding and a continuity link; the continuity link is an assertion by one identity | Treat identifier stability as sufficient | 12.2 | A |
| UAD5-17 | Rejections are "for now" with reconsideration conditions | Reject outright | 13 | L |

The question of what "recorded" means across branches and local drafts is kept as an open question (RQ-04) and is not declared as a reading.

---

## 16. Traceability

### 16.1 STEP-04 carry-forward items

| Item | What was routed | Where addressed | Disposition by this memo |
| --- | --- | --- | --- |
| **QA5-03** | Define the record element "evidence-only form" refers to | 10.2; UAD5-01; RQ-01, RQ-02 | **Defined** (basis-presentation designation) for Moderator disposition. CRC-45 text unchanged |
| **F-5** (DR-07, RJ-OQ-02) | Actor-kind authentication; no claim that the protocol guarantees a human acted; B-eligible rules evaluated at or before reliance | 9.5; 8.5; UAD5-12; RQ-05, RQ-06 | **Answered** (four things separated; no representation proves a human acted). Practice and wording **routed** |
| DR-01 | Accepted-set closure computation, citation-chain grounding, assumption-rooted derivation | 12.3; 11.4 | **Positions stated**; no approach selected |
| DR-02 | Item identity across change | 12.2; UAD5-16 | **Positions stated** (version-binding plus continuity link); no basis selected |
| DR-03, DR-10 | Record order, effective-from-recording, history preservation, evaluation-point semantics | 10.4; UAD5-07; RQ-04 | **Properties stated** (O1 to O5); no source selected |
| DR-04 | Derived conditions; availability for B-tagged rules; visibility of unresolved assumptions | 12.1; 12.4; UAD5-04 | **Positions stated**; availability statement defined |
| DR-05 | Whether carry-over is derived or stored | 12.1; 11.1 | Positions stated: derived; a cache is a projection |
| DR-06 | Source identity comparability | 10.3; UAD5-14; RQ-07 | Declared (reference to a source record); practice routed |
| DR-08 | Scope vocabulary, containment, grant-chain reconstruction | 9.3; 9.4; UAD5-15; RQ-03 | Reconstruction needs as-of data; containment's authority question **routed** |
| DR-09 | How formal-check results are recorded and attributed | 12.7; UAD5-08 | **Requirements stated** (RF-1 to RF-8); form not selected |
| GC-OQ-04 | Derived conditions, item identity, closure | 12.1 to 12.3 | As above |
| GC-OQ-05 | Collective identities and work-assignment relations | 9.4; RQ-09 | Representation needs stated; expansion-time question routed |
| EK-OQ-11, EK-OQ-12, EK-OQ-15; PS-OQ-01 | Explicit versus derived; identity across change; role-specific and machine views; condition names | 12.1, 12.2, 12.4, 12.6 | As above |
| RJ-OQ-01 | Record order, history, act-time versus standing | 10.4 | As above |
| RJ-OQ-03a | Recording of formal-check results | 12.7 | As above |
| RJ-OQ-04 | Scope vocabulary and as-of reconstruction | 9.3, 9.4 | As above |
| RJ-OQ-10 | Source identity comparison | 10.3 | As above |
| Lifecycle graphs; machine views; serialized state vocabulary (Section 13.10 of the boundary artifact) | STEP-05-owned representation choices | 12.4, 12.5, 12.6 | **Positions and admissibility tests stated**; nothing selected |
| H-C (agent skills as projections) | STEP-05 owns the representation half | 6.9; RQ-12 | Not testable until a representation exists; disposition to STEP-08 |
| TLR5-01 | Keep "recovery by new project with carry-over undefined" visible | 15.1 (RQ-15) | Kept visible |
| MW-OBS-016 follow-up | Observe whether STEP-05 re-encounters the six readings | 18.3; research register | Proposed observation (Section 18.3) |

### 16.2 STEP-01 to STEP-04 and architecture

| Source | Used in |
| --- | --- |
| STEP-01 Section 3 (layers); PR-25; INV-13; Section 10 (non-selection) | 1.3 (ROR-02, 03, 04); 7; 12.5 |
| STEP-01 PR-01 to PR-08, PR-27, PR-28; Section 6 | 9; 8.3 |
| STEP-01 PR-05, PR-13; Section 8 (INV-01 to INV-17) | 8.6; 9.5; 14.4 (inputs) |
| STEP-01 PS-OQ-01, PS-OQ-06, PS-OQ-11 | 12.6; 9.4; 15.1 (RQ-19) |
| STEP-02 EKR-09, EKR-10, EKR-26 to EKR-28, EKR-31, EKR-33, EKR-35, EKR-36, EKR-40 | 10.2; 11; 12.2; 12.3 |
| STEP-02 EK-OQ-03, EK-OQ-09, EK-OQ-11, EK-OQ-12, EK-OQ-15 | 9.4; 10.3; 12 |
| STEP-03 GCR-04, GCR-08, GCR-29, GCR-35, GCR-47, GCR-66; Section 8 | 9.1; 11; 12.3; 12.4 |
| STEP-03 GC-OQ-04, GC-OQ-05; Product Owner note A-6 | 12.1; 9.4 |
| STEP-04 Sections 4, 5, 9, 10, 11, 12; CRC-01 to CRC-64; BDR-07, 11, 14, 16, 17; HJC-12, 16, 18, 21 to 26; UAD4-11, 23, 31, 32; DR-01 to DR-10 | 8; 9; 10; 11; 12 |
| `mod-w/architecture.md` D1 to D10; Deferred Decisions; Constraints | 3; 6.7; 13 |
| `mod-w/product.md` G-3, NG-1, NG-2, NG-4, FR-3, FR-4, FR-6, FR-7, OQ-8, E-1 | 1; 12.4; 14.2 |
| `mod-w/roadmap.md` STEP-05 | 14.3 (P-2); 15.2 |
| Research: document-metadata and views; protocol/schema/state; agent skills | 6.2; 6.5; 6.9; 12.4 |

### 16.3 Requirements and decisions

| Item | Covered in |
| --- | --- |
| G-3 machine-readable protocol | 4; 6; 7 |
| NG-1, NG-2 | 1.3; 13; 14 |
| FR-3 evidence | 10; 8 |
| FR-4 self-approval | 9; 9.5 |
| FR-6 provenance | 10; 11 |
| FR-7 hypotheses and assumptions | 11; 12.1 |
| D1 to D10 | 3 |

---

## 17. Acceptance-Check Traceability

`mod-w/step-05.md` lists 25 acceptance checks. Each is numbered below in order. The "Self-assessment" column is the Development Team's view and is not a review.

| ID | Acceptance check | Where met | Self-assessment |
| --- | --- | --- | --- |
| AC5-01 | Memo added and states STEP-05 is evaluation only | Front matter; 1.2; ROR-01 | Met |
| AC5-02 | Compares Markdown, YAML frontmatter, JSON, structural schemas, sidecars, central state or registry, graph or ledger-style records, hybrids, agent instruction or skill/prompt conventions | 6.1 to 6.9; 6.10; 6.11 | Met |
| AC5-03 | Preserves D2 by evaluating protocol, schema, and state separately for every option | 7; 6.10 (RC-01) | Met |
| AC5-04 | States that schema validity does not equal governance validity | 1.3 (ROR-02); 6.4 | Met |
| AC5-05 | States that recorded state does not equal protocol authority | 1.3 (ROR-03); 12.1 | Met |
| AC5-06 | States that a representation adapter is replaceable and subordinate | 1.3 (ROR-04); 4 (Adapter) | Met |
| AC5-07 | Evaluates each option against actor identity, participation capacity, authority grants, conferral scope, independence, D10 authority-chain reconstruction | 9.2; 9.3; 9.4 | Met; labels are a reading and not independently sampled |
| AC5-08 | Evaluates each option against provenance, producing configuration, source lineage, evidence basis, revalidation | 10.3; 10.5; 11.5 | Met |
| AC5-09 | Evaluates each option against challenge, disagreement, gate basis, standing record, exception, exposure, revalidation | 11.1 to 11.5 | Met |
| AC5-10 | Evaluates each option against STEP-04 candidate rules, recorded-judgment checks, contextual judgments, violation-handling categories | 8.1 to 8.5 | Met by demand-class mapping. Not an entry-by-entry per-family table (Section 17.1) |
| AC5-11 | Defines or routes the record element for QA5-03 | 10.2; RQ-01, RQ-02 | Met (defined, and the disposition is routed) |
| AC5-12 | Addresses actor-kind authentication for F-5 without claiming a protocol representation alone proves a human acted | 9.5; 13.1 (Z-10) | Met |
| AC5-13 | Addresses derived conditions, item identity, closure, formal-check result form, record order, machine views, lifecycle graph questions, serialized state vocabulary | 12.1 to 12.7; 10.4 | Met |
| AC5-14 | Distinguishes what a representation can check from what an authorized human must judge | 8.6; 8.3; 8.4 | Met |
| AC5-15 | Identifies which semantics each option cannot carry alone | 6.1 to 6.9 (Cannot carry alone); 7 | Met |
| AC5-16 | Identifies which options would create hidden architecture decisions if selected now | 6.1 to 6.9; 13.2 | Met |
| AC5-17 | Recommends no experiment, one narrow experiment, a narrow hybrid experiment, or prerequisites, with rationale | 14.1; 14.2 | Met |
| AC5-18 | Any recommended experiment includes purpose, scope, inputs, success/failure signals, exclusions, required review gate | 14.4 | Met |
| AC5-19 | Recommended experiment is not implemented and does not become the accepted representation by recommendation | 14.1; 14.5 | Met |
| AC5-20 | Routes methodology guidance to STEP-06 and pilot validation to STEP-07 without duplicating ownership | 15.1; 15.2 | Met |
| AC5-21 | Routes research synthesis or hypothesis disposition to STEP-08 where applicable | 15.1 (RQ-12); 15.2 | Met |
| AC5-22 | Does not implement or select a final schema language, storage model, workflow engine, validator, lifecycle graph, state vocabulary, transport, CLI, prompt format, agent harness, runtime integration, database, API, or publication package | 1.3 (ROR-01); 12.5; 12.6; 13; 14.4 (Exclusions) | Met |
| AC5-23 | Does not introduce confidence scores, numeric sufficiency weights, or artificial precision | 1.3 (ROR-06); 4.3; 5; 12.4 | Met. Qualitative fit labels are unweighted and unranked (UAD5-03) |
| AC5-24 | Any concrete transferability evidence is proposed under the research governance process | 18.3; `research/mod-w-transferability/observations.md` | Met by a proposed entry (MW-OBS-017). The Moderator decides its disposition |
| AC5-25 | STEP-05 final acceptance is not recorded until Phase 3a, 3b, and 3c have occurred or been waived | 2.3 | Not a property of this memo. The memo records itself as Draft. Held by the Moderator |

### 17.1 Acceptance checks the Development Team believes are only partly satisfied or limited

- **AC5-10.** The memo evaluates families against demand classes grouped from the 64 entries (Section 8.1). It does not give a per-entry, per-family table. A reviewer who wants entry-level fit composes it from Section 8.1 and 8.2. The grouping is a reading and is declared (UAD5-02).
- **All fit labels** (Sections 6.10, 6.11, 8.2, 9.3, 10.5) are the Development Team's judgment from desk analysis. No family was built or tried. No cell was independently sampled.
- **Reading coverage** is incomplete (Section 2.4). A rule read only by extraction may be mis-stated.

---

## 18. Change Notes

### 18.1 Change notes

| Date | Change | Reason |
| --- | --- | --- |
| 2026-10-03 | Initial draft v0.1 | STEP-05 work package approved by the MOD-W Moderator (`mod-w/reviews/MODERATOR-REVIEW-STEP-05-SETUP.md`). Development Team authorized to implement |

### 18.2 Pre-submission checks

Run by the Development Team on the draft before submission, using a throwaway script and a manual re-read. They are self-review and confer no independence (Section 2.4). The script is not kept in the repository.

| Check | Result |
| --- | --- |
| Local identifiers (RC, RO, ROR, RQ, AC5, Z, UAD5, RF, VI, CD, H, P) are each defined and cited | All resolve. RC-01 to RC-15, RO-01 to RO-09, ROR-01 to ROR-10, RQ-01 to RQ-19, AC5-01 to AC5-25, Z-1 to Z-10, UAD5-01 to UAD5-17, RF-1 to RF-8, VI-1 to VI-8, CD-1 to CD-7, H-1 to H-4, P-1 to P-4 |
| Identifiers of accepted artifacts fall inside the range that exists (CRC up to 64, HJC up to 26, DR up to 10, DM up to 9, DP up to 6, GCR up to 68, EKR up to 41, PR up to 28, UAD4 up to 32, BDR up to 18, INV up to 17, and the open-question series) | No out-of-range identifier. **This checks range only.** It does not check that a cited rule says what the memo says it says |
| Forbidden-term scan (confidence, score, weight, rank, percent) | Every hit is a statement that bars the practice, with one exception: "score alike" in a hybrid reading note, reworded |
| Unqualified section cross-references that collide with the numbering of the boundary artifact (both use Sections 9, 10, 12) | Four found (Sections 9.2 and 9.6 cited without the file name). Qualified |
| Citation re-read | One wrong citation found and corrected (a Section 6.2 reference attached to PR-27). The "Section 14.4" statement in Section 2.2 was corrected to say what it says. A gap in the UAD5 numbering was closed |
| Accepted artifacts untouched | `git status` shows this memo as the only new file made by this work (`mod-w/step-05.md` and the STEP-05 setup review were already untracked). The only modified tracked file is `research/mod-w-transferability/observations.md`, by an appended proposed entry (MW-OBS-017) and its header dates. No STEP-01 to STEP-04 artifact, no architecture, domain language, roadmap, or product file was modified |

**Not checked.** Quoted accepted text against its source. Fit labels. Whether any family would behave as the memo says. The classification of catalog entries into demand classes. All of these are for the Tech Lead and QA sampling.

### 18.3 Transferability evidence

A concrete observation is proposed under the research governance process as **MW-OBS-017** in `research/mod-w-transferability/observations.md`. Status: proposed. The Moderator decides whether to accept, modify, or reject it, and it is not blocking. In summary: (1) the work package's "read these files first" instruction met inputs of about 980 KB, one of them beyond a single read, so the memo carries a reading-coverage statement (Section 2.4); (2) unqualified section cross-references became ambiguous when a step's artifact cites an earlier artifact with the same section numbering; (3) the STEP-04 declared readings were re-encountered as constraints on which record elements must be discrete (UAD4-09, UAD4-13, UAD4-31, UAD4-32), which answers the MW-OBS-016 follow-up only in part; (4) document-native mechanical checks were used again, the third step with such evidence after MW-OBS-015 and MW-OBS-016.

### 18.4 Files changed in this delivery

- Added: `prod-w/representation-options.md`.

MOD-W v5.0.1
