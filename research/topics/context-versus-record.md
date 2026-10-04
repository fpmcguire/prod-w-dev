---
artifact:
  type: research-note
  version: 0.1
  created: 2026-10-04
  updated: 2026-10-04
  evidence_as_of: 2026-10-04
context:
  project: prod-w-dev
  status: research
  source_conversations:
    - "Claude review of Pi (https://pi.dev/) for PROD-W, 2026-10-04 (not archived under research/conversations/)"
notes:
  - "Derived note. Nothing here is a PROD-W requirement, an architectural decision, or a change to MOD-W or to any accepted artifact."
  - "Statements about Pi come from pi.dev documentation pages read on 2026-10-04. The reviewer relied on Pi documentation; source links exist in the docs, but source behavior was not independently audited."
  - "Statements about Claude Code are carried from research/topics/agent-skills-and-protocol-relationship.md and were not re-verified for this note."
  - "Statements about accepted PROD-W artifacts are readings of repository state as originally reviewed at commit 79ccb6a. Later commits may have changed roadmap/status metadata, but not the accepted passages cited here. The reviewer searched for terms and read the passages cited below. The reviewer did not re-read the accepted artifacts in full."
---

# Context Versus Record

## Research status

This is a **research question with competing hypotheses**, not a decision.

It does not reopen any accepted Step, does not change the roadmap, and does not select an agent harness, prompt format, or runtime integration (NG-1, NG-2; `prod-w/protocol-semantics.md` Section 10).

## Question

> **When an AI actor produces an item, can what the model was actually given differ from what the record of that work shows, and does PROD-W need to say anything about it?**

## Why the question arises

PR-27 places the configuration that produced an action (model, reasoning effort, harness, tooling, instructions) in the action's provenance. `prod-w/methodology-guidance.md` (Section 8 and its instruction-version-binding rule) defines instructions broadly: system or standing instructions, the task brief, a role charter in force, a named skill or instruction bundle, templates the actor was told to follow.

These accepted passages describe what the actor was **told**. They do not, as far as the reviewer found, address what remained **in the model's context** when it acted. The STEP-07 pilot shows the practical edge of this: instruction version-binding was recorded as "not bound" and reasoning effort as "not determinable" (R-007, R-008; ISS-19), and the guidance allows both statements.

## What is established

As of 2026-10-04.

### From the Pi documentation (pi.dev, session-format and security pages)

Sources checked:

- https://pi.dev/docs/latest
- https://pi.dev/docs/latest/how-pi-works
- https://pi.dev/docs/latest/sessions
- https://pi.dev/docs/latest/session-format
- https://pi.dev/docs/latest/compaction
- https://pi.dev/docs/latest/message-types
- https://pi.dev/docs/latest/skills
- https://pi.dev/docs/latest/security

- Sessions are append-only JSONL trees. Entries link by `id` and `parentId`, and each carries an ISO timestamp.
- The model-visible context is **derived** from the log, not stored as one object. Pi documents a rebuild procedure: walk from the current leaf to the root, honor the latest compaction, then apply context edits.
- A **compaction** entry stores a summary of earlier messages and a system prompt and tool checkpoint. When context is rebuilt, the summary replaces the entries before the first kept entry. The replaced entries remain in the raw log.
- A **context edit** entry changes future model context for one earlier entry: it can omit the entry or replace its content. The documentation states the target entry stays unchanged in raw history, in the interface, in exports, and in session accounting. Edits apply only on the branch where they were made.
- A **custom message** entry is injected by an extension and does participate in model context. It carries a display flag. When the flag is false, the entry is hidden in the terminal interface but still sent to the model.
- Extension state entries and usage entries do not participate in model context.
- The system prompt and tool declarations are persisted as system messages that patch named sections. Replaying them in order yields the prompt and tools in force.
- Context files (`AGENTS.md`, `CLAUDE.md`) load regardless of the project-trust decision. Skills are advertised in the prompt by name and description. Their full instructions enter context only when the model reads them, and the documentation says a model may fail to load a relevant skill.

### Carried from the sibling note (Claude Code, not re-verified)

- Skill content is not re-read on later turns. After compaction only the start of an invoked skill may be kept.

### What is not established

- Whether Claude Code or Codex expose an equivalent of Pi's rebuild procedure, so that model-visible context can be reconstructed from their records.
- Whether Pi's documented rebuild matches what Pi actually sends to a provider. The reviewer did not read the source or observe a request.
- Whether Pi's session files are tamper-evident. The documentation makes no integrity claim, and the reviewer did not look for one beyond the pages listed above.

## Why Pi is useful as a reference case

Pi is useful to PROD-W and MOD-W as a concrete reference case, not as a selected harness or recommended runtime.

