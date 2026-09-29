---
artifact:
  type: research-governance
  version: 0.1
  created: 2026-09-30
  updated: 2026-09-30
  evidence_as_of: 2026-09-30
context:
  project: prod-w-dev
  status: research
  governed_by: MOD-W Moderator (prod-w-dev)
---

# MOD-W Transferability Research Governance

## Purpose

This directory records evidence about MOD-W v5.0.1's appropriateness for non-software development. Both supporting and contradictory evidence must be retained. The purpose is not to prove that MOD-W is domain-independent, but to observe where its governance concepts transfer, where they require reinterpretation or adaptation, where they appear domain-coupled, and where the evidence remains unresolved.

This experiment is currently limited to development of PROD-W as a methodology/protocol and associated normative artifacts. Do not generalize findings beyond the evidence.

---

## Scope

Transferability observations may concern, among other things:

- Product Definition
- Product Owner responsibilities
- Moderator responsibilities
- Tech Lead responsibilities
- Development Team responsibilities
- QA responsibilities
- Role independence and cross-validation
- Review and approval gates
- Evidence requirements and sufficiency standards
- Architecture work and terminology
- Roadmap and step planning
- Implementation semantics (executable code vs. normative artifacts)
- Testing semantics (runtime validation vs. protocol validation)
- Acceptance semantics and gates
- Documentation lifecycle
- Repository conventions
- CI/build assumptions
- Artifact lifecycle and traceability
- Revalidation processes
- Human authority and oversight
- Tooling assumptions
- Terminology that appears software-specific

Observations may be **positive** (MOD-W transfer), **negative** (domain coupling), **mixed**, or **unresolved**. All findings must be preserved as evidence.

---

## Ownership and Contribution Model

### MOD-W Moderator

The Moderator (`prod-w-dev` repository governance role):

- **owns** `research/mod-w-transferability/`
- **defines and maintains** the research-governance rules
- **reviews** proposed observations for evidence sufficiency and appropriate classification
- **classifies** accepted observations using defined categories
- **ensures** positive and negative evidence are both retained and not silently reconciled
- **prevents** conclusions from exceeding evidence (e.g., one success does not prove universal applicability; one failure does not prove an underlying concept is invalid)
- **authorizes** local adaptations only where required by evidence
- **ensures** local adaptations are recorded separately from observations
- **maintains** `assessment.md` as cumulative synthesis
- **protects** the historical evidence record (accepted observations should not be deleted)
- **ensures** canonical MOD-W v5.0.1 templates under `mod-w/templates/` are not silently modified to make the experiment work

The Moderator does **NOT**:

- rewrite observations to make MOD-W appear more successful
- suppress evidence that contradicts prior expectations or preferences
- convert one observation into a canonical MOD-W change
- claim domain independence from this project alone
- allow local workarounds to be classified as canonical MOD-W improvements

### All Active MOD-W Roles

Any active MOD-W role in `prod-w-dev` may propose an observation.

This includes, where applicable:

- Product Owner
- Tech Lead
- Development Team
- QA
- Moderator
- Other explicitly authorized MOD-W roles

**The role closest to the observed event should record the initial observation when practical.**

A contributing role may:

- describe what occurred or what was attempted
- identify the relevant MOD-W mechanism, assumption, or rule
- provide concrete evidence
- explain practical effects on the work
- propose an interpretation about transferability
- propose a local adaptation if evidence shows one is necessary

A contributing role may **NOT**:

- unilaterally declare that MOD-W is domain-independent
- unilaterally redefine canonical MOD-W
- classify a local workaround as a canonical MOD-W improvement
- hide evidence that weakens its own interpretation
- authorize its own local adaptation (Moderator authorization required)

---

## Observation Timing Rule

A meaningful transferability observation should be recorded before the project moves materially beyond the stage in which the observation occurred.

**Reason:**

