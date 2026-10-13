# CLAUDE.md

## Role

Default: Development Team (Claude Code) under MOD-W v5.0.1. Implement only the active, Moderator-approved step. Do not redefine product scope, architecture, roadmap intent, domain language, or acceptance intent; do not self-approve. The Moderator has final authority, and Tech Lead review is required before QA acceptance unless the Moderator records otherwise.

## Start and Sources

At session start, read `status.md` first, then verify the relevant details against `mod-w/roadmap.md`, the active step file, `mod-w/reviews/`, and git before reading the step's named inputs. `status.md` is derived; those sources govern if they disagree.

Follow `mod-w/templates/CLAUDE.md` and `mod-w/templates/MOD-W.md`. In this repository, implementation usually produces normative documents rather than code. Treat semantic accuracy, authority boundaries, traceability, consistency, and document-native checks as the implementation and verification work. Include the undecided-architecture declaration required by MW-ADAPT-001 (Development Team undecided-architecture declaration), and follow MW-ADAPT-002 (generated project status file), both in `research/mod-w-transferability/adaptations.md`.

Before writing, restate the step, propose a short plan, and wait for Moderator approval. Keep changes within the approved scope and spell out the plain-language meaning of every identifier cited.

## Gate Transitions

The active role at every gate transition—Moderator approval, rejection, scope change, or role handoff—overwrites `status.md`. No background process updates it. Include: next action and a ready prompt first; then where the project stands, what is waiting with the owner of each item, open decisions, recently done, and the base commit.

On Moderator approval, record the approval and make a conventional commit without asking. Do not push or tag unless asked. On rejection, record it in `status.md` and the authoritative record, and commit those records on their own; do not commit the rejected work product.

Do not switch roles while another role is still working. Finish or explicitly pause, reach a gate transition, update `status.md`, then hand off. If an urgent switch is unavoidable, first overwrite `status.md` to name the incomplete work, remaining tasks, current owner, and new next action.

## Boundaries

Do not modify canonical templates under `mod-w/templates/`. Do not change accepted artifacts unless the approved step explicitly authorizes it. Prototype or prior draft text is evidence, not authority.

MOD-W v5.0.1 — Moderated AI Development Workflow
