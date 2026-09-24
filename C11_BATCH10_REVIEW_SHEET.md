# T-C11 §16 Batch 10 Review Sheet — Concept / Prerequisite / Misconception Graph

Slice 4CH1–4.23–4.37C (Section 4 — Organic Chemistry, SECOND slice: d Alkenes + e Alcohols + f Carboxylic acids, 15 authorable SPs; no practicals own any batch-10 SP; the 4CH1-4.15 negative-control carve-out sits in S4-b and is untouched) · generated 2026-09-25 · decision record `scripts/c11_batch10_decisions.yaml` (pass 1: `c11-s16-batch-10`) · adversarial pass 2: `scripts/c11_batch10_review_pass2.yaml` · authorization: `scripts/c11_s16_authorization.yaml` (§16 authorized 2026-09-12; batch 10 = the second slice of the S4 section program, commissioned by the operator's 'commission batch 10' directive) · boundary ruling: `scripts/c11_batch10_boundary_ruling.yaml` (session 64, machine-checked — the THIRTEEN sanctioned boundary edges below)

**NOTHING in this batch is authoritative.** All 8 nodes / 34 batch edges (19 authored semantic + 15 derived PART_OF) are AI_SUGGESTED (SUGGESTED). HUMAN_VALIDATED is reachable only by your promotion command via the §18 pathway (`scripts/c11_promote.py` → `scripts/c11_promotions.yaml` → regeneration). **Zero batch-10 promotions exist.** This sheet is the batch's operator gate: record verdicts in `scripts/c11_batch10_verdicts_template.yaml` (fill + rename to `c11_batch10_verdicts.yaml`); a later session encodes and applies them.

How to review: for each row check the quoted evidence actually appears in the cited file and actually says what the record claims; then rule on the relation CLASS and direction, not just existence. Machine state: the full gate suite is green at the merged 188-node / 459-edge store; every quote is machine-verified against its source file (G03/c11.4; 37 quote probes + preverify checks verified BEFORE the registry grew); the 4.15 negative control is uncovered. THIRTEEN edges are cross-section boundary edges into the ELEVEN ruled targets (CON-HOMOLOGOUS-SERIES and CON-ORGANIC-FORMULAE — the batch-9 owners, x2 each; CON-HYDROCARBON, CON-ALKANES, CON-ORGANIC-REACTION-CLASSES, CON-IUPAC-NAMING and CON-CRACKING — the batch-9 owners; CON-COMBUSTION-O2 — the batch-5 owner; CON-OX-RED-AGENTS — the batch-6 owner; CON-FRACTIONAL-DISTILLATION — the batch-1 owner; CON-ACID-REACTIONS — the batch-7 owner; sanctioned per the session-64 cross-slice ruling; no duplicate concept was minted). The slice is MS-pinned PARTIAL (the Alkenes MS is the only Paper-2 mark scheme for the S4-d/e/f families: its Q4(b)(ii) Reject column anchors the ONE misconception mint and its Q2(a)(ii) accept/reject rows anchor the bromine-water-test language). NO pass-2 finding required re-authoring (FP-B10-1..6 / FN-B10-1..2 are recorded questions and resolutions).

## 1. Totals & second-pass agreement

| | nodes | authored edges | held | |
|---|---|---|---|---|
| pass-1 (extraction) | 8 | 19 (+15 derived PART_OF) | 9 |
| pass-2 verdicts | 8 CONFIRM | 19 CONFIRM · 0 HOLD · 0 REJECT | all 9 AGREE |

Raw agreement (NOT κ — single human rater, architecture §12): nodes 8/8 = 100.0%; edges — of the 19 edges pass-1 asserted (SUGGESTED), pass-2 confirmed 19 (100.0%); pass-1 quarantined 0 edges as REVIEW_REQUIRED (this batch authored NONE — every doubt was held or resolved on explicit evidence). **Zero pass-2 findings required re-authoring; zero demotions.**

Forecast calibration (C11_BATCH_FORECAST.json future_batch_records): the batch-10 record is appended by the forecast instrument at this gate (see the regenerated C11_BATCH_FORECAST.json). The S4-d/e/f slice runs in the descriptive band (nodes/SP 0.53, edges/SP 1.27), with the held adjacencies (B10-H-01..09 — the surfaces the ruling dispositioned) accounting for the gap, not thin coverage: no S1/S2/S3 or batch-9 identity was re-minted (the ELEVEN existing-owner targets reached via the THIRTEEN sanctioned boundary edges); no batch-10 SP is practical-typed (the PR lane is empty).

## 2. Concept & misconception nodes (8)

| # | code | family | title | attaches to (role) | conf | evidence (anchor → quote) | pass-2 | operator |
|---|---|---|---|---|---|---|---|---|
| 1 | `4CH1-CON-ALKENES` | CONCE | Alkenes (the C=C functional group, the general formula CnH2n, unsaturated hydrocarbons, the first four members) | 4CH1-4.23 (core); 4CH1-4.24 (core); 4CH1-4.25 (core); 4CH1-4.26 (core) | high | NOTE: “All alkenes contain a **double carbon bond**, which is the **functional group** ” | CONFIRM | ☐ |
| 2 | `4CH1-CON-BROMINE-WATER-TEST` | CONCE | The bromine-water test for alkenes (addition of halogens across C=C, decolourisation vs the saturated alkane) | 4CH1-4.27 (core); 4CH1-4.28 (core) | high | NOTE: “When bromine is reacted with an alkene a **dibromoalkane** is formed” | CONFIRM | ☐ |
| 3 | `4CH1-CON-ALCOHOLS` | CONCE | Alcohols (the hydroxyl -OH functional group, the first four members, neutral solutions and fuels) | 4CH1-4.29C (core); 4CH1-4.30C (core) | high | NOTE: “All alcohols contain the hydroxyl (**\-OH**) functional group which is the part ” | CONFIRM | ☐ |
| 4 | `4CH1-CON-ETHANOL-OXIDATION` | CONCE | Oxidation of ethanol (combustion, aerobic oxidation, treatment with an oxidising agent) | 4CH1-4.31C (core) | high | NOTE: “Ethanol can undergo oxidation in three different ways:” | CONFIRM | ☐ |
| 5 | `4CH1-CON-ETHANOL-MANUFACTURE` | CONCE | Manufacture of ethanol (hydration of ethene and fermentation with their conditions) | 4CH1-4.32C (core); 4CH1-4.33C (core) | high | NOTE: “The hydration reaction is very important industrially for the production of alco” | CONFIRM | ☐ |
| 6 | `4CH1-CON-CARBOXYLIC-ACIDS` | CONCE | Carboxylic acids (the carboxyl -COOH functional group, formulae and naming, vinegar) | 4CH1-4.34C (core); 4CH1-4.35C (core); 4CH1-4.37C (core) | high | NOTE: “**Carboxylic acids** is the name given to compounds containing the functional gr” | CONFIRM | ☐ |
| 7 | `4CH1-CON-CARBOXYLIC-ACID-REACTIONS` | CONCE | Reactions of carboxylic acids (with metals and carbonates; the -anoate salts) | 4CH1-4.36C (core) | high | NOTE: “In the reaction with metals, a **metal salt and hydrogen gas** are produced” | CONFIRM | ☐ |
| 8 | `4CH1-MIS-PROPANOL-POSITION` | MISCO | Naming propan-2-ol as propan-1-ol (ignoring the -OH position in the name) | — | high | MARK_SCHEME: “propanol/propan-2-ol/2-propanol” | CONFIRM | ☐ |

Identity-policy notes (split-first; merges are operator-only, OD-1 operand rule): pass-2 flags the 4.23-4.26 one-family ruling (B10-ID-01), the 4.27-4.28 reaction+test one-family ruling (B10-ID-02), the 4.32C-4.33C manufacture one-family ruling (B10-ID-03), the 4.34C+4.35C+4.37C acids one-family ruling (B10-ID-04), and the ONE single-Reject-column misconception mint (B10-ID-05). All are operator identity decisions (template §identity_decisions). No batch-10 SP attaches a practical node (none is practical-typed; the 4CH1-4.43C practical belongs to batch 11's slice).

## 3. Authored semantic edges (19)

| # | edge | conf | derivation | evidence (anchor → quote) | pass-2 | operator |
|---|---|---|---|---|---|---|
| 1 | `4CH1-CON-BROMINE-WATER-TEST REQUIRES_PREREQUISITE 4CH1-CON-ALKENES` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “This allows us to tell alkenes apart from alkanes using a simple chemical test c” | CONFIRM | ☐ |
| 2 | `4CH1-CON-ETHANOL-OXIDATION REQUIRES_PREREQUISITE 4CH1-CON-ALCOHOLS` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “Ethanol can undergo oxidation in three different ways:” | CONFIRM | ☐ |
| 3 | `4CH1-CON-ETHANOL-MANUFACTURE REQUIRES_PREREQUISITE 4CH1-CON-ALCOHOLS` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “Ethanol can also be produced by fermentation where sugar or starch is dissolved ” | CONFIRM | ☐ |
| 4 | `4CH1-CON-CARBOXYLIC-ACID-REACTIONS REQUIRES_PREREQUISITE 4CH1-CON-CARBOXYLIC-ACIDS` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “The carboxylic acids behave like other acids” | CONFIRM | ☐ |
| 5 | `4CH1-MIS-PROPANOL-POSITION WRONG_ANSWER_PATTERN 4CH1-CON-ALCOHOLS` | high | ASSESSMENT_DOCUMENTED | MARK_SCHEME: “Reject propan-1-ol / 1-propanol” | CONFIRM | ☐ |
| 6 | `4CH1-MIS-PROPANOL-POSITION REMEDIATED_BY 4CH1-CON-ALCOHOLS` | high | ASSESSMENT_DOCUMENTED | NOTE: “The 1 indicates that the -OH group is located on the first carbon atom in the mo” | CONFIRM | ☐ |
| 7 | `4CH1-CON-ALKENES REQUIRES_PREREQUISITE 4CH1-CON-HOMOLOGOUS-SERIES` | high | USED_WITHOUT_RETEACHING | NOTE: “The first four members of the alkene homologous series” | CONFIRM | ☐ |
| 8 | `4CH1-CON-ALKENES REQUIRES_PREREQUISITE 4CH1-CON-ORGANIC-FORMULAE` | high | USED_WITHOUT_RETEACHING | NOTE: “The general formula of an alkene is **C**<sub><b>n</b></sub>**H**<sub><b>2n</b><” | CONFIRM | ☐ |
| 9 | `4CH1-CON-ALKENES REQUIRES_PREREQUISITE 4CH1-CON-HYDROCARBON` | high | USED_WITHOUT_RETEACHING | NOTE: “Alkenes are unsaturated hydrocarbons” | CONFIRM | ☐ |
| 10 | `4CH1-CON-BROMINE-WATER-TEST REQUIRES_PREREQUISITE 4CH1-CON-ALKANES` | high | USED_WITHOUT_RETEACHING | NOTE: “All [alkanes](https://www.savemyexams.com/igcse/chemistry/edexcel/19/revision-no” | CONFIRM | ☐ |
| 11 | `4CH1-CON-BROMINE-WATER-TEST REQUIRES_PREREQUISITE 4CH1-CON-ORGANIC-REACTION-CLASSES` | high | USED_WITHOUT_RETEACHING | NOTE: “Alkenes undergo [addition reactions](https://www.savemyexams.com/igcse/chemistry” | CONFIRM | ☐ |
| 12 | `4CH1-CON-ALCOHOLS REQUIRES_PREREQUISITE 4CH1-CON-HOMOLOGOUS-SERIES` | high | USED_WITHOUT_RETEACHING | NOTE: “The names and structures of the first four alcohols in the homologous series are” | CONFIRM | ☐ |
| 13 | `4CH1-CON-ALCOHOLS REQUIRES_PREREQUISITE 4CH1-CON-IUPAC-NAMING` | high | USED_WITHOUT_RETEACHING | NOTE: “In terms of naming, the same system is used as for alkanes and alkenes, with the” | CONFIRM | ☐ |
| 14 | `4CH1-CON-ETHANOL-OXIDATION REQUIRES_PREREQUISITE 4CH1-CON-COMBUSTION-O2` | high | USED_WITHOUT_RETEACHING | NOTE: “Alcohols undergo **combustion** to form carbon dioxide and water” | CONFIRM | ☐ |
| 15 | `4CH1-CON-ETHANOL-OXIDATION REQUIRES_PREREQUISITE 4CH1-CON-OX-RED-AGENTS` | high | USED_WITHOUT_RETEACHING | NOTE: “Alcohols undergo oxidation to produce carboxylic acids when treated with **oxidi” | CONFIRM | ☐ |
| 16 | `4CH1-CON-ETHANOL-MANUFACTURE REQUIRES_PREREQUISITE 4CH1-CON-CRACKING` | high | USED_WITHOUT_RETEACHING | NOTE: “Ethene is a by-product of the **cracking** of hydrocarbons and is a valuable fee” | CONFIRM | ☐ |
| 17 | `4CH1-CON-ETHANOL-MANUFACTURE REQUIRES_PREREQUISITE 4CH1-CON-FRACTIONAL-DISTILLATION` | high | USED_WITHOUT_RETEACHING | NOTE: “The ethanol and water are separated afterwards by **fractional distillation**” | CONFIRM | ☐ |
| 18 | `4CH1-CON-CARBOXYLIC-ACIDS REQUIRES_PREREQUISITE 4CH1-CON-ORGANIC-FORMULAE` | high | USED_WITHOUT_RETEACHING | NOTE: “The general formula of a carboxylic acid is **C**<sub><b>n</b></sub>**H**<sub><b” | CONFIRM | ☐ |
| 19 | `4CH1-CON-CARBOXYLIC-ACID-REACTIONS REQUIRES_PREREQUISITE 4CH1-CON-ACID-REACTIONS` | high | USED_WITHOUT_RETEACHING | NOTE: “In the reaction with **carbonates** a metal salt, water and carbon dioxide gas a” | CONFIRM | ☐ |

THIRTEEN edges are CROSS-SECTION boundary edges into the ELEVEN ruled targets (sanctioned per the session-64 cross-slice ruling — no duplicate mint): the homologous-series rows x2 and the formulae-toolkit rows x2 (into the batch-9 CON-HOMOLOGOUS-SERIES and CON-ORGANIC-FORMULAE owners), the 4.25 hydrocarbon row, the 4.28 alkane-contrast row and the 4.27 addition-class row (into the batch-9 CON-HYDROCARBON, CON-ALKANES and CON-ORGANIC-REACTION-CLASSES owners), the naming row (into the batch-9 CON-IUPAC-NAMING owner), the 4.31C combustion and oxidising-agent rows (into the batch-5 CON-COMBUSTION-O2 and batch-6 CON-OX-RED-AGENTS owners), the feedstock row (into the batch-9 CON-CRACKING owner), the separation row (into the batch-1 CON-FRACTIONAL-DISTILLATION owner) and the 4.36C acid-reactions row (into the batch-7 CON-ACID-REACTIONS owner). The FOUR in-slice RP edges carry the teaching sequence the notes themselves establish.

## 4. Held candidates (9) — the abstention record

| id | candidate | failure class / reason |
|---|---|---|
| B10-H-01 | REQUIRES_PREREQUISITE(CON-ETHANOL-MANUFACTURE, CON-CATALYST) | MECHANISM-APPLIED-AS-GIVEN |
| B10-H-02 | REQUIRES_PREREQUISITE(CON-ETHANOL-MANUFACTURE, CON-REVERSIBLE-EXAMPLES) | EXPLANATION-DEEPER-THAN-DEMAND |
| B10-H-03 | REQUIRES_PREREQUISITE(CON-CARBOXYLIC-ACIDS, CON-IUPAC-NAMING) | AVAILABLE-BUT-SURFACE-MINIMAL |
| B10-H-04 | REQUIRES_PREREQUISITE(CON-CARBOXYLIC-ACIDS, CON-ORGANIC-FORMULAE) | BOUNDARY-TARGETS-ONCE |
| B10-H-05 | REQUIRES_PREREQUISITE(CON-ALKENES, CON-ISOMERS) | AVAILABLE-BUT-SURFACE-MINIMAL |
| B10-H-06 | REQUIRES_PREREQUISITE(CON-CARBOXYLIC-ACIDS, CON-ETHANOL-OXIDATION) | SAME-FAMILY-ADJACENCY |
| B10-H-07 | REQUIRES_PREREQUISITE(CON-ETHANOL-OXIDATION, CON-FUELS-COMBUSTION) | SAME-FAMILY-ADJACENCY / BOUNDARY-TARGETS-ONCE |
| B10-H-08 | REQUIRES_PREREQUISITE(CON-ETHANOL-OXIDATION, CON-CO-POISONING) | ENRICHMENT-NOT-LOAD-BEARING |
| B10-H-09 | RELATED_TO(CON-ALCOHOLS, CON-EXO-ENDO) | ENRICHMENT-NOT-LOAD-BEARING |

Every held candidate cites its §19 failure class; the abstention record remains part of the graph provenance. A held record is a valid outcome — the abstention is the system's honest output.

## 5. Operator verdict surface

- **19 SUGGESTED edges** (B10-E-01..19) — the §18 promotion surface
- **8 nodes** (7 CONCEPT B10-N-01..07 + 1 MISCONCEPTION B10-M-01) — node authority stays SUGGESTED; nodes have no §18 pathway (node promotion is a separate identity decision, deferred)
- **5 identity decisions** (B10-ID-01..05) — MERGE/SPLIT/KEEP_AS_IS
- **9 held candidates** — acknowledge the quarantine (no reopening)
- **0 REVIEW_REQUIRED edges** — zero RR settlements needed

Pathway: fill `scripts/c11_batch10_verdicts_template.yaml` → rename to `c11_batch10_verdicts.yaml` → a later session encodes + applies via `c11_verdict_encode_batch10`-style reconciliation + `c11_promote.py` (§18) + the gated generator re-run. NOTHING is promoted at this gate.
