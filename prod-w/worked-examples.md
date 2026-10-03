---
artifact:
  type: methodology-worked-examples
  id: PROD-W-WE
  version: 0.2
  created: 2026-10-04
  updated: 2026-10-04
  status: Draft - Development Team work product for STEP-06. Not reviewed. Not accepted.
  produced_by: Development Team
  produced_under: STEP-06
source:
  step: mod-w/step-06.md
  methodology_guidance: prod-w/methodology-guidance.md
  role_charters: prod-w/role-charters.md
  templates: prod-w/templates.md
  protocol_semantics: prod-w/protocol-semantics.md
  gate_challenge_revalidation_semantics: prod-w/gate-challenge-revalidation-semantics.md
  rule_judgment_boundary: prod-w/rule-judgment-boundary.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Worked Examples

**Status:** Draft v0.2. Development Team work product for STEP-06. Not reviewed. Not accepted.

---

## 0. Read This First

**These are methodology examples, not pilot results.** Every person, product, source, quote, and event below is **invented** to illustrate practice. Nothing here records a real project, a real decision, or any evidence that PROD-W works. The STEP-07 proof-of-concept pilot has not been run and owns that question. STEP-07 may use these examples as inputs to its own design. It should not cite them as findings.

**Each example stands alone.** Names are reused for readability (Priya, Marcus, Lena, Dana, Sam, Jo, Rosa). The facts of one example do not carry to another, and the grants in each are described where they matter.

**The opportunity** used throughout is a made-up product called ScopeLedger: a tool to help independent consultants reconcile client scope changes before they invoice.

**Citations.** Rule IDs are from the accepted artifacts (PR-, GCR-, CRC-, EKR-, and so on). Template numbers are from `prod-w/templates.md`. "G §" is `prod-w/methodology-guidance.md`. The examples are written in short form. A real record uses the full templates, each starting with the Common Block (templates §0.1).

**Short names for artifacts:** GC = `gate-challenge-revalidation-semantics.md`, RJ = `rule-judgment-boundary.md`, PS = `protocol-semantics.md`.

### 0.1 Index

| ID | Shows | Outcome |
| --- | --- | --- |
| WE-1 | A **valid progression**: deferral, then acceptance with conditional progression and residual disagreement | Progression authorized for a narrow scope |
| WE-2 | A **visible non-progression**: refusal, an attempt to amend the gate, and an escalation that ends in a recorded authority gap | No progression |
| WE-3 | **Unresolved disagreement** between two gate authority holders, and no override hierarchy | Progression under visible disagreement |
| WE-4 | A **team of one**: why self-acceptance is invalid, and the cures | Authority gap, then a flagged cure |
| WE-5 | An **invalid acceptance** found and recorded, and bare assertions typed correctly | Acceptance has no effect. Requirements arise |
| WE-6 | A **consequential commitment that is not an acceptance** | Commitment record with visible warning |
| WE-7 | **Revalidation** after counter-evidence | Requirements, tiers, and closures |
| WE-8 | **Role rotation** and **recovery by a new project** | A cascade avoided, then a new project |

---

## WE-1. A Valid Progression: Discovery Gate (team of three, with an agent)

### Setting

Priya wants to move ScopeLedger from problem framing to low-cost solution exploration. The team is three humans and an AI agent.

**Establishing act (template 1), recorded by Priya, a human, before anything else.** Root grants recorded by that act:

| Grantee | Class and scope |
| --- | --- |
| Priya | AUTH-P and AUTH-A for the ScopeLedger discovery work |
| Marcus | AUTH-G for the Discovery gate, for the gate-definition scope, and for validation of hypotheses on the problem and customer dimensions. AUTH-G conferral scope covering AUTH-P, AUTH-A, and AUTH-V in this project |
| Lena | AUTH-A and AUTH-V for the Discovery gate |
| research-agent-1 (AI, actor position) | AUTH-P and AUTH-A, bounded to retrieval and drafting tasks |

The act states why Marcus is expected to be independent: he joined after the interviews were planned, has produced no discovery items, and will not edit them. It states that this is an assertion that may be challenged. It records the practice statements (what "recorded" means, where records live, who can write, how order is established, the version-binding method for instructions, the source-register convention).

