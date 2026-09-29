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

# CAV: Surfacing Divergence vs. Monitoring Divergence

## Core conclusion

CAV should be understood as a **divergence-surfacing methodology**, not a divergence-monitoring methodology.

This does not mean CAV avoids detection. Detection is the computational mechanism; surfacing is the product/system responsibility.

> **Observe → Establish Baseline → Detect Divergence → Surface Evidence → Interpret**

## Important semantic boundary

> **Divergence is evidence of change, not a judgment of failure, defect, or non-conformance.**

Observed or historical baselines describe what has happened. They do not automatically describe what should happen.

At CAV Level 1, a system can establish that behavior has meaningfully changed without knowing what the intended behavior should have been.

## Monitoring vs. alignment

Traditional monitoring often focuses on whether an operational condition has crossed a predefined threshold.

CAV can operate earlier in the reasoning chain by surfacing sustained divergence before the system can necessarily classify that divergence as harmful.

A useful formulation:

> **Meaningful divergence can be surfaced before conventional monitoring can necessarily classify the resulting behavior as bad.**

## IDP-Align implication

For IDP-Align:

> **IDP-Align detects sustained divergence from observed baselines and surfaces that divergence with reconstructable evidence. At CAV Level 1, the divergence establishes that observed behavior has meaningfully changed; it does not establish that the new behavior is wrong, defective, or contrary to business intent.**

## Design principle to carry forward

> **Detect the divergence, surface the evidence, preserve the distinction between observation and intent, and leave judgment at the boundary with the authority and context to make it.**
