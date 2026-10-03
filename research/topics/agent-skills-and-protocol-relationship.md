---
artifact:
  type: research-note
  version: 0.1
  created: 2026-10-01
  updated: 2026-10-01
  evidence_as_of: 2026-10-01
context:
  project: prod-w-dev
  status: research
  source_conversations:
    - "ChatGPT discussion on Agent Skills best practice, summarized in a context document by the Moderator (not yet archived under research/conversations/)"
    - "Claude second-opinion review of that context document, 2026-10-01 (not yet archived under research/conversations/)"
notes:
  - "Derived note. Nothing here is a PROD-W requirement, an architectural decision, or a change to MOD-W."
  - "Statements about Claude Code come from its official documentation. Statements about other tools come from secondary sources and were not checked against those tools."
---

# Agent Skills and the Protocol

## Research status

This is a **research question with competing hypotheses**, not a decision.

It does not reopen STEP-01 or STEP-02, does not change the roadmap, and does not select a prompt format, harness, or runtime integration (NG-1, NG-2; `prod-w/protocol-semantics.md` Section 10).

## Question

> **What is the relationship between a protocol-first system such as PROD-W and Agent Skills (`SKILL.md`)?**

## Three framings

All three are hypotheses. None is adopted.

### H-A. Skills are a layer beneath the protocol

Origin: the ChatGPT discussion.

The protocol says what must happen, when, with what evidence, and under whose authority. A skill is a reusable method for a bounded capability within those limits. A role decides who exercises it. A harness runs it.

### H-B. Skills are producing configuration

Origin: the Claude review, reading PR-27 and EKR-12.

A skill is instructions plus tooling. PR-27 already places model, harness, tooling, and instructions in an action's provenance and outside actor identity. On this reading a skill is not a layer. It is part of how an actor produced an item, and it is recorded as such.

### H-C. Skills are projections of the protocol

Origin: the `prod-w-dev` README ("agent instructions may eventually become projections of the protocol").

A skill is generated from the normative protocol, as a role-specific view would be. There is one normative source and no separately authored procedure layer. This depends on a representation existing, which is STEP-05 work.

## What is established about skills

As of 2026-10-01.

From the Claude Code documentation (https://code.claude.com/docs/en/skills):

- A skill is a directory with a `SKILL.md` holding frontmatter and instructions. The instructions enter the conversation when the skill is invoked.
- A skill is invoked by the user typing its name or by the model loading it when it judges it relevant. No other invocation path exists.
- Outside Claude Code, six frontmatter fields are usable: `name`, `description`, `license`, `compatibility`, `metadata`, `allowed-tools`. User-only invocation, subagent execution, hooks, and dynamic context injection are Claude Code extensions.
- `allowed-tools` pre-approves tools for the invoking turn. It does not restrict which tools are available.
- Skill content is not re-read on later turns. After compaction only the start of an invoked skill may be kept.
- For a rule that must hold every time, the documentation directs authors to a hook, not a skill.
- Skill arguments are string substitution. There is no typed input or output contract.
- The recommended evaluation is a baseline comparison: the same prompts with the skill available and with it off, in fresh sessions, checking triggering and output separately.

From secondary sources, not verified against the tools:

- The format is published as an open standard at https://agentskills.io and is read by Codex, Gemini CLI, Cursor, and others.
- Tools differ in discovery paths, how skills are activated, sandboxing, and which optional fields are honored.

## Observations against accepted artifacts

These are readings of accepted `prod-w-dev` material, offered as inference.

1. **A skill is not an actor.** Authority is held by actors through grants (PR-01, Section 4.1). A skill cannot hold authority. The risk is its output being read as verification or acceptance (PR-14, PR-15, OBJ-09), or a human-judgment question being presented as decided (Section 9.4).
2. **Shared skills reduce substantive independence.** Section 6.5 notes that runs sharing the same instructions cannot see a defect in those instructions. A skill used by both a producer and a challenger or evaluator is shared instructions. Identity distinctness (OBJ-06) would still hold; substantive independence (HJ-07) would be weaker.
3. **In MOD-W, tool assignment is governance.** The role-tooling matrix uses the Codex / Claude Code split as a cross-validation mechanism. "Harness" is therefore not purely an execution detail.
4. **The boundary is prose against prose.** MW-OBS-010 found that a boundary loses its enforcement when both sides are normative prose. Protocol text and skill text are both prose.
5. **Skills do not enforce.** Enforcement of human-only gate authority has to sit outside the agent's reach. Skill wording is mitigation only.
6. **MOD-W already has a place for this.** MOD-W v5 reserves `mod-w/skills/` for a procedure once it has become reusable.

## Routing

| Item                                                                                        | Routed to                                        | Note                                                                                                |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------------- |
| If skills are used, is skill name and version part of the recorded producing configuration? | STEP-04, as an input to EK-OQ-09 (PS-OQ-13)      | Presence of producing configuration is already required (EKR-12, EKO-03). Only granularity is open. |
| H-C: skills as generated projections                                                        | STEP-05                                          | Depends on the representation evaluation. Do not treat as selecting one.                            |
| Disposition of H-A, H-B, H-C                                                                | STEP-08                                          | Incorporated, deferred, or rejected.                                                                |
| Experiment result (below)                                                                   | `research/mod-w-transferability/observations.md` | Recorded as a transferability observation.                                                          |

## Planned experiment

**When:** at STEP-03 close-out, when a carry-forward list for STEP-04 is needed anyway.

**Scope:** MOD-W level only. This tests a MOD-W procedure in `mod-w/skills/`. It adds nothing to PROD-W.

**Procedure under test:** carry-forward consolidation. `mod-w/reviews/STEP-03-CARRY-FORWARD.md` is the pattern for structure. It is a pointer list that disposes of nothing, which makes authority leaks easy to see.

**Method:**

1. Write the skill from that procedure, using only the six standard frontmatter fields.
2. Run it on the STEP-03 outputs in a fresh Claude Code session and a fresh Codex session.
3. Repeat both runs with the skill unavailable.
4. Have the four lists checked against the sources by a role that did not produce them.

**Measures:**

- Coverage: open items found and missed, against the sources.
- Authority leaks: any item marked disposed, decided, accepted, or resolved by the run itself.
- Cross-harness variance: differences between the two tools with the skill present.
- Skill effect: differences between with-skill and no-skill runs in the same tool.

**Falsifier:** if the no-skill runs do as well as the with-skill runs, the skill added nothing for this procedure.

**Failure modes to watch for:**

- Verdict language or scores in the output.
- The skill loading in a session for the wrong role.
- The skill's instructions being dropped later in a long session.
- A tool auto-loading a skill that another tool would treat as user-only.
- The skill and the step file disagreeing.
- The skill's output being cited as verification.
- The skill making an architecture-level choice unnoticed (the MW-OBS-010 pattern).

**Limits:** one procedure, one repository, every artifact in prose. A result here supports or weakens a hypothesis. It does not settle one.

## Not yet justified

- That skills provide harness independence.
- That the same operation behaves the same across harnesses.
- That conformance can be tested independently of the model. This needs a record representation (STEP-05).
- Any conclusion about a protocol-based MOD-W architecture.

## Future research question

> **Can a reusable procedure be carried across harnesses without weakening the independence that the governance relies on?**

## Related

- `research/topics/product-definition-skill.md`: a research topic on a product-definition skill, planned for a separate repository and PROD-W v2. It plans nothing here and does not settle H-A, H-B or H-C.
