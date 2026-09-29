---
artifact:
  type: research-register
  kind: adaptations
  version: 0.1
  created: 2026-09-30
  updated: 2026-09-30
  evidence_as_of: 2026-09-30
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

**No local adaptations have yet been authorized.**

The project has identified potential areas requiring future observation (see `observations.md`, MW-OBS-003), but these are not yet confirmed as necessitating adaptation. The project will:

1. Proceed with canonical MOD-W as baseline through early phases
2. Record observations as friction or reinterpretation needs emerge
3. Request Moderator authorization only when evidence demonstrates that canonical MOD-W cannot be applied effectively
4. Avoid premature adaptation; use canonical MOD-W until it demonstrably fails

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
