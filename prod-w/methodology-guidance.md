---
artifact:
  type: methodology-guidance
  id: PROD-W-MG
  version: 0.2
  created: 2026-10-04
  updated: 2026-10-04
  status: Draft - Development Team work product for STEP-06. Not reviewed. Not accepted.
  produced_by: Development Team
  produced_under: STEP-06
source:
  step: mod-w/step-06.md
  setup_approval: mod-w/reviews/MODERATOR-REVIEW-STEP-06-SETUP.md
  product_definition: mod-w/product.md
  architecture: mod-w/architecture.md
  domain_language: mod-w/domain-language.md
  roadmap: mod-w/roadmap.md
  protocol_semantics: prod-w/protocol-semantics.md
  evidence_knowledge_model: prod-w/evidence-knowledge-model.md
  gate_challenge_revalidation_semantics: prod-w/gate-challenge-revalidation-semantics.md
  rule_judgment_boundary: prod-w/rule-judgment-boundary.md
  representation_options: prod-w/representation-options.md
companions:
  role_charters: prod-w/role-charters.md
  templates: prod-w/templates.md
  worked_examples: prod-w/worked-examples.md
context:
  project: prod-w-dev
  governed_by: MOD-W v5.0.1
---

# PROD-W Methodology Guidance

**Product:** PROD-W - Moderated AI-Assisted Product Development Workflow
**Artifact:** Human methodology guidance for running a PROD-W-governed product-development effort
**Produced under:** STEP-06
**Status:** Draft v0.2. Development Team work product. **Not reviewed. Not accepted.** Final acceptance is pending Tech Lead review (3a), QA (3b), Product Owner sign-off (3c), and MOD-W Moderator acceptance (4a), unless any of 3a to 3c is explicitly waived and recorded.

---

## 1. Purpose and Standing

### 1.1 What this guide is

This guide tells a product team how to practice PROD-W: how to set up a project, assign roles, collect evidence, challenge claims, run gates, handle disagreement, record exceptions, and recover when authority is lost. It is written for people doing the work, with the accepted protocol cited where a statement rests on it.

### 1.2 This is guidance, not protocol revision

**The accepted protocol artifacts define what is valid. This guide defines nothing that is valid or invalid.**

- It does not revise STEP-01 to STEP-05 (`protocol-semantics.md`, `evidence-knowledge-model.md`, `gate-challenge-revalidation-semantics.md`, `rule-judgment-boundary.md`, `representation-options.md`) or any accepted MOD-W artifact.
- If this guide and an accepted artifact disagree, **the accepted artifact governs and this guide is wrong.** Report the disagreement (template 28).
- Where this guide says "must" about protocol, it cites the rule. Where it says "should", "recommended", or "practice", it is offering a project-level habit that a project may adopt, tighten, or replace. **A project may be stricter than this guide. It may never be weaker than the protocol.**
- This guide does not decide any question the accepted artifacts routed elsewhere. It records, in §18, where those questions went.

### 1.3 What this guide does not do

- It selects no schema, validator, workflow engine, lifecycle graph, serialized state vocabulary, storage model, CLI, database, transport, prompt format, agent harness, or runtime integration.
- It does not run the STEP-07 pilot. Its examples (`prod-w/worked-examples.md`) are methodology examples with invented facts. They are not pilot results and prove nothing about whether the method works.
- It does not prepare the STEP-09 publication package.
- It assigns no numeric evidence strength, sufficiency score, weight, rank, or confidence percentage, and it tells projects not to (EKR-19; BDR-14).
- It does not claim that any record, schema, signature, or tool proves a human acted (§9).

### 1.4 How to read the citations

**Short names.** PS = `prod-w/protocol-semantics.md`. EK = `prod-w/evidence-knowledge-model.md`. GC = `prod-w/gate-challenge-revalidation-semantics.md`. RJ = `prod-w/rule-judgment-boundary.md`. RO = `prod-w/representation-options.md`. Rule IDs (PR-, EKR-, GCR-, CRC-, BDR-, HJC-, TRG-, ACT-) are each unique to one artifact. A section number always carries a short name ("GC §9.2") because the artifacts reuse section numbers.

**Basis labels.** Tables in this guide mark each line either **Protocol (ID)**, meaning an accepted rule says so, or **Practice**, meaning this guide suggests it and no accepted rule requires it. A reviewer checking for accidental new rules should find every "must" under a Protocol label.

### 1.5 Reading coverage

The accepted inputs total about 1.2 MB, and `rule-judgment-boundary.md` alone is about 528 KB. This guide was produced by reading the sections that carry practice-relevant semantics and extracting from others. The coverage statement is in §20.3 so a reviewer can see which statements rest on a full reading and which on extraction.

---

## 2. Operating Principles

1. **Record the kind of thing before arguing over it.** Claim, evidence, counter-evidence, negative finding, assumption, hypothesis, inference, decision, recommendation, challenge, advisory finding, and formal-check result are different kinds of record. Collapsing them is a protocol-level failure (EKR-01).
2. **Authority is explicit.** A title, byline, seniority, tool, model, or work assignment is not an authority grant (PR-01).
3. **Independence is by identity.** A second role label, a different tool, a different model configuration, or the passage of time does not make a person independent of themselves (PR-17, PR-27).
4. **Acceptance is sufficiency for a scope, not truth** (PR-12). A gate that passes has not proved anything. It records that an authorized, independent human judged the basis sufficient for a stated progression.
5. **Evidence and judgment stay separate.** A fully populated evidence item may be irrelevant. Presence never implies sufficiency (EKR-19).
6. **Opposition stays visible.** Counter-evidence, challenges, and unresolved disagreement are recorded with the same formality as support. Nothing resolves them except a recorded act (GCR-41).
7. **Time acts on nothing.** Silence, elapsed time, and absence of objection never accept, close, or resolve anything (PR-13; GCR-67).
8. **Small-team limits are real.** When independence cannot be met, record an authority gap. Do not manufacture independence (GC §8.6).
9. **A check is not a gate.** A passing check, a complete record, and a polite review are not acceptance (PR-13, PR-14, BDR-14).

---

## 3. Orientation

This section helps a reader hold the whole method in mind. It is **non-normative** and is **not a lifecycle**. PROD-W names no states and no transitions, and a single status for an item would hide that one item can be accepted, contested, exposed, and superseded at once (RO §12.5). It is a table of the **acts** you will meet and a card of **questions** you ask of an item, not a diagram of order.

### 3.1 The acts, grouped

| Group | Act | Who may do it (authority class) | Independence needed? | Direction |
| --- | --- | --- | --- | --- |
| Producing | Create claim (ACT-01); attach evidence or counter-evidence (ACT-02); record assumption, hypothesis, inference | AUTH-P | No for the act. Source independence is a separate judgment | Neutral |
| Producing | Revise, withdraw, or supersede own item | The item's producer | No | Withdrawing or retiring own item is conservative. Revising a Tier 2 dependent closes a requirement only as producer-addressed |
| Opposing | Challenge (ACT-03) | AUTH-A | Only an independent challenger satisfies an independent-challenge requirement | Conservative |
| Opposing | Request revalidation (ACT-06) | AUTH-A, AUTH-V, or AUTH-G | No | Conservative |
| Opposing | Escalate | AUTH-A, AUTH-P, AUTH-V, or AUTH-G | No | Conservative. Resolves nothing |
| Checking | Verify formal criteria (ACT-04); record a formal-check result | AUTH-V (a result may be recorded as advisory by anyone) | A required check needs a verifier who produced nothing verified (GCR-10) | Neutral. Never acceptance |
| Determining | Accept a gate (ACT-05); record a consequential decision (ACT-07); validate a hypothesis; authorize conditional progression; grant an exception; reaffirm; confirm a correction; authority-close a challenge; accept as residual | AUTH-G for the scope, human only | **Required** over the accepted set | **Favorable.** A producer of the set may not perform these (GCR-05) |
| Determining | Refuse; defer; revoke a conditional progression authorization; retire a dependent; invalidate | AUTH-G for the scope | Not required. A producer of the set may perform conservative acts (GCR-05) | Conservative |
| Authority | Establishing act; confer, narrow, revoke a grant | Establishing identity (once). Human holding AUTH-G with a covering conferral scope | Conflicted conferral is flagged (CRC-64), self-conferral is invalid (CRC-62) | Neutral |

### 3.2 The reader's question card

To understand an item, ask these questions of the record. The answers are **read from the record**. They are not stored values and not statuses (EKR-02).

1. Who produced it, and in what configuration? Who else touched it?
2. What does it rest on? Does the chain end in evidence, or only in assumptions (assumption-rooted)?
3. Is it contested: is there a challenge or a contradicting item against it, and in what condition?
4. Is it exposed: does it depend on something contested, or something with an open trigger or requirement?
5. Is it relied on under assumption, or while a requirement is open?
6. Does it carry an open revalidation requirement? Is it recorded as current?
7. Has it been accepted? By whom, under which grant, for what scope, on what accepted set? With an exception? As residual, with what unresolved matters named?
8. Has it been superseded, withdrawn, retired, or invalidated?
9. Which view am I looking at, and what point in the record does it show? A view that disagrees with the record is wrong (RO §12.4, VI-8).

**RQ-10 at the practice level.** Projects should prefer the card (several facets) to one summary status, because accepted semantics produce several simultaneous conditions and validity does not depend on a prior node (RO §12.5). Whether readers actually find the card helpful, and whether an act-kind table like §3.1 helps them, is evidence for STEP-07 to gather. This guide selects no state names.

---

## 4. Project Establishment and Root-Grant Practice (DM-03; RQ-03, RQ-04, RQ-17)

### 4.1 What the protocol fixes, and what this section does not touch

**Protocol (D10; CRC-61, CRC-62).** A project has exactly one establishing act, recorded by an identified human, preceding every other recorded act. Root grants are the grants that act records, and only those. A root grant has no conferrer. Every other grant chains acyclically to a root. A later act marked "establishing" or "root" is not a second root. The establishing identity may be a root grantee only in the establishing act's own grants. Self-conferral is invalid for every later grant. There is no path to a second establishing act and no break-glass.

**This guide does not modify D10.** It describes how a team carries the establishing act out well and what to do when it was done badly.

### 4.2 Before the establishing act

| Step | Practice |
| --- | --- |
| 1. Agree the boundary | Write what the project governs and what it does not, including neighboring work and any earlier project. The boundary is what makes a later "new project" visible. |
| 2. Decide the people | List the human identities that will hold authority and the AI agents or other actors that will produce. Decide the identity names now. A role label is not an identity. |
| 3. Decide the gates you will need soon | The authority to accept them must exist already, because a root grant can be added later only by a conferrer, and the establishing identity cannot be its own conferrer. |
| 4. Decide who must be named | For each of acceptance, gate definition, validation, and conferral, decide which scope will exist and who holds it (§5). |
| 5. Decide the practice statements | Complete the practice statements in template 1 (what "recorded" means, where records live, who can write, how order is established, how backdating is handled, how actor kind is designated). |
| 6. Keep the record location free of project acts | Anything already in the record location that is a project act precedes the establishing act. Scaffolding that is not a project act (blank templates, this guide) is fine. If a project act exists first, **the project has no valid establishing act** (RJ §10.6). Start a new project. |

### 4.3 The establishing act (template 1)

The establishing act records, in one act:

- the establishing identity (a human) and the statement that this is the establishing act;
- the project name and boundary;
- every root grant, each with grantee, authority class, scope, and the establishing act as granting authority (PR-02: a grant missing any element is not a grant);
- the initial role-position appointments, each with the grants it relies on;
- the practice statements.

**Root-grant checklist.**

