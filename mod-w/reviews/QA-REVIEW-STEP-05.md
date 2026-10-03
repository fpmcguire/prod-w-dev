---
artifact:
  type: qa-review
  from: QA
  to:
    - MOD-W Moderator
    - Tech Lead
    - Development Team
    - Product Owner
  date: 2026-10-04
  review_artifacts:
    - prod-w/representation-options.md
    - mod-w/step-05.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-05-SETUP.md
    - mod-w/reviews/TECH-LEAD-REVIEW-STEP-05.md
    - mod-w/reviews/MODERATOR-REVIEW-STEP-05-TECH-LEAD.md
    - research/mod-w-transferability/observations.md#MW-OBS-017
  review_status: APPROVE_FOR_PRODUCT_OWNER_SIGN_OFF_WITH_NON_BLOCKING_FINDINGS
---

# QA Review: STEP-05 Deliverable (Phase 3b)

**Reviewer role:** QA (MOD-W v5.0.1), read-only
**Date:** 2026-10-04
**Review target:** `prod-w/representation-options.md` v0.1 (Draft), as committed at `7c26df2` (141,805 bytes, 1,240 lines)
**Standing:** Phase 3b QA review. This is a review, not an acceptance. Product Owner sign-off (3c) and Moderator final acceptance (4a) are not performed or recorded here. No waiver is recorded or implied. No product artifact, review record, or research register was edited. Line numbers refer to the file as read.

**Finding IDs.** Findings are numbered **QAS5-01** and up (QA, STEP-05) so they cannot be confused with the STEP-04 QA findings QA5-01 to QA5-08, one of which (QA5-03) is the carry-forward item this step answers.

---

## Recommendation

**Approve for Product Owner sign-off, with non-blocking findings.**

- **No High finding.** I found nothing that selects a representation, collapses protocol, schema, and state, turns a judgment into a check, or claims a representation proves a human acted.
- **Three Medium and four Low findings** (QAS5-01 to QAS5-07). All are about whether the demand-class method and the comparison tables can be reproduced by a reviewer, and about one sentence in the QA5-03 definition. None changes a conclusion in Sections 13 or 14.
- **No STEP-04 catalog area is misrepresented.** I found no false statement about what a catalog entry says. The grouping does **hide** demands that some entries make (QAS5-01, QAS5-02). It does not hide or alter any handling category, classification, or UAD4 choice.
- **Acceptance checks:** 21 met, 3 met with a stated limitation (AC5-03, AC5-08, AC5-10), and AC5-25 pending by design. See the table.
- **Development Team revision:** not required (see "Development Team revision" below). A short correction pass is recommended and cheap, and it is best made **before Product Owner sign-off**, because a text change after sign-off needs re-confirmation. QAS5-03 should be settled before the Moderator disposes RQ-01.

---

## Findings (most severe first)

### QAS5-01 - The demand-class mapping hides CD-7 and CD-3 demands, and its reproducibility claim is not accurate

**Severity:** Medium, non-blocking
**Location:** Section 4.2 (CD table), Section 8.1 (mapping), Section 8.2 (fit by class), Section 8.5; AC5-10
**Check:** Tech Lead flagged area (AC5-10)

Section 8.1 says "Where an entry needs several classes, each is listed. A reviewer can sample any row." The rows are catalog **families** (A to H), not entries. The class lists name classes for a family as a whole. I compared them with the 64 catalog rows (`rule-judgment-boundary.md` Section 6.2) and found:

