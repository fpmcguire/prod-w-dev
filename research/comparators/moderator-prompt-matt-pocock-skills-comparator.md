# Moderator Prompt — Matt Pocock `skills` Comparator Research for PROD-W

Use this prompt in `prod-w-dev` with the MOD-W Moderator role.

---

You are acting as the human-directed MOD-W Moderator for the `prod-w-dev` repository.

The repository is governed by MOD-W v5.0.1.

Your task is to incorporate research findings from Matt Pocock's public `skills` repository:

https://github.com/mattpocock/skills

into the `prod-w-dev` research corpus.

This is a research/comparator task.

Do NOT modify:
- `mod-w/product.md`
- `mod-w/templates/*`
- accepted MOD-W artifacts
- PROD-W architecture
- roadmap
- step files
- published `prod-w`

Do NOT import Matt Pocock's skills directly into PROD-W.
Do NOT treat his repository as a competing methodology that PROD-W must imitate.
Do NOT convert useful patterns into PROD-W requirements without later Product Owner / Moderator review.

The purpose is to document relevant precedents and identify which design patterns may be useful to PROD-W research.

---

# Research Basis

Review the current `mattpocock/skills` repository and primary files relevant to the following themes.

The repository currently distinguishes between user-invoked and model-invoked skills. User-invoked skills require explicit invocation rather than being autonomously selected by the model in normal use. This provides a useful precedent for separating consequential human-authorized actions from reusable agent capabilities.

The following skills/patterns are especially relevant to PROD-W research.

## 1. `grill-with-docs` / grilling pattern

Relevant idea:

Use structured questioning to resolve ambiguity rather than allowing an agent to silently fill gaps with assumptions.

Potential PROD-W relevance:

- challenge product assumptions;
- expose unresolved decisions;
- prevent plausible but unsupported product narratives;
- preserve human decision authority;
- distinguish inquiry from execution.

Do not assume the exact grilling implementation belongs in PROD-W.

Treat it as a precedent for a structured challenge/interrogation capability.

---

## 2. `domain-modeling`

Matt Pocock's `domain-modeling` skill actively sharpens a project's ubiquitous language while decisions are being made. It challenges vague/conflicting terminology and records resolved concepts when they are actually settled rather than merely summarizing terminology afterward.

Potential PROD-W relevance:

- maintaining precise domain language;
- distinguishing terms such as:
  - Evidence
  - Fact
  - Inference
  - Hypothesis
  - Assumption
  - Decision
  - Gate
  - Verification
  - Sufficiency
  - Challenge
  - Revalidation
  - Moderator;
- preventing vocabulary drift;
- integrating terminology work with product reasoning rather than treating the glossary as an afterthought.

Compare this pattern with:
`mod-w/domain-language.md`

Do not automatically adopt Matt's `CONTEXT.md` model.

---

## 3. `wayfinder`

Matt's `wayfinder` models large, unclear work as a set of decision questions rather than implementation tasks. It explicitly plans but does not build; the process stops when the decisions required before implementation have been resolved.

This is highly relevant to PROD-W because PROD-W already distinguishes:
- deciding what is justified;
- defining what should happen;
- implementing what has been approved.

Potential PROD-W relevance:

- explicit separation of decision work from execution;
- open questions as first-class artifacts;
- decision dependencies;
- stopping conditions based on resolved uncertainty rather than generated implementation;
- avoiding premature implementation.

Do not import Wayfinder's issue-tracker mechanics as a PROD-W requirement.

Focus on the conceptual pattern:

> decision map before execution plan

---

## 4. `research`

Matt's research skill is designed for targeted investigation of external facts using high-trust primary sources and captures the findings as a cited Markdown artifact. It distinguishes research that produces facts from processes that produce decisions.

Potential PROD-W relevance:

- evidence provenance;
- research artifacts;
- source quality;
- freshness;
- separating externally verified facts from product decisions;
- keeping research outputs independent from the decisions that later consume them.

