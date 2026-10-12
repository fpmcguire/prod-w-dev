---
artifact:
  id: RESEARCH-CONVERSATION-002
  type: raw-source-archive
  version: 0.1
  created: 2026-10-12
  updated: 2026-10-12
  evidence_as_of: 2026-10-12
context:
  project: prod-w-dev
  status: raw-source
  source: "Moderator-authored document `workflow-observations.md`, supplied to a Claude Code session on 2026-10-12"
notes:
  - "Verbatim copy of the source document below the horizontal rule. Do not edit it."
  - "The observations were collected while the Moderator developed a separate MOD-W project, not prod-w-dev. The source does not name that project or state its domain."
  - "Derived analysis: research/topics/moderator-workflow-observations.md."
---

# Moderator Workflow Observations (Separate MOD-W Project), Raw Source

---

# Workflow Observations: Mod W and Prod W

Collected while developing a new Mod W project. Intended for consideration in both **Mod W** (build workflow) and **Prod W** (product validation / feasibility methodology).

Date compiled: 2026-10-12

## Summary

| # | Observation | Type | Applies to |
|---|-------------|------|------------|
| 1 | Role handoffs and review replies need to be self-explanatory | Improvement | Mod W, Prod W |
| 2 | Mod W now has a traceable history | Positive | Mod W (check Prod W) |
| 3 | Tech lead's architecture and roadmap need fuller explanation | Improvement | Mod W, Prod W |
| 4 | No product ideation facility: propose Discover-W | New skill | Mod W, Prod W |
| 5 | Step-by-step moderation lets the moderator steer mid-development | Positive | Mod W, Prod W |
| 6 | Every gate approval must trigger record, commit, and next prompt | Process rule | Mod W, Prod W |

---

## Observation 1: Role handoffs and review replies need to be self-explanatory (improvement)

### Observation
After every role finishes its tasks, I repeat the same moderator steps: ask which role is next, accept or reject the work, record the decision, commit, and request the next role's prompt. In addition, review replies cite internal codes (R1, R2, R3 for requirements; AC1, AC2, AC3 for acceptance criteria) that the moderator cannot easily interpret.

### Idea
1. **After-task closing protocol in the role prompts.** When a role finishes, it:
   - Summarizes what was completed, files changed, and any deviations or open questions.
   - Tells the moderator exactly what to review (code review, acceptance criteria check, build/tests, summary vs. actual changes) and asks for accept or reject, with feedback if rejected.
   - Records the decision in the workflow log.
   - Commits on acceptance (revises on rejection, without committing).
   - Names the next role and hands over its prompt.
2. **Human-readable references.** Keep a lookup table mapping each code to its plain-language wording, and require roles to spell out every code they cite, e.g. "AC2 (the form shows a validation error when the email is empty)". The moderator's review checklist lists the relevant items in this spelled-out form.

| Code | Type | Plain-language requirement or criterion |
|------|------|------------------------------------------|
| R1 | Requirement | *(full text)* |
| AC1 | Acceptance criterion | *(full text)* |

### Benefits
- Fewer repeated manual prompts.
- Onboarding: people unfamiliar with the workflow are reminded of the next step and what the moderator must review.
- Faster, more confident moderator decisions.

### For consideration
- Define the role sequence once in a shared place so each role can name its successor.
- Keep the protocol and the code table in shared files referenced by all role prompts (single source of truth).
- Add a per-role moderator review checklist.
- Decide the commit policy: commit only on acceptance, or checkpoint rejected work on a branch or with a tag.
- Consider having roles include the relevant rows of the code table in their handoff summary.

---

## Observation 2: Mod W now has a traceable history (positive)

### Observation
Mod W now has a tracking system that records steps, changes, and acceptances. A developer can go back through that list to understand what was done and why, and associate each entry with the corresponding GitHub commit.

### Why it matters
- **Code comprehension.** The decision trail shows what was requested, changed, and accepted.
- **Commit traceability.** Linking log entries to commits connects the "why" with the "what".
- **Accountability.** Acceptances and rejections are documented.

### For consideration
- Keep this as a core feature, and check whether Prod W has an equivalent.
- Standardize the log entry format: role, date, decision, requirements and criteria covered (spelled out), and commit hash.

### Dependency
The closing protocol (Observation 1) feeds this log consistently, and spelled-out codes keep old entries readable later.

---

## Observation 3: Tech lead's architecture and roadmap need fuller explanation (improvement)

### Observation
I often spend several hours developing a product outside the Mod W and Prod W workflows. When I bring it in, the product owner converts it into the Mod W format for `product.md`. That work then goes either directly to the tech lead or into Claude Designer for prototyping first. The tech lead produces `architecture.md` and the roadmap. These are as critical as `product.md`, or more so, because they determine how everything is built.

### Problem
The architecture and roadmap are presented without enough explanation for the moderator to make an educated accept or reject decision.

### Idea
Require the tech lead to explain, not just deliver.

1. **Architecture explanation.** For `architecture.md`, include:
   - The chosen or recommended structure and why it was chosen.
   - Realistic alternatives (the options I could have used).
   - Ramifications of each option: trade-offs, complexity, scalability, maintenance cost, what becomes hard to change later.
   - The assumptions it depends on, drawn from `product.md`.
2. **Roadmap explanation.** For the roadmap, include:
   - How each step relates to the architecture (which components or decisions it builds on).
   - Why the steps are in this order: dependencies, risk reduction, early value, technical prerequisites.
   - What would change in the order if a different architecture option were chosen.
