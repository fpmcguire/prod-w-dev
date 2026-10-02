---
title: PROD-W Compliance Skills Pattern
type: design-concept
status: Proposed (forward-looking)
date: 2026-10-03
author: Tech Lead
audience: Future skill developers, compliance domain experts, Moderator
references:
  - mod-w/skills/
  - mod-w/templates/MOD-W.md
  - mod-w/product.md (PE-1, PE-2, PE-3, HA-1, HA-2)
  - prod-w/rule-judgment-boundary.md
---

# PROD-W Compliance Skills Pattern

## Executive Summary

PROD-W's core strength — separating mechanically-checkable rules from human judgment — provides a natural foundation for **executable agent skills** that embed regulatory compliance (ESG, EU AI Act, Privacy, Accessibility, etc.) into the MOD-W workflow.

Rather than static compliance documents, **compliance skills** are reusable MOD-W procedures that:

- Automate what is objectively checkable
- Flag what requires human judgment and authority
- Record compliance evidence into the gate decision log
- Integrate with MOD-W's agent harness
- Repeat continuously as the product.md evolves

---

## Problem: Current Compliance Workflow

### Today's Pattern

Compliance is often:

- **Bolted on late** — after product decisions are made
- **Externalized** — separate from product development gates
- **One-time** — checked once, not as product changes
- **Binary** — pass/fail, not evidence-traceable
- **Authority-unclear** — who actually decides if it's compliant?

### Result

- Conflicts between product and compliance decisions
- Sunk costs before regulatory issues surface
- Unclear responsibility and escalation paths
- No continuous revalidation as assumptions change

---

## Solution: PROD-W Compliance Skills

Embed regulatory compliance as **live, traceable, executable skills** that integrate into the product development workflow.

### Core Pattern

```
product.md + evidence register + compliance skill
         ↓
    1. Extract material claims (automated)
    2. Run checkable rules (automated)
    3. Flag judgment calls (prompt human)
    4. Record gate decision (evidence log)
         ↓
Compliance gate status (checkable + judgment + authority)
```

### Example: ESG Compliance Check Skill

**Input:**

- `product.md` with environmental/social/governance impact claims
- Evidence register from prior PROD-W steps

**Checkable Rules (Automated):**

- ✓ Does it disclose carbon footprint assumptions?
- ✓ Does it list social equity impact assessment?
- ✓ Are governance risks documented?
- ✓ Are assumptions marked for validation?

**Judgment Calls (Human Authority):**

- ? Is the carbon impact "material" under ESG framework?
- ? Does social equity concern block the go/build decision?
- ? Are the governance mitigation strategies adequate?

**Output:**

- Automated check results (passed/failed/not-applicable)
- Human judgment decisions (recorded + authorized)
- Assumption register (what compliance depends on)
- Gate status (Accepted/Escalation/Blocked)

---

## Why This Works

### 1. Reuses PROD-W's Rule/Judgment Boundary (STEP-04)

PROD-W already defines:

- **Objectively checkable:** Defined elements, record-only answer, no judgment inside (three-part test)
- **Contextual judgment:** Requires authorized human interpretation of sufficiency/risk/materiality/acceptability

Compliance rules naturally fall into both categories:

**Checkable (CR):**

- ✓ Required disclosure present in documentation
- ✓ Data source recorded and traceable
- ✓ Bias metric calculated for each demographic group
- ✓ Human override path documented

**Judgment (HJ):**

- ? Is this risk "high-risk" or general-risk under AI Act? (contextual)
- ? Is the impact "material" under ESG? (policy determination)
- ? Is transparency "adequate" for stakeholders? (audience interpretation)
- ? Does human override preserve "meaningful control"? (governance judgment)

### 2. Preserves Authority

Each compliance skill defines:

- **What is checked** (rule catalog)
- **What requires judgment** (judgment catalog)
- **Who has authority** (binding to AUTH-G holders)
- **When escalation happens** (gate decision logic)

From PROD-W core principle (PE-1, HA-1):

> Material claims require traceable evidence.
> Consequential decisions require explicitly authorized human judgment.