This is particularly relevant to PROD-W's distinction among:
- evidence;
- inference;
- decision.

Do not treat a research artifact as automatically accepted evidence.

Human/governance rules still determine whether evidence is sufficient for consequential decisions.

---

## 5. `to-spec`

Matt's `to-spec` explicitly treats a specification as a record of decisions already made rather than a new place for the model to invent decisions.

Potential PROD-W relevance:

> Decision first -> specification second

This is strongly compatible with PROD-W's concern that generated artifacts can create synthetic certainty.

Research whether PROD-W should distinguish:
- decision artifacts;
- specification artifacts;
- implementation artifacts.

Do not adopt Matt's issue-tracker publication mechanism as a requirement.

Focus on the principle:

> A specification should preserve accepted decisions rather than silently make new ones.

---

## 6. `writing-for-agents`

Review Matt Pocock's agent-writing approach as a precedent for concise, targeted agent context rather than large undifferentiated instruction corpora.

Potential PROD-W relevance:

- human view vs. machine view;
- role-specific projections;
- concise agent instructions;
- context pointers;
- keeping authoritative information centralized while providing small task-specific views.

This relates directly to the existing research hypothesis in:

`research/topics/document-metadata-and-human-machine-views.md`

Do not conclude that Matt's exact instruction format should be used.

The research question is:

> Can PROD-W separate authoritative governance information from small role/task-specific projections without duplicating or drifting the normative source?

---

## 7. `handoff`

Review the handoff pattern as a precedent for preserving continuity across agent sessions without repeatedly restating the entire project context.

Potential PROD-W relevance:

- persistent workflow continuity;
- context reduction;
- explicit reference to authoritative artifacts;
- preserving unresolved decisions;
- resumable agent work.

Treat this as relevant to future:
- role-specific projections;
- resumability;
- protocol state;
- context management.

Do not make handoff mechanics a current PROD-W requirement.

---

## 8. Repo-local configuration / reusable skills

Matt's setup approach stores repository-specific configuration in the repository rather than treating every repository as having identical global configuration.

Potential architectural lesson:

> reusable capability + project-local configuration

This may be relevant later to:
- PROD-W profiles;
- MOD-W profiles;
- agent-harness adapters;
- repository-specific governance configuration.

Do not promote this into architecture yet.

Record it as a useful precedent.

---

# Broader Architectural Pattern to Capture

The Matt Pocock repository provides useful precedent for separating:

## Human-authorized orchestration actions

Examples conceptually analogous to:
- initiate research;
- initiate challenge;
- request specification;
- authorize consequential progression.

from:

## Reusable agent capabilities

Examples conceptually analogous to:
- research;
- domain modeling;
- challenge;
- synthesis;
- provenance checking;
- verification.

The repository's current engineering README explicitly distinguishes user-invoked and model-invoked skills.

This suggests a potential PROD-W research pattern:

```text
PROD-W governance
        |
        +-- human-authorized actions
        |
        |    initiate challenge
        |    accept consequential gate
        |    request research
        |    authorize progression
        |
        +-- reusable agent capabilities
             research
             challenge
             domain modeling
             synthesis
             provenance checking
             verification
```

Treat this as a research hypothesis, not architecture.

---

# Required Research Artifact

Create:

`research/comparators/matt-pocock-skills.md`

Use the current `prod-w-dev` research-artifact metadata convention.

Suggested metadata:

```yaml
---
artifact:
  type: comparator-research
  version: 0.1
  created: 2026-09-30
  updated: 2026-09-30
  evidence_as_of: 2026-09-30

context:
  project: prod-w-dev
  status: research
  comparator: mattpocock/skills
  source_repository: https://github.com/mattpocock/skills
---
```

Do not interpret this metadata structure as a PROD-W product requirement.

---

# Required Structure for the Comparator File

Use sections substantially equivalent to the following.

## 1. Comparator Summary

Explain what Matt Pocock's repository is and why it is relevant.

Keep the framing neutral.