| Question | Why | Basis |
| --- | --- | --- |
| Is every grant the establishing identity will ever need for itself in this act? | Anything later requires a covering conferrer who is not conflicted, and the establishing identity cannot confer to itself. For a sole root grantee, no such conferrer may exist | Protocol (CRC-62; D10) |
| Is there a conferral scope, and who holds it? | Without a conferral scope held by a human, no later grant can be made. Conferral is a scope of AUTH-G (RJ §10.2.1) | Protocol |
| Is a gate-definition scope granted? | Gates are defined before use (GCR-12) by a human holding it | Protocol (GC §5.2) |
| Is a validation scope granted for the hypothesis families you expect? | Validation is an AUTH-G act with narrow scope available (GCR-64) | Protocol |
| Is **at least one human other than the main producer** named with AUTH-G for the first consequential gate? | If the only AUTH-G holder is the main producer, the first gate is an authority gap. Root grants are not flagged as conflicted conferral (D10), so naming them here is the cleanest route. It is caught only by challenge if it is a proxy | Practice (the gap is Protocol: GC §8.6) |
| Are scopes stated by reference (an explicit list of gates and item classes) rather than by description? | A containment decision is mechanical only where scopes refer to identifiers in a recorded vocabulary. Description-based scope is a judgment (HJC-25) | Practice (RO §9.4) |
| Are grants no wider than needed? | Narrow grants make human acceptance cheap to assign and limit what a later revocation strands | Practice (GC §12.2) |
| Is the basis for the establishing identity's standing stated? | Root legitimacy is not checked (HJC-22). A stated basis is an assertion that others can challenge | Practice |

**Disclose the proxy limit.** Authority placed in the establishing act is not flagged as conflicted conferral even where the grantee later accepts the establishing identity's work (D10; RJ §10.6). If you name a friend or subordinate as the independent acceptor, a reviewer cannot tell from the grant alone whether that is independence or a proxy. Say in the act why the grantee is independent, so the claim is on the record and can be challenged.

### 4.4 If the establishing act was done badly

| Situation | Consequence | Practice |
| --- | --- | --- |
| The founder omitted a self-grant | It cannot be added later by the founder. It needs a covering conferrer who is not the founder and not downstream of founder-conferred authority | If no such conferrer exists, the grant is unobtainable. Decide whether the project can proceed without it or must restart as a new project (§16.2) |
| A project act precedes the establishing act | The project has no valid establishing act (RJ §10.6) | Start a new project and carry work over as imported prior work (template 26) |
| A second "establishing act" was recorded later | It is not a second root. Its grants are ordinary conferrals and are invalid unless the conferrer's conferral scope covers them (RJ §10.2.2) | Treat the later act as an ordinary conferral and record whether it is valid under the chain. Do not rely on it as a root |
| All root grants were revoked or renounced | No valid chain can exist again (D10) | Recovery is by a new project (§16.2) |

### 4.5 What "recorded" means (RQ-04)

The protocol keeps "recorded" open between branches and local drafts, and record order is a representation question (RO §10.4, RQ-04). The practice below is a way to avoid a *hidden* decision, not a rule.

| Situation | Practice |
| --- | --- |
| Private draft | Label it not yet recorded. It may be worked on and shared for comment. Nothing may rely on it in a gate, decision, or commitment |
| Shared project record | An item is **recorded** when an identified actor places it in the project's agreed record location, in that location's order. State in the establishment record what the location is |
| Branch or alternate line | State whether it is advisory, proposed, or the active project record. Only the active line counts as the project record. Merging a branch records its contents from the merge. It does not backdate their effect |
| Concurrent writers | If two acts cannot be put in order, treat the order between them as unresolved, not as "before". The establishing act must be unambiguously first |
| Correcting order after the fact | Record the correction as a visible act. Do not backdate its effect (GCR-47) |
| Imported prior work | Record as source material or carry-over candidate (template 26). Prior acceptance does not transfer |

**Record order and time.** Order should not rest on the recorder's own assertion alone, because a timestamp the actor writes can be written backwards and "not backdated" then cannot be checked (RO §10.4, O2). Practice: say in the establishment record what assigns position (for example, an order assigned by the record location rather than by the author), and say how out-of-order entries are handled. Selecting a store is not this guide's job (NG-2).

### 4.6 Write control (RQ-17)

Whether a grant or revocation recorded in a file that the grantee or the revoked holder can edit is *safely* recorded is a tamper-locality property of the environment, not of the representation (RO §5, criterion RC-10; RQ-17). Practice:

- State in the establishment record who can write to the record location and who can edit whose records.
- **Edit your own records only.** A change to another actor's record is made as a new record by the changer (a challenge, a revision, a supersession), never in place. Never rewrite history.
- Keep authority records (grants, revocations, the establishing act) where the people they bind cannot quietly alter them. Where the team cannot separate that (one person, or an agent that can write to the same store as its operator), **say so** in the establishment record. The limit is then a known weak point, not a hidden one.
- Where a second person exists, give them a read copy of authority records and a way to notice divergence. The mechanism is the project's choice.
- None of this makes a record true or proves who wrote it (§9).

### 4.7 Scope vocabulary and containment (RQ-03)

If scopes are references to a recorded vocabulary and a containment relation says one scope covers another, the relation is itself an assertion, and a wider relation widens every grant that refers to it. The protocol does not say who may record it (RQ-03, routed to the MOD-W Moderator as a protocol question). Practice until it is answered:

- Prefer an explicit list of scopes with **no** containment relation.
- If a containment relation is used, record it in the establishing act, or record it afterward only as an act by a human holding a conferral scope covering the *widest* scope the relation could reach. Treat adding or widening a containment relation as a conferral.
- Review containment relations in every grant review (template 27).
- If scopes are stated by description, say plainly that containment is a judgment (HJC-25) and decide it case by case, with the decider named.

---

## 5. Role Positions and Authority Scopes (DM-02)

Role charters are in `prod-w/role-charters.md`. This section gives the operating summary.

### 5.1 The five things kept apart

| Thing | Rule of thumb |
| --- | --- |
| Actor identity | Ask "who is this?" Answer with the identity, never the label |
| Role label | A convenience name. Confers nothing (PR-03) |
| Authority grant | Ask "where did they get the right?" Answer with the grant and its chain to the establishing act |
| Participation capacity | Ask "what did they do to this item?" One capacity per act (PR-08) |
| Work assignment | Provenance. Confers no authority. Makes the assigner a producer only if they supplied the substance or adopted the item (GCR-08) |

Appointment to a role position that carries grants **is a conferral**. Appointment to a position with no grants is not. Work assignment is neither (RJ §10.2.5).

### 5.2 Illustrative positions

| Position | Typical grants (illustrative, PS §4.7) | Standing |
| --- | --- | --- |
| Product Moderator | AUTH-G for named gates; often AUTH-A | Some human role position must hold AUTH-G for each consequential gate. That is the only role requirement in PROD-W |
| Product Owner / Researcher | AUTH-P, AUTH-A | Illustrative |
| Product Architect / Tech Lead | AUTH-P, AUTH-A | Illustrative |
| Implementation Team | AUTH-P | Illustrative |
| QA / Validator | AUTH-V, AUTH-A | Illustrative |
| External evaluator | AUTH-A, sometimes AUTH-V. Never AUTH-G by default (PR-22) | Illustrative |
| Challenge function | AUTH-A | **Not a protocol role.** Product Skeptic and similar positions are open research hypotheses (PS §4.7). A project may compose such a position from AUTH-A and call it a project convention |

### 5.3 Who holds the scopes (DM-02)

Scopes to decide at establishment, with suggestions, are in `role-charters.md` §5. In brief: **gate acceptance** goes to someone who is not the main producer of the gate's basis; **gate definition** to a human unlikely to produce the basis; **validation** is granted narrowly to the person closest to a dimension who did not produce its evidence; **conferral** is kept as small as the team can bear and held where its use is least conflicted; **closure authority** is spread across at least two holders where possible so one conflict does not create a gap.

---

## 6. Independence Practice for Teams of One or Two (DM-04)

### 6.1 What independence means in practice

Independence is evaluated between **actor identities** over the **accepted set**, not over the decision record's text. An acceptor must be a producer of no member of the accepted set: the subject, the material basis followed transitively, the materiality and dependency designations (including the non-material ones), the challenge responses relied on, and the formal-check records relied on (GCR-01, GCR-03). No contribution is too small to count (GCR-03).

What is **not** in the accepted set, and therefore does not disqualify a would-be acceptor: the acceptor's own acceptance-act content, the opposition (challenges and contradicting items recorded against the basis), background items with a standing non-material designation, upstream acceptances as acts, and the gate definition (GC §4.3). So an independent human **may challenge and then accept**. A challenger is not thereby a producer of the accepted set.

### 6.2 The substance test (practice)

Identity is checked by the record. **Substance is declared and left open to challenge** (RJ §10.4; GCR-09; HJC-12). Before relying on someone as independent, ask:

1. Did they, or an identity they control, create, edit, restate, summarize, rename, or adopt any member?
2. Did they supply the conclusion or key content, even where someone or something else typed it? An agent used as a typist for a human's conclusions leaves the human a producer (GC §4.6).
3. Did they assign any member to someone else, and with what instructions?
4. Did they record a designation that shaped the basis?
5. Did they perform a verification you now rely on?
6. Did they confer a grant a favorable act relies on?
7. Is there a relationship a reasonable reviewer would want to know about?
8. Is this really two people, or one person with two accounts?

Record the answers in the independence declaration (template 16). The declaration is an assertion. It can be challenged. It is never proof (GCR-09).

### 6.3 Work-assignment disclosure (practice)

Record every work assignment as it happens: who assigned what to whom, and whether the assigner specified conclusions. If an acceptor-to-be assigned work, they disclose it (GCR-09). A disputed producer attribution is treated against the disputed actor's own favorable acts until a gate authority holder independent of the item resolves it (GCR-07). So: **disclose early, because a late dispute costs the disputed actor the ability to accept.**

### 6.4 Teams by size (practice, built on GCR-03, GCR-05, GCR-07, GCR-08)

**A. One human plus AI agents.** The human establishes the project, holds the root grants, and is the producer of nearly everything.

| Can do and have it count | Can do but it does not count as independent | Cannot validly do |
| --- | --- | --- |
| Produce claims, evidence, assumptions, hypotheses, inferences. Record counter-evidence. Challenge (self-challenge, recorded, **not independent**, PR-19). Refuse, defer, escalate, request revalidation, withdraw or retire own items (conservative acts, GCR-05). Revise own items | Agent review of the human's work (PR-27, PR-28). A second agent configuration agreeing (PR-20). Self-verification (GCR-10) | Accept a gate over their own accepted set. Authorize conditional progression. Grant an exception. Reaffirm. Close a challenge in their own favor, including resolving a challenge they raised against their own item (GCR-05; RJ §10.6). Waive anything. Cure an authority gap by acting |

A one-human project can still produce a complete, honest record, a prepared basis, and **recommendations** (a recommendation by someone without the needed authority is a recommendation, ACT-07). It cannot produce a valid consequential acceptance of its own work.

**Cures, in the order a one-human team should consider them.**

1. **Name an independent human in the establishing act** with AUTH-G for the gates you expect. They must be a real individual human, not a team or an agent (GCR-08). They may challenge and accept, but they must not edit the items, supply the conclusions, or perform verifications they rely on. Say why they are independent (§4.3).
2. Name that human **later**, through a conferral by someone who holds a covering conferral scope. If that conferrer is the only producer, the conferral is **flagged and escalation-eligible** (CRC-64), not invalid, and the flag stays on every favorable act that relies on it. This is possible but weaker. Record the flag and expect it to be challenged.
3. **Re-base** the subject on independent items, visibly.
4. **Stop at the gate.** The protocol permits it (GC §8.6). A gate that has no valid acceptor has no valid progression.

Two cures do not exist: acceptance by the conflicted human under another label, and an exception (an exception cannot cover independence, GCR-06).

**B. Two humans plus AI agents (A and B).** The strongest small arrangement is mirror-image: A produces and B accepts A's work; B produces and A accepts B's work. Conditions that keep it clean:

- **Producer-of-record discipline.** Record who produced each item at the time. Late disputes cost the disputed person their acts (GCR-07).
- **Reviewers challenge. They do not edit.** If B edits A's draft or suggests wording that A adopts, B may have supplied substance and become a producer, and B can no longer accept it. Comment as a challenge or an advisory finding, and let the producer revise.
- **Co-produced items need a third.** An item both A and B produced has no acceptor in the team (PR-21). Avoid joint authorship of anything that will reach a gate, or accept that it is an authority gap.
- **Designations count.** Whoever records "non-material" for an item keeps it out of the accepted set and becomes a producer of the designation (GC §4.3).
- **Verifications count.** If B relies on a check, B must not have run it (CRC-07).
- **Agents inherit their assigner's problems.** If A directs an agent to draft and supplies the conclusion, A is a producer. If B then accepts, B must be independent of A's and the agent's output. Independence is fine here: B is not a producer. Make sure B did not give the agent the conclusion.
- **Conferral conflict.** If A holds the only conferral scope, any grant to B that a favorable act by B relies on is flagged if A produced the set B accepts. Put B in the root grants.