### 3. Integrates with MOD-W Workflow

Compliance skills live in `mod-w/skills/` and are called at the right gate:

```
Phase 0: Product Definition (product.md created)
         ↓
Phase 0a: Run compliance skills (ESG, AI Act, Privacy, etc.)
         ↓ (produces compliance evidence + judgment flags)
Phase 0b: Product Moderator reviews compliance gate
         ↓ (accepts or returns for revision with authority binding)
Phase 1+: Proceed with confidence (all compliance gates accepted)
```

Or within PROD-W itself:

```
PROD-W STEP-06: Methodology Guidance
         ├─ When to call prod-w-esg-compliance-check
         ├─ When to call prod-w-ai-act-assessment
         ├─ When to call prod-w-privacy-audit-gate
         └─ How to record compliance decision in gate log
```

### 4. Executes Continuously

Compliance skills can be re-run when:

- Product.md is updated
- Evidence changes
- Assumptions are challenged
- External regulation changes
- Before major gates or go/no-build decisions

This means compliance is **live**, not a historical artifact.

---

## Architecture

### Skill Location and Ownership

```
mod-w/skills/
├── prod-w-esg-compliance-check.md
│   ├── ESG checkable rules (E/S/G split)
│   ├── ESG judgment calls
│   ├── Evidence templates
│   ├── Authority binding (ESG Officer, CFO, etc.)
│   └── Escalation logic
│
├── prod-w-ai-act-risk-assessment.md
│   ├── Risk tier classification rules
│   ├── High-risk checkpoints
│   ├── Transparency requirement checklist
│   ├── Human override verification
│   └── Authority binding (Legal, Compliance Officer)
│
├── prod-w-privacy-audit-gate.md
│   ├── GDPR/CCPA/regional privacy rules
│   ├── Data handling judgment calls
│   ├── Consent/transparency verification
│   └── Privacy Officer authority
│
├── prod-w-accessibility-check.md
│   ├── WCAG/ADA checkable criteria
│   ├── Accessibility judgment calls
│   └── Accessibility Officer authority
│
└── prod-w-compliance-gate-aggregate.md
    ├── Aggregate findings from all compliance skills
    ├── Escalation routing (which findings need which authority)
    ├── Waiver/exception handling
    └── Final compliance gate decision
```

**Ownership:**

- **Authored by:** Domain expert (ESG specialist, AI Act lawyer, Privacy Officer) + Tech Lead
- **Reviewed by:** Moderator
- **Executed by:** Agents (Claude Code subagent, etc.) in MOD-W harness
- **Approved by:** Moderator + domain expert as standing procedure

---

## Implementation Pattern (For Future Skills)

When creating a compliance skill, follow this template:

### 1. Skill Metadata

```markdown
---
skill: prod-w-[domain]-[check|assessment|gate]
status: [Proposed | In Development | Ready]
domain: [ESG | AI Act | Privacy | Accessibility | etc.]
owner: [Domain Expert Title] + Tech Lead
authority_binding: [Who has AUTH-G to accept this gate]
trigger_gates:
  - Phase 0 (Product Definition gate)
  - PROD-W STEP-06 (Methodology)
  - Any go/no-build decision
---
```

### 2. Rule Catalog (Checkable)

Format: One per rule, with sources and evaluation kind

```markdown
| ID    | Rule                                    | Source           | Evaluation | Handling |
| ----- | --------------------------------------- | ---------------- | ---------- | -------- |
| CR-01 | Does product.md disclose carbon impact? | ESG-Framework v3 | Automated  | I, F     |
| CR-02 | Is data lineage recorded?               | AI Act Art. 13   | Automated  | I, X     |
```

Use PROD-W's handling categories:

- **I (Invalidating):** Missing this blocks compliance
- **F (Flagging):** Missing this requires escalation
- **X (Visible exception):** Can be waived with documented exception

### 3. Judgment Catalog (Human Authority)

Format: One per judgment, with authority binding

