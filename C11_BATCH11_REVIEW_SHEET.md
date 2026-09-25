# T-C11 §16 Batch 11 Review Sheet — Concept / Prerequisite / Misconception Graph

Slice 4CH1–4.38C–4.50C (Section 4 — Organic Chemistry, THIRD slice: g Esters + h Synthetic polymers, 13 authorable SPs; the 4CH1-4.43C practical-typed SP rides the scoped T-C10 practical 4CH1-PR-12 — the batch-3 1.60C/PR-04 precedent; the 4CH1-4.15 negative-control carve-out sits in S4-b and is untouched) · generated 2026-09-25 · decision record `scripts/c11_batch11_decisions.yaml` (pass 1: `c11-s16-batch-11`) · adversarial pass 2: `scripts/c11_batch11_review_pass2.yaml` · authorization: `scripts/c11_s16_authorization.yaml` (§16 authorized 2026-09-12; batch 11 = the final slice of the S4 section program — batch 11 COMPLETES S4 — commissioned by the operator's 'commission batch 11' directive) · boundary ruling: `scripts/c11_batch11_boundary_ruling.yaml` (session 66, machine-checked — the TWELVE sanctioned boundary edges below)

**NOTHING in this batch is authoritative.** All 5 nodes / 29 batch edges (17 authored semantic + 12 derived PART_OF) are AI_SUGGESTED (SUGGESTED). HUMAN_VALIDATED is reachable only by your promotion command via the §18 pathway (`scripts/c11_promote.py` → `scripts/c11_promotions.yaml` → regeneration). **Zero batch-11 promotions exist.** This sheet is the batch's operator gate: record verdicts in `scripts/c11_batch11_verdicts_template.yaml` (fill + rename to `c11_batch11_verdicts.yaml`); a later session encodes and applies them.

How to review: for each row check the quoted evidence actually appears in the cited file and actually says what the record claims; then rule on the relation CLASS and direction, not just existence. Machine state: the full gate suite is green at the merged 193-node / 488-edge store; every quote is machine-verified against its source file (G03/c11.4; 33 quote probes + preverify checks verified BEFORE the registry grew); the 4.15 negative control is uncovered. TWELVE edges are cross-section boundary edges into the TWELVE ruled targets (TEN existing owners: CON-ALCOHOLS and CON-CARBOXYLIC-ACIDS — the batch-10 owners, x2 each; CON-ALKENES — the batch-10 owner; CON-ORGANIC-FORMULAE, CON-IUPAC-NAMING, CON-ORGANIC-REACTION-CLASSES and CON-CO-POISONING — the batch-9 owners; CON-CO2-GREENHOUSE — the batch-5 owner; CON-SIMPLE-DISTILLATION — the batch-1 owner; CON-ACID-REACTIONS — the batch-7 owner; sanctioned per the session-66 cross-slice ruling; no duplicate concept was minted). The slice is MS-pinned PARTIAL with three-pin documentation (the Synthetic Polymers MS is the only Paper-2 MS file for the S4-h family — its Q4(c) is the same paper question as the Alkenes MS Q2(c), whose Reject column anchors the ONE misconception mint; the Crude Oil MS carries the condensation/biodegradation/inertness rows; the esters families have no dedicated Paper-2 MS file). NO pass-2 finding required re-authoring (FP-B11-1..4 / FN-B11-1..3 are recorded questions and resolutions).

## 1. Totals & second-pass agreement

| | nodes | authored edges | held | |
|---|---|---|---|---|
| pass-1 (extraction) | 5 | 17 (+12 derived PART_OF) | 10 |
| pass-2 verdicts | 5 CONFIRM | 17 CONFIRM · 0 HOLD · 0 REJECT | all 10 AGREE |

Raw agreement (NOT κ — single human rater, architecture §12): nodes 5/5 = 100.0%; edges — of the 17 edges pass-1 asserted (SUGGESTED), pass-2 confirmed 17 (100.0%); pass-1 quarantined 0 edges as REVIEW_REQUIRED (this batch authored NONE — every doubt was held or resolved on explicit evidence). **Zero pass-2 findings required re-authoring; zero demotions.**

Forecast calibration (C11_BATCH_FORECAST.json future_batch_records): the batch-11 record is appended by the forecast instrument at this gate (see the regenerated C11_BATCH_FORECAST.json). The S4-g/h slice runs in the deepest consolidation band (nodes/SP 0.38, edges/SP 1.31), with the held adjacencies (B11-H-01..10 — the surfaces the ruling dispositioned) accounting for the gap, not thin coverage: no S1/S2/S3 or batch-9/10 identity was re-minted (the TEN existing-owner targets reached via the TWELVE sanctioned boundary edges); the 4.43C practical rides the scoped PR-12 (the PR lane is node-free by the batch-3 precedent).

## 2. Concept & misconception nodes (5)

| # | code | family | title | attaches to (role) | conf | evidence (anchor → quote) | pass-2 | operator |
|---|---|---|---|---|---|---|---|---|
| 1 | `4CH1-CON-ESTERS` | CONCE | Esters (the R-COO-R functional group, esterification of alcohols with carboxylic acids, ethyl ethanoate, the -yl/-oate naming, volatile sweet-smelling uses) | 4CH1-4.38C (core); 4CH1-4.39C (core); 4CH1-4.40C (core); 4CH1-4.41C (core); 4CH1-4.42C (core) | high | NOTE: “Esters are compounds with the functional group R-COO-R” | CONFIRM | ☐ |
| 2 | `4CH1-CON-ADDITION-POLYMERS` | CONCE | Addition polymers (monomers joined by C=C opening, the repeat unit with extension bonds and subscript n, deducing the monomer) | 4CH1-4.44 (core); 4CH1-4.45 (core); 4CH1-4.46 (core) | high | NOTE: “Polymers are large molecules of **high relative molecular mass** and are made by” | CONFIRM | ☐ |
| 3 | `4CH1-CON-POLYMER-DISPOSAL` | CONCE | Disposal of addition polymers (landfill non-biodegradability; incineration products — carbon dioxide, toxic hydrogen chloride, carbon monoxide) | 4CH1-4.47 (core) | high | NOTE: “Waste polymers are disposed of in landfill sites but this takes up valuable land” | CONFIRM | ☐ |
| 4 | `4CH1-CON-CONDENSATION-POLYMERS` | CONCE | Condensation polymerisation and polyesters (dicarboxylic acid + diol, the ester link with one water per link, deducing the monomers, biopolyesters) | 4CH1-4.48C (core); 4CH1-4.49C (core); 4CH1-4.50C (core) | high | NOTE: “For every ester linkage formed in condensation polymerisation, one molecule of w” | CONFIRM | ☐ |
| 5 | `4CH1-MIS-POLYMER-DOUBLE-BOND` | MISCO | Drawing a double-bonded product for the addition-polymer repeat unit (the C=C not opened to a single bond) | — | high | MARK_SCHEME: “Any double-bonded product scores 0/2” | CONFIRM | ☐ |

Identity-policy notes (split-first; merges are operator-only, OD-1 operand rule): pass-2 flags the 4.38C-4.42C one-family ruling (B11-ID-01), the 4.44-4.46 one-family ruling (B11-ID-02), the 4.48C-4.50C one-family ruling with the biopolyesters fold (B11-ID-03), and the ONE single-Reject-column misconception mint (B11-ID-04). All are operator identity decisions (template §identity_decisions). The 4CH1-4.43C practical SP carries NO node (the batch-3 1.60C/PR-04 precedent — the practical's edges are PR-anchored, rows 5-7 below).

## 3. Authored semantic edges (17)

| # | edge | conf | derivation | evidence (anchor → quote) | pass-2 | operator |
|---|---|---|---|---|---|---|
| 1 | `4CH1-CON-ESTERS REQUIRES_PREREQUISITE 4CH1-CON-ALCOHOLS` | high | USED_WITHOUT_RETEACHING | NOTE: “Alcohols and carboxylic acids react to make esters in **esterification** reactio” | CONFIRM | ☐ |
| 2 | `4CH1-CON-ESTERS REQUIRES_PREREQUISITE 4CH1-CON-CARBOXYLIC-ACIDS` | high | USED_WITHOUT_RETEACHING | NOTE: “Ethanoic acid will react with ethanol in the presence of concentrated sulfuric a” | CONFIRM | ☐ |
| 3 | `4CH1-CON-ESTERS REQUIRES_PREREQUISITE 4CH1-CON-ORGANIC-FORMULAE` | high | USED_WITHOUT_RETEACHING | NOTE: “CH3COOH + C2H5OH → CH3COOC2H5 + H2O” | CONFIRM | ☐ |
| 4 | `4CH1-CON-ESTERS REQUIRES_PREREQUISITE 4CH1-CON-IUPAC-NAMING` | high | USED_WITHOUT_RETEACHING | NOTE: “E.g. The ester formed from **pent**anol and **butan**oic acid is called **pent**” | CONFIRM | ☐ |
| 5 | `4CH1-PR-12 REQUIRES_PREREQUISITE 4CH1-CON-ESTERS` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “To prepare a small sample of ethyl ethanoate” | CONFIRM | ☐ |
| 6 | `4CH1-PR-12 REQUIRES_PREREQUISITE 4CH1-CON-SIMPLE-DISTILLATION` | high | USED_WITHOUT_RETEACHING | NOTE: “The ester is then distilled off as soon as it is formed and collected in a separ” | CONFIRM | ☐ |
| 7 | `4CH1-PR-12 REQUIRES_PREREQUISITE 4CH1-CON-ACID-REACTIONS` | high | USED_WITHOUT_RETEACHING | NOTE: “To remove acidic impurities, sodium carbonate solution can be added, until the m” | CONFIRM | ☐ |
| 8 | `4CH1-CON-ADDITION-POLYMERS REQUIRES_PREREQUISITE 4CH1-CON-ALKENES` | high | USED_WITHOUT_RETEACHING | NOTE: “Many polymers can be made by the addition of alkene monomers” | CONFIRM | ☐ |
| 9 | `4CH1-CON-ADDITION-POLYMERS REQUIRES_PREREQUISITE 4CH1-CON-ORGANIC-REACTION-CLASSES` | high | USED_WITHOUT_RETEACHING | NOTE: “This process is called **addition polymerisation**” | CONFIRM | ☐ |
| 10 | `4CH1-MIS-POLYMER-DOUBLE-BOND WRONG_ANSWER_PATTERN 4CH1-CON-ADDITION-POLYMERS` | high | ASSESSMENT_DOCUMENTED | MARK_SCHEME: “Any double-bonded product scores 0/2” | CONFIRM | ☐ |
| 11 | `4CH1-MIS-POLYMER-DOUBLE-BOND REMEDIATED_BY 4CH1-CON-ADDITION-POLYMERS` | high | ASSESSMENT_DOCUMENTED | NOTE: “To draw a repeat unit, change the double bond in the monomer to a **single bond*” | CONFIRM | ☐ |
| 12 | `4CH1-CON-POLYMER-DISPOSAL REQUIRES_PREREQUISITE 4CH1-CON-ADDITION-POLYMERS` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “This makes addition polymers unreactive and chemically **inert** so don’t easily” | CONFIRM | ☐ |
| 13 | `4CH1-CON-POLYMER-DISPOSAL REQUIRES_PREREQUISITE 4CH1-CON-CO2-GREENHOUSE` | high | USED_WITHOUT_RETEACHING | NOTE: “Polymers release a lot of heat energy when they burn and produces carbon dioxide” | CONFIRM | ☐ |
| 14 | `4CH1-CON-POLYMER-DISPOSAL REQUIRES_PREREQUISITE 4CH1-CON-CO-POISONING` | high | USED_WITHOUT_RETEACHING | NOTE: “If incinerated by incomplete combustion, carbon monoxide will be produced which ” | CONFIRM | ☐ |
| 15 | `4CH1-CON-CONDENSATION-POLYMERS REQUIRES_PREREQUISITE 4CH1-CON-ESTERS` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “An ester linkage is formed with the subsequent loss of **one** water molecule pe” | CONFIRM | ☐ |
| 16 | `4CH1-CON-CONDENSATION-POLYMERS REQUIRES_PREREQUISITE 4CH1-CON-CARBOXYLIC-ACIDS` | high | USED_WITHOUT_RETEACHING | NOTE: “An example is terylene which is a **polyester** made from **dicarboxylic** acid ” | CONFIRM | ☐ |
| 17 | `4CH1-CON-CONDENSATION-POLYMERS REQUIRES_PREREQUISITE 4CH1-CON-ALCOHOLS` | high | USED_WITHOUT_RETEACHING | NOTE: “The monomers have two **functional** groups present, one on **each end**” | CONFIRM | ☐ |

TWELVE edges are CROSS-SECTION boundary edges into the TWELVE ruled targets (sanctioned per the session-66 cross-slice ruling — no duplicate mint): the esterification-reactant rows x2 and the diol/dicarboxylic monomer rows x2 (into the batch-10 CON-ALCOHOLS and CON-CARBOXYLIC-ACIDS owners), the formulae-toolkit row and the naming-construction row (into the batch-9 CON-ORGANIC-FORMULAE and CON-IUPAC-NAMING owners), the practical's distil-off row and carbonate-purification row (into the batch-1 CON-SIMPLE-DISTILLATION and batch-7 CON-ACID-REACTIONS owners), the C=C-monomer row and the addition-class row (into the batch-10 CON-ALKENES and batch-9 CON-ORGANIC-REACTION-CLASSES owners), and the incineration rows (into the batch-5 CON-CO2-GREENHOUSE and batch-9 CON-CO-POISONING owners). The THREE in-slice RP edges carry the teaching sequence the notes themselves establish (S4-h presupposes S4-g; the disposal note presupposes the addition-polymer surface; the practical instantiates the esterification).

## 4. Held candidates (10) — the abstention record

| id | candidate | failure class / reason |
|---|---|---|
| B11-H-01 | REQUIRES_PREREQUISITE(CON-ESTERS, CON-CATALYST) | MECHANISM-APPLIED-AS-GIVEN |
| B11-H-02 | REQUIRES_PREREQUISITE(CON-ESTERS, CON-SIMPLE-MOLECULAR) | AVAILABLE-BUT-SURFACE-MINIMAL |
| B11-H-03 | REQUIRES_PREREQUISITE(CON-ADDITION-POLYMERS, CON-CATALYST) | MECHANISM-APPLIED-AS-GIVEN |
| B11-H-04 | REQUIRES_PREREQUISITE(CON-ADDITION-POLYMERS, CON-ORGANIC-FORMULAE) | BOUNDARY-TARGETS-ONCE |
| B11-H-05 | REQUIRES_PREREQUISITE(CON-ADDITION-POLYMERS, CON-COVALENT-BOND) | VOCABULARY-APPLIED-AS-GIVEN |
| B11-H-06 | REQUIRES_PREREQUISITE(CON-ADDITION-POLYMERS, CON-IUPAC-NAMING) | AVAILABLE-BUT-SURFACE-MINIMAL |
| B11-H-07 | REQUIRES_PREREQUISITE(CON-CONDENSATION-POLYMERS, CON-ORGANIC-FORMULAE) | BOUNDARY-TARGETS-ONCE |
| B11-H-08 | REQUIRES_PREREQUISITE(CON-CONDENSATION-POLYMERS, CON-REVERSIBLE) | ENRICHMENT-NOT-LOAD-BEARING |
| B11-H-09 | REQUIRES_PREREQUISITE(CON-POLYMER-DISPOSAL, CON-FUELS-COMBUSTION) | SAME-FAMILY-ADJACENCY / BOUNDARY-TARGETS-ONCE |
| B11-H-10 | REQUIRES_PREREQUISITE(4CH1-PR-12, CON-REVERSIBLE) | EXPLANATION-DEEPER-THAN-DEMAND |

Every held candidate cites its §19 failure class; the abstention record remains part of the graph provenance. A held record is a valid outcome — the abstention is the system's honest output.

## 5. Operator verdict surface

- **17 SUGGESTED edges** (B11-E-01..17) — the §18 promotion surface
- **5 nodes** (4 CONCEPT B11-N-01..04 + 1 MISCONCEPTION B11-M-01) — node authority stays SUGGESTED; nodes have no §18 pathway (node promotion is a separate identity decision, deferred)
- **4 identity decisions** (B11-ID-01..04) — MERGE/SPLIT/KEEP_AS_IS
- **10 held candidates** — acknowledge the quarantine (no reopening)
- **0 REVIEW_REQUIRED edges** — zero RR settlements needed

Pathway: fill `scripts/c11_batch11_verdicts_template.yaml` → rename to `c11_batch11_verdicts.yaml` → a later session encodes + applies via `c11_verdict_encode_batch11`-style reconciliation + `c11_promote.py` (§18) + the gated generator re-run. NOTHING is promoted at this gate. Batch 11 completes S4 — after this verdict session the §16 S1-S4 authoring program is complete.