3. **Moderator decision support.** The tech lead's closing protocol lists what the moderator must review and asks for an explicit decision on the architecture before the roadmap is accepted, since the roadmap depends on it.

### For consideration
- Add a required "options and ramifications" section to the architecture template.
- Add a "roadmap rationale" section mapping steps to architecture components and dependencies.
- Decide whether architecture is accepted separately from the roadmap, and in which order.
- Define how the Claude Designer prototyping path hands its results to the tech lead, so prototype decisions are not lost.
- Log architecture and roadmap decisions with the options considered, so the history captures why a choice was made.
- Pre-workflow work has no log entries or R/AC codes; the product owner's conversion step is where a baseline entry could be created.

---

## Observation 4: No product ideation facility: propose Discover-W (new skill)

### Observation
Mod W is a build workflow. Prod W is a product validation / feasibility methodology. Neither provides a way to ideate a product, so that work currently happens outside the system, often over several hours (see Observation 3).

### Decision
Create a new skill, **Discover-W**. Naming convention: all Mod and Prod skills end in "-W".

### Purpose
Discover-W interrogates the moderator and helps them brainstorm while developing a product. Its output is a `product.md` file that can be imported into Mod W or Prod W.

### How it relates to the other observations
- Replaces the ad hoc pre-workflow phase, so ideation is structured and logged.
- Reduces the product owner's conversion burden if it emits `product.md` already in the Mod W format.
- Can write a baseline log entry so the history does not start with a gap.
- Can produce R and AC codes with plain-language wording from the start (Observation 1).

### Open questions
- **Format contract.** Should `product.md` be identical for Mod W and Prod W, or does each need extra sections (e.g. feasibility hypotheses for Prod W)?
- **Interview structure.** Which areas should it probe: problem, users, value, scope, constraints, risks, success criteria, non-goals?
- **Roles.** A single role, or the same role, handoff, and closing-protocol pattern as the other skills?
- **Moderator control.** Should it summarize and ask for acceptance before writing `product.md`?
- **Claude Designer path.** Does prototyping happen after Discover-W, and how are results fed back into `product.md`?
- **Re-entry.** Can a `product.md` be sent back into Discover-W later to refine or extend the product?

### Expected benefit
A complete, structured path from idea to build: Discover-W, then Prod W (validate) and/or Mod W (build), with consistent artifacts and traceability.

---

## Observation 5: Step-by-step moderation lets the moderator steer mid-development (positive)

### Observation
Having a human moderator in the loop takes time, but it lets the moderator watch the product take shape step by step. Because progress is visible at each stage, it is easy to jump in mid-cycle and ask for changes, alterations, or additional features.

### Why it matters
- **Early course correction.** Changes requested mid-step are cheaper than rework after the build.
- **Evolving product understanding.** Seeing real output reveals missing features that were hard to foresee during ideation.
- **Moderator control.** Accept/reject checkpoints double as natural points to redirect the work.

### For consideration
- Add an explicit "change request" path to the closing protocol, e.g. *accept with changes* or *accept and add a new requirement*.
- Define how a change request updates `product.md`, the R and AC codes, and the roadmap, and which role handles each update.
- Log each change request with its reason, so scope changes stay traceable.
- Have the responsible role state the impact of a change (effort, affected steps, architecture implications) before the moderator confirms it.
- Treat mid-cycle changes as normal rather than as exceptions, even with Discover-W in place.

---

## Observation 6: Every gate approval must trigger record, commit, and next prompt (process rule)

### Rule
For both Mod W and Prod W, whenever the moderator reviews or approves a code change at any gate:

1. **Record** the review and decision in the workflow log.
2. **Commit** the approved change to Git.
3. **Generate** the prompt for the next gate.

This is the workflow-level rule behind the closing protocol in Observation 1.

### Suggested sequence at each gate
1. The moderator reviews the change and decides (accept, reject, or accept with changes).
2. On approval, write the log entry: gate, date, decision, requirements and criteria covered (spelled out), notes on requested changes.
3. Commit the change and add the commit hash to the log entry.
4. Generate and present the next gate's prompt, naming the next role or step.

### For consideration
- **Enforcement.** A gate is complete only when record, commit, and next prompt are all done.
- **Rejections.** Record them, but do not commit and do not generate the next gate's prompt. Generate the revision prompt for the same gate instead.
- **Ordering.** Log first, then commit, so the hash can be added (possibly via a small follow-up commit, or a log that references the commit afterwards).
- **Scope.** Define what counts as a "gate" in each workflow so the rule applies consistently.

### Expected benefit
No manual repetition by the moderator, a complete audit trail with commit links, and no stalled handoffs.

---

## Cross-cutting recommendations

1. **Shared protocol file.** One closing protocol (Observations 1, 5, 6) referenced by all role prompts in both workflows.
2. **Shared code table.** One R/AC reference table with a spell-out rule (Observation 1).
3. **Standard log entry format.** Role/gate, date, decision, requirements and criteria (spelled out), change requests, commit hash (Observations 2, 6).
4. **Role sequence defined once.** So each role can name its successor (Observation 1).
5. **Templates with required explanation sections.** Architecture options and ramifications, roadmap rationale (Observation 3).
6. **Discover-W as the entry point.** Producing `product.md` plus a baseline log entry (Observation 4).