**C. Three or more humans.** Separate producers from at least two AUTH-G holders with disjoint production sets and a challenge function. Authority gaps remain possible when every holder contributed to a basis. They can be prevented by rotating who produces what, not by relabeling.

### 6.5 AI agents and external evaluators in a small team

- Agents are producers. The accountable actor position is unchanged when model, effort, harness, tooling, or instructions change (PR-27). Name the actor position, not the model.
- **Controlled re-execution** (the same role, same inputs, different configuration) is valuable and should be done. Use it to find defects, record advisory findings and revisions, and escalate. It never produces independence, verification for gate purposes, or acceptance (PS §6.5; PR-28). The test: **self-review feeds production and escalation. It never feeds acceptance.**
- Several agents agreeing is agreement, not corroboration. Corroboration needs separately present, attributable source evidence (EKR-17).
- An external evaluator is advisory by default. It may supply the existence of a required independent challenge (CRC-12). Whether it is substantively independent is a judgment. Same-model-family reviewers share blind spots; record the limit.
- Whether a team or an agent fleet may be a single actor identity is open (PS-OQ-06). A collective may be recorded as a producer only with recorded membership, expands to its members for independence, and can never hold AUTH-G (GCR-08). Practice: record individuals.

---

## 7. Evidence Guidance (DM-01; RQ-02)

### 7.1 What kind of thing is it? (the distinctions)

Classify before you argue. Every item has exactly one class at a time, and reclassification is a recorded act (EKR-01).

| Kind | Practice question | Distinguishing test | Common mistake |
| --- | --- | --- | --- |
| **Claim** | What is asserted, and could it matter? | Can it be supported, contradicted, or qualified? Creating one asserts nothing about validity | Treating a confident statement as evidence for itself (EKR-13) |
| **Material claim** | Would a change in its standing plausibly change a decision, a promise, or an investment? | Materiality is a recorded human judgment, not a class | Treating every note as material, or marking material claims non-material to keep them out of the accepted set |
| **Evidence** | Can a reader follow it to a source that is traceable independently of anyone's assertion about the target? | A source that is not just someone asserting the conclusion | An agent's output with no followable source (that is a claim, inference, or advisory finding) |
| **Counter-evidence** | Does the same kind of item, with the same elements, weaken or contradict the target? | Polarity is per target, not a property of the item | Filing it as "the negative one" in a notes appendix |
| **Negative finding** | Does it record the *result of an attempt*, with the attempt described? | An attempt record: what, where, when, how, with what reach | "We found nothing" with no record of what was searched |
| **Assumption** | Is something being leaned on without having been established? | Reliance without establishment | Treating it as fact because it has been repeated |
| **Hypothesis** | Does it state what would count against it? | Recorded validation criteria. Without them it is an assumption (EKR-21) | An untestable "hypothesis" hiding an assumption under a respectable name |
| **Inference** | Does it say "this implies that" and cite what it was drawn from? | It cites, and its chain reaches evidence or an assumption | Presenting it as observed fact, or attaching it in place of evidence |
| **Decision** | Did an actor with the required authority commit, on a stated basis? | Authority basis recorded | Calling a recommendation a decision |
| **Recommendation** | Is this a proposal by someone without the needed AUTH-G? | Absence of the authority | Hiding it as a decision |
| **Advisory finding** | Would treating it as a determination exceed its producer's authority? | Producer lacks the authority for the matter | Recording an evaluator's conclusion as acceptance |
| **Evaluative claim** | Is the content a value judgment? | "Desirable", "good", "worth it" | Presenting it as observation or as established by evidence alone |

### 7.2 Evidence collection procedure

This is a practice sequence for each question the project needs evidence on.

1. **State the target.** Which claim, hypothesis, or decision is this evidence for or against? An item with no target is evidence for nothing, though it stays visible (EK §7.2).
2. **Plan the search, including the opposite.** Before searching, write what would support the target, what would weaken it, and where each would be found. A search designed only to find support is selective by construction (EKR-18).
3. **Record the attempt before you read results** (template 7). What was searched, where, when, how, and what it could and could not have found. An unrecorded attempt cannot support an absence inference (EK §7.5).
4. **Capture the source** (template 4) and give it a stable source reference at first use.
5. **Record the evidence item** (template 6): what the source says (marked as a quote or as a summary), how it was obtained, observation time, basis kind, evaluation dimension, target, polarity, limitations, lineage.
6. **Record counter-evidence the same way**, the same day, whether or not it helps. An actor that has produced or obtained information contradicting an item it relies on **must** record it as counter-evidence (EKR-18).
7. **Keep evidence and interpretation apart.** Interpretation goes in an inference (template 8) that cites the evidence. The evidence item carries no conclusion.
8. **Record hypothesis test results either way** against criteria recorded beforehand (EKR-18; template 10).
9. **Do not edit validation criteria after results exist.** That is a supersession of the hypothesis, never a correction (GCR-65).
10. **Say what you could not find.** A visible absence statement makes an absence visible. It does not satisfy a gate slot (GC §5.2).

**Agents that retrieve.** An agent that retrieves a source and reports it can produce evidence *through the source*. Attribute the evidence to the source's real origin, and record the retrieval and the agent's configuration as the producer's act (EK §7.1). An agent that generates claims from its own training or reasoning, with no source a reader can follow, has produced a claim, inference, or advisory finding, however fluent.

**Agreement is not evidence.** If three agents conclude X, the record needs the source each rests on. If they rest on one source, that is one source (EKR-17; INV-11).

**Selective recording.** The most damaging counter-evidence is the kind never attached. No tool can detect it. Practice: each producer states at handoff, "I know of no unrecorded contradicting information I hold," and any AUTH-A holder attaches counter-evidence they hold.

### 7.3 Assumptions and hypotheses in practice

- **Record every assumption** you are leaning on, material or not (EKR-22). The cheapest moment is when you notice yourself writing "obviously".
- **Turn assumptions into hypotheses when you can say what would count against them.** Record the criteria first (EKR-21).
- **Reliance under assumption.** Ordinary production work that relies on an unvalidated item records the reliance on the dependency link. That needs no gate authority's authorization (GC §9.2). The moment the work is cited in a gate acceptance, a consequential decision, or a consequential commitment, an authorization is needed (CRC-19; §12.5, §15).
- **Assumption-rooted items.** If every support chain beneath a basis item ends only in assumptions or unvalidated hypotheses, identify it as assumption-rooted at any gate that uses it (GCR-66).
- **Validation is an acceptance.** Only a human holding AUTH-G for the scope, independent over the validation's accepted set, validates. Accumulated support, agent agreement, time, absence of objection, completion of dependent work, and a verification never validate (EKR-24).

### 7.4 Negative findings in practice

Record the attempt and the inference separately. "We searched the three trade directories and two review sites for tools that reconcile scope changes before invoicing, between these dates, with these terms, and found none" is an attempt record. "Therefore no competitor exists" is an inference that cites it and can be challenged. State the reach: who was not asked and where was not searched. A search that found nothing is informative only in proportion to what it could have found.

### 7.5 Categories and thresholds (DM-01)

**Categories are prompts for required coverage. They are not a taxonomy and not scores** (EK §7.3; EKR-19). The protocol says gates specify required evidence categories where applicable, and leaves the contents to the project's product category. The three dimensions below are illustrative; add or drop to fit.

**Evidence basis kind** (how the information came to exist): direct observation or measurement; an artifact, record, or data set; testimony recorded as testimony; an experiment or test result; a search result including a negative one; a computation over other evidence, with lineage.

**Evaluation dimension** (what it bears on): problem; customer; commercial viability; technical feasibility; differentiation. Keep technical feasibility and commercial viability separate. Evidence for one is not evidence for the other (WD-3).

**Illustrative gate-slot contents by product category.** A gate definition chooses slots for the opportunity at hand. The rows below show what a team might ask for. They are examples of *coverage*, not minimums and not sufficiency tests.

| Product category | Slots a project might require (target: kinds and expectations) |
| --- | --- |
| Workflow or business tool for a professional segment | Problem existence and frequency: direct observation or recorded testimony from more than one organization, plus an artifact of the current workflow. Switching cost: testimony and the artifact. Willingness to pay: testimony from the person who holds the budget, recorded as testimony, plus a counter-evidence search for free or incumbent alternatives. Differentiation: a recorded comparison of named alternatives |
| Consumer app | Problem existence: observation or usage data from users outside the team's circle. Retention: an experiment or test result, with limitations. Acquisition channel: a test result or an artifact. Counter-evidence search for failed analogs |
| Internal tool | Problem: observation of the current process and the people who do it. Adoption: testimony from the people expected to change. Cost to build and serve: computation with lineage. Counter-evidence: why earlier attempts stalled |
| Regulated domain (health, finance, safety) | The above, plus compliance or policy evidence from the governing text itself (an artifact, with version and date), and a record of who with standing was consulted. Technical feasibility evidence separate from compliance evidence |
| AI-assisted product or agent feature | Problem and customer as above. Technical feasibility: test results on realistic inputs with the configuration recorded, including failures. A negative-finding attempt record for known failure modes. Cost to serve |

**Writing thresholds in natural language.** A threshold is a sentence a person can check by reading the record. Useful patterns:

| Pattern | Example wording |
| --- | --- |
| Coverage | "Evidence on willingness to pay exists from a budget holder as well as from a user." |
| Source independence | "The two customer evidence items do not rest on the same source reference and neither is derived from the other." |
| Counter-evidence reach | "A recorded attempt searched for existing alternatives in at least the named channels, and its reach is stated." |
| Recency | "Observation of the current workflow is dated no earlier than the stated review point." (Checked once, at the act. It is not a clock.) |
| Negative finding expected | "A negative-finding record exists for the claim that no alternative addresses scope reconciliation." |
| Unresolved-assumption treatment | "Every assumption relied on for the commercial-viability slot is identified, and each is covered by a conditional progression authorization or is out of the basis." |
| Challenge criterion | "The differentiation claim has been challenged by an actor who produced none of its basis." |

**Avoid:** evidence scores, confidence percentages, "strong signal", "likely", and "high confidence" without stating source and limits; "three agents agree" as validation; counting items as if quantity were sufficiency (a number of items is a presence condition at most, and the acceptor still judges adequacy); treating a polished narrative as evidence; a threshold that cannot be checked by reading the record. A count may appear in a gate definition only as a presence condition. If it appears, say it establishes presence, not sufficiency.

**What the acceptor still judges.** Presence and designation can be checked from the record. Relevance, adequacy, and sufficiency are contextual judgments reserved to the AUTH-G holder (GCR-14; HJC-01, HJC-02). Write the thresholds so the checkable part is checkable and the judgment part is named as a judgment.

### 7.6 Evaluative claims and the basis-presentation designation (RQ-02)

"This will be useful" is a value judgment. If it is presented as established by evidence alone, or as observed fact, it hides a judgment (EKR-28). The protocol check (CRC-45) can tell whether the record carries an evaluative designation and a stated presentation. Unless someone states how a claim is presented, one limb of that check stays **unresolved** and protection rests on challenge. STEP-05 proposed a *basis-presentation designation* as the record element, and whether to require it is a new rule that only the Moderator can make (RQ-01, RQ-02).

**Practice (this guide does not make it a rule).** A project that wants the protection can adopt it as a **stricter condition in its own gate definitions**: "every evaluative claim in the basis carries a basis-presentation designation." That is a project's legitimate stricter condition (GC §5.2), not a protocol requirement. Failing it leaves the gate requirement unsatisfied and needs an exception to accept against. A project that does not adopt it is still conforming and relies on challenge. Record the choice in the establishment record.

Also practice for everyone: when you write a claim that contains "should", "better", "desirable", "worth", say it is a value judgment, and keep it out of any evidence item.

---

