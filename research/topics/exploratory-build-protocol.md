# Exploratory Build Protocol - Research Design

**Date:** 2026-10-14
**Status:** Research design authorized; not an active MOD-W rule
**Source:** MW-OBS-023
**Owner:** MOD-W Moderator

## Purpose and Boundary

This note develops a possible optional protocol for obtaining runnable evidence before production architecture and implementation are committed. It covers two exploration types:

1. **Rapid product visualization:** make screens, flows, states, and interactions tangible for design review.
2. **Technical feasibility testing:** answer a bounded technical question whose uncertainty could materially affect architecture or product feasibility.

This is not a production fast lane, an MVP release process, a new `-W` workflow, or an active local adaptation. It changes no canonical MOD-W template or accepted PROD-W artifact. Exploratory output has no production standing through documentation backfill, branch merging, deployment, or Moderator approval of its visual intent.

## Relationship to Existing MOD-W

- Rapid visualization is a refinement of the optional Prototype Ceremony.
- Technical feasibility testing is an adjacent spike path whose fit with that ceremony remains a research question.
- Any candidate code is a Reference Implementation and must be dispositioned by the Tech Lead.
- Existing work may be documented as evidence, but authoritative adoption requires the applicable MOD-W gates to be executed.
- User interaction becomes PROD-W evidence only when a PROD-W trial defines the product hypothesis, participants, evidence, and limits.

## Proposed Exploration Charter

Before implementation, record:

- exploration type;
- question or hypothesis;
- intended reviewer or audience;
- baseline commit and exploration branch;
- time or scope limit;
- non-goals;
- prohibited shortcuts and safety constraints;
- evidence to collect;
- expected fidelity by dimension: visual, interaction, data, technical, accessibility, and operational;
- whether code is presumed throwaway;
- owner, deployment access, and expiration policy.

The charter may live in `prototype/README.md` or the authorizing MOD-W review record during an initial trial. A separate mandatory charter artifact is not yet justified.

## Proposed Git and Deployment Lifecycle

1. Start from a named baseline commit.
2. Use `explore/visualization-<topic>` or `explore/feasibility-<topic>`.
3. Permit checkpoint commits as exploration provenance, not gate approvals.
4. Deploy only to an isolated review environment with an owner, access policy, source commit, and expiration or archival rule.
5. Do not use production credentials, sensitive data, or irreversible external actions.
6. Close with one decision:
   - `STOP`: retain findings; archive or remove the branch and preview;
   - `REVISE`: refine the charter or upstream product/design framing;
   - `PROCEED`: begin or revise normal MOD-W architecture and planning;
   - `TRIAL`: route the artifact into an explicitly governed PROD-W proof-of-concept trial.
7. Do not merge exploratory code wholesale merely because its design or feasibility finding is accepted.

Branching provides isolation and provenance. It does not confer authority, evidential sufficiency, security, maintainability, or production readiness.

## Proposed Evidence and Handoff

An exploration should preserve:

- charter and source commit;
- runnable or otherwise inspectable review surface;
- reproduction instructions and pinned dependencies;
- supported flows, states, viewports, and environments;
- mocked or nonfunctional behavior;
- shortcuts and omitted production qualities;
- positive, negative, and contradictory findings;
- security, privacy, licensing, accessibility, and deployment limits;
- closing decision and rationale.

If work proceeds, the Tech Lead records which prototype behaviors and assumptions are accepted, modified, rejected, or require mandatory divergence. Production implementation remains Development Team work under normal steps and reviews.

## Proposed Artifact Responsibilities

| Concern | Proposed location |
|---|---|
| Product-specific screens, flows, component states, variants, and accessibility intent | `design-spec.md` |
| Durable design-system principles and token guidance, when warranted | Optional `DESIGN.md` |
| Runnable prototype, components, and custom gallery or Storybook | `prototype/` |
| Review URLs, commit, reproduction, fidelity, limitations, and expiry | `prototype/README.md` |
| Storybook-specific deployment, story coverage, add-ons, mocks, and limitations | Conditional `prototype/storybook-notes.md` |
| Advisory technical implications, dependencies, reuse candidates, and confidence | `architecture-notes.md` |
| Production packaging, library, framework, and dependency decisions | `architecture.md` |
| Prototype adoption and mandatory divergence | Relevant `step-xx.md` |
| Results, contradictions, and closing decision | `prototype/findings.md` or equivalent review record |

No separate `component-library.md` is proposed initially. Add an artifact only if a trial demonstrates an information need not served by the design specification, live review surface, prototype manifest, architecture notes, and findings.

## Storybook and Custom Gallery Path

A custom gallery is the lighter default for rapid visualization. Storybook is a candidate when systematic component-state coverage, reusable component APIs, accessibility inspection, or visual regression is itself material to the exploration.

If Storybook is used, `prototype/storybook-notes.md` or equivalent metadata should record:

- selection rationale;
- source branch, commit, and preview URL;
- mapping from Design Specification identifiers to stories;
- states, variants, viewports, and coverage gaps;
- accessibility evidence and unresolved issues;
- mocks, add-ons, dependencies, and technical shortcuts;
- candidate production value without presuming adoption;
- archival or continuation recommendation.

Storybook is a review surface and evidence mechanism. The Tech Lead separately decides whether it, the component APIs, or the packaging model continue into production.

## Minimum Safety and Quality Floor

Exploration should stay rapid, but not create misleading or unsafe evidence. The proposed minimum is:

- no production secrets or sensitive personal data;
- no irreversible external actions;
- visible identification as an exploratory preview;
- basic keyboard reachability, focus visibility, semantic structure, and contrast for UI review;
- third-party asset and component licensing identified before adoption;
- limitations stated wherever reviewers could mistake simulation for working behavior.

Full production test coverage, optimization, resilience, observability, and operational hardening are normally outside exploration scope unless they are the feasibility question.

## Questions for a Trial

1. Does one shared protocol with two exploration types remain clearer than separate ceremonies?
2. Does branch isolation prevent accidental adoption, or merely delay it?
3. Which metadata belongs in existing artifacts, and does any new mandatory artifact prove necessary?
4. Does a deployed component review surface improve Moderator, Tech Lead, and QA judgments?
5. What is the maintenance and cleanup cost of previews, galleries, Storybook, and exploration branches?
6. Can the protocol remain meaningfully rapid while preserving provenance, accessibility, and safety?
7. Do `STOP`, `REVISE`, `PROCEED`, and `TRIAL` cover real outcomes without ambiguity?

## Advancement Condition

Do not propose a local adaptation or canonical MOD-W change from this note alone. First run at least one bounded trial, preserve contradictory evidence, and review whether the existing Prototype Ceremony could have achieved the same result with less machinery.