1. **CD-7 appears in no row of Section 8.1.** It is a full column in 8.2 and the basis of the F and X handling categories in 8.5. In the catalog, 17 entries carry F or X handling: CRC-12, 13, 16, 17, 20, 22, 28, 29, 35, 37, 38, 39, 47, 51, 53, 59, 64. Section 4.2 names only CRC-18, 28, and 47 for CD-7. CD-7 is where the families differ most (8.2: RO-01 Con, RO-03/06/07 2nd). A reader composing entry-level fit for a flag-carrying entry (for example CRC-37, CRC-39) from 8.1 and 8.2 cannot tell that CD-7 applies.
2. **Producer-set independence (CD-3) is mapped only for Family B**, with the note "No schema can compute it." The same set-difference is required by CRC-20 and CRC-23 (Family C), CRC-46, CRC-48, CRC-50 (Family F), CRC-55, CRC-57 (Family G), and CRC-64 (Family H). The Family C, F, G, and H rows list no CD-3 for them. The 8.2 label for CD-3 would not change (Con or Can't), but the entries need an evaluator and producer-set data that the rows do not show.
3. **15 of 64 entries are never named in the Section 4.2 example lists:** CRC-02, 04, 09, 10, 15, 17, 20, 22, 31, 35, 46, 57, 58, 59, 64. Several appear only inside a family range heading in 8.1. The memo does not say the lists are partial.
4. **CRC-32 (authority gap)** is placed under CD-5. "No identity can satisfy the independence condition" quantifies over all recorded identities and grants. It is only as good as the completeness of the record, which 8.6 says no one can determine, but 8.1 does not connect the two.
5. **Version-binding and continuity** (UAD5-06, UAD5-16, both level A) have no demand class. They are covered in Family G's row and in 10.5, 12.2, but a reader using only 4.2 to 8.2 would not find them.

**Effect.** The grouping is an adequate analytic method for a desk memo, as the Tech Lead found. Its stated property, that the mapping is a reading a reviewer can sample entry by entry, is overstated. A reviewer can sample only at family level.

**Suggested direction (smallest).** Either (a) add an entry-by-class appendix (64 rows, classes only, no fit labels), or (b) change the 8.1 sentence to say the mapping is family-level and the Section 4.2 lists are examples, and add CD-7 and CD-3 to the rows of Families C to H where they apply. Option (b) is a text edit.

### QAS5-02 - CD-6 mixes a checkable recorded designation with a non-checkable attribution truth

**Severity:** Medium, non-blocking
**Location:** Section 4.2 (CD-6 row), 8.1 Family A, 8.2 (CD-6 row and note), 8.3 (Recorder identity row), 9.5; AC5-10, AC5-12

CD-6 is defined as "that the recorded identity and kind are the ones that acted." That is HJC-21, which the catalog pairs with CRC-01 and CRC-03 precisely because the **check** is only of the recorded designation. Section 8.1 Family A says this itself: "CRC-01 and 03 check a recorded designation (HJC-21)." Section 9.5 says a kind designation "can [be carried by] any family" and 8.3 says for the Recorder identity facet "The recorded kind is checked."

But 4.2 lists CRC-01 and CRC-03 as CD-6 examples, 8.2 labels CD-6 **Can't for every family**, and UAD5-03 says "the weakest cell governs." Applied as written, CRC-01, CRC-03, the Recorder identity facet, and every entry that requires a human AUTH-G holder (CRC-20, 23, 25, 27, 46, 55, 57, 63 and others) come out **Can't in all families**. That contradicts 9.5 and 8.3, and it overstates the limit for a check that families can do (presence of a recorded kind).

**Effect.** No conclusion in 9.5 is wrong. The wrong direction is in the mapping: it makes a checkable designation look uncheckable. A Product Owner or later reader following the weakest-cell rule would reach it.

**Suggested direction.** Split the class. Keep CD-6 for attribution truth and authentication (Can't everywhere, by design), and map the recorded-kind check to CD-1 and CD-2.

### QAS5-03 - One sentence in the QA5-03 definition can reopen the reading it closes

**Severity:** Medium, non-blocking, bears on the Moderator's disposition of RQ-01
**Location:** Section 10.2, Property 3 (lines 643); Property 1; AC5-11

Property 1 says the element is "recorded, not inferred" and that a checker "must not derive 'established by evidence alone' from a claim citing evidence items." That closes the QA5-03 failure scenario (evaluators A and B, three evidence items, no inference; QA-REVIEW-STEP-04-REVISION line 133).

Property 3 then says: "A decision record that cites a claim as established is a recorder of that presentation." Citing a claim in a decision basis is routine (CRC-48, CRC-49). Whether a given citation is "as established" is the same interpretation question. Read literally, the sentence lets a citation count as the designation. Read charitably, it means the decision record must **state** the presentation, but it does not say so.

**Effect.** The Moderator is asked to accept this definition as STEP-05's answer (option (i), recommended in 10.2). If accepted as written, two evaluators could again differ on whether a decision's citation is a recorded presentation, which is the divergence QA5-03 raised.

**Suggested direction.** Reword Property 3 to say that a decision record is a recorder only where it **states** the presentation, and that citing alone is not a designation. This is a one-sentence change and adds no rule.

### QAS5-04 - Some comparison-table labels do not follow from the memo's own rules or tables

**Severity:** Low, non-blocking
**Location:** Section 6.10 (both tables), 9.3, 10.5, 6.4; UAD5-03; AC5-07, AC5-08

The labels are declared as the Development Team's unsampled judgment (17.1), so this is a consistency finding, not a challenge to any one judgment. Three cases I could verify from the memo's own text:

1. **RC-04 (provenance and version-binding) in the hybrid table is Strong for H-1 to H-4, and Strong for RO-07 in the family table.** Section 10.5 closes with "P2 is **2nd for every family, including the best fit**, because ... no family contains that binding," and says H-1 and H-4 "take the RO-02 column" (Con and 2nd throughout). RC-04 is defined to include binding a reference to the version in force. RO-02 is itself Partial for RC-04. H-1 (RO-01 + RO-02, both Partial) cannot be Strong.
2. **RC-01 for RO-04 is Strong†**, but the RC-01 question asks whether the family "invites merging" the layers, and 6.4 lists "Rule creep" ("invites reading a schema pass as governance validity, which is INV-13") as a limit of RO-04. The † note and the reading note explain the intent (Strong for L2 only), but the cell contradicts the criterion's own question.
3. **RC-03 (authority) is Weak for RO-02 and Partial for RO-03**, while in 9.3 the RO-02 and RO-03 columns are identical in every row (R1 to R12). RC-05 is Weak for RO-01 and Partial for RO-02 and RO-03, while all three are Con for CD-3 and 2nd for CD-4 in 8.2.

**Effect.** The memo says nothing is scored or ranked (ROR-06) and none of these cells drives a conclusion in 13 or 14. They still weaken the claim that criteria are "used consistently across options," which `mod-w/step-05.md` asks for. Case 1 flatters the hybrids, including H-1, which Z-2 rejects for acts.

**Suggested direction.** Correct RC-04 for H-1 to H-4 (and RO-07) or state why the criterion differs from P2. Re-read the other cells against 8.2 and 9.3.

### QAS5-05 - The "Suitable only as" summary does not match the role table

**Severity:** Low, non-blocking
**Location:** Section 6.11 (table and the four bullets below it); AC5-15

The table marks RO-05 **S** for methodology support and RO-01 **S (reports)** for advisory tooling output. The summary bullets list methodology support as "RO-09, and RO-01 as a human document" and advisory tooling support as "RO-04 output, RO-03 output, and RO-09," omitting both. The table is the fuller statement. The bullets are what the Scope asked for ("suitable only as schema support, state support, methodology support, or advisory tooling support").

### QAS5-06 - Hybrids and RO-09 are evaluated more thinly than the nine-family framing suggests

**Severity:** Low, non-blocking
**Location:** Section 7 (last row), 10.5, 11.2; AC5-03, AC5-08, AC5-09

- **Section 7** gives hybrids one pooled row ("H-1 to H-4: See Section 6.8") with no per-design protocol, schema, and state cell. D2 is "evaluated separately for every option." The reading paragraph does state the layer fit of H-2, H-3 versus H-1, H-4, so the substance is present, but not per hybrid.
- **Section 10.5** has no RO-09 column and says only that hybrids "follow the same logic." RO-09's provenance role is in 6.9 and UAD5-06, so nothing is missing in substance. The omission is unstated.
- **Section 11.2** gives prose for RO-01 to RO-09 but not for H-1 to H-4. It says it is "composed from Section 8.2 by the weakest cell," which a reader can do through 11.1's class column.

### QAS5-07 - Carry-forward section does not say which STEP-04 items it is not carrying

**Severity:** Low, non-blocking, informational
**Location:** Section 16.1; AC5-20, AC5-21

Section 16.1 is titled "STEP-04 carry-forward items." It contains the STEP-05-owned items, TLR5-01, and MW-OBS-016. It does not mention F-1, F-3, F-4, F-6, or QA5-07, which the Moderator acceptance record routes to STEP-06, STEP-07, or Moderator disposition. Nothing is lost, because none is representation-owned and each has another owner. A one-line statement would make the omission visible rather than silent. F-4 (volume of flags and false findings) is partly covered by RQ-13.

---

## What I sampled

### Option coverage (AC5-02, AC5-03, AC5-15, AC5-16)

- All nine families in `mod-w/step-05.md` Scope are present as RO-01 to RO-09 in Section 6, each with the same headings (what it is, layer, strengths, limits, cannot carry alone, hidden decisions, suitable only as). RO-06 is split into registry and stored condition, and RO-07 into relationship records and ledger properties. The splits follow accepted semantics and are not additions.
- Hybrids: H-1 to H-4 are a table with source of truth, composition, benefit, and cost. "Hybrid as a family of designs, not a compromise" (Tech Lead Recommendation 3) is stated and applied.
- Cross-checked 6.10, 6.11, 7, 9.3, 10.5, 11.2, and 13.2 for each family. Gaps are QAS5-05 and QAS5-06 only.
- The 18 items of "Required Output Structure" map to Sections 1 to 18 of the memo in order. Section 4 defines all eight required terms.

### Traceability (AC5-04 to AC5-06, AC5-11, AC5-12, AC5-14, AC5-17 to AC5-25; Section 16, Section 17)

- **Acceptance-check table (Section 17).** Compared the 25 AC5 rows with the 25 checks in `mod-w/step-05.md`, in order and by wording. They match.
- **Quotations and rule statements checked against source.**
  - F-5 and QA5-03 text against `MODERATOR-REVIEW-STEP-04-ACCEPTANCE.md` Section 4: matches, including "CRC-45 is unresolved where none exists."
  - QA5-03 failure scenario against `QA-REVIEW-STEP-04-REVISION.md` line 133: matches.
  - CRC-45 text, handling (N, U), evaluation kind (S), and the "unresolved, not read as satisfied" rule against the catalog: matches.
  - CRC-06, 07, 09, 14, 22, 24, 26, 36, 54, 56, 59, 60 to 64 as characterized in 6.4, 8.1, 9.1, 10.1, 11.1: match. The "four", "nine", and "four" element counts in 6.4 match CRC-26, CRC-23, CRC-60.
  - The eight facets of 8.3 against Section 4.5 of the boundary artifact: match. The seven handling categories of 8.5 against Section 6.1: match.
  - HJC-12, 16, 18, 21 to 26 as described in 8.4: consistent with the catalog's pairs.
  - Boundary-artifact section references 4.10, 5.4, 9.4.3 to 9.4.5, 9.5, 9.6, 9.7, 11.2, 11.3, 12.1, 12.6, 12.7, 13.10, 15.4: each heading exists.
  - `mod-w/product.md` OQ-8 and E-1 as quoted: match. Roadmap STEP-05 to STEP-09 goals and the statement "the roadmap has no experiment step" (P-2): match. PS-OQ-01 and EK-OQ-11 are the same item as routed.
  - INV-01 to INV-17: 17 examples, as 14.4 says.
- **MW-OBS-017 evidence.** File sizes of the eight named inputs sum to 981,320 bytes (rule-judgment-boundary.md 527,934; gate-challenge-revalidation-semantics.md 173,232; evidence-knowledge-model.md 104,449; protocol-semantics.md 69,101; product.md 48,554; architecture.md 24,245; domain-language.md 22,324; roadmap.md 11,481). This matches the observation's "about 981 KB." The observation is marked Proposed and non-blocking, and does not alter MOD-W.
- **MW-OBS-017 follow-up question** ("does QA sampling find a misstated accepted rule among statements marked as extracted?"). Answer from this sample: **no misstated accepted rule found.** The sample is partial (see Limits). The findings above concern the memo's own analytic apparatus, not its quotation of accepted text.

### Comparison criteria (AC5-03, AC5-15; Section 5, 6.10)

- Section 5 defines RC-01 to RC-15, each with a question and a source. All ten criteria listed in `mod-w/step-05.md` are covered (separation, coverage, auditability, readability, diffability, provenance, independence, revalidation, portability, premature-selection risk), plus authority, challenge and gate, boundary preservation, tamper locality, and view derivability.
- Qualitative labels only. No number, total, weight, rank, or confidence appears. I scanned for score, weight, rank, confidence, and percent. Every hit is a prohibition, a non-selection statement, or an experiment exclusion. The ordinal labels (Strong, Partial, Weak, Moderate and High risk) are explicitly unsummed (ROR-06, UAD5-03).
- Consistency of labels across tables: QAS5-04.

### Carry-forward routing (AC5-11, AC5-12, AC5-13, AC5-20, AC5-21; Sections 9.5, 10, 12, 15, 16)

- Every STEP-05-owned item in the STEP-04 routing records is addressed: QA5-03 (10.2), F-5 and DR-07 (9.5), DR-01 to DR-10, RJ-OQ-01, 02, 03a, 04, 10, GC-OQ-04, GC-OQ-05, EK-OQ-11, 12, 15, PS-OQ-01, H-C. Section 16.1 maps each to a section.
- RQ-01 to RQ-19: each names an owner. Owners are consistent with the roadmap (STEP-06 methodology, STEP-07 pilot, STEP-08 synthesis, STEP-09 publication) and with the STEP-04 routing table. "Later architecture" is a Scope-listed route in `mod-w/step-05.md`.
- STEP-05 does not take over STEP-06 or STEP-07 work: no templates, charters, worked examples, or pilot content are present. RX-1 fixtures are drawn from accepted material only (14.4).
- The memo does not record Moderator acceptance of anything. It records Draft status (front matter, 2.3, 17).
- Residual: QAS5-07 (unstated non-ownership of F-1, F-3, F-4, F-6, QA5-07).

### AC5-10: demand-class grouping (Tech Lead flagged area)

I extracted the 64 catalog rows and compared them to Sections 4.2, 8.1, and 8.2:

- **Is the grouping adequate?** As an analytic method for this step, yes. It is declared (UAD5-02), qualitative, and does not reclassify. The family-level rows read correctly for the demands they list.
- **Is any catalog area misrepresented?** No. I found no row that states a catalog rule wrongly.
- **Is any catalog area hidden by the grouping?** Yes, in the sense of **omitted demands**, not misdescribed ones: CD-7 (visibility) is attached to no family; producer-set independence is shown only for Family B; version-binding has no class; CD-6 is defined so that it contradicts 9.5 (QAS5-01, QAS5-02). Family H also omits the timing limb of CRC-60 ("takes effect when recorded"), which is a CD-4 demand and is covered under CRC-24 in 10.4.
- Handling categories (8.5) are given per category with the families that fall short, not per entry. This is consistent with the declared method.

### RX-1 (AC5-17 to AC5-19; Section 14)

Read in full. It states purpose, scope (two arms, throwaway encodings), inputs (accepted material only), qualitative success and failure signals, exclusions, and a six-step review gate. It is severable (14.1), not implemented, and says its success selects nothing and its failure rejects nothing (14.5). Prerequisites P-1 to P-4 are Moderator-visible and none requires running the experiment. The case rests on one producer's desk reading, which the memo says (14.2).

---

## Acceptance-check status, AC5-01 to AC5-25

"Met" is QA's assessment from the sampling above. It is not acceptance.

| Check | QA status | Note |
| --- | --- | --- |
| AC5-01 | Met | Front matter, 1.2, ROR-01 |
| AC5-02 | Met | All nine families, 6.1 to 6.9, with hybrids in 6.8 |
| AC5-03 | Met, limitation | Families evaluated separately in Section 7. Hybrids share one pooled row (QAS5-06) |
| AC5-04 | Met | ROR-02; 6.4 |
| AC5-05 | Met | ROR-03; 12.1 |
| AC5-06 | Met | ROR-04; Section 4 (Adapter) |
| AC5-07 | Met | 9.2, 9.3, 9.4 cover identity, capacity, grants, conferral scope, independence, D10 chain. Labels are unsampled judgment (17.1). Cross-label inconsistency noted in QAS5-04 |
| AC5-08 | Met, limitation | 10.3 and 10.5, 11.5. RO-09 has no column in 10.5 (QAS5-06). RC-04 labels (QAS5-04) |
| AC5-09 | Met | 11.1 to 11.5. Hybrids by composition (QAS5-06) |
| AC5-10 | Met, limitation | Demand-class method is declared and adequate. Reproducibility claim overstated and some demands omitted (QAS5-01, QAS5-02) |
| AC5-11 | Met | Defined in 10.2 and routed for disposition (RQ-01, RQ-02). Property 3 should be reworded (QAS5-03) |
| AC5-12 | Met | 9.5 and Z-10. No claim that a representation proves a human acted. I found none anywhere in the memo |
| AC5-13 | Met | 12.1 to 12.7, 10.4 |
| AC5-14 | Met | 8.3, 8.4, 8.6 |
| AC5-15 | Met | "Cannot carry alone" in 6.1 to 6.9, Section 7. Summary bullets in 6.11 out of sync (QAS5-05) |
| AC5-16 | Met | 6.1 to 6.9, 13.2 |
| AC5-17 | Met | 14.1, 14.2 |
| AC5-18 | Met | 14.4 |
| AC5-19 | Met | 14.1, 14.5 |
| AC5-20 | Met | 15.1, 15.2 |
| AC5-21 | Met | RQ-12; 15.2 |
| AC5-22 | Met | No schema language, store, engine, validator, graph, vocabulary, transport, CLI, prompt format, harness, runtime integration, database, API, or package is selected. Examples of classes (JSON Schema, YAML) appear only because Scope names them |
| AC5-23 | Met | No score, weight, rank, or confidence. Ordinal labels unsummed |
| AC5-24 | Met | MW-OBS-017 is present, concrete, Proposed, non-blocking. Moderator disposition is pending. Evidence figures verified |
| AC5-25 | Pending by design | The memo records Draft status. This QA record, Tech Lead review, and Moderator Tech Lead review do not constitute final acceptance. Product Owner sign-off is pending and no waiver is recorded |

---

## Development Team revision

**Not required** before Product Owner sign-off or Moderator final acceptance. No finding is High. None changes a classification, handling category, UAD5 level, rejection (Section 13), or the RX-1 recommendation.

**Recommended** (text edits, no new semantics), preferably before Product Owner sign-off:

1. QAS5-03: reword Property 3 of Section 10.2. Settle this before the Moderator disposes RQ-01.
2. QAS5-01 and QAS5-02: correct the Section 8.1 reproducibility sentence, add CD-7 and CD-3 to the rows where they apply, and split or restate CD-6.
3. QAS5-04 to QAS5-07: align the cited labels, bullets, and the one-line scope statement.

If the Moderator prefers not to revise, these can be carried as named soft spots with the memo's existing statement that all labels are unsampled desk judgment (17.1). That choice is the Moderator's.

---

## Moderator-visible items

1. **Whether to make the recommended correction pass** (above), or carry QAS5-01 to QAS5-07 as recorded soft spots.
2. **QA5-03 disposition (RQ-01, RQ-02).** Option (i) is recommended by the memo. QAS5-03 bears on whether the definition, as worded, actually closes the evaluator-divergence path.
3. **RX-1 authorization and placement (RQ-18, P-2).** The roadmap has no experiment step. Not a QA decision.
4. **Scope containment and record order (RQ-03, RQ-04).** Open authority questions that no accepted artifact answers. Not a Development Team defect.
5. **MW-OBS-017 disposition.** Proposed, non-blocking.
6. **Same-vendor review.** This QA review, the Tech Lead review, and the memo itself were all produced by Claude-family models. Under PR-27 and PR-28 that is not independent corroboration. The memo states it (2.4, RQ-16). No role outside the producing configuration has reviewed STEP-05.
7. **Gate sequencing.** Product Owner sign-off is pending. No waiver is recorded.

---

## Limits of this review

- **Desk review of one memo by one reviewer.** I built or ran nothing. I did not test any family against a record. I cannot confirm any fit label. I can only compare labels with each other and with the memo's own text (QAS5-04).
- **Partial source verification.** I checked the quotations and rule statements listed under "Traceability" against source, and I read in full the catalog (`rule-judgment-boundary.md` Section 6.2, CRC-01 to CRC-64), Sections 4.5 and 6.1, 9.4.4 and 9.4.5, and the STEP-04 acceptance and post-acceptance records. I did **not** re-read all of the memo's statements about STEP-02 and STEP-03 rules, `rule-judgment-boundary.md` Sections 7, 8, 10.2 to 10.4, 13.1 to 13.7, 14.2, 15 to 17, `mod-w/domain-language.md`, or `research/` notes other than MW-OBS-017. A statement drawn from those and not listed above was not checked. The memo's reading-coverage statement (2.4) says which of its statements rest on extracted text, and my sample does not cover all of them.
- **Demand-class mapping.** I checked the mapping against the 64 catalog rows by reading and by a throwaway script that extracted the entry numbers named in Section 4.2 and counted CD-6 and CD-7 in 8.1 rows. I did not build an independent entry-by-class mapping, so I cannot say the classes would otherwise be right.
- **Mechanical checks.** I did not repeat the Tech Lead's identifier-sequence check (RC, RO, ROR, RQ, AC5, UAD5, RF, VI, CD, H, P). I rely on it, and my own reading found no gap in those sequences. No executable validation exists for this repository.
- **Same-vendor limit.** See Moderator-visible item 6.
- **Not reviewed.** Product Owner sign-off. Moderator acceptance. Whether RX-1 should run. Whether any UAD5 choice should be promoted to architecture. Whether the memo is suitable as a publication artifact.
- **Absence of other findings** does not show that no other inconsistency or unlisted choice remains. I ran no adversarial review beyond the paths above.

---

MOD-W v5.0.1
