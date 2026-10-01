---
artifact:
  type: research-register
  kind: adaptations
  version: 0.1
  created: 2026-09-30
  updated: 2026-10-01
  evidence_as_of: 2026-10-01
context:
  project: prod-w-dev
  status: research
  governed_by: MOD-W Moderator
---

# MOD-W Local Adaptations Register

This file records only **approved local adaptations** made in `prod-w-dev` when MOD-W v5.0.1 cannot be applied literally or effectively in the non-software development context.

An approved adaptation does **not** imply that canonical MOD-W v5.0.1 should change. It records a local decision to work around or reinterpret a canonical MOD-W mechanism in this specific experiment.

Local adaptations are authorized by the Moderator and must be supported by evidence recorded in `observations.md`.

**See `README.md` for the distinction between observations and adaptations and for authorization procedures.**

---

## Current Status

**One local adaptation has been authorized: `MW-ADAPT-001`** (below), authorized by Frank McGuire (MOD-W Moderator) on 2026-09-30 per `mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Section 4.

The project otherwise continues to:

1. Proceed with canonical MOD-W as baseline through early phases
2. Record observations as friction or reinterpretation needs emerge
3. Request Moderator authorization only when evidence demonstrates that canonical MOD-W cannot be applied effectively
4. Avoid premature adaptation; use canonical MOD-W until it demonstrably fails

---

## MW-ADAPT-001 — Development Team Undecided-Architecture Declaration

**Date:** 2026-09-30  
**Source observation:** MW-OBS-010  
**Affected MOD-W area:** Tech Lead to Development Team boundary (Phase 1 to Phase 2)  
**Proposed by:** Development Team (as Option C for MW-OBS-008)  
**Authorized by:** Frank McGuire (MOD-W Moderator)  
**Status:** Active

### Canonical MOD-W Behavior

`mod-w/templates/MOD-W.md` line 40 relies on role separation alone (Codex plans and reviews; a different role implements) to keep planning and implementation independent. It assumes the two outputs are in different media (prose vs. code), which is not true in `prod-w-dev`.

### Local Adaptation

Every Development Team deliverable in `prod-w-dev` must include a declaration section listing the decisions it had to make that the accepted architecture (or other accepted upstream artifact) did not already decide, with the reasoning and the input each was derived from. This section routes to the Tech Lead, in addition to whatever Moderator review already occurs.

### Reason

Role separation alone does not surface an architecture-level decision made inside an implementation artifact when both are prose in the same repository. MW-OBS-010 demonstrated this concretely (PR-27), and an independent Moderator re-read of `prod-w/protocol-semantics.md` Section 4 against `mod-w/architecture.md` D4 confirmed it (`mod-w/reviews/MODERATOR-DELTA-REVIEW-STEP-01.md` Section 0). A mechanical acceptance-check-to-location check (MW-OBS-008 Option B) would not have caught it, because the decision was well-traced to a location — the defect was in the level of the decision, not its documentation.

### Scope and Reversibility

Applies to all Development Team deliverables in `prod-w-dev` from this point forward. Temporary/experimental: reconsider if it produces no findings for two consecutive steps (may be unnecessary overhead) or if it fails to catch a recurrence (may need strengthening, e.g. combined with Option B).

### Effect on Canonical MOD-W

This is a local experimental adaptation. Canonical MOD-W v5.0.1 is unchanged.

### Interaction with Other Adaptations

Complements, does not replace, any adaptation later authorized for MW-OBS-008 (Option A/B address the vanished build gate; this addresses the boundary-enforcement gap that took its place). No conflict. No other adaptation exists yet.

### Re-evaluation Condition

Re-evaluate at the STEP-02 gate: did the declaration section produce any findings, and did any architecture-level content still slip past it?

### STEP-02 Re-evaluation - 2026-10-01

**Disposition:** Re-evaluated; remains Active with strengthened review expectation.

**Did the declaration section produce findings?** Yes. `prod-w/evidence-knowledge-model.md` Section 12 produced 16 declared choices, including architecture-adjacent UAD-04 to UAD-07. The Tech Lead review confirmed the declared UADs as valid STEP-02 operationalization after revision.

**Did any architecture-level or authority/revalidation-level content still slip past it?** Yes, partially. QA D-05 identified four choices that met the Section 12.1 declaration test but were not listed in Section 12. The Tech Lead follow-up review confirmed D-05a, D-05c, and D-05d as operationalization and confirmed D-05b with a STEP-03 change. The Product Owner's R-1, recorded as EK-OQ-17, also shows an architecture-adjacent self-approval risk around correction designation.

**Effect on adaptation:** MW-ADAPT-001 remains useful because it produced findings. It is not sufficient by self-audit alone. For STEP-03, after the Development Team declaration, Tech Lead or QA should sample for unlisted choices in authority, independence, evidence standing, and revalidation before acceptance.

### Moderator Rationale

Authorized on the same date as STEP-01 acceptance. The adaptation is cheap, reversible, targeted at a demonstrated failure mode (PR-27), and produced by the role best placed to know what it decided. It does not substitute for, and does not need to wait on, disposition of MW-OBS-008's build-gate options (A/B remain open).

---

## Adaptation Template

When an adaptation becomes necessary and is proposed for authorization, it will follow this structure:

## MW-ADAPT-XXX — Short title

**Date:**  
**Source observation:** MW-OBS-XXX (reference the specific observation(s) supporting this adaptation)  
**Affected MOD-W area:**  
**Proposed by:** [Role proposing the adaptation]  
**Authorized by:** MOD-W Moderator  
**Status:** Proposed | Active | Retired | Superseded-by

### Canonical MOD-W Behavior

Describe the original MOD-W behavior, assumption, or rule from `mod-w/templates/` or `mod-w/MOD-W.md`.

### Local Adaptation

Describe exactly what is being changed, reinterpreted, extended, or bypassed for `prod-w-dev`.

Distinguish:

- Minor reinterpretation of terminology (usually not called an "adaptation")
- Local process change (e.g., review frequency, artifact format)
- Role responsibility extension or narrowing
- Gate or approval requirement modification
- Artifact type or content change
- Tooling or automation bypass

### Reason

Why is this adaptation necessary?

- Does canonical MOD-W create artificial overhead?
- Does a core mechanism fail in practice?
- Is terminology systematically misleading?
- Is a role responsibility undefined?
- Does a gate become a bottleneck?

### Scope and Reversibility

Define:

- How narrowly does the adaptation apply (specific phase? specific role?)
- Is the adaptation temporary (pending evidence) or longer-term?
- Can the project revert to canonical MOD-W later if evidence changes?
- Does this adaptation affect other roles or downstream work?

### Effect on Canonical MOD-W

State explicitly:

> This is a local experimental adaptation. Canonical MOD-W v5.0.1 is unchanged.

unless a future separate MOD-W improvement process actually decides to change canonical MOD-W based on evidence from this and other projects.

### Interaction with Other Adaptations

If multiple adaptations exist, note:

- Dependencies between adaptations
- Conflicting adaptations
- Cumulative effect (do multiple adaptations suggest a deeper pattern?)

### Re-evaluation Condition

State what evidence or future stage should cause the adaptation to be reconsidered or retired.

Examples:

- "If architecture phase reveals that canonical MOD-W's terminology naturally reinterprets to apply, this adaptation may be retired."
- "If the adaptation persists beyond implementation phase, recommend evaluation for canonical MOD-W consideration."
- "Retire when PROD-W protocol is deployed and can be validated against canonical testing assumptions."

### Moderator Rationale

Record the Moderator's authorization decision and reasoning.

---

## Adaptation Retirement

When an adaptation is no longer used or is superseded:

- Mark status as `Retired` or `Superseded-by: MW-ADAPT-XXX`
- Record the date and reason
- Do not delete; preserve for historical record
- Note in `assessment.md` whether the adaptation proved necessary, became unnecessary, or revealed something about MOD-W transferability

---

## Summary: Adaptations vs. Workarounds

### Approved Adaptations (This Register)

✓ Authorized by Moderator  
✓ Evidence-based (sourced from observations)  
✓ Reversible and scoped  
✓ Part of the research record  
✓ Affect how MOD-W is applied in this project

### Informal Workarounds (Not Recorded Here)

✗ Done locally without Moderator review  
✗ Not authorized as project policy  
✗ Not part of the research record  
✗ Individual team workarounds are not adaptations

If a team member discovers a workaround is necessary, **propose it as an observation first**, then request authorization as an adaptation if evidence supports it. This preserves the research record and prevents local practice from obscuring what canonical MOD-W actually requires.