Do not call it a PROD-W competitor unless evidence supports that characterization.

A suitable characterization is:

> A repository of composable agent skills and workflows that provides useful precedents for human invocation boundaries, decision-first planning, research artifacts, domain-language discipline, specification handoff, and agent-context design.

---

## 2. Why It Is Relevant to PROD-W

Explain that the value is primarily architectural/process precedent rather than direct feature reuse.

Highlight:

- human invocation boundaries;
- reusable capabilities;
- decision vs. execution separation;
- domain-language maintenance;
- research provenance;
- specification as decision preservation;
- context management;
- project-local configuration.

---

## 3. Relevant Skills / Patterns

Create subsections for:

- grilling / `grill-with-docs`
- `domain-modeling`
- `wayfinder`
- `research`
- `to-spec`
- `writing-for-agents`
- `handoff`
- setup/repo-local configuration

For each, record:

### What it does

Describe only what the source supports.

### Relevant PROD-W principle

Map it to an existing PROD-W research concern.

### Potential lesson

Describe what may be reusable conceptually.

### What NOT to infer

Explicitly identify what should not be imported or assumed.

---

## 4. Five Comparator Themes

Organize the synthesis around these five themes.

### A. Human Invocation Authority

Research question:

> Which workflow actions should require explicit human invocation rather than being autonomously initiated by an AI agent?

Possible PROD-W implications:
- challenge initiation;
- gate decisions;
- escalation;
- consequential progression.

Do not decide these here.

---

### B. Decision vs. Execution Separation

Research question:

> Can PROD-W make a strong structural distinction between unresolved product decisions and downstream implementation work?

Use `wayfinder` and `to-spec` as precedents.

Potential conceptual chain:

```text
Open question
    ↓
Investigation / challenge
    ↓
Decision
    ↓
Specification
    ↓
Execution
```

Compare this with PROD-W's existing concern about agents generating apparent product certainty through implementation elaboration.

---

### C. Domain Language Maintenance

Research question:

> Should PROD-W treat domain-language maintenance as an active governance discipline rather than a passive glossary artifact?

Compare Matt's `domain-modeling` approach with the current MOD-W `domain-language.md` model.

Do not change MOD-W based on this comparator.

---

### D. Research Provenance

Research question:

> How should externally sourced research become durable evidence without automatically becoming an accepted product conclusion?

Use the `research` skill as precedent.

Connect to existing PROD-W concepts:
- evidence;
- provenance;
- evidence freshness;
- inference;
- human acceptance.

---

### E. Agent Context Design

Research question:

> Can authoritative governance remain centralized while agents receive small task-specific views or context pointers?

Connect to existing research:
`research/topics/document-metadata-and-human-machine-views.md`

Potential long-term relevance:
- role-specific projections;
- external evaluators;
- resumability;
- agent-harness independence.

Keep this as hypothesis.

---

# Explicitly Exclude Software-Specific Skills From Direct PROD-W Adoption

Document that skills such as:

- TDD;
- diagnosing bugs;
- code review;
- codebase architecture improvement;
- implementation pipelines;

are primarily software-engineering capabilities.

They may provide indirect lessons about:
- feedback loops;
- independent verification;
- stopping criteria;
- evidence generation;

but they should not become PROD-W concepts merely because they are useful in engineering.

---

# Comparator Conclusions

The comparator document should not end with:

> PROD-W should adopt Matt Pocock's skills.

Instead, use a conclusion substantially like:

> Matt Pocock's skills repository provides practical precedent for several patterns relevant to PROD-W: explicit invocation boundaries, composable agent capabilities, decision-first planning, active domain-language maintenance, source-grounded research artifacts, specification as a record of prior decisions, and compact agent-facing context. These patterns should be treated as research inputs rather than copied directly into PROD-W.

Also state that the repository does not by itself establish:
- the correct PROD-W role model;
- the correct protocol representation;
- the correct invocation policy;
- the correct artifact structure;
- the correct agent-harness architecture.

---

# Product Impact Review

