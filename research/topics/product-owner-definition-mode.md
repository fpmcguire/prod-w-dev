---
artifact:
  type: research-note
  version: 0.1
  created: 2026-10-03
  updated: 2026-10-03
  evidence_as_of: 2026-10-03
context:
  project: prod-w-dev
  status: research
notes:
  - "Kept as a research note by Moderator decision, 2026-10-03. Not an entry in the MOD-W transferability observation register, and no MW-OBS number is assigned."
  - "Derived note. Nothing here is a PROD-W requirement, an architectural decision, or a change to MOD-W."
  - "Drafted by a Claude-family model and second-read by another. Not independent (PR-27, PR-28)."
---

# MOD-W's Product Owner Definition Mode Is a Four-Step Prompt and a Template, with No Elicitation Procedure, Completeness Check, or Format Check

**Date:** 2026-10-03 (investigation and draft)  
**MOD-W area:** Product Definition ceremony; Product Owner role (Definition mode); `product.md` template  
**Project stage:** Between STEP-04 acceptance and STEP-05. Outside any Step  
**Observed by role:** None. Drafted by GitHub Copilot (Claude model) in a VS Code session at the Moderator's request  
**Classification (if ever registered):** `NOT_YET_TESTED` for whether the definition-mode procedure is sufficient to produce a well-formed `product.md`  
**Status:** Research note, by Moderator decision 2026-10-03. Not an observation-register entry. Not accepted as evidence  
**Significance:** Medium  
**Related:** MW-OBS-001, MW-OBS-002, MW-OBS-014

### Scope caveats, stated first

1. **This may not be a non-software finding.** The gap would exist in a software project too. The Moderator decided on 2026-10-03 to keep this as a research note and not as a register entry.
2. **This is a self-report.** The drafter investigated and wrote this in one session. A second pass by another Claude-family reviewer (a claude.ai chat, 2026-10-03) supplied corrections that were checked against the files and are applied below. Neither pass is independent of the Development Team's producing configuration (PR-27, PR-28).
3. **The canonical MOD-W repository was read over the web on 2026-10-03, at commit `1eb5e1a`.** It is not archived here and may have changed since. The commit lets a reader check the claims.
4. **No MOD-W Step or gate was involved.**

### MOD-W Mechanism or Assumption

MOD-W's Phase 0a is "Moderator + Product Owner produce approved `product.md`" (`mod-w/templates/MOD-W.md`). The Product Owner's Definition tooling is "Claude chatbot + Perplexity + Gemini". The assumption is that this role and its prompt are enough to help the user define the intended project and produce `product.md` in the expected format.

### Observation

**What MOD-W provides for definition mode**

- **Prompt:** the canonical `prompts/product-owner.md`, Mode 1 (Product Definition). Given a product brief from the Moderator, the Product Owner is told to:
  1. clarify the problem, users and value proposition;
  2. identify primary workflows and edge cases;
  3. propose out-of-scope items for the iteration;
  4. draft or refine `product.md`.
- **Operating setting:** the Moderator drives it with external chatbots, and "there is no configured agent infrastructure at this stage". The Moderator may use Perplexity and Gemini "informally" to challenge scope and assumptions.
- **Style rules:** plain language, bullets, in scope against out of scope, and answer depth `minimal`, `options` or `full`.
- **Gate:** the Moderator approves `product.md` before architecture work.
- **Roles and tooling docs:** `docs/roles.md` says the Product Owner is supported by chatbot sessions during definition, and that the Tech Lead "cross-validates `product.md` with the Product Owner". `docs/role-tooling-matrix.md` lists the three tools as optional ("use what fits the project") and gives Gemini the job of informal cross-validation of scope, goals and user workflows.
- **Approval checks, in one place only:** the Gemini integration article (`articles/modw-with-gemini.md`, "Product shaping phase") lists three Moderator checks: requirements are specific and testable, constraints are explicit, assumptions are documented.
- **Ceremony:** `docs/ceremonies.md` section 1a gives When, Who, Purpose and Output (an approved `product.md`) and no activities list. Step Planning (section 2) does have one.
- **Format:** `templates/PRODUCT.md` is the only format definition. `docs/artifacts.md` adds one sentence on content (problem, users, workflows, requirements, constraints, out-of-scope items and product-level acceptance intent). The template's headings are Problem Statement, Target Users, Goals, Non-Goals, High-Level Requirements (R-IDs with Must have, Should have and Nice to have), Key User Scenarios, Acceptance Criteria, Risks, Assumptions and Constraints, Open Questions, Sources and Change Log.

**What MOD-W does not provide**