- Pi provides an example of a session record that is not identical to model-visible context. The raw record, active branch, compaction summaries, context edits, skill loading, custom messages, and system/tool replay together determine what the model sees.
- Pi's JSONL session tree is relevant to PROD-W questions about record order, branching, reconstruction, and what counts as a project record versus a derived view.
- Pi shows one pattern where compaction changes model context while raw entries remain available for later inspection.
- Pi's replayable system/tool messages are relevant to instruction-version binding, tool-version visibility, and producing-configuration records.
- Pi's skill-loading model clarifies the difference between instructions that are available, instructions advertised to the model, and instructions actually loaded into context.
- Pi's trust model is a useful warning for PROD-W and MOD-W: project trust, context loading, and sandboxing are separate concerns. Trusting a project or loading its resources does not by itself make tool execution safe.

These points do not justify adopting Pi, requiring any Pi-like format, or treating Pi as satisfying harness conformance. They show that "context versus record" is a real design dimension that a later harness-conformance question can test.

## Competing hypotheses

All three are hypotheses. None is adopted.

### CR-H1. The record is sufficient as it stands

Accountability attaches to produced items, actor identity, and the stated producing configuration (PR-27). What remained in the model's context is an implementation detail of the harness. If it matters, a reader weighs "instructions: not bound" and similar statements as the guidance already allows.

*Reading in favor:* the guidance already permits "not determinable" and says that such a statement stays visible and is an input to the reader's weighing.

*Reading against:* the existing facets cover what was given, not what survived. A reader cannot tell that an instruction was dropped by compaction or never loaded.

### CR-H2. Retained context is part of producing configuration

The "instructions" or "tooling" facet should be read to include context management: whether compaction, truncation, or context editing occurred between the instruction being given and the action being produced. This is a statement an actor makes, not a mechanism PROD-W prescribes.

*Reading in favor:* it uses an existing facet and selects nothing.

*Reading against:* it asks an actor to state something it may not be able to determine. The guidance's "not determinable" would cover that case, which brings it close to CR-H1 in practice.

### CR-H3. This is a harness-conformance matter, not a protocol matter

A harness either can or cannot give a faithful account of model-visible input. PROD-W states no requirement. Where a harness cannot, the actor says "not determinable". The question belongs with deferred agent-harness conformance (RQ-19) and with the research note `research/topics/agent-harness-conformance.md`.

*Reading in favor:* consistent with the accepted decision not to select or require any harness.

*Reading against:* the conformance note predates acceptance and uses state names and role-based denial, which conflict with the accepted semantics. It would need rework before it could carry this question.

## Observations against accepted artifacts

These are readings, offered as inference.

- **CR-O1.** The pilot recorded what was not bound and why. It did not need to record what was retained, because a single session never compacted in the recorded work, as far as the reviewer could tell from the issue log. That the issue did not arise in the pilot is not evidence that it does not arise.
- **CR-O2.** Section 6.5 says runs that share instructions cannot see a defect in those instructions. A dropped instruction is a different defect. The run does not share a flawed instruction; it lacks one. Section 6.5 does not obviously cover it.
- **CR-O3.** The question is separable from skills. It applies to any instruction, including the task brief, once context is managed.
- **CR-O4.** Pi's design makes the gap visible because it documents its rebuild procedure. A harness that does not document one would show the same gap less visibly. The reviewer has not verified this for any other harness.

## What cannot yet be justified

- That any harness's record is incomplete. In Pi the raw entries are retained. The point is that the record needs a documented procedure to reconstruct what the model saw.
- That the gap affects any protocol rule or gate outcome. No STEP-07 evidence shows an effect.
- That PROD-W should add a facet, a field, or a rule.
- Any conclusion about Pi's suitability as a harness for PROD-W.

## Possible test (not run)

1. Run one short task with a skill and a task brief in Pi and in Claude Code, with a compaction forced midway.
2. From each harness's record alone, attempt to state which instructions were in the model's context at the final action.
3. Compare each statement with the request actually sent, where the harness allows it to be observed.
4. Record whether the instruction was present, dropped, or undeterminable.

**Falsifier:** if both harnesses let a reader recover model-visible context accurately from the record, CR-H1 is strengthened for those harnesses under this test. The question may still matter at the protocol level if PROD-W needs a way to record whether a harness has that reconstructability property.

## Routing

| Item | Routed to | Note |
| --- | --- | --- |
| Disposition of CR-H1, CR-H2, CR-H3 | STEP-08 | Incorporated, deferred, or rejected. |
| CR-H2, granularity of the instructions facet | Candidate link to EK-OQ-09 and RQ-08 | Not verified against those rows. The sibling note routes a related granularity question to EK-OQ-09. |
| CR-H3 | RQ-19 (deferred) | Depends on rework of `agent-harness-conformance.md`. |
| Record integrity and order | Carried from STEP-05 / later representation work | Related to ISS-10. Not decided here. |