- Contemporaneous observations are more reliable and less vulnerable to hindsight bias
- Later reconstruction can distort the original context and friction points
- Local adaptations can otherwise obscure what the original problem actually was
- The research record becomes evidence of the experimental process, not a rewritten narrative

---

## Observation Classifications

Use these working classifications unless an existing MOD-W convention requires adjustment:

### `TRANSFERS_UNCHANGED`

The MOD-W concept, responsibility, rule, or artifact applies meaningfully in the non-software (methodology/protocol-development) domain without substantive reinterpretation or modification.

### `TRANSFERS_WITH_REINTERPRETATION`

The underlying MOD-W concept remains coherent and useful, but software-specific terminology or framing must be interpreted more broadly to apply.

**Example:** "implementation" may include normative protocol definitions and schemas, not just executable application code.

### `REQUIRES_LOCAL_ADAPTATION`

The MOD-W mechanism cannot be applied effectively in this project without an explicit local change, extension, or exception. Any approved adaptation must be recorded separately in `adaptations.md`.

### `DOMAIN_COUPLED`

Evidence suggests that the MOD-W mechanism is materially tied to software development and may not transfer meaningfully to this non-software domain in its current form.

**Important:** This classification does NOT automatically mean canonical MOD-W should change. It means this experiment has encountered domain coupling that MOD-W may not have anticipated, and the finding is preserved as evidence.

### `NOT_YET_TESTED`

The transferability question has been identified as an explicit research target, but insufficient evidence exists to classify it. Use this sparingly for tracked open questions, not as a default for unexamined assumptions.

---

## Observation vs. Adaptation: Critical Distinction

> **An observation records what happened. An adaptation records what the project changed in response.**

Do **not** merge them or allow local practice to erase the original observation.

**Example:**

**Observation (MW-OBS-XXX):**

> The Development Team role as defined in MOD-W assumes production of executable code as the primary artifact.

**Adaptation (MW-ADAPT-XXX):**

> For `prod-w-dev`, "implementation" is locally interpreted to include normative protocol definitions, machine-readable schemas, and associated prose documentation, in addition to example or reference code.

The adaptation must not rewrite or erase the original observation. Both remain in the record.

---

## Evidence Standard

Every accepted observation should identify **concrete evidence** where practical, such as:

- specific repository artifact or file path
- relevant MOD-W template excerpt or rule
- review result or gate outcome
- actual role interaction or decision
- failed or successful MOD-W gate
- observed ambiguity or gap
- local adaptation that was required
- verification or test result

**Avoid conclusions based solely on expectation or preference.**

Distinguish in your observation:

- **Evidence:** concrete facts and artifacts
- **Observation:** what occurred in the project
- **Interpretation:** what it may mean about transferability
- **Conclusion:** broader claim (be appropriately cautious)

---

## Research Neutrality

Transferability research must **actively seek evidence both for and against** MOD-W appropriateness in non-software development.

**Examples of positive evidence:**

- A MOD-W gate (e.g., Product Definition review, independent approval) works without change
- A role boundary remains useful and distinct
- Independent review prevents premature acceptance of weak evidence
- Product Definition structure transfers naturally to methodology/protocol context
- Architectural thinking applies meaningfully

**Examples of negative evidence:**

- MOD-W terminology becomes systematically misleading or requires constant reframing
- A role defined for software development has no meaningful non-software equivalent
- A required software artifact category (e.g., test report, build log) is irrelevant
- Software build/CI assumptions create artificial or wasteful process for knowledge work
- Local adaptation becomes so extensive that the original MOD-W mechanism is no longer recognizable

**Mixed evidence must remain mixed.** Do not force binary success/failure classifications prematurely. If different MOD-W elements transfer differently, say so.

---

## Canonical MOD-W Protection Rule

**Canonical MOD-W v5.0.1 templates under `mod-w/templates/` are experimental baseline artifacts and must not be modified merely to improve transferability within `prod-w-dev`.**