- No interview or elicitation questions, no way to decide when a definition is complete, and no checklist for the format, in the core docs read. The only approval checks found are the three Gemini-article bullets above. They are not in the role prompt or the ceremony description.
- `docs/moderator-checklist.md` has eight Step-level sections and opens with "Use this checklist for every Step". It has no Product Definition section. It mentions `product.md` only as "still accurate for this Step" (section 1) and in a Challenge question (section 2).
- No agent, rule or skill for definition mode. In this repository `mod-w/agents/`, `mod-w/rules/` and `mod-w/skills/` are empty on disk and not tracked by git, so they do not exist in the repository on GitHub. Canonical MOD-W has `agents/` (architect, qa, reviewer, validator) and `rules/` (architecture, security, testing). By name, none addresses definition (their contents were not read). It has no top-level `skills/` folder. `docs/artifacts.md` reserves `skills/` for `SKILL.md` procedures added only when a procedure becomes reusable, and the README's example layout shows `skills/` as "empty until a procedure earns one".
- `prompt-guidelines.md` is generic (restate, plan, wait, execute; red-team check) and contains nothing specific to definition.

**What happened in this project's `mod-w/product.md`**

- It departs substantially from the template. It uses FR-, G-, NG-, HA-, PE-, WD-, GR-, RR-, A-, OQ- and E- identifiers, not R-IDs. It has a "Target Users and Stakeholders" section with a stakeholder table (Stakeholder, Primary Interest, Authority Scope), not the template's User, Context, Goal table. It has no Key User Scenarios section and no priority column. It adds sections the template lacks, including Evidence Expectations and Human Authority Boundary.
- Its product-level acceptance criteria are "Acceptance Criterion 1" to "5" in prose, not `AC-n` identifiers. `mod-w/roadmap.md` cites them as AC-2 to AC-5, which resolves by number and name and not by identifier. `mod-w/id-glossary.md` already records that AC-n IDs were not found in `product.md`.
- The template says R-IDs are "required for traceability", the lifecycle model is `R-ID -> DS-ID -> D-ID -> step-xx.md`, and `STEP-XX.md` asks for R-IDs. Step files here cite FR- and similar identifiers instead, so traceability works through a different scheme.
- MW-OBS-002 records that Moderator review caught premature mechanisation in the draft. No format or completeness checklist is recorded as having been applied.

### Evidence

- `mod-w/templates/MOD-W.md` (roles table, Phase 0a, Canonical Documents)
- `mod-w/templates/PRODUCT.md`, `STEP-XX.md`, `document-lifecycle.md` (Traceability Model), `ai-agents.md`, `prompt-guidelines.md`
- `mod-w/product.md` (identifier scheme and section list)
- `mod-w/agents/`, `mod-w/rules/`, `mod-w/skills/` (empty on disk and untracked by git, 2026-10-03)
- `research/mod-w-transferability/observations.md` (MW-OBS-001, MW-OBS-002), `research/observations/MW-OBS-014-informal-cross-model-review.md`
- Canonical MOD-W at commit `1eb5e1a`, read 2026-10-03 via GitHub: `README.md`, `prompts/product-owner.md`, `docs/ceremonies.md`, `docs/moderator-checklist.md`, `docs/roles.md`, `docs/artifacts.md`, `docs/role-tooling-matrix.md`, `articles/modw-with-gemini.md`, and the `prompts/`, `agents/` and `rules/` directory listings, at https://github.com/fpmcguire/mod-w. **Not archived in this repository.**

### Contradictory Evidence, Preserved

- **PROD-W got an approved `product.md` anyway.** MW-OBS-001 and MW-OBS-002 record that the Product Definition concept transferred and the Moderator gate worked. A thin procedure may be adequate because the Moderator supplies the missing structure.
- **The thin procedure may be deliberate.** MOD-W describes itself as a living methodology and says docs should "earn their existence". A short prompt may be a choice.
- **The deviation from the template may be intentional.** `product.md` was accepted by the Moderator. No record shows the R-ID departure was unintended.
- **Read since the first draft:** `docs/roles.md`, `docs/artifacts.md`, `docs/moderator-checklist.md`, `docs/role-tooling-matrix.md` and the Gemini article. They add the points above and no definition procedure.
- **Still not read:** the contents of the upstream `agents/` and `rules/` files, and `docs/step-lifecycle.md`, `docs/quality-gates.md`, `docs/faq.md` and `docs/glossary.md`. They may contain guidance this draft missed.
- **Sample of one**, on a methodology project whose Product Owner and Moderator are closely related.

### Effect on Work

- None so far. PROD-W's own definition is accepted and later steps are built on it.
- It bears on PROD-W's own design. If PROD-W specifies how a user is helped to define a project, it cannot reconstruct a MOD-W process. Any such procedure would be new, and would need its own evidence under the protocol.

### Local Adaptation Required

None proposed. Offered for Moderator consideration only:

1. Decide whether the thin definition mode is a MOD-W finding worth registering, or a limit that MOD-W accepts by design.
2. If PROD-W is later asked how a project is defined, treat that as new design work and not a transfer of an existing MOD-W procedure.
3. Check the documents listed as still not read before registering this.

### Moderator decisions

- **Register or note:** kept as a research note (Moderator, 2026-10-03). It is not appended to `research/mod-w-transferability/observations.md`.
- **Identifier deviation (R-IDs against the typed identifiers in `product.md`):** resolved by the Moderator on 2026-10-03 as an accepted terminology reinterpretation, not an adaptation. It is recorded in `mod-w/id-glossary.md` Section 1.1. `mod-w/product.md` is unchanged and no crosswalk exists.