## 8. Producing Configuration and Source Comparability (DM-05; RQ-07, RQ-08)

### 8.1 Producing configuration

**Protocol.** For any item or act produced by an AI actor, state the five facets: model, reasoning effort, harness, tooling, and instructions. Each is stated, or marked not applicable, or marked **not determinable** with the reason where known. Absence of any statement is **flagged**, and the act keeps its effect. A gate definition may require named facets, and then a shortfall is an unsatisfied gate requirement. Recording configuration confers no independence (CRC-39; PR-27). Sub-facet detail such as sampling parameters and token counts is not required (RJ §11.2).

**Practice conventions (DM-05).**

| Topic | Convention |
| --- | --- |
| Identity vs configuration | Name the actor position ("research-agent-1"). Never put a model name where an actor identity is required (PR-07) |
| Model | State it at the level the provider or operator exposes, with a version designation if one exists. If you only know "the hosted default", say that and mark the rest not determinable |
| Not determinable | Use it for a facet you truly cannot recover (a hosted tool that does not expose effort or harness). State the reason where known. It satisfies presence, stays visible, and is an input to the reader's weighing. Do not guess to fill a blank. Honest recording must not be punished harder than silence |
| What counts as instructions | Anything given to the actor that tells it what to do or how to behave: system or standing instructions, the task brief, a role charter in force, a named skill or instruction bundle, templates it was told to follow. A named instruction bundle is a kind of instructions and is covered when the statement resolves to what was given (RJ §11.2) |
| What does not count as instructions | The source material the actor was asked to work on. Record it as a source input (template 4). If the line is unclear for an input (a document that both informs and instructs), record it as both and say so |
| Tooling | The tools and data access the actor actually had. Include retrieval tools used for evidence |
| Granularity | Facet level is enough. If a gate needs finer, the gate definition says so (RJ §11.2 "Not required") |
| When it changes | A new configuration is a new producing configuration for a new action by the same accountable actor. Re-record it; do not create a new reviewer |

**Version-binding of instructions (RQ-08).** The instruction statement must resolve to what was in force at the act, **not to a later version** (RJ §11.2). A bare path to a file that someone can edit does not do that. Practice: choose and record one binding method per project that lets a reader recover the exact text later. Options a project may use (this guide selects none): a copy of the text recorded with the statement; a revision identifier of the instruction text; a content digest of the text; a dated immutable copy. Whatever you choose, say so in the establishment record, and apply it equally to a skill file used as instructions. If binding was not done, say "not bound" and why (template 11). A statement that cannot be bound is visible, flagged, and weighed by the reader. It is not a violation that voids the act (UAD4-11).

### 8.2 Re-execution and reviewer limits

When a role is re-run under another configuration, record the second run as a distinct action by the same accountable actor with its own configuration statement. State the reviewer limitation (for example, "same model family as the producer") on any review used to inform a gate. Review by Claude-family models of Claude-family output is not independent corroboration (PR-27, PR-28; RQ-16).

### 8.3 Source comparability (RQ-07)

**Protocol.** Evidence items that share an identified source must be identifiable as sharing it, and derived evidence names the items it derives from (EKR-11). Three articles citing one survey are one source. How two *descriptions* are determined to be the same source is not decided by any check; two descriptions that do not reference the same source record are not determined to be the same, and whether they are is a judgment. The lineage gap is flagged (RO §10.3; CRC-38).

**Practice convention.**

1. Keep a **source register** (template 4). Give each distinct source a stable project-local source reference at first use and **reuse it**. Two evidence items that cite the same source reference share a source.
2. Before creating a new reference, look for the same source. Compare owner or origin, title, edition or version, date, and link. A secondary report of a primary source is *not* the same source, but record the derived-from link.
3. Record the comparability judgment on the item (template 6): **same as** / **distinct from** / **unclear relative to**, with the reason.
4. **Treat "unclear" as one source for independence expectations** until someone resolves it. This is the conservative reading and is consistent with how the protocol treats pending determinations, but it is practice. A gate slot that expects source independence is then not met by two items whose sources are unclear.
5. Record what you know about lineage: syndicated content, citations of one dataset, reposted interviews, scraped copies, agent summaries of the same document.
6. Unrecorded lineage cannot be found by any check. If you later learn two items share a source, record it. That is a recorded event, and it can bear on gates that relied on their independence.

---

## 9. Actor-Kind Binding Practice (RQ-05)

**What the protocol can and cannot do (RO §9.5).** Four things are easily run together:

| Thing | What it is | Who can carry it |
| --- | --- | --- |
| Kind designation | A recorded statement that an identity is human, AI, evaluator, or automated | Any record. CRC-03 checks the recorded kind of an AUTH-G act against it |
| Attribution integrity | That the act recorded under an identity was written by or for that identity | No record family. A file-based record is self-assertable |
| Authentication | A binding between an act and a credential presented at the time | A mechanism outside the record |
| Human-presence assurance | That a human, not an agent holding the human's credential, performed the act | **Nothing.** No representation, schema, signature, or record can establish this |

**No claim in this guide, in the templates, or in later artifacts may say the protocol, a schema, a record, or a signature guarantees that a human acted.** The accurate statement is: *the record designates this actor as human and states the binding method used. Whether the designation is accurate is a judgment (HJC-21), challengeable by an AUTH-A actor and closed only by an independent human with authority.*

**Practice.** For consequential acts by an AUTH-G holder, record an actor-kind binding note (template 25). Choose none, one, or several of these **descriptive** categories, which this guide does not rank and makes none required (that would be a new rule, RQ-05):

- none stated;
- access-control placement only;
- a credential was presented;
- out-of-band confirmation by another identity;
- third-party attestation.

Practical habits that make the weak point more visible without claiming more than it delivers:

- For the first few consequential acts and for any act that changes authority (grants, revocations, exceptions), obtain an **out-of-band confirmation by a second identity** (the acceptor's own channel, different from the one the record was written in), and record who confirmed and how. State that the confirmer may be the same person and that the confirmation proves nothing about presence.
- Do not record credentials, keys, or secrets in the project record.
- Be especially careful in two directions. An agent presenting as a human to hold AUTH-G, and an agent acting through a human's credential or session, are both outside what any check can see.
- Wording for any outward claim: "records designate human-held authority and record the binding method used". Never "guarantees", "proves", or "verifies that a human".

Evidence on whether the weak point is exploitable and at what cost is for STEP-07 (F-5, F-2). Claim wording for publication is STEP-09's.

---

## 10. Challenge and Disagreement Practice

### 10.1 Raising a challenge

A valid challenge records challenger, target, target scope, and basis (GCR-23). Use template 12. If target or basis is missing it is recorded as invalid and has no effect, so state them. Targets include items, relationships (a materiality designation, a dependency link, a producer attribution, a correction designation), and determinations (an acceptance, an exception, an authorization, a closure, the validity of an act).

| What you are alleging | Typical target scope | Typical attached material |
| --- | --- | --- |
| Missing evidence | Sufficiency of a basis | A statement of the gap; a request to seek counter-evidence |
| Misclassification | Content / designation | The reason it belongs to another class |
| Weak inference | Content | The alternative interpretation |
| Authority defect | Validity of an act | The grant that should have been relied on |
| Independence defect | Independence or attribution | The producer record |
| Contradiction | Content | Sourced counter-evidence (attached as evidence) |
| Material omission | Omission from a basis | The omitted item |

A challenge is cheap by design. It produces **contestation** and **exposure** on direct material dependents, and **no requirement** by itself. Source-identified counter-evidence produces a requirement on direct material dependents. A bare contradicting claim or inference reaches that status only by grounding (P1), by an independent AUTH-G acceptance (P2), or by a request (P3) (GC §7.3, §7.4). If you want a requirement to arise and have no sourced counter-evidence, **file a request with a stated basis** (template 21).

### 10.2 Responding, closing, and what never closes

Any actor may respond (explanation, evidence, concession, dispute of standing, escalation). **A response never closes a challenge**, including one by the target's producer (GCR-25).

| Closure | By | Practice note |
| --- | --- | --- |
| Challenger resolution | The challenger, with a reason | Ends only that challenge's contribution. Another AUTH-A actor may adopt it again. A producer of the challenged set cannot validly resolve a challenge in the set's favor, even one they raised (GCR-05; RJ §10.6) |
| Authority closure | An AUTH-G holder independent of the challenged item's accepted set and not the author of a challenged determination | If none exists, it is an authority gap (§14) |
| Mootness by withdrawal | The target's producer withdraws the target with no successor | The challenge stays in history. Dependents receive a trigger (TRG-1) |

**Not closure:** elapsed time, silence, absence of objection, the producer's response, agent agreement, downstream work, a verification, or a supersession of the target. Supersession carries the challenge to the successor (GCR-28).

### 10.3 Unresolved is normal

An unresolved challenge does not block progression by itself (GCR-27). The protocol forces **treatment at the gate**: the decision record cites every challenge standing against the basis and states how it stood (§12.4). Disagreement ends only by challenger resolution, authority closure, concession with closure or carry-over, or resolution by decision. **No consensus is required.** A decision that picks one position records a sufficiency determination for a scope, not a finding of truth, and the unselected position stays recorded and can be reopened by a new trigger or challenge (GCR-36).

**Disagreement is not a failure of the method. False consensus is.**

### 10.4 Practice habits

- Challenge the **relationship** and the **designation** as readily as the item. A non-material designation on an item presumed material is the easiest place to hide support.
- A challenged non-material designation restores the presumption of materiality until an independent AUTH-G holder resolves it (GCR-34).
- When you concede a point, revise or withdraw the item **and** make sure the challenge is closed or carried. A concession alone is not a closure (GC §8.3).
- Do not delete anything. Withdrawal, supersession, and retirement leave the item recorded.

---

## 11. Formal Checks, Findings, and Decidability (DM-06, DM-08)

### 11.1 What a formal check is for

A formal check confirms that **defined, named criteria** were satisfied. It is bounded by those criteria. It is not a sufficiency judgment and never substitutes for acceptance (PR-14). No number or combination of satisfied checks is acceptance, validation, or progression (BDR-14). A gate whose every mechanical condition is satisfied has not thereby been accepted (PR-13).

A **formal-check result** records one application of a check: the rule or criteria applied, the evaluation point, the record elements examined (by reference), and what the result says (satisfied, violated, satisfied under exception, or unresolved). Those words are what a result may *say*. They are not a value set or a state vocabulary (BDR-11).

### 11.2 Content of a result (DM-08, general)

Use template 22. Practice for each result:

| Entry | Practice |
| --- | --- |
| Check and criteria | Name both. A verification that names no criteria is not a verification (PS §5.3) |
| Version | Say which version of the criteria or rule you applied. A criterion changed later is a different criterion |
| Evaluation point | Say what point in the record you looked at. "Satisfied" means the record showed it *then* |
| Elements examined | List them by reference, bound to the version you saw. A reader must be able to repeat the check |
| What it says | One of the four. **Unresolved** is distinct from **satisfied** and from "no result" |
| Violated | Name the rule or rules |
| Standing | AUTH-V holder / human AUTH-G holder / advisory only |
| Producer | An AI producer's configuration is recorded (CRC-39) |
| Limits | A result is record-relative. It does not say the record is complete or accurate or the world is as recorded |
| Effect claimed / not claimed | State both. Not claimed: acceptance, sufficiency, validation, progression, independence, corroboration, truth |

A result is **never written into the item's recorded condition** (RO §12.7, RF-6). A tool or a person writing "valid" onto an artifact is a state write-back and misleads readers.

### 11.3 Standing of a result

A result is advisory and informs reviewers. It gains additional standing only when relied on to satisfy a gate-required formal check (the producer holds AUTH-V, and the verifier produced nothing verified, GCR-10), or when recorded as a finding that an acceptance is invalid (§11.4). It is challengeable. It confers no independence or corroboration: two checkers agreeing is agreement (PR-20). A pending challenge does not suspend any requirement the result created (RJ §9.4.3).

### 11.4 Findings that an acceptance is invalid (CRC-59)

A finding that an acceptance is invalid is the event that gives rise to requirements on what relied on that acceptance (TRG-6). Its required content is fixed:

1. the **rule or rules violated**, each named;
2. the **evaluation point**;
3. the **record elements examined**.

It is recorded by an **AUTH-V holder for the scope** or by a **human AUTH-G holder**. A **non-human** AUTH-V holder may record one only where each rule asserted violated is decidable from the record, and the finding states the elements and evaluation point. If the asserted invalidity depends on interpretation, the output stays advisory or request-like and does not itself trigger TRG-6. A human AUTH-G holder states the same three elements and is not limited by the decidability bound where exercising authorized judgment (CRC-59; RJ §9.4.5).

**A bare assertion** ("this acceptance is invalid") has no such standing. **Type it by the authority the recorder actually holds** (DM-08):

| Recorder holds | Record it as | Notes |
| --- | --- | --- |
| AUTH-A | A **challenge** to the acceptance (target scope: validity of an act) | It produces contestation and exposure |
| AUTH-A, with sourced information bearing against the basis | **Counter-evidence** against the item (attach the evidence) | Counter-evidence on a direct material dependency creates a requirement |
| AUTH-A, AUTH-V, or AUTH-G | A **revalidation request** with a stated basis (P3) | Creates the requirement on the dependent |
| An actor with no applicable authority (for example an agent without AUTH-A) | An **advisory finding** | Informs. Does nothing else |

Do not type a bare assertion as a finding. Do not re-type a real finding as a challenge to reduce its effect.

### 11.5 Checks must not become gate acceptance

Practice for keeping them apart:

- A gate's formal-check slot is filled by a **verification record**, not by a sentence in the decision record that "the checks passed".
- The decision record cites verifications by reference and carries its own **contextual sufficiency judgment**.
- A tool or QA colleague never records "gate passed". Their output is "check C satisfied at evaluation point E".
- Where a result says **violated** or **unresolved** and the acceptor proceeds anyway, that is an override and needs a recorded exception, and a non-waivable condition cannot be overridden at all (§12.6).
- A representation that cannot compute an answer leaves the condition **unresolved**, not satisfied. The requirement stays and falls to human review (RJ §9.5; BDR-07).

### 11.6 Deciding whether a criterion is decidable (DM-06)

A gate-required formal check by a **non-human** verifier counts only if each named criterion is designated in the gate definition as **decidable from the record** (CRC-15). That designation is itself a recorded judgment, challengeable (HJC-24). Use the boundary's own test as a practice checklist (BDR-01; RJ §4.3):

| Question | If "no" |
| --- | --- |
| **T1. Defined elements.** Do accepted semantics define every record element the criterion needs? | Not decidable. The criterion needs an element nobody has defined, or one whose meaning depends on a practice choice |
| **T2. Record-only answer.** Is the answer fixed by those elements alone, without asking what a source says about the world or what someone intended? | Not decidable |
| **T3. No judgment inside.** Can you reach the answer without deciding sufficiency, relevance, persuasion, risk, materiality, acceptability, warrant, or substantive independence (other than by applying a recorded designation)? | Not decidable |
| **Agreement corollary.** Would two competent evaluators, given the same record and evaluation point, always agree? | Not decidable as stated |

**When in doubt, it is not decidable** (BDR-02). Over-claiming objectivity is the larger risk. A criterion does not become decidable because a program can compute it, and it is not judgment merely because it is laborious.

Examples (illustrative):

| Criterion as drafted | Decidable? | Why / better wording |
| --- | --- | --- |
| "Each customer evidence item records a source reference, a producer, an observation time, a target, a polarity, and a limitations statement." | Yes | Presence of defined elements |
| "The acceptor is a producer of no member of the accepted set." | Yes, given recorded producers | Identity, not substance (substance is a separate judgment) |
| "Evidence for willingness to pay is convincing." | No | Sufficiency judgment. Move it to the acceptor's contextual judgments |
| "A counter-evidence search was recorded for the differentiation claim." | Yes (presence of the attempt record) | Whether the search was adequate is a judgment |
| "The sources are independent." | No as stated | Rephrase to the checkable part: "no two items cite the same source reference". Substantive independence remains a judgment |
| "The inference is well supported." | No | Warrant is a judgment. Checkable: "the inference cites at least one evidence item or assumption and its chain grounds" |

Write each gate criterion twice if needed: the **checkable part** (what a verifier may record) and the **judgment part** (what the acceptor decides). A criterion that is entirely judgment is not a formal check and belongs in the gate's contextual judgments.

### 11.7 Checks run by tools or AI

An AI or automated checker is an actor. It holds AUTH-V only by a grant, bounded by decidability (RJ §10.3.1). Its results carry its producing configuration. Same-vendor or same-lineage checkers share blind spots; say so. No selection of a validator is made here. A check that passes does not make the protocol satisfied (PR-25: structural validity never establishes protocol validity).

---

## 12. Gate Practice

### 12.1 Defining a gate (template 13)

A gate is a defined decision point governing a stated **progression** for a stated **scope**. It is **defined before it is used**, by a human holding AUTH-G for the project's gate-definition scope (GCR-12). A consequential decision made without a governing gate definition is a **recommendation**, and the missing gate is a visible condition. PROD-W assumes no universal lifecycle. Gates may loop, branch, and reopen.

**The slots (GC §5.2) and how to fill them:**

| Slot | What to write | Checkable part | Judgment part |
| --- | --- | --- | --- |
| Progression and scope | What crosses the gate, for what scope | The definition exists and the act is within it | Whether the scope is right |
| Acceptor grants and rule | Which AUTH-G grants may accept; how many independent acceptances (default one) | Grants resolve; acceptances counted. A producer's acceptance is never counted (PR-18) | None |
| Gate basis | The accepted set plus the standing record | Computable from links | Whether it is the right basis |
| Required evidence | One block per slot: target, dimension, acceptable kinds, source-independence expectation, optional recency | Slot filled by present items with the required designations. Recency against recorded times | Relevance, adequacy, sufficiency |
| Required challenge criteria | Which targets must have been challenged, by whom, whether independence is required, any stricter response rule | The challenge exists; challenger not a producer of the challenged item | Adequacy of the challenge and of responses |
| Formal checks | Named criteria; whether verification must be independent | A verification exists, names its criteria, and its verifier meets GCR-10 | None (the bounded part) |
| Stricter conditions (optional) | Whatever the project adds | Present or absent | Whether satisfied, if itself a judgment |
| Contextual sufficiency | The acceptor's judgment | The act exists and is valid | All of it |

**Do not amend a definition to fit a basis already refused or deferred.** An amendment after a refusal or deferral on the same basis applies only as a recorded exception (GCR-13).

### 12.2 A filled gate definition (hypothetical, for illustration)

*This is invented for methodology illustration. It is not a pilot gate.*

**Gate:** "Discovery to solution exploration" for the opportunity "reconciling scope changes before invoicing for independent consultants".

- **Progression and scope:** movement from problem framing to low-cost solution exploration. Not build.
- **Acceptor grants:** AUTH-G for this gate. One valid independent acceptance.
- **Required evidence:**
  - *Problem exists:* direct observation or recorded testimony from more than one organization, and an artifact of the current process. Dimension: problem. Counter-evidence search required.
  - *Customer would change behavior:* testimony recorded as testimony, with the respondent's role stated. Dimension: customer.
  - *Existing alternatives:* a recorded attempt record of named channels, with stated reach. Dimension: differentiation.
- **Challenge criteria:** the "willingness to pay" inference has been challenged by an actor who produced none of its basis. Default treatment rule applies.
- **Formal checks:** (a) each evidence item carries source reference, producer, observation time, target, polarity, limitations; (b) the acceptor is a producer of no member of the accepted set. Independent verification required for (a). Both are designated decidable.
- **Stricter conditions:** every evaluative claim in the basis carries a basis-presentation designation.
- **Contextual judgments:** relevance and adequacy of the three slots; whether challenge responses are adequate; whether residual disagreement is acceptable.
- **Waivable:** recency. **Not waivable:** the six items of §12.6.
- **Escalation:** another AUTH-G holder for this gate; role-conflict resolver: none designated (so a conflict is an authority gap).

### 12.3 Outcomes (acts, not states)

| Outcome | Use when | Who | What the record must show |
| --- | --- | --- | --- |
| **Acceptance** | The AUTH-G holder judges the basis sufficient for the scope | Human AUTH-G holder satisfying the nine conditions (GC §5.4) | Acceptor, capacity, grant, scope, accepted set, treatment of each standing-record item, formal-check status, independence declaration, determination, time (template 15) |
| **Refusal** | Sufficiency is not found for the basis as it stands | Human AUTH-G holder. A producer of the set may refuse (GCR-05) | Which conditions are unsatisfied or why sufficiency was not found, and what would change it. Not final. Erases nothing |
| **Deferral** | No determination is made yet | Human AUTH-G holder | What is awaited and from which position. Time never converts it into anything |
| **Conditional progression** | Progress or rely while a named condition stays unresolved and tracked | Independent human AUTH-G holder | Nine elements (template 17) |
| **Exception** | A specific waivable requirement is dispensed with for a specific progression | Independent human AUTH-G holder, together with an acceptance | Template 18 |
| **Escalation** | A different authority is needed | Any holder of AUTH-A, P, V, or G | Template 19. Resolves nothing |

An actor without AUTH-G for the gate performs none of acceptance, refusal, deferral, conditional progression, or exception. Their corresponding output is an **advisory finding** recommending one (PR-15, PR-23).

### 12.4 Before accepting: the standing record and the readiness walk-through

The validity conditions for an acceptance (GC §5.4) are the content of template 14. Work through it before the act. Three of them are where acceptances most often fail:

- **Every standing-record item is cited with a treatment** (GCR-17). The standing record is: every challenge and contradicting item recorded against any member of the accepted set or against the gate itself (including those since withdrawn); exposure of basis items; open requirements; reliance under assumption and reliance while open; every earlier refusal or deferral on the same gate and basis; and every exception already applying. Treatments available: **answered**, **conceded or withdrawn by the challenger**, **moot**, **accepted as residual**, **covered by exception** (GC §5.5). Omitting an item makes the acceptance invalid. Letting time pass, treating agent agreement as an answer, or having a non-AUTH-G actor determine a treatment are not available.
- **Every relied-on unvalidated hypothesis or assumption** (including assumption-rooted items) is covered by a conditional progression authorization recorded **at or before** the acceptance, and every open requirement on a basis item is closed or covered by a reliance-while-open authorization (CRC-19). An authorization recorded after the acceptance does not cure it (GCR-47).
- **Independence declaration** is present (GCR-09).

**Earlier refusals and deferrals are in the standing record of a later acceptance.** This stops shopping for a favorable acceptor. The later acceptance must say what changed since (GCR-39).

If any readiness question is "no" or "unknown", the honest outcomes are refusal, deferral, escalation, or correcting the basis. They are not acceptance with a note.

### 12.5 Accepted as residual, and conditional progression

**Accepted as residual.** The acceptor judges the basis sufficient *notwithstanding* a named unresolved matter, with rationale. The decision carries a marker "accepted with unresolved ___" which dependents see. It is ordinary acceptance made with open eyes. It is not an exception and not validation. It cannot cover a dispute about the validity or independence of an act, including the acceptor's own independence or a disputed attribution of the acceptor (GC §8.5).

**Conditional progression.** Use it when the project may move forward **while a named condition stays open and tracked**. It has two grounds:

| Ground | The unresolved condition | Mark produced |
| --- | --- | --- |
| G1 | A relied-on unvalidated material hypothesis, or a relied-on assumption | Reliance under assumption |
| G2 | A relied-on item with an open revalidation requirement | Reliance while open |

The nine elements (template 17): the authorizer and grant; independence and the declaration; the progression and scope; each item relied on with its ground; what would resolve it and who is expected to; the rationale (a judgment); the reliance bound; a statement that the unmet requirement remains unsatisfied and open; optionally a review event. It is non-delegable, not inherited by later gates, takes effect when recorded, is revocable by any AUTH-G holder for the scope as a conservative act, and **never ends by time**. It ends by validation, refutation, retirement, closure of the requirement, or revocation (GCR-42).

**Distinguishing test (normative, GCR-48):** after the progression, does the unmet requirement remain **open and tracked**? If yes it is conditional progression. If it is dispensed with for that progression, it is an exception. A project may not record one under the other's name.

### 12.6 Exceptions

An exception is dispensation from one specific unsatisfied gate requirement for one specific progression, by an independent human AUTH-G holder, performed with an acceptance. The result is an **acceptance with exception**. A waiver without an acceptance authorizes nothing. The record carries the authorized human, grant, rationale, the unsatisfied requirement, scope, provenance, and the marker "exception", and the marker travels with the acceptance wherever it is cited. An override (acceptance despite a standing refusal, a failing formal check, or another holder's contrary determination) is an exception naming the overridden determination or check.

**Never waivable, by any act** (GCR-46):

1. independence over the accepted set;
2. explicit, attributable, human AUTH-G authorization;
3. citation of the standing record and recording of treatments (a stricter *response* rule may be waived. The visibility of what exists may not);
4. visibility of the exception itself;
5. the decision record's identification of its nature and authority basis;
6. the FR-7 conditions where a material hypothesis is relied on. A requirement that such a hypothesis be validated cannot be waived into silence. It is handled by conditional progression.

**Practice.** If you reach for an exception more than occasionally for the same requirement, the gate definition is wrong. Amend it **for future bases**, as a recorded amendment, rather than normalizing the exception. Do not amend it for the basis that was just refused (GCR-13).

### 12.7 The five instruments side by side

| | Validation | Ordinary acceptance | Accepted as residual | Conditional progression | Exception |
| --- | --- | --- | --- | --- | --- |
| What it says | A hypothesis's criteria are met for a scope | The gate's conditions are sufficient | Sufficiency despite a named unresolved matter | Proceed or rely while a named condition stays unresolved | This requirement is dispensed with for this progression |
| Unmet requirement stays open and tracked? | n/a | n/a | The matter stays open and visible | **Yes** | **No.** Visible only as an exception |
| Marker | Validation record | Acceptance record | "Accepted with unresolved..." | Reliance under assumption / while open | Exception |
| It is not | Truth | Validation | An exception | Validation, reaffirmation, or a waiver | Ordinary conformance, or a cure of invalid independence |

### 12.8 Worked examples

The worked examples (`prod-w/worked-examples.md`) show a valid progression with conditional progression and residual acceptance (WE-1), a visible non-progression by refusal and escalation (WE-2), unresolved disagreement and conflicting determinations (WE-3), a team of one reaching an authority gap (WE-4), an invalid acceptance attempt and its finding (WE-5), a commitment that is not an acceptance (WE-6), revalidation after counter-evidence (WE-7), and rotation and recovery by new project (WE-8). They are methodology illustrations with invented facts, not pilot results.

---

## 13. Revalidation Practice

### 13.1 The idea

When material support for a decision changes, is contradicted, or is withdrawn, the decision does not stay silently valid (PR-26; WD-6). A **trigger** is a recorded event on an upstream item. It creates a **requirement** on direct material dependents, and exposure on indirect ones. The requirement is a single standing obligation per dependent, with reasons attached, until a closure addresses every reason present (GCR-58).

| Trigger events (non-exhaustive; each is a recorded event) | Effect |
| --- | --- |
| Source-identified counter-evidence on a material dependency (TRG-2) | Requirement on direct material dependents |
| Withdrawal of an upstream item, or a meaning-altering change recorded as a supersession (TRG-1) | Requirement |
| Invalidation of an upstream item (TRG-3), or its supersession by a replacing item (TRG-4) | Requirement |
| A dependency change: link added, removed, or materiality redesignated (TRG-5) | Requirement |
| An acceptance found invalid or withdrawn by its acceptor (TRG-6) | Requirement on everything that relied on it |
| Revision, retirement, supersession, or invalidation of a dependent | A trigger for its dependents (GCR-62) |
| A challenge, bare contradicting claim, or bare contradicting inference | **Exposure only**, until a route (P1, P2, P3) gives it more |
| Age of evidence or elapsed time | **No direct effect.** May be the stated basis of a request (GCR-67) |

### 13.2 Procedure

1. **Identify the changed or contradicted item.**
2. **List direct material dependents** (and note presumed-material ones: items cited by a consequential decision are presumed material unless a non-material designation with rationale stands).
3. **Record the request or the trigger** with a stated basis (template 21).
4. **Decide the tier** for each dependent: Tier 1 (a consequential decision or a member of the accepted set of one) or Tier 2.
5. **Decide whether reliance continues.** Exposure never bars reliance. An open requirement bars *silent new reliance*. New reliance (citing it as basis in a new acceptance, decision, or progression) needs a closure or a reliance-while-open authorization (G2). The historical acceptance stands and is not erased. This governs **recorded** reliance, not conduct in the world (GC §7.6).
6. **Close** by an outcome that meets the authority conditions:
   - **Tier 1 reaffirmation** is a fresh acceptance by an independent human AUTH-G holder over the accepted set computed on the *current* basis, with the new reasons in the standing record and treated.
   - **Tier 2 reaffirmation** requires an AUTH-G holder who produced neither the dependent nor its material basis closure.
   - **Revision** carries the requirement to the successor. A Tier 2 revision by the producer closes only as producer-addressed. That is not independent closure and joins the standing record if the dependent later becomes standing.
   - **Retirement** by the dependent's producer or any AUTH-G holder for the scope.
   - AUTH-A, AUTH-V, evaluators, and agents may request, challenge, and escalate. **They may not close.**
7. **Do not wait for a clock.** An open requirement that stays open for a long time blocks only silent new reliance (GC §11.6).

### 13.3 Burden controls (practice, built on GC §11.7)

- One requirement per dependent, with reasons.
- Direct dependents only. Consequences travel through outcomes.
- Use challenges for dissent and counter-evidence for sourced contradiction. Do not file requests as a reflex.
- One closure act may close several dependents if the closer holds the authority for each.
- Prefer cheap producer retirement or revision for non-consequential Tier 2 items.
- Grant validation and closure scopes narrowly so a qualified person other than the Moderator can act.
- Keep a count of open requirements per consequential decision in your issue log. Friction is evidence for STEP-07, not a reason to stop recording (GC §11.7).

---

## 14. Escalation Procedures and Authority Gaps

### 14.1 What escalation is

Escalation routes an unresolved matter to the authority able to resolve it. It **resolves nothing**. It stays visible until the addressee records a determination (resolve, refuse, or defer). If the addressee never responds, the escalation stays visible; time does not act (GCR-37, GCR-41). The path is derived from **grants**, not role names (GC §8.4).

### 14.2 Procedure (template 19)

1. **Name the matter** exactly: the item, challenge, gate, designation, attribution, or determination.
2. **State the reason**: insufficient evidence, conflict of interest, unresolved disagreement, disputed designation or attribution, refused or deferred gate, or authority gap.
3. **Derive the resolving authority** from the table below, as a grant class and scope plus its independence condition, and **list the identities holding it now**.
4. **State the determination you are asking for.**
5. **Record what remains unaffected** and what cannot proceed in the meantime.
6. **Do not mark anything closed.** Leave the matter in its current condition and let the addressee's record change it.

| Matter | Resolving authority | Independence condition on the resolver |
| --- | --- | --- |
| A challenge against an item or determination | Challenger resolution, or an AUTH-G holder in scope | Independent of the challenged item's accepted set. Not the author of a challenged determination (GCR-26) |
| A disputed producer attribution | An AUTH-G holder | Independent of the disputed item (GCR-07) |
| A disputed materiality designation or redesignation | An AUTH-G holder | Independent of the designation, the item, and the dependent (GCR-34) |
| A correction designation on a standing item | An AUTH-G holder | A producer of neither the item nor the change (GCR-51) |
| An open revalidation requirement | By tier (§13.2) | By tier |
| Conditional progression or an exception | An AUTH-G holder for the gate | Independent of the accepted set (GCR-43) |
| A refused or deferred gate | Another AUTH-G holder for the gate, or the role-conflict position the gate definition designates | Independent of the accepted set |
| Conflicting determinations by AUTH-G holders | The position the gate definition designates for role conflicts. If none, an authority gap | |
| Insufficient evidence | Producers (AUTH-P) gather more; an AUTH-G holder defers | |

The protocol defines **no override hierarchy** among gate authority holders, and whether top authority should be reviewable or overridable (Product OQ-7, GC-OQ-10) is unsettled. Do not invent a hierarchy in a gate definition without recording that it is project practice and that the protocol does not provide one.

### 14.3 Authority gaps

An **authority gap** exists where the resolving authority for a matter cannot be filled by any identity meeting the independence condition (for example, the only AUTH-G holder produced the whole accepted set, or authored the determination under challenge).

- **Record it** against the matter (template 20). It is a visible condition.
- **The matter stays unresolved and visible.** Progression that depends on it can occur only through valid acts by other independent holders. If none exist, no valid progression exists.
- **Not cures:** acceptance by the conflicted holder, a second role label, a collective identity, an agent or evaluator, a waiver, time, or a self-conferred grant (GC §8.6).
- **Cures:** a grant of the needed authority to an independent human by a granting authority (a conflicted conferrer's grant is flagged and escalation-eligible, CRC-64); visible re-basing of the subject on independent items; substitution of the acceptor.
- **Stopping is allowed.** A project may stop at an authority gap. The protocol does not require otherwise.
- **What the conflicted holder may still do:** conservative acts only (refuse, defer, escalate, request revalidation, challenge, withdraw or retire own items) (GCR-05).

### 14.4 Escalating protocol questions

A question about what the *protocol* means or should say is not a gate matter in a product project. In `prod-w-dev` such questions go to the MOD-W Moderator (the product role "Product Moderator" has no authority here, PR-24). In a downstream product project, the project records the question as a method issue (template 28) and routes it to whoever governs the protocol revision. This guide does not define that route for downstream projects.

---

## 15. Consequential Commitments That Are Not Acceptances (DM-09)

### 15.1 The gap

CRC-19 invalidates an **acceptance** that relies on an unvalidated hypothesis or assumption without a conditional progression authorization. CRC-48 requires a **decision record** to identify its basis, authority basis, and nature, and treats a record that does not meet the human, grant, and independence conditions as a recommendation. Neither reaches a consequential commitment that is *neither*: a team signs a contract, announces a launch, hires, or spends budget by some route outside any gate acceptance or recorded decision. The protocol adds no rule for these (RJ-OQ-12; CRC-19, CRC-47). It leaves to methodology whether the project routes each through a gate acceptance or a decision record **so that CRC-19 or CRC-48 reaches it**.

### 15.2 Practice

**Default practice (recommended; a project may choose otherwise and say so in its establishment record).**

1. **Decide what is consequential for this project** and write it down in advance: commits resources, makes an external promise, changes product direction, validates a major claim, or authorizes movement through a gate. Ordinary production work that relies on an unvalidated item is *not* consequential in this sense; it records reliance under assumption and moves on (GC §9.2).
2. **Route every consequential commitment through either a gate acceptance or a recorded decision (ACT-07).** Define a gate class for recurring commitments ("commit to a customer", "begin spend category X") so the commitment is an acceptance and CRC-19 applies in full. For one-off commitments use a decision record by an AUTH-G holder with an authority basis and independence declaration, so CRC-48 applies.
3. **If a commitment is made by an authority outside the project's gates** (an executive, a funder, a customer contract) and so cannot be an acceptance or decision here, complete a **commitment record** (template 24). It states plainly that it is not a PROD-W acceptance, names the basis (organizational authority is not a PROD-W grant, and the record says which it is), lists the unvalidated hypotheses, assumptions, and open requirements relied on, keeps the reliance marks on the dependency links, and states a **visible warning** wherever the commitment is cited.
4. **Name the later gate or review** that would test the reliance, and who is expected to run it.
5. **Do not let a commitment record stand in for validation.** Progression under assumption is never represented as validation (GCR-44).
6. **Watch for laundering.** A commitment made by an AUTH-G holder who is a producer of the basis it relies on is not made independent by being called a commitment. Say so in the record, or route it differently.

**What the protocol still does not say.** Whether a consequential commitment that is not an acceptance must be refused if it relies on something unvalidated is not decided. Whether this default is workable (how many commitments, how costly) is a question for the STEP-07 pilot. Template 24 is the record that keeps the reliance visible meanwhile.

---

## 16. Grant Review, Role Rotation, and Recovery by New Project (DM-07; RQ-15)

DM-07 is registered in `rule-judgment-boundary.md` §6.6 as "grant review practice and role rotation, including re-conferral after a revocation or renunciation cascades downstream", and RJ §10.6 and D10 additionally route to it "what carries into a new project" after a terminal loss of authority. `mod-w/step-06.md` and RQ-15 name only the second. This section covers both.

### 16.1 Grant review and role rotation

**Protocol facts to work from (CRC-63; RJ §10.2.4).** A revocation or narrowing takes effect when recorded and is not retroactive. Grants downstream of a revoked or narrowed grant **fall prospectively** with the chain. Acts that relied on a fallen grant after the revocation are invalid. Acts performed while the whole chain was effective stand. A grantee's renunciation is a revocation and cascades the same way. Re-conferral is a new conferral by a human whose covering conferral scope is effective, recorded after the revocation. A revoked or fallen holder cannot re-confer on its own behalf. Removal runs one way: a covering peer may remove a subtree, and a descendant that revokes an ancestor cuts its own chain (D10).

**Practice.**

| Moment | Practice |
| --- | --- |
| **Scheduled review** | At a project review point, walk the grants (template 27): still wanted, chain still effective, holder still independent of the sets they are expected to act on, downstream dependents of each grant. The review point is a visible prompt and has no automatic effect |
| **Someone joins** | Confer a grant only from a holder whose covering conferral scope is effective and who is not conflicted for the set the grantee will act on. Appointment to a grant-bearing position is a conferral |
| **Someone leaves or changes role** | **Before** the outgoing holder renounces or is revoked, list every grant they conferred. Those appointees will fall with the chain. Arrange re-conferral by a *different* holder with a covering scope, record it, and only then let the outgoing holder's grant end |
| **Hand-over of the top** | The sole root grantee cannot hand over after the fact: their renunciation takes down successors they conferred. Make hand-over by **root grants in the establishing act**, or by the root grantee leaving their grants in place |
| **Rotating acceptors** | Acceptances made while the chain was effective stand. A new holder does not inherit them and is not bound by them. New reliance needs the new holder's own acts |
| **Revocation of a challenger's standing** | A revocation or narrowing that affects an actor able to challenge, made by a producer of the item, is flagged and escalation-eligible even if no challenge is open (CRC-64). Avoid doing it. If it is necessary, state the purpose and expect it to be challenged |
| **Narrowing** | Use narrowing rather than revoke-and-re-confer, when you mean to reduce a grant. Revoke-and-re-confer cascades fully |
| **Cascade preview** | Before any revocation, draw up the list of what falls (template 27). Narrowing a described scope is a judgment (HJC-25); say who decides |

### 16.2 Recovery by new project (RQ-15)

**Protocol (D10).** A project has exactly one establishing act. If every root grant is revoked or renounced, no valid chain can exist again. For a project with one root grantee this is terminal. **There is no break-glass**, because one would be a way to mint a root. **Recovery is by a new project.** What carries into a new project **is not defined** by any accepted artifact (TLR5-01 kept this visible). The representation must make a project boundary explicit (RQ-15).

**This guide does not define carry-over as accepted protocol.** Everything below is **project practice**.

| Step | Practice |
| --- | --- |
| 1. Confirm recovery is needed | Is the authority chain really unrecoverable? Check: is any root grantee still effective? Can a remaining holder with a covering conferral scope confer what is needed? If so, that is not recovery, it is ordinary re-conferral (§16.1). If a project act preceded the establishing act, or the establishing act is missing, the project has no valid establishing act and recovery is the only path |
| 2. Write down what happened | Write a closing note: what failed, which grants fell, what was relied on. Keep it beside the old record as a document. It is not an act in the old project, which has no remaining authority to record acts. The old record stays visible and is not edited |
| 3. Establish the new project | Template 1, with an explicit boundary that names the old project and states that the new project is a different project with a different authority chain |
| 4. Import prior work as prior work | Template 26 for each item brought across: its use (source material, context, evidence through its underlying source, or carry-over candidate); the old project's authority-chain status; what the old record says about it |
| 5. Do not inherit acceptance | **Prior acceptance status in the new project is none.** The old acceptance was an act under a different chain. An imported item is not standing in the new project until a fresh recorded act by the appropriate authority here, over the accepted set here |
| 6. Cite the underlying source | When imported material was evidence, cite the evidence's source and rebuild the evidence record in the new project. Do not cite "the old gate accepted it" |
| 7. Bring the opposition across | Challenges, counter-evidence, and unresolved disagreement from the old record are carried as visible items. Do not import the support and drop the opposition |
| 8. Re-establish authority | New root grants, in the new establishing act, including independent holders if possible (§4.3). Authors of imported work remain producers of it (GCR-07) and are limited accordingly |
| 9. Reconsider dependencies | State which dependencies of imported items are being reconsidered and which are being relied on as imported |
| 10. Keep the question visible | Record that carry-over semantics are undefined by the protocol and that this project's treatment is practice. Raise it as an issue to the Moderator through the usual route (template 28) |

A hypothetical walk-through is WE-8.

---

## 17. What Belongs in the Record and What Belongs in the Document (RQ-14)

**Criterion from STEP-05 (RO §12.4).** A piece of information belongs **with the record** if a catalog entry reads it, or if its absence would break a visibility invariant. It belongs **in the document** if only a human reasons from it. RQ-14 asks what else; it is routed to STEP-06 and the Product Owner. The practice below is a proposal pending Product Owner input.

| Belongs with the record (practice, applying the criterion) | Belongs in the document (practice) |
| --- | --- |
| Acting identity, capacity, target, time or position, action kind, grant relied on | Narrative explanation of why the team believes something |
| Class of each item; producers (including every contributor who supplied substance); producers' work assignments | Drafting history that does not change who supplied substance |
| Source reference, target, polarity, evidence basis kind, limitations present, observation time, derived-from links | Meeting notes and informal reasoning (move them into a claim, inference, or challenge if the team relies on them) |
| Validation criteria for hypotheses; inference citations; evaluative and basis-presentation designations | Opinion commentary |
| Materiality designations and dependency links, with recorders | Roadmaps and plans (until they are a decision, a gate subject, or a commitment) |
| Gate definition references, slot fillers, treatments, determinations, conditions, exceptions and markers | Reports for a particular reader, generated as views |
| Configuration facet statements and instruction version-binding | Presentation formatting and layout |
| Rationale text (its **presence** is checked. Its **adequacy** is a judgment) | |

Two cautions. **Contributor provenance is record, not document**, because who supplied substance determines the producer set and so who may accept. **Confidence is not metadata** here: Product OQ-8 lists it as an example, and the accepted boundary does not adopt it as a record element (BDR-14). Do not store hand-set status words on an item. A document that shows a status is a **view** and should name the record and the point it shows. If a view disagrees with the record, the view is wrong.

---

## 18. Routing: What Is Not Decided Here

### 18.1 Pilot questions (STEP-07)

This guide has no pilot evidence. It provides the practice STEP-07 would exercise. The pilot owns answers to, among others:

| Question | Source |
| --- | --- |
| Burden of detection and recording: flag volume, effort to record treatments, configuration recording burden | DP-01; RQ-13 |
| Whether blocking-eligible rules are better blocked or detected-and-flagged in use | DP-02 |
| Whether authorizations or grants need protocol-effective terms | DP-03 |
| Whether flagging conflicted conferral and revocation is strong enough, with the named adversarial cases | DP-04 |
| Adequacy of the never-a-correction kinds | DP-05 |
| Whether non-human verification is adopted and its effect | DP-06 |
| Whether the actor-kind weak point is exploitable and at what cost | RQ-05 (F-5, F-2) |
| Whether the card of questions and the act-kind table help readers | RQ-10 |
| Whether practice defaults in §§4, 6, 8, 15, 16 are workable | This guide |
| Backdating evidence for record order | RQ-04 |
| Burden of the revalidation mechanism (open requirements per decision, closure effort, authority-gap frequency, whether teams begin to ignore requirements) | GC §11.7 |

### 18.2 Research and hypothesis disposition (STEP-08)

Disposition of agent-skills hypotheses H-A, H-B, H-C (RQ-12), and of MOD-W transferability findings, is STEP-08's. This guide treats none of them as a requirement (NG-4).

### 18.3 Moderator-visible and later routing

| Question | Routed to |
| --- | --- |
| RQ-01 basis-presentation designation as STEP-05's answer; RQ-02 whether to require it | MOD-W Moderator (a new rule is Moderator-visible); §7.6 gives project-level practice only |
| RQ-03 who may record a scope vocabulary and containment relation | MOD-W Moderator (protocol question); §4.7 gives practice |
| RQ-06 conformance statement form | Later architecture; STEP-09 |
| RQ-09 membership expansion at a point after an act | MOD-W Moderator |
| RQ-11 serialized state vocabulary | MOD-W Moderator, after STEP-06 and STEP-07 |
| RQ-16 standing of same-vendor model review | MOD-W Moderator |
| RQ-18 where RX-1 sits | MOD-W Moderator |
| GC-OQ-10, Product OQ-7 reviewability or override of top authority | Unsettled by D10. Not decided here |
| Identity and credential integration; transport; evaluator contract | Later architecture; deferred |
| Publication claim wording | STEP-09 |

### 18.4 New items found while writing this guide

| ID | Observation | Routed to |
| --- | --- | --- |
| MG-N1 | `mod-w/step-06.md` and RQ-15 describe DM-07 as recovery by new project, while the accepted register defines DM-07 as grant review practice and role rotation, with recovery routed to it by RJ §10.6 and D10. This guide covers both (§16) and changes neither text | MOD-W Moderator, for awareness. No action is needed to proceed |
| MG-N2 | Draft v0.1 of these three files, present untracked at the start of this work, adopted "Product Skeptic" as a role and misdescribed DM-06 and DM-07. v0.2 supersedes it | Recorded as a change note. Evidence offered under research governance (§20.4) |
| MG-N3 | The practice default for consequential commitments (§15) adds a definition-in-advance of what counts as consequential. The protocol leaves "consequential commitment" undefined beyond its examples | STEP-07 to test; Tech Lead to confirm it is practice and not a new rule |

---

## 19. Preparing for STEP-07

This guide does not run the pilot. A project preparing a proof-of-concept trial would have ready:

- a completed establishing act (template 1) with an independent human AUTH-G holder named, or an acknowledged authority gap;
- role-position entries (template 2) and grants;
- a source register (template 4);
- one small opportunity statement as a claim record, with initial material claims;
- an evidence plan including counter-evidence search;
- a challenge plan naming who will challenge which targets;
- gate definitions (template 13) for at least a discovery gate and a build/no-build gate, recorded before use;
- the independence declaration practice (template 16);
- a known place for the issue log (template 28);
- a statement of what in the pilot is expected to exercise practice defaults in §§4, 6, 8, 15, and 16.

---

## 20. Traceability, Self-Checks, and Change Notes

### 20.1 Traceability

**G-4 and AC-2.**

| AC-2 element | Where |
| --- | --- |
| Role charters | `role-charters.md`; this guide §§5, 6 |
| Decision workflow examples | §§3, 12, 13, 15; `worked-examples.md` WE-1 to WE-8 |
| Evidence procedures | §§7, 8, 9 |
| Gate criteria with worked examples | §§11.6, 12; `worked-examples.md` WE-1, WE-2, WE-3 |
| Escalation procedures | §14; `role-charters.md` §8 |
| Templates for key artifacts | `templates.md` |

**Requirements.** FR-1 roles and authority: `role-charters.md`, §5. FR-3 evidence visible and traceable: §§7, 8, 12.4. FR-4 self-approval invalidity operationally clear: §6, `role-charters.md` §7, templates 14 and 16. FR-5 unresolved disagreement visible: §10, WE-3. FR-6 provenance: templates 0.1, 5, 6, 11; §§8, 17. FR-7 hypotheses validated or visible unresolved assumptions: §§7.3, 12.5, templates 9, 10, 17. NG-1 and NG-2: §1.3 and §20.2.

**DM-* items (from `rule-judgment-boundary.md` §6.6).**

| ID | Item | Where |
| --- | --- | --- |
| DM-01 | Evidence categories, thresholds, gate-slot contents by product category | §7.5; template 13; WE-1 |
| DM-02 | Role positions; who holds gate-definition, validation, conferral scopes | §5; `role-charters.md` §§4, 5 |
| DM-03 | Project establishment and root-grant practice | §4; template 1 |
| DM-04 | Independence, work-assignment disclosure, substance test for teams of one or two | §6; `role-charters.md` §§6, 7; templates 16, 20; WE-4 |
| DM-05 | Producing-configuration conventions, "not determinable", what counts as instructions | §8; template 11 |
| DM-06 | Designating formal-check criteria as decidable from the record | §11.6; template 13 |
| DM-07 | Grant review practice and role rotation; re-conferral after cascade; (with RQ-15) recovery by new project | §16; templates 3, 26, 27; WE-8 |
| DM-08 | Content of a formal-check result or finding; typing a bare assertion | §11.2 to §11.4; templates 22, 23; WE-5 |
| DM-09 | Consequential commitments that are not acceptances | §15; template 24; WE-6 |

**STEP-05 routed practice questions (from `representation-options.md` §15.1).**

| ID | Question | Where | Level |
| --- | --- | --- | --- |
| RQ-02 | Basis-presentation designation for evaluative claims | §7.6 | Project-level stricter condition. Any rule is the Moderator's |
| RQ-03 | Who records scope vocabulary and containment | §4.7 | Practice. Protocol question remains with the Moderator |
| RQ-04 | Meaning of "recorded" across boundaries; record order and time | §4.5 | Practice. Backdating evidence is STEP-07's |
| RQ-05 | Actor-kind binding records | §9; template 25 | Practice. No requirement. No claim a human acted |
| RQ-07 | Source-comparability practice | §8.3; template 4 | Practice |
| RQ-08 | Binding instruction content to a version | §8.1 | Practice. No mechanism selected |
| RQ-10 | Orientation of act kinds; single status versus facets | §3 | Practice. Usability evidence is STEP-07's |
| RQ-14 | Record versus document metadata | §17 | Proposal pending Product Owner |
| RQ-15 | Recovery by new project, carry-over undefined | §16.2; template 26 | Practice. Carry-over not defined as accepted |
| RQ-17 | Control of writes to the record store | §4.6 | Practice. Environment property |

**Accepted semantics relied on (principal).** Roles, authority, actor identity, capacities, self-approval: PS §§4, 5, 6, PR-01 to PR-28. Evidence and knowledge classes, provenance, negative findings, agent agreement, hypotheses: EK §§4, 6, 7, 8. Accepted set, independence declaration, gate slots, validity conditions, standing record and treatments, outcomes, challenge lifecycle, counter-evidence classification, disagreement, escalation, authority gap, conditional progression, exception, revalidation closure, validation, time: GC §§4 to 9, 11 to 13. Boundary tests, formal-check result, CRC-59 finding content, grants and establishment, configuration granularity, handling: RJ §§4, 6.6, 9, 10, 11. Authentication, scope containment, record order, version-binding, views, formal-check result form: RO §§9, 10, 12, 15.

**MOD-W step acceptance checks (`mod-w/step-06.md`).**

| Acceptance check | Where it is met |
| --- | --- |
| Guidance added under `prod-w/` and states it is guidance, not protocol revision | This file; §1.2 |
| Role charters distinguish actor identity, role labels, authority grants, participation capacity, work assignment | `role-charters.md` §2 |
| Project establishment and root-grant practice without modifying D10 | §4 (§4.1 states D10 is not modified) |
| Independence practice for small teams, including authority gaps | §6; §14.3; `role-charters.md` §§6, 7 |
| Evidence guidance distinguishes evidence, counter-evidence, negative findings, assumptions, hypotheses, inferences, decisions | §7.1 |
| Category and threshold practice without universal sufficiency scores | §7.5 |
| Gate guidance: slots, acceptance, refusal, deferral, exception, conditional progression, escalation | §§12, 14 |
| Templates preserve producer, reviewer/challenger, verifier, acceptor, authority, provenance, standing-record distinctions | `templates.md` §0.1 (Common Block), templates 12, 14, 15, 16 |
| Worked examples: one valid progression and one visible non-progression or unresolved disagreement | `worked-examples.md` WE-1 (valid), WE-2 and WE-3 (non-progression and unresolved disagreement) |
| Formal-check guidance records findings without letting checks become acceptance | §11 |
| Actor-kind binding without claiming the protocol proves a human acted | §9; template 25 |
| Source comparability and producing-configuration version binding at practice level | §8 |
| Recovery by new project visible; carry-over not defined as accepted unless marked project practice | §16.2; template 26 |
| Pilot-validation questions routed to STEP-07 and research disposition to STEP-08 | §18 |
| No representation, schema, validator, lifecycle graph, serialized state vocabulary, tool, or publication package selected or implemented | §1.3; §20.2 |
| Any transferability evidence proposed under research governance | §20.4 |
| Final acceptance not recorded until 3a, 3b, 3c occurred or waived | Status block; §20.5 |

### 20.2 Self-checks performed

The Development Team ran these checks on v0.2 before handoff. They are self-run and unreviewed. They are not independent verification.

| Check | Method | Result |
| --- | --- | --- |
| No forbidden tooling or representation selection | Text search of all four files for named schema languages, serialization formats as selections, validators, workflow engines, CLIs, databases, transports, prompt formats, harness names; and review of every place a mechanism is mentioned | See §20.2.1 |
| No numeric sufficiency, score, weight, rank, or percentage | Text search for "score", "weight", "rank", "confidence", "%", "percent", and digits adjacent to evidence words | See §20.2.1 |
| No claim a human acted | Text search for "guarantee", "proves", "verif" near "human" | See §20.2.1 |
| Rule IDs exist | Every PR-, EKR-, GCR-, CRC-, BDR-, HJC-, ACT-, TRG- ID cited was matched to the cited accepted artifact | See §20.2.1 |
| All 28 templates exist and match the index | Counted headings against the index | See §20.2.1 |
| Examples are methodology examples | Every worked example is labelled hypothetical, uses invented facts, and is stated not to be a pilot result | Reviewed by reading |
| Final acceptance not claimed | Status blocks of all four files | Each states Draft, not reviewed, not accepted |
| Accepted artifacts unmodified | `git status` and `git diff` over `mod-w/` and `prod-w/` accepted files | See §20.2.1 |

#### 20.2.1 Results

| Check | Result |
| --- | --- |
| Forbidden selection | The only match for tooling or format words across the four files is the sentence in §1.3 that says none is selected. No schema language, serialization, validator, engine, CLI, database, transport, prompt format, or harness is named as a choice. Mechanisms mentioned in §8.1 (a copy of the text, a revision identifier, a content digest, a dated immutable copy) are listed as options a project may use. None is selected |
| Numeric sufficiency | Every occurrence of "score", "weight", "rank", "confidence", or "%" is in a sentence that forbids or disclaims it. Counts of items in examples (for example "40 sample threads") are descriptions of invented facts, not sufficiency thresholds. §7.5 says a count may appear in a gate definition only as a presence condition |
| No claim a human acted | Every occurrence of "guarantee" or "proves" near "human" is a disclaimer. §9 and template 25 state what may and may not be claimed |
| Rule IDs | A script resolved all 191 distinct identifiers cited across the four files against the accepted artifacts. **None was missing.** This checks existence only. It does not check that the cited rule says what the sentence says. Hand-reading the cited passages found and corrected four meaning errors in the first draft of v0.2 (the TRG-1 definition, a Tier 2 closure rule, who may amend a gate definition, and a closing note shown as an act in a project with no authority). Other citations were checked by reading the passage where it was read (§20.3) and not otherwise |
| Templates | 28 numbered templates exist and match the index in `templates.md` §0.2. Every "template N" reference in the other three files resolves to an existing template |
| Cross-references | Every "G §" and "guidance §" reference in the companion files resolves to an existing heading. One wrong reference (`role-charters.md` to §6.2) was corrected to §6.4 |
| Examples | All eight examples state they are hypothetical, use invented names, products, and sources, and say they are not pilot results |
| Final acceptance | Not claimed in any of the four files |
| Accepted artifacts unmodified | `git status` shows only new untracked files under `prod-w/` and the pre-existing modification to `mod-w/roadmap.md` that was present before this work began. No accepted STEP-01 to STEP-05 artifact is changed |

**What these checks do not show.** That the guidance is usable by a real team; that any practice default is workable (STEP-07's question); that sections not read in full (§20.3) are free of misstatement; or that any accepted rule is correctly paraphrased where only the identifier was resolved. They are self-run by the producer and are not independent verification.

### 20.3 Reading coverage

| Input | Read in full | Sections read or extracted |
| --- | --- | --- |
| `mod-w/step-06.md`, `MODERATOR-REVIEW-STEP-06-SETUP.md`, `roadmap.md`, `domain-language.md` | Yes | |
| `mod-w/architecture.md` | No | D10 read in full. Other decisions extracted by search |
| `mod-w/product.md` | No | Extracted by search only (G-4, AC-2 mention, OQ-7, OQ-8 location). Not read in full |
| `prod-w/protocol-semantics.md` | Mostly | §§4 to 8 read in full. §§9 to 13 not read in full |
| `prod-w/evidence-knowledge-model.md` | No | §§4, 6, 7, 8 and §9.1 read. §§5, 9.2 to 14 extracted by heading and cross-reference only |
| `prod-w/gate-challenge-revalidation-semantics.md` | Mostly | §§4 to 9, 11 to 13 read in full. §§10, 14 to 17 not read in full |
| `prod-w/rule-judgment-boundary.md` | No | §§4, 6.6, 9, 10, 11 read. Selected catalog rows by search. §§5, 7, 8, 12 to 17 not read |
| `prod-w/representation-options.md` | No | §§9.4, 9.5, 10, 12.4 to 12.7, 15 read. §§1 to 8, 11, 13, 14, 16 to 18 not read in full |

Statements about the unread sections are limited to what the read sections or the registers say. A reviewer sampling for misstated rules should concentrate on §§7.3, 7.6, 13.1 (trigger names), 15, and 16.

### 20.4 Transferability evidence

Concrete MOD-W transferability evidence encountered in this step is **proposed under research governance** as **MW-OBS-018** in `research/mod-w-transferability/observations.md`, status proposed, not blocking. In summary: a work package and an accepted register labelled one identifier differently (DM-07); untracked draft files authored before the step's setup approval contradicted accepted text; and the reading-coverage follow-up recorded in MW-OBS-017 recurred (inputs of about 1.2 MB). The Moderator decides whether to accept, modify, or reject it.

### 20.5 Acceptance status

**Not accepted.** Pending: Tech Lead review (3a), QA (3b), Product Owner sign-off (3c), and MOD-W Moderator acceptance (4a), unless 3a to 3c are explicitly waived and recorded. This guide records no review, waiver, or acceptance. Marking the step complete is the Moderator's act.

### 20.6 Files in this delivery

- `prod-w/methodology-guidance.md` (this file; replaces draft v0.1)
- `prod-w/role-charters.md` (replaces draft v0.1)
- `prod-w/templates.md` (replaces draft v0.1)
- `prod-w/worked-examples.md` (new)
- `research/mod-w-transferability/observations.md` (MW-OBS-018 appended, proposed)

No accepted STEP-01 to STEP-05 artifact, `mod-w/` accepted artifact, or other file is changed.

### 20.7 Change notes

| Date | Version | Change | Reason |
| --- | --- | --- | --- |
| 2026-10-04 | 0.1 | Initial draft | STEP-06 Development Team work product |
| 2026-10-04 | 0.2 | Rewritten against the accepted artifacts. Corrected role positions (Product Skeptic removed as a role; PS §4.7), DM-06 and DM-07 meanings, gate slots, treatments, conditional progression elements, and exception content. Added §3 orientation, §6 teams by size, §7.5 category and threshold practice, §8 configuration and source conventions, §9 actor-kind binding, §11 findings and decidability, §14 authority gaps, §15 commitments, §16 grant review and recovery, §17 record versus document, and §18 routing. Added `worked-examples.md`. | Draft v0.1 contradicted accepted semantics in several places and did not meet the acceptance checks |

MOD-W v5.0.1