After writing the comparator, inspect the current accepted/draft:

`mod-w/product.md`

Do NOT modify it.

Determine whether the comparator reveals:

1. an already-covered PROD-W research question;
2. a genuinely missing product-level question;
3. an architecture-level question;
4. a research hypothesis only.

Report findings to the Moderator.

If a genuine Product Definition gap is discovered, recommend returning that issue to the Product Owner.

Do not silently update the Product Definition.

---

# Architecture Impact Review

The initial Tech Lead architecture phase has been accepted. Do not reopen or modify accepted architecture from this comparator task.

Record architecture-relevant findings as comparator research for later Moderator and Tech Lead consideration.

Potential architecture questions include:
- user-invoked vs. model-invoked actions;
- capability vs. authority separation;
- context pointers;
- project-local profiles;
- specification/decision separation.

These are inputs to Tech Lead reasoning, not Moderator architecture decisions.

---

# MOD-W Transferability Review

Consider whether this comparator produces any meaningful observation about MOD-W transferability.

For example:

Matt's distinction between user-invoked and model-invoked behavior may highlight that MOD-W currently expresses some authority boundaries primarily through role instructions rather than a capability/invocation model.

If this is merely conceptual comparison, do NOT create a transferability observation.

Create/propose an observation only if the actual `prod-w-dev` project encounters concrete evidence.

Comparator research alone is not evidence that MOD-W succeeds or fails outside software development.

---

# Research Neutrality

Actively record limitations and counterpoints.

Examples:

- Matt's skills are primarily optimized for software-engineering agent workflows.
- The system is intentionally pragmatic rather than a formal governance protocol.
- Issue-tracker mechanics may not transfer to product governance.
- Explicit invocation is not necessarily equivalent to human authorization.
- A reusable skill is not equivalent to a PROD-W role or protocol action.
- Agent-context minimization can create hidden-dependency problems if authoritative sources are unclear.

Do not turn superficial similarity into architectural equivalence.

---

# Source Quality

Prefer primary repository files and documentation.

For every substantive factual statement about Matt Pocock's skills:
- cite/reference the exact repository file or documentation source in the Markdown research artifact;
- distinguish source-supported facts from PROD-W interpretation.

Do not rely on secondary blog posts if the repository itself provides the necessary evidence.

---

# Constraints

Do NOT:

- copy Matt Pocock's skills into this repository;
- install his skills;
- modify `.claude` or `.codex` configuration;
- modify `mod-w/product.md`;
- modify `mod-w/templates/*`;
- create PROD-W architecture decisions;
- create new PROD-W roles;
- promote Product Skeptic / Product Advocate based on this comparator;
- define a skill runtime;
- define invocation policy;
- define agent-harness architecture;
- claim novelty;
- claim superiority;
- commit unless separately instructed.

---

# Final Report to Moderator

Return:

1. file created;
2. primary sources reviewed;
3. most relevant skills/patterns;
4. five main comparator themes;
5. patterns potentially useful for PROD-W;
6. patterns deliberately NOT recommended for direct adoption;
7. any Product Definition gap discovered;
8. any architecture questions surfaced;
9. any proposed MOD-W transferability observation;
10. confirmation that `mod-w/product.md` was unchanged;
11. confirmation that `mod-w/templates/*` were unchanged;
12. confirmation that no external skills were installed;
13. `git diff --stat`;
14. `git status`;
15. recommended next action.

Do not commit.

Stop at the Moderator research-review boundary.

---

## Recommended research positioning

The core point to preserve is that Matt Pocock's repo is most valuable as a **design precedent**, especially for:

- explicit invocation boundaries;
- decision-first workflows;
- durable research artifacts;
- active domain-language work;
- concise agent-facing context;
- reusable capabilities separated from project-local configuration.

The comparator remains useful as research input after initial architecture acceptance, especially for later representation, agent-context, and invocation-policy decisions. Treat these ideas as research rather than architectural commitments unless a later Moderator-approved step incorporates them.
