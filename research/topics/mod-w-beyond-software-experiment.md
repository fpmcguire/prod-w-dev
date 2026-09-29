---
artifact:
  type: research-note
  version: 0.1
  created: 2026-09-29
  updated: 2026-09-29
  evidence_as_of: 2026-09-29
context:
  project: prod-w-dev
  status: research
  source_conversation: research/conversations/2026-09-29-prod-w-origin-protocol-research-conversation.md
---

# MOD-W Beyond Software: `prod-w-dev` Experiment

## Experiment purpose

`prod-w-dev` is intended to do two things at once:

1. Develop PROD-W.
2. Evaluate how well MOD-W transfers beyond software engineering into methodology/protocol development.

## Primary research question

> **Can MOD-W govern disciplined AI-assisted development of a non-software artifact?**

## Why a separate repository matters

The repository separation should remain:

```text
mod-w/
  methodology being tested

prod-w-dev/
  MOD-W-governed research/development workspace

prod-w/
  resulting clean PROD-W product/protocol repository
```

The development evidence should not be mixed into the product itself.

## Transferability questions

The experiment should observe:

- Do existing MOD-W roles still make sense?
- What does Development Team mean for a protocol/methodology deliverable?
- What constitutes implementation?
- What constitutes testing?
- What constitutes QA?
- Can Tech Lead review normative protocol semantics rather than source code?
- Which MOD-W concepts transfer unchanged?
- Which require domain-neutral generalization?
- Which fail outside software development?

## Experimental discipline

> **Do not modify MOD-W prematurely to make the experiment succeed.**

When a software-specific assumption causes friction:

1. record the assumption;
2. record the observed problem;
3. classify it as possible domain coupling;
4. adapt locally only if needed;
5. do not change canonical MOD-W yet.

## Hypothesis to test, not assume

MOD-W may ultimately prove to be broader than software development—possibly a moderated, evidence-gated method for producing complex technical artifacts with AI.

The `prod-w-dev` project should generate evidence for or against that hypothesis.
