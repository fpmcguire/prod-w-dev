# Agent Execution Environment Integrity — Research Design Note

**Date:** 2026-11-24  
**Status:** Proposed research; not approved protocol or adaptation  
**Evidence:** MW-OBS-024–026; `research/conversations/2026-11-24-step-02a-dev-team-environment-retrospective.md`

## Research question

How can MOD-W preserve independent, sufficient verification when roles share mutable execution environments and agent sessions can be interrupted?

## Candidate mechanisms

| Candidate | Research hypothesis | Boundary |
|---|---|---|
| Execution Environment Preflight | Checking actual toolchain, artifact identity and prerequisites reduces avoidable failures | Project-specific checks; not a universal technology stack |
| Agent Execution Recovery | Explicit interruption and recovery authority preserves gate integrity | Harness implements cancellation and process management; Moderator governs recovery |
| Verification Evidence Continuity | Checkpoints and revalidation prevent stale evidence reuse | Generated status.md remains orientation, not authoritative evidence |
| Verification Evidence Sufficiency | Preserved diagnostics and coverage make successful results interpretable | Warnings require disposition, not automatic rejection |

## Candidate evaluation design

Compare baseline and candidate procedures across repeated software and normative-artifact tasks. Record actual executable paths and versions, artifact identity, service prerequisites, command coverage, completion and diagnostic references. For non-software tasks substitute relevant evaluator versions, schemas, model configuration and source availability. Test deliberate version drift, interrupted commands, changed artifacts, zero-work checks and warning-bearing successful results in a controlled disposable environment. Do not deliberately disrupt active project reviews.

Measure Moderator interventions, reruns, elapsed time, false blockers, stale-evidence acceptance and diagnostic recovery. Record both benefits and costs. Compare shared supported environments with isolated ones; isolation alone does not guarantee comparable results. Preserve raw evidence securely, redact secrets and use references rather than unnecessarily duplicating logs.

## Open decisions

- Which checks are required by project, role or command, and who authorizes exceptions?
- What identity and change conditions invalidate earlier evidence?
- What cancellation and timeout behavior is supported by each harness? Incident-specific five/ten-minute limits are not universal defaults.
- How are non-blocking findings assigned owners and tracked beyond acceptance?
- Can existing MW-ADAPT-002 support orientation without becoming an evidence authority?
- Do accepted MOD-W or PROD-W artifacts already address these questions?

## Evidence limits and governance

The case is one software project, with the same human Moderator and role-authored retrospective evidence. The original Codex stall, R4 installation divergence and Firefox root cause remain unresolved. YAML is not established as causal. Genuine implementation defects also occurred. No measured counterfactual demonstrates savings from preflight or recovery mechanisms. Review canonical MOD-W and accepted PROD-W semantics before drafting normative changes. Moderator approval is required before any local trial or adaptation. This note does not reopen STEP-02A or authorize implementation.
