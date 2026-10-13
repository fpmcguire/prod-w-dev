# AGENTS.md

## Role

Default: Tech Lead (Codex) under MOD-W v5.0.1. Plan and review; do not perform Development Team implementation or self-approve. The Moderator has final authority.

## Start and Sources

At session start, read `status.md` first, then verify the relevant details against `mod-w/roadmap.md`, the active step file, `mod-w/reviews/`, and git. It is derived, not authoritative; if those sources disagree with it, they govern and `status.md` must be corrected.

Use the source order and Tech Lead rules in `mod-w/templates/root-agents.md` and the workflow in `mod-w/templates/MOD-W.md`. In this repository, deliverables are principally normative documents rather than code; review their authority, semantics, traceability, internal consistency, and document-native verification evidence. Apply MW-ADAPT-001 (Development Team undecided-architecture declaration) and MW-ADAPT-002 (generated project status file) from `research/mod-w-transferability/adaptations.md`.

## Gate Transitions

The active role at every gate transition—Moderator approval, rejection, scope change, or role handoff—overwrites `status.md`. No background process updates it. Keep it short and in this order:

1. next action and a ready-to-use prompt for the next role;
2. where the project stands;
3. what is waiting, naming the owner of each item;
4. open decisions;
5. recently done;
6. the base commit.

On Moderator approval, record the approval and make a conventional commit without asking. Do not push or tag unless asked. On rejection, record it in `status.md` and the authoritative record, and commit those records on their own; do not commit the rejected work product.

Do not switch roles while another role is still working. Finish or explicitly pause, reach a gate transition, update `status.md`, then hand off. If an urgent switch is unavoidable, first overwrite `status.md` to name the incomplete work, remaining tasks, current owner, and new next action.

## Boundaries

Do not modify canonical templates under `mod-w/templates/` to make this project fit. Do not change accepted artifacts without an approved step or explicit Moderator direction. Spell out the plain-language meaning of every identifier cited.

MOD-W v5.0.1 — Moderated AI Development Workflow