**Gate definition (template 13), recorded by Marcus before use.** Progression: from problem framing to low-cost solution exploration, **not build**. One valid independent acceptance. Required evidence slots: problem existence (observation or testimony from more than one organization, plus an artifact of the current process, with a counter-evidence search); behavior change (testimony recorded as testimony, respondent role stated); existing alternatives (an attempt record with stated reach). Challenge criterion: the adoption inference challenged by an actor who produced none of its basis. Formal check: each evidence item carries the required elements; independent verification required; the criterion is designated decidable. Stricter condition: every evaluative claim carries a basis-presentation designation. Not waivable: the six items of G §12.6.

### Records, in order

1. **Claim C-1** (Priya, material): "Independent consultants lose billable time because scope changes are not reconciled before invoicing." Material because the whole opportunity rests on it.
2. **Source register** (template 4): S-1, S-2, S-3 are three consultants interviewed by Priya. Priya notes that S-2 and S-3 were referred by S-1: *distinct people, but the referral is recorded in the comparability note.* S-4 is an email thread about an invoice dispute that S-1 shared. S-5 and S-6 are product pages for two existing tools, retrieved by research-agent-1.
3. **Evidence E-1 to E-4** (templates 6, supports C-1): interview notes marked as testimony, plus the artifact S-4. Each has limitations stated ("three people, all in design consulting").
4. **Claim C-2** (Priya): "No existing tool reconciles scope changes before invoicing."
5. **First attempt at the gate.** Priya has recorded no search for alternatives yet. Marcus **defers**: **Deferral D-1** states what is awaited ("a recorded counter-evidence search for existing alternatives, from Priya or the agent") and from which position. Nothing is accepted and nothing is refused.
6. **Attempt record A-1** (template 7, by research-agent-1 under Priya's assignment): searched two directories and one review site with stated terms and dates. Found two tools that partially address it (S-5, S-6). **E-5 and E-6** are recorded as **counter-evidence** to C-2, with the same elements as supporting evidence. The agent's producing configuration is recorded (template 11) with instructions bound to the version in force at the act.
7. **Assumption AS-1** (Priya): "Consultants control their own tool budgets." No evidence yet. **Inference I-2**: "Consultants will pay for a reconciliation tool," citing only AS-1 and a second assumption AS-2. Its chain ends only in assumptions. It is **assumption-rooted**.
8. **Inference I-1** (Priya): "Consultants who invoice by project would adopt a reconciliation tool," citing E-1, E-3, and AS-1.
9. **Claim C-3** (Priya, evaluative): "Reconciling scope changes is worth solving." Basis-presentation designation recorded: *presented as a value judgment*, not as observed fact.
10. **Lena's challenge Ch-1** (template 12): target: inference I-1; target scope: sufficiency of the basis; basis: "the only source on adoption is S-1, and AS-1 is unvalidated". Lena produced none of I-1's basis, so she is an independent challenger.
11. **Priya's response R-1**: she **supersedes** I-1 with I-1b, narrowed to "consultants who invoice by project", and records AS-1 explicitly. A response does not close the challenge. **Ch-1 carries to I-1b** visibly as carried (GCR-28). Lena does not record resolution, so Ch-1 stays **unresolved**.
12. **Priya's response R-2** to the counter-evidence: she supersedes C-2 with C-2b, narrowed to "no tool reconciles scope changes *against the consultant's own project records* before invoicing". E-5 and E-6 carry to C-2b **for re-assessment** (GCR-28).
13. **Lena's formal-check result F-1** (template 22): check "each evidence item carries source reference, producer, observation time, target, polarity, limitations"; evaluation point: the record at the time of her check; elements examined: E-1 to E-6, by reference; result: **satisfied**. Effect claimed: satisfies the gate's formal-check slot for that criterion. Effect not claimed: sufficiency, acceptance.

### The acceptance

Marcus works through the readiness checklist (template 14):

| Condition | Marcus's finding |
| --- | --- |
| Human holding AUTH-G for this gate | Yes, by root grant |
| Gate definition recorded before | Yes |
| Accepted set listable, producers recorded | Subject (Priya's progression statement), C-1, C-2b, E-1 to E-6, A-1, I-1b, I-2, AS-1, AS-2, C-3, Priya's materiality designations, R-1, R-2, F-1 (Lena the verifier). Producers: Priya, research-agent-1, Lena (F-1) |
| Marcus a producer of none | Yes. He suggested the segment to interview. That is a **work assignment** with no conclusions specified, and he **discloses** it. The gate definition is not in the accepted set |
| Formal checks satisfied by an independent verifier | Yes: F-1, Lena. She is a producer of nothing she verified |
| Evidence slots and challenge criterion satisfied | Problem and behavior slots filled. Alternatives slot filled by A-1 and E-5, E-6. The challenge criterion is met by Ch-1 (an independent challenger). Whether the *adequacy* is enough is Marcus's judgment |
| Standing record cited with treatments | See below |
| Assumptions and assumption-rooted items covered by conditional progression | **CP-1** recorded before the acceptance, covering AS-1, AS-2, and the assumption-rooted I-2 |
| Explicit, attributable, with independence declaration | Yes |

**Standing-record treatments (template 15):**

| Item | Treatment | Why |
| --- | --- | --- |
| Deferral D-1 (earlier, same gate and basis) | Cited. "What changed": A-1, E-5, E-6 are now recorded | GCR-39 |
| Counter-evidence E-5, E-6 | **Answered**. Marcus judges C-2b, as narrowed, is not contradicted by two tools that do not reconcile against the consultant's own project records. He records why | The judgment is his |
| Challenge Ch-1 (carried to I-1b) | **Accepted as residual**, with rationale: the exploration is low-cost and reversible, and the only adoption evidence is thin. The decision carries the marker "accepted with unresolved Ch-1" | GC §5.5 |
| Exposure of I-1b through AS-1 | Cited. Covered by CP-1 | |

**CP-1 (template 17)** records ground G1: items relied on (AS-1, AS-2, I-2), what would resolve each (validation criteria to be recorded as hypotheses H-1 and H-2), who is expected to resolve it (Marcus holds the validation scope for these dimensions), the rationale (low cost to explore before any commitment), the reliance bound (solution exploration only), and a statement that **the requirement remains unsatisfied and open**. It produces reliance-under-assumption marks on each dependency link.

**Determination:** **Accepted**, for low-cost solution exploration only. **Not build.** Not inherited by a later gate. Independence declaration attached. The acceptance is a determination of sufficiency for that scope, not a finding that consultants will pay, and it validates nothing.

### What this shows

- A **deferral** records what is awaited and is cited by the later acceptance, with what changed.
- **Counter-evidence** is recorded the same way as support and is **treated**, not dropped.
- A challenge can stay **unresolved** and the gate can still be accepted, if the acceptor records it as residual with a marker.
- Conditional progression and acceptance as residual are **different instruments**: CP-1 leaves the assumptions open and tracked. The residual treatment leaves a challenge open and visible.
- Marcus is independent because he is a producer of nothing in the accepted set. His work assignment is disclosed, not hidden.
- The agent produced evidence **through sources** and its configuration was recorded. Its agreement with Priya was never used as corroboration.

### What this does not show

That ScopeLedger is a good idea, that the evidence is adequate in any real case, or that three interviews is enough. Adequacy was Marcus's invented judgment in an invented case.

---

## WE-2. A Visible Non-Progression: Build Gate Refused

### Setting

The same team later wants to proceed to build. The gate definition for build requires: customer evidence on willingness to pay from a budget holder; technical-feasibility evidence recorded separately from commercial evidence; independent challenge of the differentiation claim; a verification that each evidence item carries the required elements. Marcus holds AUTH-G for the gate and is the only holder.

### Records

1. Priya submits a basis. The differentiation claim **C-4** ("ScopeLedger is clearly better than alternatives") cites only research-agent-1's synthesis of competitor websites and a second agent's agreement. There is no customer evidence on payment and no feasibility evidence.
2. **Lena's challenge Ch-2** (template 12): target: C-4; scope: sufficiency of the basis; basis: "C-4 is an inference from website summaries, not evidence, and the agreement of two agents is not corroboration (EKR-17)". She attaches sourced counter-evidence **E-7** (a customer-facing page showing an incumbent's scope-change feature), recorded as counter-evidence to C-4.
3. **Marcus refuses** (template 15). The refusal states which conditions are unsatisfied: no customer payment evidence; no feasibility evidence; the challenge criterion met but unanswered on a basis that lacks evidence; counter-evidence E-7 standing. It states **what would change the determination**: customer evidence on payment from a budget holder, a recorded feasibility test, and a response to Ch-2 with sources. The refusal is **not final**, erases nothing, and stays in the standing record of any later acceptance (GCR-19, GCR-39).
4. **Priya disagrees** and records a **recommendation** R-3: "Proceed to build." It is a recommendation, because Priya holds no AUTH-G for this gate (ACT-07, INV-16).
5. **Priya asks Marcus** (who holds the gate-definition scope; Priya does not) to amend the gate definition to remove the feasibility slot, and then to accept. An amendment made after a refusal on the same basis **applies to that basis only as a recorded exception** (GCR-13). Marcus declines to grant one, and records why. A feasibility slot is waivable in principle. Whether to waive it for this progression is his judgment.
6. **research-agent-1 suggests** the second agent "approve" the build to unblock the team. This is invalid: AUTH-G is human only (PR-05; INV-04), and agent agreement is not acceptance (PR-13, PR-20).
7. **Priya escalates** (template 19) the refused gate: matter: the refusal; reason: refused gate; resolving authority sought: another AUTH-G holder for the build gate, independent of the accepted set; identities holding it now: **none**; determination asked for: resolve or defer.
8. **Authority-gap record** (template 20): no identity meeting the independence condition can fill the resolving authority for a second view on the refusal. The options recorded: grant AUTH-G for the gate to an independent human (a conferral by Marcus, flagged if he is a producer of the set he would be conferring for, which he is not); re-base on independent items; substitute; or stop. The team **stops at the gate** and continues production work: customer interviews on payment and a feasibility test.

### Outcome and what this shows

**No progression.** The record shows: the basis, the refusal and its reasons, the counter-evidence, the recommendation, the attempted amendment and its treatment as an exception question, the escalation that resolves nothing, and the authority gap.

- **Refusal is a legitimate outcome** and a learning trail, not a failure.
- **Amending the standard to fit a refused basis is a recorded exception**, not a quiet fix.
- **A recommendation is not a decision.** Agent agreement is not acceptance.
- **Escalation resolves nothing.** With no second holder, the matter is an authority gap, which the protocol allows a project to stop at.
- The team is not blocked from *work*. The protocol governs recorded reliance in gates, decisions, and commitments, not conduct in the world (GC §7.6).

---

## WE-3. Unresolved Disagreement Between Gate Authority Holders

### Setting

A technical-feasibility gate for ScopeLedger. Two humans hold AUTH-G for the gate by root grant, and both also hold AUTH-A: **Dana** (the tech lead) and **Marcus**. Neither produced the feasibility basis, which Priya and research-agent-1 produced. The gate definition **designates no position for resolving role conflicts**.

### Records

1. Priya's claim **C-5**: "A prototype using an off-the-shelf language model can extract scope changes from email threads well enough for a pilot." Evidence: test results on 40 sample threads, recorded with the producing configuration of the agent that ran them, including the failures (E-8). Counter-evidence: three threads where the model invented scope changes (E-9), recorded by Priya as required by EKR-18.
2. **Dana refuses** with reasons: the sample is small, the failures are in the cases that matter, and the test used the producer's own examples. She records what would change the determination.
3. **Marcus**, independently, finds the basis sufficient **for a pilot of this scope** and wants to accept.
4. Marcus's acceptance is **valid only if it cites Dana's refusal** as part of the standing record with a treatment, **including what changed since**. He records: "Not changed. I weigh the failures differently. I judge the pilot scope tolerates them because every extraction is reviewed by the consultant." He records the refusal as **accepted as residual**, with a marker: **"accepted with unresolved: refusal by Dana on the same basis."**
5. **The protocol defines no override hierarchy** among gate authority holders (GCR-39). Dana's refusal is not overridden. It remains recorded and visible. Either holder may escalate to a designated conflict position, and none is designated, so the disagreement is **unresolved and visible**, and any dependent sees the marker.
6. **Dana records a challenge Ch-3** against Marcus's acceptance (target: the acceptance; scope: sufficiency for the stated scope; basis: the failures are in the cases the pilot cannot review). It is a first-class record. It is not an act of veto.

### Outcome and what this shows

Progression is authorized for the pilot scope **under visible, unresolved disagreement**. No consensus was required or sought (GCR-36, GCR-38).

- **No override hierarchy exists.** Say so rather than inventing one.
- **Practice lesson:** when a gate has more than one holder, **designate a role-conflict position in the gate definition**, or decide in advance that the project accepts the cost of an authority gap. Do this before a disagreement exists. A definition amended after the disagreement applies only as an exception (GCR-13).
- The unselected position (Dana's refusal) stays recorded and can be reopened by a new trigger or challenge (GC §8.3).
- The marker is **ordinary acceptance made with open eyes**. It is not an exception and it validates nothing.

---

## WE-4. A Team of One: Authority Gap and Its Cures

### Setting

Sam is a solo founder with several AI agents. Sam establishes the ScopeLedger project and, knowing the limits, records **every grant Sam needs in the establishing act**, including AUTH-P and AUTH-A for the work, AUTH-G for gate acceptance and gate definition, and a conferral scope. Sam is the only human.

### What happens

1. Sam defines a build gate (valid: Sam holds the gate-definition scope; defined before use). Sam and the agents produce the whole basis. Sam supplies the conclusions and has the agents write them up.
2. **Sam attempts to accept** the build gate. **This is invalid.** Sam is a recorded producer of the accepted set (PR-16, GCR-03). Recording the act under "Moderator" changes nothing (PR-17; INV-02). Sam's agents reviewing the basis and agreeing is not independence (PR-27, PR-28; PR-20). Sam challenging the basis is recorded and is not independent (PR-19). An exception cannot cover independence (GCR-06).
3. **The honest record** is therefore: a prepared basis, Sam's self-challenge (useful, and recorded as such), agent review findings (advisory), and a **recommendation** by Sam to proceed (not a decision). Sam records the **authority gap** (template 20) against the build gate.
4. **What Sam can still do validly:** refuse, defer, escalate, request revalidation, withdraw or retire Sam's own items, revise (conservative acts, GCR-05).

### Cures, as Sam considers them

| Cure | What it needs | Weakness |
| --- | --- | --- |
| **A. Name an independent human in the establishing act** | Sam would have had to do this at the start | If Sam had named **Jo** (an advisor with no involvement in the work) as AUTH-G for the build gate **in the establishing act**, no conferral flag arises. Root grants are not flagged (D10). A proxy is caught only by challenge, so Sam should have stated why Jo is independent |
| **B. Confer to Jo later** (chosen) | Sam's conferral scope covers it. Sam records template 3 | Sam is a producer of the set. A conferral by a conflicted holder is **flagged and escalation-eligible** (CRC-64), **not invalid**. The flag stays on every favorable act relying on Jo's grant, and is part of the standing record. It will be challenged |
| C. Re-base on independent items | Evidence produced by someone other than Sam | Takes time. Must be done visibly |
| D. Stop | Nothing | The protocol permits it |

Sam pursues B and records the flag. **Jo** reads the basis, **challenges** two points (a challenger is not thereby a producer of the accepted set), receives responses, and declines to resolve one. Jo discloses that Sam briefed Jo for an hour on the product vision. Jo **did not edit anything and supplied no conclusions**. Jo decides the briefing was not substance. That is a judgment the declaration states and any AUTH-A holder may challenge.

Jo's acceptance cites the flag, the unresolved challenge (as residual), and the assumptions (covered by a conditional progression authorization **recorded by Jo before accepting**, not by Sam). Jo is independent over the set, so Jo can authorize it. Sam could not.

### What this shows

- **A one-human team cannot validly accept its own work** and no relabeling fixes it.
- The most valuable single practice for a solo founder is to **name an independent human in the establishing act**, with a stated basis for independence, **before** the first gate matters.
- **A flagged cure is weaker than a root grant, but it is available**, and the flag keeps the weakness visible.
- Self-challenge and agent review are **valuable for producing better work**. They feed production and escalation. They never feed acceptance (PS §6.5).

---

## WE-5. An Invalid Acceptance, a Valid Finding, and Bare Assertions Typed Correctly

### Setting

A team of three humans (Priya, Marcus, Lena) and an agent. Marcus holds AUTH-G for the Discovery gate. Lena holds AUTH-V. During drafting, **Marcus edited the wording of inference I-3** in the material basis, changing "some consultants" to "most consultants". The edit is recorded in the history of I-3 and Marcus is therefore recorded as a producer of it.

### What happens

1. Marcus **accepts** the Discovery gate. The acceptance record exists and is explicit and attributable.
2. **It is invalid.** Marcus is a recorded producer of I-3, a member of the material basis and therefore of the accepted set (GCR-03). "I only edited it" is not an exemption, and no contribution is too small. The acceptance had **no intended effect from the outset**, whether or not anyone notices. It stays visible as invalid (PR-11).
3. **Lena records a finding (template 23)** that the acceptance is invalid:
   - **Rule violated:** GCR-03 and PR-16 (the acceptor is a recorded producer of a member of the accepted set).
   - **Evaluation point:** the acceptance act A-7.
   - **Record elements examined:** A-7's acceptor identity; the producer record of I-3 including the edit by Marcus; the listing of the accepted set showing I-3 as a member.
   - **Decidable from the record:** yes, because the producer record and set membership are recorded.
   - Lena holds AUTH-V for the scope, so the finding has standing.
4. **Effect:** a requirement arises on every dependent that relied on the acceptance (TRG-6). **Progression through the gate was not authorized.** Marcus cannot clear the requirement by disputing the finding: a challenge to a finding does not suspend the requirement it created (RJ §9.4.3). Marcus may **withdraw his own acceptance**, which is a conservative act and is itself a TRG-6 event (CRC-59).
5. **Repair options.** A **fresh acceptance** by an independent AUTH-G holder (Dana, if she holds the grant and produced nothing in the set). Or **re-basing**: replace I-3 in the basis with an inference drawn from independent evidence that Marcus did not touch, recorded visibly. A successor that merely restates I-3 is **not** a cure, because a producer is never removed by restatement (GCR-07). A co-acceptor does not cure it (PR-18). A waiver does not cure it (GCR-06). If there is no other holder, it is an authority gap.

### Bare assertions, typed by what the recorder holds

Others in the project react to the acceptance:

| Who says what | What it is, and why |
| --- | --- |
| **Priya** (AUTH-A): "That acceptance looks sketchy." | A **challenge** to the acceptance (scope: validity of an act). A bare assertion is not a finding. It creates contestation and exposure |
| **Priya**, adding: "and here is the edit history showing Marcus changed I-3." | Still a **challenge**, now citing the edit history, which she records as an evidence item (counter-evidence against the decision). Sourced counter-evidence on a direct material dependency creates a requirement. A revalidation **request** with a stated basis would too (P3) |
| **research-agent-1**, holding no applicable authority, writes "this acceptance is invalid." | An **advisory finding**. It informs. It triggers nothing |
| **An external evaluator** (an AI service) writes "Marcus and Priya appear close, so independence is doubtful." | **Substantive independence is a judgment** (HJC-12). It is not decidable from the record, and an evaluator is not a human AUTH-G holder. It stays an **advisory finding** or becomes a challenge. It does not trigger TRG-6 |
| **A non-human AUTH-V holder** writes a finding asserting the acceptance is invalid because "the evidence is not convincing". | Not a finding. The rule asserted depends on interpretation, so it is **advisory or request-like** and does not itself trigger TRG-6 (CRC-59) |

### What this shows

- Invalidity does not depend on detection. Detection is a recorded event that starts consequences.
- A finding has **three required contents**. A bare "invalid" has none, and is typed by the authority the recorder actually has.
- **Reviewers should challenge, not edit.** One edit by the acceptor-to-be was enough to disqualify them.
- A check or finding is **not** gate acceptance and writes nothing into the item's condition.

---

## WE-6. A Consequential Commitment That Is Not an Acceptance

### Setting

Rosa is the company's executive sponsor. She has organizational authority over spending but holds **no PROD-W AUTH-G** for any ScopeLedger gate. The team's Discovery gate was accepted with a conditional progression authorization covering the **pricing hypothesis H-3** ("consultants will pay a monthly subscription"), which is **unvalidated**.

A customer asks for a signed pilot agreement now. Rosa wants to sign.

### What the team decided in advance

The establishment record states the project's **commitment routing practice** (G §15.2): any commitment that makes an external promise or commits spend is routed through either a gate acceptance or a decision record. A commitment that cannot be (because it is made by an authority outside the project's gates) gets a **commitment record**.

### Two ways this could go

**Route 1: through a decision record.** Marcus (AUTH-G, independent over the set) records a decision (ACT-07): "Sign a pilot agreement with Customer X for 3 months." He cites the basis, including H-3, and records a **conditional progression authorization** (ground G1) covering the reliance on H-3 **at or before** the decision. CRC-48 applies: basis, authority basis, and nature are recorded. A decision without those would be a recommendation. Because the decision authorizes progression, the validity conditions of an acceptance apply to it, including coverage of reliance on an unvalidated hypothesis (GC §5.4, condition 8).

**Route 2: Rosa signs under organizational authority** (the case here). Marcus does not hold a gate that covers customer contracts, and Rosa will not wait. The team completes **template 24**:

- **Commitment:** a 3-month pilot agreement with Customer X.
- **Why consequential:** an external promise with spend.
- **Routing:** neither a gate acceptance nor a decision record; a commitment by an authority outside the project's gates.
- **Made by, on what authority:** Rosa, organizational authority. **Stated as such. This is not a PROD-W grant.**
- **Unvalidated hypotheses relied on:** H-3. **Assumptions:** AS-1 (budget control). **Open requirements:** none.
- **Reliance marks:** present on each dependency link from the commitment to H-3 and AS-1.
- **Visible warning**, wherever the commitment is cited: *"This commitment relies on H-3, which is unvalidated. It is not a PROD-W acceptance and does not validate anything."*
- **Later gate or review:** a pricing-validation gate, with Marcus holding the validation scope for the customer dimension, expected before any renewal.
- **Independence note:** Rosa is not a producer of H-3's basis.

### What this shows

- The protocol adds **no rule** for a commitment that is not an acceptance. The team's **practice** keeps the reliance visible.
- **Nothing is validated** by signing. H-3 stays unvalidated.
- If H-3 is later **refuted** (counter-evidence on a material dependency, TRG-2), everything that carried the reliance mark is findable.
- An alternative the team can adopt in future: define a gate class for customer commitments so Route 1 is the normal route.

**Not shown:** whether the practice default is workable. That is a question for STEP-07.

---

## WE-7. Revalidation After Counter-Evidence

### Setting

Following WE-1, the team has an accepted Discovery decision **D-1** (Tier 1: a consequential decision), the narrowed differentiation claim **C-2b**, and an inference **I-4** (not in any consequential accepted set: Tier 2) that cites C-2b.

### What happens

1. **Lena records source-identified counter-evidence E-10** against C-2b: a published survey (source S-9) in which several invoicing tools add scope-change features. It has source, producer, time, target, polarity (contradicts), limitations, and lineage.
2. **A requirement arises on each direct material dependent by the event** (TRG-2, GCR-30), without waiting for anyone to adjudicate. The dependents are **D-1** and **I-4**. One requirement per dependent, with E-10 as a reason (GCR-58).
3. **Indirect dependents** (things that rely on I-4) are **exposed**, not given requirements. Consequences travel through outcomes.
4. **Dana**, reading the project, writes a claim **C-6**: "The market is moving away from this." It cites no source. It is a **bare contradicting claim**. It produces **exposure**, not a requirement. Dana has AUTH-A, so she can file a **request** with a stated basis (template 21), which creates a requirement on the dependent (P3). She does.
5. **Lena also files a request** that evidence E-4 (the invoice-dispute thread, which she notes is old) may no longer reflect current practice. Age is not a trigger by itself. She states her basis and the request creates a requirement on the dependent that cites it (GCR-67; GC §13.2).
6. **Closures.**

| Dependent | Tier | Outcome | Who |
| --- | --- | --- | --- |
| **I-4** | 2 | **Revision**: Priya revises I-4 into a successor reflecting E-10 | Priya, as producer. This closes the requirement **only as producer-addressed**. It is **not independent closure** |
| **I-4's successor** (optional) | 2 | **Reaffirmation**, if the team expects the successor to reach a gate | Marcus (AUTH-G; a producer of neither I-4 nor its material basis closure). This gives an independent closure |
| **D-1** | 1 | **Reaffirmation is a fresh acceptance** by an independent AUTH-G holder over the accepted set computed on the **current** basis, with E-10, C-6's exposure, and the requests in the standing record and **treated** | Marcus. The earlier acceptance stays as history. He narrows the scope of the reaffirmation to "continue exploration only" |

7. **Reliance meanwhile.** While D-1 has an open requirement, it is **not recorded as current**, and **new reliance** on it (citing it as basis in a new gate or decision) needs a closure or a **reliance-while-open authorization** (ground G2). Its historical acceptance stands. Work in the world is not halted.
8. **Standing transition.** If I-4's successor later enters the accepted set of a consequential acceptance, its **producer-addressed** closure counts as part of that acceptance's standing record and must be treated there. Priya cannot clear a requirement on her own draft and carry the clearance into a gate.

### What this shows

- **Sourced counter-evidence** has a stronger effect than a challenge or a bare claim because it cost the contributor a source, a basis, and limitations.
- Cheaper contributions have **defined routes** to a requirement (grounding, independent acceptance, or a request).
- **Time and age are inputs and request grounds. They never create or close a requirement.**
- Burden is controlled by one requirement per dependent, direct dependents only, and cheap producer revision at Tier 2.

---

## WE-8. Role Rotation and Recovery by a New Project

### Part A: Marcus wants to leave

**Setting.** The ScopeLedger project's establishing act gave root grants to Priya (AUTH-P, AUTH-A) and to Marcus (AUTH-G for the gates, gate definition, and a **conferral scope**). Marcus later **conferred** AUTH-V to Lena and AUTH-G for the feasibility gate to Dana. Marcus now wants to step away.

**Grant review (template 27).** Before doing anything, Priya and Marcus prepare a **cascade preview**:

- Lena's AUTH-V chain passes through Marcus's grant to the root.
- Dana's AUTH-G chain passes through Marcus's grant to the root.
- **If Marcus renounces his root grant, both fall prospectively** (CRC-63; D10). A renunciation is a revocation and cascades.
- **Only Marcus holds a conferral scope.** Nobody else could re-confer to Lena or Dana. Priya cannot (she holds none).
- Acts already performed while the whole chain was effective **stand**. Acts relying on a fallen grant after the renunciation would be **invalid**.

**What they decide.**

- Marcus **does not renounce**. A hand-over by renunciation would strand Lena and Dana with no way back. Conferring a conferral scope on Dana first would not help: Dana's chain would still run through Marcus's root grant.
- Marcus **leaves his grants in place**, stops acting, and records a note that he is inactive. The note is practice. It does not change the grants.
- The team records that the **root-grant design** was the weakness: a second conferral holder should have been named in the establishing act.
- If a clean break is needed, the realistic path is **a new project** (Part B).

**Lessons.** Plan departures before they happen. Hand-over of the top is by root grants in the establishing act or by leaving grants in place, not by renunciation. Narrow a grant when you mean to reduce it. Do not revoke and re-confer. Note that this practice limitation is a consequence of D10, not a protocol defect this guide can fix.

### Part B: Priya is lost, and the project cannot recover

**Setting (different history).** A project has one root grantee, Priya, who holds every grant. She leaves suddenly. Her account is gone. All root grants are effectively unusable. No other holder exists. (If a remaining human held a covering conferral scope the matter would be re-conferral, not recovery. Here none does.)

**There is no break-glass.** A second establishing act would be a way to mint a root. The project's authority chain is terminal (D10). Recovery is by a **new project**. The protocol does not define what carries over. What follows is **project practice** (G §16.2).

**What the team does.**

1. **Confirms** that no effective root grantee remains and no holder with a covering conferral scope exists.
2. **Writes a closing note**: what failed, which grants fell, what was relied on. It is kept **beside** the old record as a document, not recorded as an act in the old project, which has no remaining authority to record acts. The old record is not edited.
3. **Establishes a new project** (template 1), by Marcus, with a boundary that names the old project and states this is a different project with a different authority chain. Root grants name Marcus, Dana, and Lena, with two conferral holders this time, and an independent holder for each gate expected soon.
4. **Imports prior work as prior work** (template 26):
   - Claim C-1 with evidence E-1 to E-4: used as **evidence through its underlying sources** (S-1 to S-4). The team **rebuilds the evidence records in the new project** citing the sources, not "the old gate accepted this".
   - The old Discovery acceptance: **prior acceptance status in the new project: none.** The item is not standing here. A fresh act by an AUTH-G holder, over the accepted set here, is needed.
   - Lena's unresolved challenge Ch-1: **brought across as a visible item**. The support is not imported without the opposition.
   - Priya and research-agent-1 **remain producers** of what they authored. Marcus can accept the imported items only if he produced none of them.
   - **Dependencies being reconsidered:** the willingness-to-pay inference and the differentiation claim. **Relied on as imported:** the problem-existence evidence, because its sources are directly citable.
5. **Records the issue** (template 28): carry-over semantics are undefined by the protocol, and this project's treatment is practice. Routed to the MOD-W Moderator through the usual route. No claim is made that the carry-over is accepted.

### What this shows

- A cascade can be **seen before it happens**, and avoided, if grants are reviewed.
- **Recovery is by a new project.** It makes the boundary explicit and does not inherit acceptance.
- **Carry-over stays undefined** at the protocol level, and the project says so.
- **Nothing was patched.** No second root was recorded in the old project and no old acceptance was treated as alive.

---

## Change Notes

| Date | Version | Change | Reason |
| --- | --- | --- | --- |
| 2026-10-04 | 0.1 | Initial worked examples (WE-1 to WE-8), all hypothetical methodology examples | STEP-06 Development Team work product; provides inputs for STEP-07 without being pilot results |
| 2026-10-04 | 0.2 | Metadata and status aligned to the STEP-06 v0.2 package. The worked examples are first-version content (WE-1 to WE-8); no example text was changed. | Tech Lead finding TLR6-01 (non-blocking version/status inconsistency) |

MOD-W v5.0.1