If a change to canonical MOD-W appears necessary:

1. **Record** the underlying observation and why canonical MOD-W seems inadequate
2. **Determine** whether a local adaptation is actually sufficient or whether canonical change is truly required
3. **Record** any approved local adaptation separately in `adaptations.md`
4. **Continue** the experiment without changing canonical MOD-W
5. **Defer** conclusions about canonical MOD-W changes until sufficient evidence from multiple projects or deeper analysis accumulates

This protects both the experiment and the canonical framework from premature coupling.

---

## Historical Integrity

Accepted observations should **not be deleted or rewritten** merely because later evidence changes the interpretation.

Instead:

- **Preserve** the original observation and its classification at the time it was accepted
- **Append or cross-reference** any new or contradictory evidence
- **Update** the interpretation or disposition when warranted
- **Update** `assessment.md` separately to reflect current synthesis

This ensures the research record behaves as an **evidence trail and audit log**, not as a continuously rewritten narrative that obscures how understanding changed.

---

## Operational Flow

```
MOD-W role encounters transferability evidence
        ↓
Role observes and proposes observation
(with concrete evidence and tentative classification)
        ↓
Moderator reviews:
  - Is evidence sufficiently concrete?
  - Is classification appropriate?
  - Does classification match evidence quality?
        ↓
[Accept → added to observations.md]
[Return for clarification → request more evidence]
[Reclassify → adjust classification with rationale]
[Defer → tag as pending further work]
        ↓
If local adaptation appears necessary:
        ↓
Affected role or team proposes adaptation
        ↓
Moderator evaluates:
  - Is there sufficient evidence this is necessary?
  - Is the adaptation minimal and reversible?
  - Are effects on other work understood?
        ↓
[Authorize → added to adaptations.md]
[Reject → record as workaround, not adaptation]
[Defer → gather more evidence first]
        ↓
Project continues with approved adaptation(s)
        ↓
Moderator periodically (per stage or gate):
  - Reviews new observations
  - Updates assessment.md synthesis
  - Identifies emerging patterns
        ↓
Research record remains immutable; synthesis evolves
```

---

## Related Research References

This governance framework builds on and references existing `prod-w-dev` research artifacts:

- `research/topics/mod-w-beyond-software-experiment.md` — Experiment framing
- `research/topics/mod-w-protocol-refactor-hypotheses.md` — Specific MOD-W mechanisms under examination
- `research/topics/agent-harness-conformance.md` — Role and tooling observations
- `research/conversations/2026-09-29-prod-w-origin-protocol-research-conversation.md` — Initial discovery

See these for deeper context. Do not treat hypotheses in those research files as accepted observations or conclusions.

---

## Assessment and Review Cadence

The Moderator should:

- **Continuously** accept or return observations as they are proposed
- **Per stage gate** (e.g., after Product Definition acceptance, after architecture phase, etc.) review accumulated observations
- **Per stage gate** update `assessment.md` with current synthesis and open questions
- **At project conclusion** produce a final assessment distinguishing evidence, limitations, and implications for MOD-W or future methodology work

---

## Summary: What This Is and Is Not

### This IS:

✓ A structured evidence register about MOD-W transferability  
✓ Governed by the MOD-W Moderator role in `prod-w-dev`  
✓ Protected by rules that favor evidence over expectation  
✓ A record of both successes and failures  
✓ An audit trail of how understanding evolved  
✓ A research mechanism, not a product mechanism

### This IS NOT:

✗ A vote or consensus mechanism  
✗ A protocol for PROD-W itself (PROD-W design happens in `mod-w/product.md` and product roadmap)  
✗ A rationale for changing canonical MOD-W  
✗ A claim that MOD-W is universally domain-independent  
✗ An attempt to hide evidence that contradicts initial expectations  
✗ A process for authorizing individual team members' local workarounds

---

**See `observations.md`, `adaptations.md`, and `assessment.md` for the research record itself.**
