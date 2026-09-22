# T-C11 §16 Batch 6 Review Sheet — Concept / Prerequisite / Misconception Graph

Slice 4CH1-2.15–2.27 (Section 2 — Inorganic Chemistry, SECOND slice: d Reactivity Series / e Extraction & Uses of Metals, 13 SPs) + practical PR-06 · generated 2026-09-22 · decision record `scripts/c11_batch6_decisions.yaml` (pass 1: `c11-s16-batch-6`) · adversarial pass 2: `scripts/c11_batch6_review_pass2.yaml` · authorization: `scripts/c11_s16_authorization.yaml` (§16 authorized 2026-09-12; batch 6 commissioned by the operator's 'commission batch 6' directive) · boundary ruling: `scripts/c11_batch6_boundary_ruling.yaml` (session 57, machine-checked — the 4 sanctioned boundary edges below)

**NOTHING in this batch is authoritative.** All 13 nodes / 28 batch edges are AI_SUGGESTED (SUGGESTED). HUMAN_VALIDATED is reachable only by your promotion command via the §18 pathway (`scripts/c11_promote.py` → `scripts/c11_promotions.yaml` → regeneration). **Zero batch-6 promotions exist.** This sheet is the batch's operator gate: record verdicts in `scripts/c11_batch6_verdicts_template.yaml` (fill + rename to `c11_batch6_verdicts.yaml`); a later session encodes and applies them.

How to review: for each row check the quoted evidence actually appears in the cited file and actually says what the record claims; then rule on the relation CLASS and direction, not just existence. Machine state: the full gate suite is green at the merged 142-node / 334-edge store; every quote is machine-verified byte-for-byte against its source file (G03/c11.4; 99 quote probes + 91 record anchors pre-verified BEFORE the registry grew, then re-verified by the generator); the 4.15 negative control is uncovered. FOUR edges are cross-section boundary edges into the ruled targets (CON-ELECTROLYSIS + CON-METAL-PROPERTIES — batch-3 owners; CON-REACT-ORDER + CON-RUSTING — the batch-6 mints the batch-5 ruling deferred to, closing its two future_boundary_notes; sanctioned per the session-57 cross-slice ruling; no duplicate concept was minted). The REACTIVITY pin wraps the Q2a Reject line across a pdftotext line break; the misconception attribution is recorded in the node's derivation_notes. The extraction family is UNPINNED (no PMT MS exists in any unit — meta.ms_coverage_note): misconception mining is confined to the reactivity-series surface (one clean Reject-column pattern).

## 1. Totals & second-pass agreement

| | nodes | authored edges | held | |
|---|---|---|---|
| pass-1 (extraction) | 13 | 16 (+12 derived PART_OF) | 9 |
| pass-2 verdicts | 13 CONFIRM(+note) | 16 CONFIRM(+note) · 0 HOLD · 0 REJECT | all 9 AGREE |

Raw agreement (NOT κ — single human rater, architecture §12): nodes 13/13 = 100.0%; edges — of the 16 edges pass-1 asserted (SUGGESTED), pass-2 confirmed 16 (100.0%); pass-1 quarantined 0 edges as REVIEW_REQUIRED (this batch authored NONE — every doubt was held or resolved on explicit evidence). **One pass-2 finding (FP-B6-5, a non-load-bearing 2-word evidence fragment) was re-authored BEFORE the gate; zero demotions at the re-authored state.**

Forecast calibration (C11_BATCH_FORECAST.json future_batch_records): the batch-6 record is appended by the forecast instrument at this gate (see the regenerated C11_BATCH_FORECAST.json). The S2-d/e families run in the descriptive band the item-14 plan anticipated (nodes/SP 1.00, edges/SP 1.23), with the inline-re-teach abstentions (B6-H-01/02/06/08) accounting for the gap, not thin coverage: no S1/S3/batch-5 identity was re-minted (the 2 existing-owner targets reached via 2 sanctioned boundary edges + the 2 deferral closures); 2.21 attaches no concept node (PR-06 owns it — the 1.13/1.60C/2.14 precedent) with the practical->concept edge authored.

## 2. Concept & misconception nodes (13)

| # | code | family | title | attaches to (role) | conf | evidence (anchor → quote) | pass-2 | operator |
|---|---|---|---|---|---|---|---|---|
| 1 | `4CH1-CON-REACT-ARRANGE` | CONCE | Arranging metals into a reactivity series from water and dilute-acid reactions | 4CH1-2.15 (core) | high | NOTE: “Based on these reactions a reactivity series of metals can be produced” | CONFIRM | ☐ |
| 2 | `4CH1-CON-METAL-DISPLACEMENT` | CONCE | Metal displacement reactions as reactivity-series evidence (metal + metal oxide; metal + salt solution) | 4CH1-2.16 (core) | high | NOTE: “The reactivity of metals decreases going down the reactivity series.” | CONFIRM | ☐ |
| 3 | `4CH1-CON-REACT-ORDER` | CONCE | The order of reactivity of the named metals (K to Au) | 4CH1-2.17 (core) | high | NOTE: “Carbon is an important element and has its own place on the reactivity series” | CONFIRM | ☐ |
| 4 | `4CH1-CON-RUSTING` | CONCE | Rusting of iron (both oxygen and water required; the control-tube investigation) | 4CH1-2.18 (core) | high | NOTE: “Oxygen and water must be present for rust to occur” | CONFIRM | ☐ |
| 5 | `4CH1-CON-RUST-PREVENTION` | CONCE | Preventing rusting (barrier methods, sacrificial protection, galvanising) | 4CH1-2.19 (core) | high | NOTE: “Rust can be prevented by coating iron with barriers that prevent the iron from coming into contact w” | CONFIRM | ☐ |
| 6 | `4CH1-CON-OX-RED-AGENTS` | CONCE | Oxidation, reduction, oxidising and reducing agents (oxygen and electron frameworks) | 4CH1-2.20 (core) | high | NOTE: “Oxidation is any reaction in which a substance gains oxygen” | CONFIRM_WITH_NOTE | ☐ |
| 7 | `4CH1-CON-ORES` | CONCE | Ores and native (uncombined) metals as sources of metals | 4CH1-2.22C (core) | high | NOTE: “Useful metals are often chemically combined with other substances forming ores” | CONFIRM | ☐ |
| 8 | `4CH1-CON-EXTRACTION-METHOD` | CONCE | Extraction method related to reactivity-series position (electrolysis above carbon; carbon reduction below) | 4CH1-2.23C (core) | high | NOTE: “The position of the metal on the reactivity series determines the method of extraction” | CONFIRM | ☐ |
| 9 | `4CH1-CON-EXTRACTION-EVALUATION` | CONCE | Commenting on a metal extraction process from given information | 4CH1-2.24C (core) | high | NOTE: “Iron is extracted in a large container called a blast furnace from its ore, hematite” | CONFIRM_WITH_NOTE | ☐ |
| 10 | `4CH1-CON-METAL-USES` | CONCE | Uses of aluminium, copper, iron and steel explained by their properties | 4CH1-2.25C (core) | high | NOTE: “The uses of aluminium, copper and steel are summarised in these tables” | CONFIRM | ☐ |
| 11 | `4CH1-CON-ALLOYS` | CONCE | Alloys as mixtures of a metal with other elements | 4CH1-2.26C (core) | high | NOTE: “An alloy is a mixture of two or more metals or metal with a non-metal such as carbon” | CONFIRM | ☐ |
| 12 | `4CH1-CON-ALLOY-HARDNESS` | CONCE | Why alloys are harder than pure metals (distorted layers resist sliding) | 4CH1-2.27C (core) | high | NOTE: “Alloys are harder than pure metals because:” | CONFIRM | ☐ |
| 13 | `4CH1-MIS-ION-OXIDE-REASONING` | MISCO | Explaining a metal-oxide displacement outcome by references to ions and oxides instead of the reactivity comparison | — | high | MARK_SCHEME: “(it/iron is) less reactive (than aluminium)”<br>remediation: “This means that a more reactive metal will displace a less reactive metal from i” | CONFIRM_WITH_NOTE | ☐ |

Identity-policy notes (split-first; merges are operator-only, OD-1 operand rule): pass-2 flags the 2.20-vs-1.59C electron-framework overlap (B6-ID-01), the 2.23C/2.24C method-vs-evaluation split (B6-ID-02), the 2.15/2.16/2.17 trio (B6-ID-03), the 2.18/2.19 conditions-vs-prevention split (B6-ID-04), the 2.26C/2.27C definition-vs-mechanism split (B6-ID-05) and the single-Reject-column misconception mint (B6-ID-06). All are operator identity decisions (template §identity_decisions). 2.21 attaches NO batch-6 concept node (PR-06 owns it — the 1.13/1.60C/2.14 precedent).

## 3. Authored semantic edges (16)

| # | edge | conf | derivation | evidence (anchor → quote) | pass-2 | operator |
|---|---|---|---|---|---|---|
| 1 | `4CH1-CON-ALLOY-HARDNESS REQUIRES_PREREQUISITE 4CH1-CON-ALLOYS` | high | DEFINITIONAL_DEPENDENCY | NOTE: “Alloys are harder than pure metals because:” | CONFIRM | ☐ |
| 2 | `4CH1-CON-CO2-FROM-CARBONATES REQUIRES_PREREQUISITE 4CH1-CON-REACT-ORDER` | high | USED_WITHOUT_RETEACHING | NOTE: “Carbonates of metals from the lower half of the reactivity series tend to decompose on hea” | CONFIRM | ☐ |
| 3 | `4CH1-CON-EXTRACTION-EVALUATION REQUIRES_PREREQUISITE 4CH1-CON-EXTRACTION-METHOD` | high | USED_WITHOUT_RETEACHING | NOTE: “Make sure you can explain why aluminium is extracted by electrolysis while iron is extract” | CONFIRM | ☐ |
| 4 | `4CH1-CON-EXTRACTION-METHOD REQUIRES_PREREQUISITE 4CH1-CON-ELECTROLYSIS` | high | USED_WITHOUT_RETEACHING | NOTE: “Instead, aluminium is extracted by electrolysis” | CONFIRM | ☐ |
| 5 | `4CH1-CON-EXTRACTION-METHOD REQUIRES_PREREQUISITE 4CH1-CON-OX-RED-AGENTS` | high | USED_WITHOUT_RETEACHING | NOTE: “Lower placed metals can be extracted by heating with carbon which reduces them” | CONFIRM | ☐ |
| 6 | `4CH1-CON-EXTRACTION-METHOD REQUIRES_PREREQUISITE 4CH1-CON-REACT-ORDER` | high | DEFINITIONAL_DEPENDENCY | NOTE: “The position of the metal on the reactivity series determines the method of extraction” | CONFIRM | ☐ |
| 7 | `4CH1-CON-METAL-DISPLACEMENT REQUIRES_PREREQUISITE 4CH1-CON-REACT-ORDER` | high | DEFINITIONAL_DEPENDENCY | NOTE: “The reactivity of metals decreases going down the reactivity series.” | CONFIRM | ☐ |
| 8 | `4CH1-CON-METAL-USES REQUIRES_PREREQUISITE 4CH1-CON-METAL-PROPERTIES` | high | USED_WITHOUT_RETEACHING | NOTE: “Very good conductor of electricity and ductile” | CONFIRM | ☐ |
| 9 | `4CH1-CON-O2-PERCENT-DETERMINATION REQUIRES_PREREQUISITE 4CH1-CON-RUSTING` | high | USED_WITHOUT_RETEACHING | NOTE: “To determine the percentage of oxygen in air using the oxidation of iron” | CONFIRM | ☐ |
| 10 | `4CH1-CON-REACT-ORDER REQUIRES_PREREQUISITE 4CH1-CON-REACT-ARRANGE` | high | DEFINITIONAL_DEPENDENCY | NOTE: “Based on these reactions a reactivity series of metals can be produced” | CONFIRM | ☐ |
| 11 | `4CH1-CON-RUST-PREVENTION REQUIRES_PREREQUISITE 4CH1-CON-OX-RED-AGENTS` | high | USED_WITHOUT_RETEACHING | NOTE: “The more reactive metal will oxidise and therefore corrode first, protecting the less reac” | CONFIRM | ☐ |
| 12 | `4CH1-CON-RUST-PREVENTION REQUIRES_PREREQUISITE 4CH1-CON-REACT-ORDER` | high | USED_WITHOUT_RETEACHING | NOTE: “Iron can be prevented from rusting using the reactivity series” | CONFIRM | ☐ |
| 13 | `4CH1-CON-RUST-PREVENTION REQUIRES_PREREQUISITE 4CH1-CON-RUSTING` | high | DEFINITIONAL_DEPENDENCY | NOTE: “Rust can be prevented by coating iron with barriers that prevent the iron from coming into” | CONFIRM | ☐ |
| 14 | `4CH1-MIS-ION-OXIDE-REASONING REMEDIATED_BY 4CH1-CON-METAL-DISPLACEMENT` | high | ASSESSMENT_DOCUMENTED | NOTE: “This means that a more reactive metal will displace a less reactive metal from its compoun” | CONFIRM | ☐ |
| 15 | `4CH1-MIS-ION-OXIDE-REASONING WRONG_ANSWER_PATTERN 4CH1-CON-METAL-DISPLACEMENT` | high | ASSESSMENT_DOCUMENTED | MARK_SCHEME: “Reject references to ions and oxides” | CONFIRM | ☐ |
| 16 | `4CH1-PR-06 REQUIRES_PREREQUISITE 4CH1-CON-REACT-ARRANGE` | high | USED_WITHOUT_RETEACHING | NOTE: “To investigate the reactions between dilute hydrochloric and sulfuric acids with the metal” | CONFIRM | ☐ |

Four edges are CROSS-SECTION boundary edges into the ruled targets (sanctioned per the session-57 cross-slice ruling — no duplicate mint): the 2.23C electrolysis row and the 2.25C properties row (batch-3 owners), and the TWO deferral closures the batch-5 ruling explicitly deferred to this batch (the 2.12 carbonate-decomposition row into CON-REACT-ORDER and the 2.10 iron-route row into CON-RUSTING — closing its future_boundary_notes and held B5-H-10).

## 4. Held candidates (9) — the abstention record

| id | candidate | failure class / reason |
|---|---|---|
| B6-H-01 | REQUIRES_PREREQUISITE(CON-METAL-USES, CON-ALLOYS) | RE-TEACHED INLINE |
| B6-H-02 | REQUIRES_PREREQUISITE(CON-OX-RED-AGENTS, CON-REDOX-ELECTRONS) | RE-TEACHED INLINE + NON_MINT PROTECTION |
| B6-H-03 | MISCONCEPTION "naming the acid or water as the factor that changes the metal-acid vigour" (the REACTIVITY_MS Q1ai IGNORE class) | INSUFFICIENT CHARACTERIZATION (the B5-H-04/B5-H-05 conventio |
| B6-H-04 | REQUIRES_PREREQUISITE(CON-EXTRACTION-METHOD, CON-EXO-ENDO) | OD-2 INCIDENTAL |
| B6-H-05 | REQUIRES_PREREQUISITE(CON-RUST-PREVENTION, CON-CO2-FROM-CARBONATES) — the galvanising ZnCO3 line | OD-2 SURFACE-CHEMISTRY DETAIL + NO DEPENDENCY |
| B6-H-06 | REQUIRES_PREREQUISITE(CON-REACT-ORDER, CON-METAL-DISPLACEMENT) — the reverse direction | DOUBLE-COUNTING THE ARRANGEMENT DEMAND |
| B6-H-07 | REQUIRES_PREREQUISITE(CON-EXTRACTION-EVALUATION, CON-REACT-ORDER) — direct edge skipping the method node | FC-3 DENSITY |
| B6-H-08 | REQUIRES_PREREQUISITE(CON-ORES, CON-OX-RED-AGENTS) | ENRICHMENT_BEYOND_SPEC + BRIDGE CONTEXT |
| B6-H-09 | REQUIRES_PREREQUISITE(CON-RUSTING, CON-OX-RED-AGENTS) | FC-3 DENSITY + WRONG SURFACE OWNER |

Every held candidate cites its §19 failure class; the IGNORE-class wrong-answer candidate is refused for insufficient characterization (the session-53 Step-3 rule). A held record is a valid outcome — the abstention is the system's honest output.

## 5. Operator verdict surface

- **16 SUGGESTED edges** (B6-E-01..16) — the §18 promotion surface
- **13 nodes** (12 CONCEPT B6-N-01..12 + 1 MISCONCEPTION B6-M-01..01) — node authority stays SUGGESTED; nodes have no §18 pathway (node promotion is a separate identity decision, deferred)
- **6 identity decisions** (B6-ID-01..06) — MERGE/SPLIT/KEEP_AS_IS
- **9 held candidates** — acknowledge the quarantine (no reopening)
- **0 REVIEW_REQUIRED edges** — zero RR settlements needed

Pathway: fill `scripts/c11_batch6_verdicts_template.yaml` → rename to `c11_batch6_verdicts.yaml` → a later session encodes + applies via `c11_verdict_encode_batch6`-style reconciliation + `c11_promote.py` (§18) + the gated generator re-run. NOTHING is promoted at this gate.