```markdown
| ID    | Judgment                          | Authority          | Why Judgment             |
| ----- | --------------------------------- | ------------------ | ------------------------ |
| HJ-01 | Is this "high-risk" under AI Act? | Compliance Officer | Contextual determination |
| HJ-02 | Is carbon impact "material"?      | CFO / ESG Officer  | Policy decision          |
```

### 4. Execution Logic

```markdown
1. **Extract claims:** Parse product.md for regulated domain
2. **Run automated checks:** Test each CR rule
3. **Surface judgments:** Prompt authorized human for each HJ
4. **Record decision:** Write to evidence/gate log
5. **Gate status:** Accepted / Escalation / Blocked
```

### 5. Evidence Templates

Define what evidence is required for each check:

```markdown
### Evidence for CR-01 (Carbon Impact Disclosure)

Required fields in product.md:

- [ ] Carbon footprint scope (direct, indirect, supply chain)
- [ ] Methodology (GHG Protocol, ISO 14064, etc.)
- [ ] Data source (calculated, measured, estimated)
- [ ] Confidence level
- [ ] Assumptions marked for validation

Template:
```

#### Environmental Impact

- **Carbon Footprint:** [scope] – [value] [unit]
  - Methodology: [reference]
  - Data source: [measured/calculated/estimated]
  - Confidence: [high/medium/low]
  - Assumptions: [list with A-IDs]

```

```

### 6. Gate Template

How the gate decision is recorded:

```markdown
## ESG Compliance Gate Decision

**Date:** [date]  
**Authority:** [Name, Title]  
**Status:** Accepted | Escalation | Blocked

### Checkable Rules

| Rule  | Result | Evidence                                         |
| ----- | ------ | ------------------------------------------------ |
| CR-01 | ✓ PASS | Carbon Impact section present, methodology cited |
| CR-02 | ✗ FAIL | No social equity impact assessment               |

### Judgment Calls

| Judgment | Decision              | Reasoning                                               | Authority                |
| -------- | --------------------- | ------------------------------------------------------- | ------------------------ |
| HJ-01    | MATERIAL              | Product targets healthcare; equity concerns justified   | ESG Officer: [Signature] |
| HJ-02    | ACCEPTABLE MITIGATION | Mitigation strategy includes [X]; escalation not needed | CFO: [Signature]         |

### Escalations

- CR-02 (social equity) routed to [Title] for decision

### Gate Outcome

**Compliance Gate:** ACCEPTED  
**Conditions:** ESG mitigation strategy to be validated by [date]  
**Waivers:** None  
**Next review:** [date or trigger]
```

---

## Integration with MOD-W

### When Compliance Skills are Called

1. **Phase 0 (Product Definition):**
   - Run all applicable compliance skills after product.md is drafted
   - Flag any critical gaps before Moderator gate
   - Fold compliance constraints into Phase 1 Architecture

2. **PROD-W STEP-06 (Methodology Guidance):**
   - Document which compliance skills apply to the workflow
   - Define when each skill is triggered
   - Record authority bindings for judgment calls

3. **Before Go/No-Build Decisions:**
   - Re-run compliance skills with current product.md + evidence
   - Update compliance gate status
   - Confirm all waivers/exceptions still valid

4. **On Product Changes:**
   - Re-run affected compliance skills
   - Flag new risks or gaps
   - Update gate decision if needed

### Skill Invocation (Example Prompt)

```
You are executing the prod-w-esg-compliance-check skill.

Input:
- product.md (attached)
- Evidence register from PROD-W STEP-02 and STEP-03 (attached)
- Authority binding: ESG Officer [Name], CFO [Name]

Procedure:
1. Extract environmental/social/governance impact claims
2. Test each claim against CR rules (CR-01 to CR-15)
3. For each failed check, determine if it's invalidating (I) or flagging (F)
4. Identify judgment calls (HJ-01 to HJ-10)
5. Prepare prompts for authorized humans
6. Record gate decision using the template

Output:
- Checkable rules result table
- Judgment prompts (for human escalation)
- Gate status (Accepted/Escalation/Blocked)
- Evidence record for compliance log
```

---

## Future Compliance Skills (Planned)

