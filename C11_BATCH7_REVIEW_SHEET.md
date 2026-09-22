# T-C11 §16 Batch 7 Review Sheet — Concept / Prerequisite / Misconception Graph

Slice 4CH1-2.28–2.43C (Section 2 — Inorganic Chemistry, THIRD slice: f Acids, Alkalis & Titrations / g Acids, Bases & Salt Preparations, 16 SPs) + practicals PR-07 (2.42) / PR-08 (2.43C) · generated 2026-09-23 · decision record `scripts/c11_batch7_decisions.yaml` (pass 1: `c11-s16-batch-7`) · adversarial pass 2: `scripts/c11_batch7_review_pass2.yaml` · authorization: `scripts/c11_s16_authorization.yaml` (§16 authorized 2026-09-12; batch 7 commissioned by the operator's 'Proceed with batch 7' directive) · boundary ruling: `scripts/c11_batch7_boundary_ruling.yaml` (session 59, machine-checked — the 2 sanctioned boundary edges below)

**NOTHING in this batch is authoritative.** All 15 nodes / 33 batch edges are AI_SUGGESTED (SUGGESTED). HUMAN_VALIDATED is reachable only by your promotion command via the §18 pathway (`scripts/c11_promote.py` → `scripts/c11_promotions.yaml` → regeneration). **Zero batch-7 promotions exist.** This sheet is the batch's operator gate: record verdicts in `scripts/c11_batch7_verdicts_template.yaml` (fill + rename to `c11_batch7_verdicts.yaml`); a later session encodes and applies them.

How to review: for each row check the quoted evidence actually appears in the cited file and actually says what the record claims; then rule on the relation CLASS and direction, not just existence. Machine state: the full gate suite is green at the merged 157-node / 367-edge store; every quote is machine-verified byte-for-byte against its source file (G03/c11.4; 135 quote probes + 107 record anchors pre-verified BEFORE the registry grew, then re-verified by the generator); the 4.15 negative control is uncovered. TWO edges are cross-section boundary edges into the ruled targets (CON-REACT-ORDER — the batch-6 owner; CON-ION-CHARGE-RULES — the batch-3 owner; sanctioned per the session-59 cross-slice ruling; no duplicate concept was minted). BOTH batch families are MS-pinned (the best coverage of any slice — meta.ms_coverage_note): the Titrations MS Q2a(iv) Reject line and the Salt-Prep MS Q2a(iii) class anchor the TWO misconception mints; the pdftotext line-wrap attributions are recorded in the nodes' derivation_notes. ONE pass-2 finding (FP-B7-4) was re-authored BEFORE the gate: the PR-08 edge anchors were swapped away from the source note's 'Wash filtrate' line, which conflicts with the pinned MS Q7a(iii) (the conflict is recorded in the findings, not silently quoted or dropped).

## 1. Totals & second-pass agreement

| | nodes | authored edges | held | |
|---|---|---|---|
| pass-1 (extraction) | 15 | 19 (+14 derived PART_OF) | 9 |
| pass-2 verdicts | 15 CONFIRM(+note) | 19 CONFIRM(+note) · 0 HOLD · 0 REJECT | all 9 AGREE |

Raw agreement (NOT κ — single human rater, architecture §12): nodes 15/15 = 100.0%; edges — of the 19 edges pass-1 asserted (SUGGESTED), pass-2 confirmed 19 (100.0%); pass-1 quarantined 0 edges as REVIEW_REQUIRED (this batch authored NONE — every doubt was held or resolved on explicit evidence). **One pass-2 finding (FP-B7-4, the PR-08 anchor swap) was re-authored BEFORE the gate; zero demotions at the re-authored state.**

Forecast calibration (C11_BATCH_FORECAST.json future_batch_records): the batch-7 record is appended by the forecast instrument at this gate (see the regenerated C11_BATCH_FORECAST.json). The S2-f/g families run in the descriptive band the item-14 plan anticipated (nodes/SP 0.94, edges/SP 1.19), with the inline-re-teach abstentions (the separation-technique surfaces) and the held S3-lane surfaces (B7-H-01/02/05/09) accounting for the gap, not thin coverage: no S1/S3/batch-5/6 identity was re-minted (the 2 existing-owner targets reached via the 2 sanctioned boundary edges); 2.42/2.43C attach no concept node (PR-07/PR-08 own them — the 1.13/1.60C/2.14/2.21 precedent) with the practical->concept edges authored.

## 2. Concept & misconception nodes (15)

| # | code | family | title | attaches to (role) | conf | evidence (anchor → quote) | pass-2 | operator |
|---|---|---|---|---|---|---|---|---|
| 1 | `4CH1-CON-INDICATORS` | CONCE | Indicators for distinguishing acidic and alkaline solutions (litmus, phenolphthalein, methyl orange) | 4CH1-2.28 (core) | high | NOTE: “Two colours indicators are used to distinguish between acids and alkalis” | CONFIRM | ☐ |
| 2 | `4CH1-CON-PH-SCALE` | CONCE | The pH scale 0-14 and the acidity/alkalinity classification bands | 4CH1-2.29 (core) | high | NOTE: “The pH scale goes from 0 - 14” | CONFIRM | ☐ |
| 3 | `4CH1-CON-UNIVERSAL-INDICATOR` | CONCE | Universal indicator as approximate pH measurement (colour-chart matching) | 4CH1-2.30 (core) | high | NOTE: “Universal indicator is a wide range indicator and can give only an approximate value for pH” | CONFIRM | ☐ |
| 4 | `4CH1-CON-ACID-ALKALI-IONS` | CONCE | Acids as hydrogen-ion sources and alkalis as hydroxide-ion sources in aqueous solution | 4CH1-2.31 (core) | high | NOTE: “When acids are added to water, they form positively charged hydrogen ions” | CONFIRM | ☐ |
| 5 | `4CH1-CON-NEUTRALISATION` | CONCE | Neutralisation (alkalis neutralise acids; H+ + OH- -> water) | 4CH1-2.32 (core) | high | NOTE: “A neutralisation reaction occurs when an acid reacts with an alkali” | CONFIRM_WITH_NOTE | ☐ |
| 6 | `4CH1-CON-TITRATION` | CONCE | Acid-alkali titration technique (pipette, burette, endpoint, concordant titres) | 4CH1-2.33C (core) | high | NOTE: “Use the pipette and pipette filler and place exactly 25 cm3 sodium hydroxide solution into the conic” | CONFIRM | ☐ |
| 7 | `4CH1-CON-SOLUBILITY-RULES` | CONCE | Solubility rules for ionic compounds in water (the salt-preparation method-selection frame) | 4CH1-2.34 (core) | high | NOTE: “Ionic compounds are generally soluble in water compared to covalent substances, but there are except” | CONFIRM | ☐ |
| 8 | `4CH1-CON-PROTON-TRANSFER` | CONCE | Acids and bases as proton transfer (donor and acceptor) | 4CH1-2.35 (core); 4CH1-2.36 (core) | high | NOTE: “The earlier definition of an acid and a base can be extended” | CONFIRM | ☐ |
| 9 | `4CH1-CON-ACID-REACTIONS` | CONCE | Reactions of acids with metals, bases and metal carbonates to form salts | 4CH1-2.37 (core) | high | NOTE: “When acids react with metals they form a salt and hydrogen gas” | CONFIRM | ☐ |
| 10 | `4CH1-CON-BASES-ALKALIS` | CONCE | Bases and alkalis (metal oxides/hydroxides/ammonia as bases; alkalis = soluble bases) | 4CH1-2.38 (core) | high | NOTE: “Bases are substances which can neutralise an acid, forming a salt and water” | CONFIRM | ☐ |
| 11 | `4CH1-CON-SALT-INSOLUBLE-REACTANT` | CONCE | Preparing a pure, dry soluble salt from an insoluble reactant (excess-base route) | 4CH1-2.39 (core) | high | NOTE: “A soluble salt can be made from the reaction of an acid with an insoluble base” | CONFIRM | ☐ |
| 12 | `4CH1-CON-SALT-TITRATION-ROUTE` | CONCE | Preparing a pure, dry soluble salt from an acid and alkali (titration route) | 4CH1-2.40C (core) | high | NOTE: “It is also possible to prepare a sample of a dry salt starting from an acid and an alkali” | CONFIRM | ☐ |
| 13 | `4CH1-CON-SALT-PRECIPITATION` | CONCE | Preparing a pure, dry insoluble salt from two soluble reactants (precipitation) | 4CH1-2.41C (core) | high | NOTE: “Insoluble salts can be prepared using a precipitation reaction” | CONFIRM | ☐ |
| 14 | `4CH1-MIS-ENDPOINT-PH-ABOVE-7` | MISCO | Identifying complete neutralisation as the pH changing to any value above 7 (instead of the temperature maximum / pH reaching 7) | — | high | MARK_SCHEME: “temperature goes down/stops rising/stays constant”<br>remediation: “A neutralisation reaction occurs when an acid reacts with an alkali” | CONFIRM | ☐ |
| 15 | `4CH1-MIS-PRECIPITATE-IN-FILTRATE` | MISCO | Recovering the insoluble salt from the filtrate instead of the residue in a precipitation preparation | — | high | MARK_SCHEME: “they would obtain sodium nitrate instead”<br>remediation: “The precipitate is recovered by filtration” | CONFIRM | ☐ |

Identity-policy notes (split-first; merges are operator-only, OD-1 operand rule): pass-2 flags the 2.35/2.36 one-family ruling (B7-ID-01), the qualitative-rules-vs-quantitative-owners split (B7-ID-02), the self-contained solution-ion reading (B7-ID-03), the three-route salt-preparation split (B7-ID-04), and the TWO single-Reject-column misconception mints (B7-ID-05, B7-ID-06). All are operator identity decisions (template §identity_decisions). 2.42/2.43C attach NO batch-7 concept node (PR-07/PR-08 own them — the 1.13/1.60C/2.14/2.21 precedent).

## 3. Authored semantic edges (19)

| # | edge | conf | derivation | evidence (anchor → quote) | pass-2 | operator |
|---|---|---|---|---|---|---|
| 1 | `4CH1-CON-ACID-REACTIONS REQUIRES_PREREQUISITE 4CH1-CON-NEUTRALISATION` | high | DEFINITIONAL_DEPENDENCY | NOTE: “When an acid reacts with a base, a neutralisation reaction occurs” | CONFIRM | ☐ |
| 2 | `4CH1-CON-ACID-REACTIONS REQUIRES_PREREQUISITE 4CH1-CON-REACT-ORDER` | high | USED_WITHOUT_RETEACHING | NOTE: “Only metals above hydrogen in the reactivity series will react with dilute acids” | CONFIRM | ☐ |
| 3 | `4CH1-CON-BASES-ALKALIS REQUIRES_PREREQUISITE 4CH1-CON-NEUTRALISATION` | high | DEFINITIONAL_DEPENDENCY | NOTE: “Bases are substances which can neutralise an acid, forming a salt and water” | CONFIRM | ☐ |
| 4 | `4CH1-CON-NEUTRALISATION REQUIRES_PREREQUISITE 4CH1-CON-ACID-ALKALI-IONS` | high | DEFINITIONAL_DEPENDENCY | NOTE: “A neutralisation reaction occurs when an acid reacts with an alkali” | CONFIRM | ☐ |
| 5 | `4CH1-CON-PROTON-TRANSFER REQUIRES_PREREQUISITE 4CH1-CON-ACID-ALKALI-IONS` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “The earlier definition of an acid and a base can be extended” | CONFIRM | ☐ |
| 6 | `4CH1-CON-SALT-INSOLUBLE-REACTANT REQUIRES_PREREQUISITE 4CH1-CON-ACID-REACTIONS` | high | DEFINITIONAL_DEPENDENCY | NOTE: “A soluble salt can be made from the reaction of an acid with an insoluble base” | CONFIRM | ☐ |
| 7 | `4CH1-CON-SALT-INSOLUBLE-REACTANT REQUIRES_PREREQUISITE 4CH1-CON-SOLUBILITY-RULES` | high | DEFINITIONAL_DEPENDENCY | NOTE: “A knowledge of the solubility of ionic compounds helps us to determine the most appropriat” | CONFIRM | ☐ |
| 8 | `4CH1-CON-SALT-PRECIPITATION REQUIRES_PREREQUISITE 4CH1-CON-SOLUBILITY-RULES` | high | DEFINITIONAL_DEPENDENCY | NOTE: “The solid salt obtained is the precipitate, thus in order to successfully use this method ” | CONFIRM | ☐ |
| 9 | `4CH1-CON-SALT-TITRATION-ROUTE REQUIRES_PREREQUISITE 4CH1-CON-TITRATION` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “A titration can be used for this” | CONFIRM | ☐ |
| 10 | `4CH1-CON-SOLUBILITY-RULES REQUIRES_PREREQUISITE 4CH1-CON-ION-CHARGE-RULES` | high | USED_WITHOUT_RETEACHING | NOTE: “A knowledge of the solubility of ionic compounds helps us to determine the most appropriat” | CONFIRM | ☐ |
| 11 | `4CH1-CON-TITRATION REQUIRES_PREREQUISITE 4CH1-CON-INDICATORS` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “Add a few drops of a suitable indicator to the solution to the conical flask” | CONFIRM | ☐ |
| 12 | `4CH1-CON-TITRATION REQUIRES_PREREQUISITE 4CH1-CON-NEUTRALISATION` | high | DEFINITIONAL_DEPENDENCY | NOTE: “They can determine exactly how much alkali is needed to neutralise a quantity of acid - an” | CONFIRM | ☐ |
| 13 | `4CH1-CON-UNIVERSAL-INDICATOR REQUIRES_PREREQUISITE 4CH1-CON-PH-SCALE` | high | EXPLICIT_TEACH_SEQUENCE | NOTE: “A few drops are added to the solution and the colour is matched with a colour chart which ” | CONFIRM | ☐ |
| 14 | `4CH1-MIS-ENDPOINT-PH-ABOVE-7 REMEDIATED_BY 4CH1-CON-NEUTRALISATION` | high | ASSESSMENT_DOCUMENTED | NOTE: “A neutralisation reaction occurs when an acid reacts with an alkali” | CONFIRM | ☐ |
| 15 | `4CH1-MIS-ENDPOINT-PH-ABOVE-7 WRONG_ANSWER_PATTERN 4CH1-CON-NEUTRALISATION` | high | ASSESSMENT_DOCUMENTED | MARK_SCHEME: “Reject changing to any pH value > 7” | CONFIRM | ☐ |
| 16 | `4CH1-MIS-PRECIPITATE-IN-FILTRATE REMEDIATED_BY 4CH1-CON-SALT-PRECIPITATION` | high | ASSESSMENT_DOCUMENTED | NOTE: “The precipitate is recovered by filtration” | CONFIRM | ☐ |
| 17 | `4CH1-MIS-PRECIPITATE-IN-FILTRATE WRONG_ANSWER_PATTERN 4CH1-CON-SALT-PRECIPITATION` | high | ASSESSMENT_DOCUMENTED | MARK_SCHEME: “the filtrate does not contain lead(II) sulfate/the insoluble salt” | CONFIRM | ☐ |
| 18 | `4CH1-PR-07 REQUIRES_PREREQUISITE 4CH1-CON-SALT-INSOLUBLE-REACTANT` | high | USED_WITHOUT_RETEACHING | NOTE: “To prepare a pure, dry sample of hydrated copper(II) sulfate crystals” | CONFIRM | ☐ |
| 19 | `4CH1-PR-08 REQUIRES_PREREQUISITE 4CH1-CON-SALT-PRECIPITATION` | high | USED_WITHOUT_RETEACHING | NOTE: “The solid salt obtained is the precipitate, thus in order to successfully use this method ” | CONFIRM | ☐ |

TWO edges are CROSS-SECTION boundary edges into the ruled targets (sanctioned per the session-59 cross-slice ruling — no duplicate mint): the 2.37 acid-metal placement row (into the batch-6 CON-REACT-ORDER owner) and the 2.34 ion-family rules row (into the batch-3 CON-ION-CHARGE-RULES owner). The TWO practical edges ride the PR-05/PR-06 shape (2.42/2.43C attach no concept node).

## 4. Held candidates (9) — the abstention record

| id | candidate | failure class / reason |
|---|---|---|
| B7-H-01 | REQUIRES_PREREQUISITE(CON-PH-SCALE, CON-ACID-ALKALI-IONS) | ENRICHMENT, NOT LOAD-BEARING |
| B7-H-02 | REQUIRES_PREREQUISITE(CON-BASES-ALKALIS, CON-PH-SCALE) | INCIDENTAL TO THE DEMAND |
| B7-H-03 | REQUIRES_PREREQUISITE(PR-07, CON-WATER-CRYST) | NAMING-APPLIED-AS-GIVEN |
| B7-H-04 | WRONG_ANSWER_PATTERN(CON-SALT-INSOLUBLE-REACTANT) — the reagent-selection wrong-answer class (Salt-Prep MS Q1a "REJECT the use of reagents that would not work, eg magnesium chloride") | INSUFFICIENT CHARACTERIZATION (the session-53 Step-3 rule; t |
| B7-H-05 | RELATED_TO(CON-TITRATION, CON-CONC-CALC) and the titre-calculation dependency surface | S3-OWNER SURFACE (the G07 MS-only class; the batch-6 Q1ai ra |
| B7-H-06 | MISCONCEPTION mint — "suggesting universal indicator as the titration indicator" (indicator note examiner tip) | NOTE-ANCHORED, NOT MS-DOCUMENTED |
| B7-H-07 | RELATED_TO(CON-ACID-REACTIONS, CON-CO2-FROM-CARBONATES) — the CO2 adjacency | DIFFERENT CHEMISTRY, REAL ADJACENCY |
| B7-H-08 | WRONG_ANSWER_PATTERN(CON-SALT-INSOLUBLE-REACTANT) — omitting the excess-base step (the "dangerously concentrated" acid error) | NOTE-ANCHORED ONLY + EXISTING-OWNER ADJACENCY |
| B7-H-09 | REQUIRES_PREREQUISITE(CON-TITRATION, CON-CONCENTRATION) | CONTEXT FRAMING, NOT LOAD-BEARING |

Every held candidate cites its §19 failure class; the reagent-selection wrong-answer candidate is refused for insufficient characterization (the session-53 Step-3 rule; the B6-H-03 precedent) and the note-anchored ERRONEOUS_BELIEF lane is held for operator ruling (B7-H-06). A held record is a valid outcome — the abstention is the system's honest output.

## 5. Operator verdict surface

- **19 SUGGESTED edges** (B7-E-01..19) — the §18 promotion surface
- **15 nodes** (13 CONCEPT B7-N-01..13 + 2 MISCONCEPTION B7-M-01..02) — node authority stays SUGGESTED; nodes have no §18 pathway (node promotion is a separate identity decision, deferred)
- **6 identity decisions** (B7-ID-01..06) — MERGE/SPLIT/KEEP_AS_IS
- **9 held candidates** — acknowledge the quarantine (no reopening)
- **0 REVIEW_REQUIRED edges** — zero RR settlements needed

Pathway: fill `scripts/c11_batch7_verdicts_template.yaml` → rename to `c11_batch7_verdicts.yaml` → a later session encodes + applies via `c11_verdict_encode_batch7`-style reconciliation + `c11_promote.py` (§18) + the gated generator re-run. NOTHING is promoted at this gate.