| Domain            | Skill                            | Trigger                 | Authority                 |
| ----------------- | -------------------------------- | ----------------------- | ------------------------- |
| **ESG**           | prod-w-esg-compliance-check      | Phase 0, PROD-W STEP-06 | ESG Officer, CFO          |
| **AI Act**        | prod-w-ai-act-risk-assessment    | Phase 0, before build   | Compliance Officer, Legal |
| **Privacy**       | prod-w-privacy-audit-gate        | Phase 0, if user data   | Privacy Officer (DPO)     |
| **Accessibility** | prod-w-accessibility-check       | Phase 0, if UI product  | Accessibility Officer     |
| **Industry**      | prod-w-[sector]-compliance       | Sector-specific         | Sector Compliance Officer |
| **Aggregate**     | prod-w-compliance-gate-aggregate | All gates ready         | Moderator + Compliance    |

---

## Benefits

### For Product Teams

- Compliance gates are **clear, not mysterious**
- Authority is **explicit** (who decides?)
- Evidence is **traceable** (why was this decided?)
- Continuous **revalidation** (not one-time)

### For Compliance Officers

- Compliance **is automated where possible**
- **Judgment calls are captured** and authorized
- **Evidence is recorded** for audit trails
- **Escalation paths are clear**

### For Regulators & Auditors

- **Evidence trail** shows what was checked and when
- **Authority bindings** show who was accountable
- **Assumptions** are visible (so risk is visible)
- **Waivers** and **exceptions** are explicit (not hidden)

---

## Alignment with PROD-W Core

This pattern operationalizes PROD-W's core principles:

**PE-1: Material claims require traceable evidence.**
→ Every compliance requirement is a material claim with evidence binding

**PE-2: Agent agreement is not independent evidence.**
→ Compliance requires human authority, not just agent agreement

**PE-3: Inference and fact remain distinct.**
→ Checkable rules (facts) separate from judgments (interpretations)

**HA-1: Consequential decisions require explicitly authorized human judgment.**
→ Each skill defines who has authority for judgment calls

**HA-2: Human authority is preserved at gates, not compromised.**
→ Compliance gates remain explicitly human-authorized

**AH-1: Assumptions are surfaced and tracked.**
→ Compliance depends on assumptions (data sources, scope, frameworks) marked for challenge

---

## Open Questions for Implementation

1. **Judgment recording:** How detailed should human judgment entries be? (Free text vs. structured form)
2. **Exception lifecycle:** When does a waiver expire? How is it challenged?
3. **Regulation versioning:** How do skill rules update when regulations change?
4. **Cross-compliance:** What happens when two compliance skills conflict? (E.g., ESG vs. AI Act on transparency)
5. **Nested products:** If product.md itself produces outputs (e.g., PROD-W produces protocol.md), do we run compliance skills on outputs too?
6. **Continuous triggers:** How often should compliance skills auto-run? (On every product.md change, or manually triggered?)

---

## Next Steps (Implementation, If Approved Later)

If this pattern is adopted, the implementation sequence would be:

1. **Validate pattern** with domain experts (ESG, Legal, Privacy, Accessibility specialists)
2. **Implement first skill** (recommend: prod-w-esg-compliance-check as proof of concept)
3. **Define skill interface** in MOD-W skill template
4. **Integrate skill execution** into MOD-W agent harness
5. **Create authority binding process** (how Moderator assigns compliance authority)
6. **Establish continuous trigger logic** (when compliance skills are re-run)

---

## Status and Governance

**Current Status:** Research design concept (Proposed, forward-looking)

**Governance:** This document lives in `research/topics/` as a design hypothesis. It requires **no additional gate** to exist here.

**Future Governance:** If this pattern is adopted for implementation:

- The first compliance skill (e.g., prod-w-esg-compliance-check) will be authored per the template and placed in `mod-w/skills/`
- That skill will require normal MOD-W skill review and Moderator approval before use
- The pattern itself becomes a reusable reference for creating additional compliance skills

**Archive:** This concept informs future compliance-skill development and serves as reference architecture for regulatory integration into PROD-W.
