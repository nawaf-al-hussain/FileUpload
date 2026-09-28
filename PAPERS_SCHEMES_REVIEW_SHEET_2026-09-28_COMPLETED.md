# PAPERS/SCHEMES AXIS — OPERATOR REVIEW SHEET (T-PS1)

**Scope:** the 77 SUGGESTED exam papers (with their 722 SUGGESTED question versions, 631 SUGGESTED mark schemes and 132 linked SUGGESTED QP/MS documents) — the remainder after pilot.teacher's in-app session brought 14 papers to VALIDATED. **Census:** live production DB, read-only probes, 2026-09-28T12:24Z · evidence `psaxis_detail.json` + `orphan_map_v4.json` (this folder).

**Rules (unchanged):**

1. This sheet **records** decisions; it does not apply them. Any flip (paper / qv / scheme / document, any direction) is applied only on the operator's **named instruction**, written to `content_review_audit` with the operator label — the agent asserts no validation of its own.
2. The in-app paper screen offers **VALIDATE_ALL** ("N versions + N schemes, force=false") — it validates the paper row **plus its question versions and mark schemes**, but **not** the linked QP/MS *document* rows (live counterexample: 4CH1/1C Specimen 2017 paper VALIDATED, both docs still SUGGESTED). Document states are therefore a second decision axis — tracked in the two right-hand grid columns and §B/§D.
3. FLAGGED never serves. FLAG is always safe and reversible (UNFLAG).
4. One decision per row: **A** = VALIDATE_ALL (paper+qv+schemes) · **F** = FLAG · **R** = REJECT · **D** = DEFER (say why). Document columns accept independent **V** (validate doc) / **F** marks.

**Scope arithmetic (exact, ties the census together):** 800 SUGGESTED question versions = **722** under the 77 papers (§A) + **19** left over under 2 already-VALIDATED papers (§C) + **59** parked under REJECTED papers (§E) · 703 SUGGESTED schemes = 631 (§A) + 19 (§C) + 53 (§E). 176 SUGGESTED QP/MS documents are linked to **no** paper row at all (§B/§D).

---

## §A — THE 77: paper review grid (the main queue)

Doc cell format: `STA·pages·chunks` (STA = validation_state prefix; `1p` = single-file markdown-lane extraction, that lane has no page concept). `—` = no doc link (see §B). Q counts **all** questions including deactivated ones. Prior audit actions: none of the 77 has any audit row — all are untouched by any reviewer so far.
### 4CH0/1C — 15 papers · 191 qv · 156 schemes

| # | Paper | Engine | Q | qv S/V | sch S/V | QP doc | MS doc | Decision | Notes |
|---|-------|--------|---|--------|---------|--------|--------|----------|-------|
| 1 | 4CH0/1C · January 2012 | pdflane | 11 | 11/0 | 11/0 | SUG·1p·13c | SUG·26p·20c | ☐A ☐F ☐R ☒D |  |
| 2 | 4CH0/1C · June 2012 | glm-ocr | 13 | 13/0 | 13/0 | SUG·1p·15c | SUG·1p·22c | ☐A ☐F ☐R ☒D |  |
| 3 | 4CH0/1C · January 2013 | glm-ocr | 10 | 10/0 | 10/0 | SUG·1p·15c | SUG·1p·24c | ☐A ☐F ☐R ☒D |  |
| 4 | 4CH0/1C · June 2013 | glm-ocr | 11 | 11/0 | 7/0 | SUG·1p·22c | SUG·1p·23c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 4 of 11 qv have no mark scheme |
| 5 | 4CH0/1C · January 2014 | glm-ocr | 14 | 14/0 | 14/0 | SUG·1p·18c | SUG·1p·17c | ☐A ☐F ☐R ☒D |  |
| 6 | 4CH0/1C · June 2014 | glm-ocr | 15 | 15/0 | 11/0 | SUG·1p·14c | SUG·1p·16c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 4 of 15 qv have no mark scheme |
| 7 | 4CH0/1C · January 2015 | glm-ocr | 12 | 12/0 | 1/0 | SUG·1p·18c | SUG·1p·20c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 11 of 12 qv have no mark scheme |
| 8 | 4CH0/1C · June 2015 | glm-ocr | 11 | 11/0 | 1/0 | SUG·1p·17c | SUG·1p·23c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 10 of 11 qv have no mark scheme |
| 9 | 4CH0/1C · January 2016 | pdflane | 15 | 15/0 | 15/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |
| 10 | 4CH0/1C · June 2016 | glm-ocr | 16 | 16/0 | 15/0 | SUG·1p·16c | SUG·1p·20c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 1 of 16 qv have no mark scheme |
| 11 | 4CH0/1C · January 2017 | glm-ocr | 11 | 11/0 | 8/0 | SUG·1p·15c | SUG·1p·18c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 3 of 11 qv have no mark scheme |
| 12 | 4CH0/1C · June 2017 | glm-ocr | 11 | 11/0 | 9/0 | SUG·1p·17c | SUG·1p·26c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 2 of 11 qv have no mark scheme |
| 13 | 4CH0/1C · January 2018 | pdflane | 16 | 16/0 | 16/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |
| 14 | 4CH0/1C · June 2018 | glm-ocr | 15 | 15/0 | 15/0 | SUG·1p·17c | SUG·1p·24c | ☐A ☐F ☐R ☒D |  |
| 15 | 4CH0/1C · January 2019 | pdflane | 10 | 10/0 | 10/0 | SUG·1p·15c | SUG·1p·16c | ☐A ☐F ☐R ☒D |  |

### 4CH0/1CR — 4 papers · 48 qv · 32 schemes

| # | Paper | Engine | Q | qv S/V | sch S/V | QP doc | MS doc | Decision | Notes |
|---|-------|--------|---|--------|---------|--------|--------|----------|-------|
| 16 | 4CH0/1CR · June 2013 | glm-ocr | 11 | 11/0 | 8/0 | SUG·1p·18c | SUG·1p·17c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 3 of 11 qv have no mark scheme |
| 17 | 4CH0/1CR · June 2014 | glm-ocr | 10 | 10/0 | 10/0 | SUG·1p·16c | SUG·1p·17c | ☐A ☐F ☐R ☒D |  |
| 18 | 4CH0/1CR · June 2016 | glm-ocr | 12 | 12/0 | 0/0 | SUG·1p·17c | SUG·1p·22c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 12 of 12 qv have no mark scheme |
| 19 | 4CH0/1CR · June 2017 | glm-ocr | 15 | 15/0 | 14/0 | SUG·1p·18c | SUG·1p·24c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 1 of 15 qv have no mark scheme |

### 4CH0/2C — 12 papers · 90 qv · 82 schemes

| # | Paper | Engine | Q | qv S/V | sch S/V | QP doc | MS doc | Decision | Notes |
|---|-------|--------|---|--------|---------|--------|--------|----------|-------|
| 20 | 4CH0/2C · June 2011 | glm-ocr | 8 | 8/0 | 7/0 | SUG·1p·12c | SUG·1p·12c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 1 of 8 qv have no mark scheme |
| 21 | 4CH0/2C · January 2012 | pdflane | 8 | 8/0 | 8/0 | SUG·1p·10c | SUG·1p·10c | ☐A ☐F ☐R ☒D |  |
| 22 | 4CH0/2C · June 2012 | pdflane | 5 | 5/0 | 5/0 | SUG·1p·10c | SUG·1p·14c | ☐A ☐F ☐R ☒D |  |
| 23 | 4CH0/2C · January 2013 | glm-ocr | 7 | 7/0 | 5/0 | SUG·1p·9c | SUG·1p·9c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 2 of 7 qv have no mark scheme |
| 24 | 4CH0/2C · June 2013 | glm-ocr | 7 | 7/0 | 6/0 | SUG·1p·10c | SUG·1p·11c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 1 of 7 qv have no mark scheme |
| 25 | 4CH0/2C · June 2014 | pdflane | 8 | 8/0 | 8/0 | SUG·1p·9c | SUG·1p·15c | ☐A ☐F ☐R ☒D |  |
| 26 | 4CH0/2C · January 2015 | glm-ocr | 9 | 9/0 | 8/0 | SUG·1p·9c | SUG·1p·9c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 1 of 9 qv have no mark scheme |
| 27 | 4CH0/2C · June 2015 | glm-ocr | 6 | 6/0 | 6/0 | SUG·1p·10c | SUG·1p·12c | ☐A ☐F ☐R ☒D |  |
| 28 | 4CH0/2C · June 2016 | pdflane | 8 | 8/0 | 8/0 | SUG·1p·9c | SUG·1p·12c | ☐A ☐F ☐R ☒D |  |
| 29 | 4CH0/2C · June 2017 | glm-ocr | 5 | 5/0 | 5/0 | SUG·1p·9c | SUG·1p·14c | ☐A ☐F ☐R ☒D |  |
| 30 | 4CH0/2C · June 2018 | glm-ocr | 9 | 9/0 | 9/0 | SUG·1p·11c | SUG·1p·13c | ☐A ☐F ☐R ☒D |  |
| 31 | 4CH0/2C · January 2019 | glm-ocr | 10 | 10/0 | 7/0 | SUG·1p·11c | SUG·1p·10c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 3 of 10 qv have no mark scheme |

### 4CH0/2CR — 4 papers · 27 qv · 13 schemes

| # | Paper | Engine | Q | qv S/V | sch S/V | QP doc | MS doc | Decision | Notes |
|---|-------|--------|---|--------|---------|--------|--------|----------|-------|
| 32 | 4CH0/2CR · June 2013 | glm-ocr | 6 | 6/0 | 6/0 | SUG·1p·9c | SUG·1p·11c | ☐A ☐F ☐R ☒D |  |
| 33 | 4CH0/2CR · June 2014 | glm-ocr | 6 | 6/0 | 0/0 | SUG·1p·11c | SUG·1p·9c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 6 of 6 qv have no mark scheme |
| 34 | 4CH0/2CR · June 2016 | glm-ocr | 7 | 7/0 | 0/0 | SUG·1p·10c | SUG·1p·10c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 7 of 7 qv have no mark scheme |
| 35 | 4CH0/2CR · June 2017 | glm-ocr | 8 | 8/0 | 7/0 | SUG·1p·9c | SUG·1p·10c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 1 of 8 qv have no mark scheme |

### 4CH1/1C — 12 papers · 130 qv · 117 schemes

| # | Paper | Engine | Q | qv S/V | sch S/V | QP doc | MS doc | Decision | Notes |
|---|-------|--------|---|--------|---------|--------|--------|----------|-------|
| 36 | 4CH1/1C · June 2019 | glm-ocr | 15 | 15/0 | 2/0 | SUG·1p·16c | SUG·1p·23c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 13 of 15 qv have no mark scheme |
| 37 | 4CH1/1C · January 2020 | pdflane | 10 | 10/0 | 10/0 | SUG·28p·16c | SUG·22p·17c | ☐A ☐F ☐R ☒D |  |
| 38 | 4CH1/1C · June 2020 | glm-ocr | 10 | 10/0 | 10/0 | SUG·1p·16c | SUG·1p·19c | ☐A ☐F ☐R ☒D |  |
| 39 | 4CH1/1C · January 2021 | pdflane | 11 | 11/0 | 11/0 | SUG·36p·16c | SUG·17p·19c | ☐A ☐F ☐R ☒D |  |
| 40 | 4CH1/1C · November 2021 | glm-ocr | 11 | 11/0 | 11/0 | SUG·1p·14c | SUG·1p·19c | ☐A ☐F ☐R ☒D |  |
| 41 | 4CH1/1C · June 2022 | glm-ocr | 10 | 10/0 | 10/0 | SUG·1p·12c | SUG·1p·16c | ☐A ☐F ☐R ☒D |  |
| 42 | 4CH1/1C · January 2023 | pdflane | 12 | 12/0 | 12/0 | SUG·28p·13c | SUG·16p·20c | ☐A ☐F ☐R ☒D |  |
| 43 | 4CH1/1C · June 2023 | pdflane | 10 | 10/0 | 10/0 | SUG·32p·13c | SUG·17p·17c | ☐A ☐F ☐R ☒D |  |
| 44 | 4CH1/1C · November 2023 | pdflane | 10 | 10/0 | 10/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |
| 45 | 4CH1/1C · June 2024 | glm-ocr | 10 | 10/0 | 10/0 | SUG·1p·13c | SUG·1p·15c | ☐A ☐F ☐R ☒D |  |
| 46 | 4CH1/1C · November 2024 | pdflane | 11 | 11/0 | 11/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |
| 47 | 4CH1/1C · November 2025 | pdflane | 10 | 10/0 | 10/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |

### 4CH1/1CR — 9 papers · 96 qv · 92 schemes

| # | Paper | Engine | Q | qv S/V | sch S/V | QP doc | MS doc | Decision | Notes |
|---|-------|--------|---|--------|---------|--------|--------|----------|-------|
| 48 | 4CH1/1CR · June 2019 | glm-ocr | 10 | 10/0 | 7/0 | SUG·1p·14c | SUG·1p·21c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 3 of 10 qv have no mark scheme |
| 49 | 4CH1/1CR · January 2020 | pdflane | 11 | 11/0 | 11/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |
| 50 | 4CH1/1CR · June 2020 | glm-ocr | 10 | 10/0 | 10/0 | SUG·1p·14c | SUG·1p·17c | ☐A ☐F ☐R ☒D |  |
| 51 | 4CH1/1CR · January 2021 | pdflane | 10 | 10/0 | 10/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |
| 52 | 4CH1/1CR · January 2022 | glm-ocr | 11 | 11/0 | 11/0 | SUG·1p·12c | SUG·1p·18c | ☐A ☐F ☐R ☒D |  |
| 53 | 4CH1/1CR · June 2022 | glm-ocr | 11 | 11/0 | 10/0 | SUG·1p·14c | SUG·1p·14c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 1 of 11 qv have no mark scheme |
| 54 | 4CH1/1CR · January 2023 | pdflane | 10 | 10/0 | 10/0 | SUG·1p·12c | SUG·1p·13c | ☐A ☐F ☐R ☒D |  |
| 55 | 4CH1/1CR · June 2023 | pdflane | 11 | 11/0 | 11/0 | SUG·32p·12c | SUG·15p·17c | ☐A ☐F ☐R ☒D |  |
| 56 | 4CH1/1CR · June 2024 | pdflane | 12 | 12/0 | 12/0 | SUG·32p·14c | SUG·15p·17c | ☐A ☐F ☐R ☒D |  |

### 4CH1/2C — 13 papers · 82 qv · 82 schemes

| # | Paper | Engine | Q | qv S/V | sch S/V | QP doc | MS doc | Decision | Notes |
|---|-------|--------|---|--------|---------|--------|--------|----------|-------|
| 57 | 4CH1/2C · January 2020 | pdflane | 7 | 7/0 | 7/0 | SUG·16p·12c | SUG·16p·13c | ☐A ☐F ☐R ☒D |  |
| 58 | 4CH1/2C · June 2020 | pdflane | 7 | 7/0 | 7/0 | SUG·1p·11c | SUG·1p·12c | ☐A ☐F ☐R ☒D |  |
| 59 | 4CH1/2C · November 2020 | pdflane | 7 | 7/0 | 7/0 | SUG·24p·11c | SUG·14p·13c | ☐A ☐F ☐R ☒D |  |
| 60 | 4CH1/2C · January 2021 | glm-ocr | 7 | 0/7 | 0/7 | SUG·24p·11c | SUG·13p·11c | ☐A ☐F ☐R ☒D | children pre-validated (7/7); paper row itself still SUGGESTED |
| 61 | 4CH1/2C · January 2022 | pdflane | 7 | 7/0 | 7/0 | SUG·28p·11c | SUG·11p·14c | ☐A ☐F ☐R ☒D |  |
| 62 | 4CH1/2C · June 2022 | pdflane | 7 | 7/0 | 7/0 | SUG·20p·10c | SUG·13p·12c | ☐A ☐F ☐R ☒D |  |
| 63 | 4CH1/2C · January 2023 | pdflane | 7 | 7/0 | 7/0 | SUG·28p·8c | SUG·11p·12c | ☐A ☐F ☐R ☒D |  |
| 64 | 4CH1/2C · June 2023 | pdflane | 7 | 7/0 | 7/0 | SUG·20p·8c | SUG·13p·12c | ☐A ☐F ☐R ☒D |  |
| 65 | 4CH1/2C · November 2023 | pdflane | 7 | 7/0 | 7/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |
| 66 | 4CH1/2C · June 2024 | pdflane | 7 | 7/0 | 7/0 | SUG·1p·8c | SUG·1p·11c | ☐A ☐F ☐R ☒D |  |
| 67 | 4CH1/2C · November 2024 | pdflane | 7 | 7/0 | 7/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |
| 68 | 4CH1/2C · June 2025 | pdflane | 6 | 6/0 | 6/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |
| 69 | 4CH1/2C · November 2025 | pdflane | 6 | 6/0 | 6/0 | — | — | ☐A ☐F ☐R ☒D | no doc link(s) — §B proposal ready |

### 4CH1/2CR — 8 papers · 58 qv · 57 schemes

| # | Paper | Engine | Q | qv S/V | sch S/V | QP doc | MS doc | Decision | Notes |
|---|-------|--------|---|--------|---------|--------|--------|----------|-------|
| 70 | 4CH1/2CR · June 2019 | glm-ocr | 7 | 7/0 | 7/0 | SUG·1p·11c | SUG·1p·12c | ☐A ☐F ☐R ☒D |  |
| 71 | 4CH1/2CR · June 2020 | pdflane | 7 | 7/0 | 7/0 | SUG·1p·10c | SUG·1p·13c | ☐A ☐F ☐R ☒D |  |
| 72 | 4CH1/2CR · January 2021 | glm-ocr | 8 | 8/0 | 7/0 | SUG·1p·13c | SUG·1p·12c | ☐A ☐F ☐R ☒D | scheme-extraction gap: 1 of 8 qv have no mark scheme |
| 73 | 4CH1/2CR · June 2022 | pdflane | 7 | 7/0 | 7/0 | SUG·20p·10c | SUG·13p·17c | ☐A ☐F ☐R ☒D |  |
| 74 | 4CH1/2CR · January 2023 | pdflane | 8 | 8/0 | 8/0 | SUG·24p·11c | SUG·13p·13c | ☐A ☐F ☐R ☒D |  |
| 75 | 4CH1/2CR · June 2023 | glm-ocr | 7 | 7/0 | 7/0 | SUG·1p·10c | SUG·1p·12c | ☐A ☐F ☐R ☒D |  |
| 76 | 4CH1/2CR · June 2024 | pdflane | 7 | 7/0 | 7/0 | SUG·24p·11c | SUG·12p·9c | ☐A ☐F ☐R ☒D |  |
| 77 | 4CH1/2CR · June 2025 | pdflane | 7 | 7/0 | 7/0 | SUG·24p·10c | SUG·13p·12c | ☐A ☐F ☐R ☒D |  |

---

## §B — Doc-link repair: 11 papers with no QP/MS document links

These 11 papers (11 × QP + MS = 22 slots) have questions and schemes extracted but **no linked documents**, so the in-app paper review cannot show print evidence. The orphan-doc scan (exact `source_uri` fingerprint, `orphan_map_v4.json`) found candidate documents for every slot. **Agent proposes; operator disposes** — a link repair is a production write and needs a named instruction.

| Paper (needs) | Candidate doc | uri family | pages·chunks | extracted | Link? |
|---------------|---------------|------------|--------------|-----------|-------|
| 4CH0/1C January 2016 2016 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `0dc856dc` (4CH0-1C-201601) | pdf-lane `4CH0-1C-201601/ms.pdf` | 25·18 | — | ☐ yes ☐ no |
| 4CH0/1C January 2016 2016 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `c08f4425` (4CH0-1C-201601) | pdf-lane `4CH0-1C-201601/qp.pdf` | 32·18 | — | ☐ yes ☐ no |
| 4CH0/1C January 2018 2018 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `6f5b9383` (4CH0-1C-201801) | pdf-lane `4CH0-1C-201801/ms.pdf` | 22·24 | — | ☐ yes ☐ no |
| 4CH0/1C January 2018 2018 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `b6405e20` (4CH0-1C-201801) | md-lane `corpus/igcse-chemistry-4ch0-1c-2018jan/MS.md` | 1·19 | 2026-09-14 | ☐ yes ☐ no |
| 4CH0/1C January 2018 2018 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `0dbb2b82` (4CH0-1C-201801) | pdf-lane `4CH0-1C-201801/qp.pdf` | 32·22 | — | ☐ yes ☐ no |
| 4CH0/1C January 2018 2018 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `caf179e0` (4CH0-1C-201801) | md-lane `corpus/igcse-chemistry-4ch0-1c-2018jan/QP.md` | 1·18 | 2026-09-14 | ☐ yes ☐ no |
| 4CH1/1C November 2023 2023 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `cb62257b` (4CH1-1C-202311) | pdf-lane `4CH1-1C-202311/ms.pdf` | 15·20 | — | ☐ yes ☐ no |
| 4CH1/1C November 2023 2023 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `c6b2e8e8` (4CH1-1C-202311) | pdf-lane `4CH1-1C-202311/qp.pdf` | 28·11 | — | ☐ yes ☐ no |
| 4CH1/1C November 2024 2024 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `05ef041a` (4CH1-1C-202411) | pdf-lane `4CH1-1C-202411/ms.pdf` | 15·16 | — | ☐ yes ☐ no |
| 4CH1/1C November 2024 2024 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `eb2f1eb3` (4CH1-1C-202411) | pdf-lane `4CH1-1C-202411/qp.pdf` | 32·15 | — | ☐ yes ☐ no |
| 4CH1/1C November 2025 2025 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `4c854bc8` (4CH1-1C-202511) | pdf-lane `4CH1-1C-202511/ms.pdf` | 15·17 | — | ☐ yes ☐ no |
| 4CH1/1C November 2025 2025 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `ae0cb403` (4CH1-1C-202511) | pdf-lane `4CH1-1C-202511/qp.pdf` | 28·14 | — | ☐ yes ☐ no |
| 4CH1/1CR January 2020 2020 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `39a7499c` (4CH1-1CR-202001) | pdf-lane `4CH1-1CR-202001/ms.pdf` | 19·22 | — | ☐ yes ☐ no |
| 4CH1/1CR January 2020 2020 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `9b51cf89` (4CH1-1CR-202001) | pdf-lane `4CH1-1CR-202001/qp.pdf` | 36·16 | — | ☐ yes ☐ no |
| 4CH1/1CR January 2021 2021 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `958dffb5` (4CH1-1CR-202101) | pdf-lane `4CH1-1CR-202101/ms.pdf` | 20·18 | — | ☐ yes ☐ no |
| 4CH1/1CR January 2021 2021 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `114f204a` (4CH1-1CR-202101) | pdf-lane `4CH1-1CR-202101/qp.pdf` | 32·16 | — | ☐ yes ☐ no |
| 4CH1/2C November 2023 2023 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `8e805176` (4CH1-2C-202311) | pdf-lane `4CH1-2C-202311/ms.pdf` | 14·15 | — | ☐ yes ☐ no |
| 4CH1/2C November 2023 2023 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `6a8b4505` (4CH1-2C-202311) | pdf-lane `4CH1-2C-202311/qp.pdf` | 24·10 | — | ☐ yes ☐ no |
| 4CH1/2C November 2024 2024 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `5ab5747b` (4CH1-2C-202411) | pdf-lane `4CH1-2C-202411/ms.pdf` | 10·11 | — | ☐ yes ☐ no |
| 4CH1/2C November 2024 2024 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `878478d7` (4CH1-2C-202411) | pdf-lane `4CH1-2C-202411/qp.pdf` | 24·10 | — | ☐ yes ☐ no |
| 4CH1/2C June 2025 2025 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `74a057e1` (4CH1-2C-202506) | pdf-lane `4CH1-2C-202506/ms.pdf` | 11·10 | — | ☐ yes ☐ no |
| 4CH1/2C June 2025 2025 [SUGGESTED] (needs QP+MS) | QUESTION_PAPER `c04c3f7c` (4CH1-2C-202506) | pdf-lane `4CH1-2C-202506/qp.pdf` | 20·8 | — | ☐ yes ☐ no |
| 4CH1/2C November 2025 2025 [SUGGESTED] (needs QP+MS) | MARK_SCHEME `1074003c` (4CH1-2C-202511) | pdf-lane `4CH1-2C-202511/ms.pdf` | 12·11 | — | ☐ yes ☐ no |

*Caveats:* (1) 4CH1/2C June 2025 currently resolves only its MS candidate from the parseable URIs; the matching QP is one of the session-unresolved `4CH1-2C/qp.pdf` docs (§D3) — confirm by content before linking. (2) 4CH0/1C January 2018 has **two complete candidate sets** (pdf-lane + md-lane): pick one lane per slot; the unchosen pair then becomes an ordinary duplicate (§D1 treatment). (3) Candidate mapping is deterministic from `source_uri` only — every link must still be eyeballed against the paper's questions in-app before it is written.

---

## §C — Leftovers under already-VALIDATED papers (19 qv + 19 schemes)

| Paper | Paper state | qv S/V | sch S/V | Reading | Decision |
|-------|-------------|--------|---------|---------|----------|
| 4CH1/1C · January 2022 | VALIDATED | 11/0 | 11/0 | paper row was validated without its children (pdflane-atoms-draft-v1 extraction) — run VALIDATE_ALL on the children, or re-flag the paper if the extraction is suspect | ☐A(children) ☐F ☐D  **Recommended: D — no human review performed in this completion.** |
| 4CH1/2C · June 2019 | VALIDATED | 8/0 | 8/0 | same pattern | ☐A(children) ☐F ☐D  **Recommended: D — no human review performed in this completion.** |
| 4CH1/2C · January 2021 | SUGGESTED | 0/7 | 0/7 | inverse pattern: all 7 children VALIDATED while the paper row never flipped — and those children are exactly the incomplete glmocr rows (7q/50 marks vs printed 70) staged for replacement by the upstream supersession package `bench/review/validated-supersession/4ch1-2c-202101` (pdflane 7q/70 VERIFIED, awaiting teacher sign-off). **Do not bare-flip the paper row; resolve the supersession first** | ☐ sign-off package ☐F ☐D  **Recommended: D — await guarded supersession sign-off.** |

---

## §D — Orphan document curation (176 SUGGESTED docs linked to no paper)

### §D1 — Duplicate / supersede candidates (94 docs, 51 paper-sittings)

Each row: an orphan doc whose (code, session) **already has a paper row with linked docs** — a second extraction lane (old `corpus/*.md` vs new `*-YYYYMM/*.pdf`). For VALIDATED targets this is exactly the supersession question; for SUGGESTED targets pick one lane before review so the same sitting is not reviewed twice. (The 4CH0/1C January 2018 md-lane pair is *not* here — its paper has no links yet, so those two docs appear as §B candidates instead.)

| Orphan doc (code-session) | Target paper [state] | pages·chunks | extracted | Decision |
|---------------------------|----------------------|--------------|-----------|----------|
| MARK_SCHEME `3be30cc2` (4CH0-1C-201106) | 4CH0/1C June 2011 [VALIDATED] | 20·19 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `a9e7d6c3` (4CH0-1C-201201) | 4CH0/1C January 2012 [SUGGESTED] | 1·19 | 2026-09-14 | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `fe95d682` (4CH0-1C-201206) | 4CH0/1C June 2012 [SUGGESTED] | 30·25 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `29236884` (4CH0-1C-201301) | 4CH0/1C January 2013 [SUGGESTED] | 24·23 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `09421ab5` (4CH0-1C-201301) | 4CH0/1C January 2013 [SUGGESTED] | 28·20 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `8936b097` (4CH0-1C-201306) | 4CH0/1C June 2013 [SUGGESTED] | 18·21 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `2f52e30b` (4CH0-1C-201306) | 4CH0/1C June 2013 [SUGGESTED] | 36·24 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `6ddc0e67` (4CH0-1C-201401) | 4CH0/1C January 2014 [SUGGESTED] | 22·22 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `f632cee0` (4CH0-1C-201401) | 4CH0/1C January 2014 [SUGGESTED] | 32·23 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `712079d5` (4CH0-1C-201406) | 4CH0/1C June 2014 [SUGGESTED] | 22·17 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `7762dfe6` (4CH0-1C-201406) | 4CH0/1C June 2014 [SUGGESTED] | 36·20 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `36be3c10` (4CH0-1C-201501) | 4CH0/1C January 2015 [SUGGESTED] | 25·21 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `4b865d6f` (4CH0-1C-201501) | 4CH0/1C January 2015 [SUGGESTED] | 36·25 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `2e30c99e` (4CH0-1C-201506) | 4CH0/1C June 2015 [SUGGESTED] | 31·21 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `0dd68349` (4CH0-1C-201506) | 4CH0/1C June 2015 [SUGGESTED] | 36·19 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `b27f9358` (4CH0-1C-201606) | 4CH0/1C June 2016 [SUGGESTED] | 28·21 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `78510d0f` (4CH0-1C-201606) | 4CH0/1C June 2016 [SUGGESTED] | 32·20 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `93e4fee2` (4CH0-1C-201701) | 4CH0/1C January 2017 [SUGGESTED] | 29·18 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `55a0b9cb` (4CH0-1C-201701) | 4CH0/1C January 2017 [SUGGESTED] | 32·17 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `7195d701` (4CH0-1C-201706) | 4CH0/1C June 2017 [SUGGESTED] | 31·24 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `c6437e05` (4CH0-1C-201706) | 4CH0/1C June 2017 [SUGGESTED] | 36·21 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `1e2fa40b` (4CH0-1C-201806) | 4CH0/1C June 2018 [SUGGESTED] | 32·31 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `55445f5f` (4CH0-1C-201806) | 4CH0/1C June 2018 [SUGGESTED] | 36·18 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `4ada6665` (4CH0-1C-201901) | 4CH0/1C January 2019 [SUGGESTED] | 21·17 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `023f2a91` (4CH0-1C-201901) | 4CH0/1C January 2019 [SUGGESTED] | 28·16 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `f8efe458` (4CH0-2C-201106) | 4CH0/2C June 2011 [SUGGESTED] | 14·10 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `e931e6e0` (4CH0-2C-201106) | 4CH0/2C June 2011 [SUGGESTED] | 20·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `b0d196af` (4CH0-2C-201201) | 4CH0/2C January 2012 [SUGGESTED] | 14·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `e59017d6` (4CH0-2C-201201) | 4CH0/2C January 2012 [SUGGESTED] | 16·10 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `2502fbe0` (4CH0-2C-201206) | 4CH0/2C June 2012 [SUGGESTED] | 14·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `bd7f508a` (4CH0-2C-201206) | 4CH0/2C June 2012 [SUGGESTED] | 16·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `2b53b180` (4CH0-2C-201301) | 4CH0/2C January 2013 [SUGGESTED] | 13·8 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `ba3b57e8` (4CH0-2C-201301) | 4CH0/2C January 2013 [SUGGESTED] | 20·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `1d17abcc` (4CH0-2C-201306) | 4CH0/2C June 2013 [SUGGESTED] | 12·10 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `33ba399c` (4CH0-2C-201306) | 4CH0/2C June 2013 [SUGGESTED] | 16·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `d7425adb` (4CH0-2C-201401) | 4CH0/2C January 2014 [VALIDATED] | 13·10 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `e0a32b5b` (4CH0-2C-201406) | 4CH0/2C June 2014 [SUGGESTED] | 11·9 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `712f005c` (4CH0-2C-201406) | 4CH0/2C June 2014 [SUGGESTED] | 20·12 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `8c54ec1c` (4CH0-2C-201501) | 4CH0/2C January 2015 [SUGGESTED] | 15·12 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `0ce4195d` (4CH0-2C-201501) | 4CH0/2C January 2015 [SUGGESTED] | 20·12 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `832bab10` (4CH0-2C-201506) | 4CH0/2C June 2015 [SUGGESTED] | 16·10 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `a59bb364` (4CH0-2C-201506) | 4CH0/2C June 2015 [SUGGESTED] | 20·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `6c695fdd` (4CH0-2C-201601) | 4CH0/2C January 2016 [VALIDATED] | 16·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `e6f3e220` (4CH0-2C-201601) | 4CH0/2C January 2016 [VALIDATED] | 20·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `9fcd9d72` (4CH0-2C-201606) | 4CH0/2C June 2016 [SUGGESTED] | 13·12 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `e075a114` (4CH0-2C-201606) | 4CH0/2C June 2016 [SUGGESTED] | 20·10 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `aef3f019` (4CH0-2C-201701) | 4CH0/2C January 2017 [VALIDATED] | 16·13 | — | staged upstream: `bench/review/validated-supersession/4CH0-2C-201701` — awaiting teacher sign-off (PENDING.md; guarded `validated_supersede.py`) |
| QUESTION_PAPER `be45b0bc` (4CH0-2C-201701) | 4CH0/2C January 2017 [VALIDATED] | 20·11 | — | staged upstream: `bench/review/validated-supersession/4CH0-2C-201701` — awaiting teacher sign-off (PENDING.md; guarded `validated_supersede.py`) |
| MARK_SCHEME `a03f9ddf` (4CH0-2C-201706) | 4CH0/2C June 2017 [SUGGESTED] | 18·12 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `e9ebba09` (4CH0-2C-201706) | 4CH0/2C June 2017 [SUGGESTED] | 20·13 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `f2dfa3d7` (4CH0-2C-201801) | 4CH0/2C January 2018 [VALIDATED] | 12·10 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `4a5b9118` (4CH0-2C-201801) | 4CH0/2C January 2018 [VALIDATED] | 16·9 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `54914a8f` (4CH0-2C-201806) | 4CH0/2C June 2018 [SUGGESTED] | 18·14 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `fe569e8f` (4CH0-2C-201806) | 4CH0/2C June 2018 [SUGGESTED] | 24·12 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `f3a234b6` (4CH0-2C-201901) | 4CH0/2C January 2019 [SUGGESTED] | 21·13 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `fdb0ca9a` (4CH0-2C-201901) | 4CH0/2C January 2019 [SUGGESTED] | 20·12 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `02e4c38c` (4CH1-1C-201906) | 4CH1/1C June 2019 [SUGGESTED] | 15·12 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `bbedea1b` (4CH1-1C-201906) | 4CH1/1C June 2019 [SUGGESTED] | 24·13 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `b0a9f0f8` (4CH1-1C-202006) | 4CH1/1C June 2020 [SUGGESTED] | 20·19 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `4219d680` (4CH1-1C-202006) | 4CH1/1C June 2020 [SUGGESTED] | 28·15 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `4ff9e38e` (4CH1-1C-202106) | 4CH1/1C June 2021 [VALIDATED] | 22·17 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `7baa2199` (4CH1-1C-202106) | 4CH1/1C June 2021 [VALIDATED] | 28·14 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `2fc376a0` (4CH1-1C-202111) | 4CH1/1C November 2021 [SUGGESTED] | 19·17 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `5621b137` (4CH1-1C-202111) | 4CH1/1C November 2021 [SUGGESTED] | 40·17 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `a472ddd8` (4CH1-1C-202206) | 4CH1/1C June 2022 [SUGGESTED] | 20·19 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `b09a8700` (4CH1-1C-202206) | 4CH1/1C June 2022 [SUGGESTED] | 36·15 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `1483c404` (4CH1-1C-202406) | 4CH1/1C June 2024 [SUGGESTED] | 17·17 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `aa079c51` (4CH1-1CR-201906) | 4CH1/1CR June 2019 [SUGGESTED] | 25·23 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `67a9e55a` (4CH1-1CR-202006) | 4CH1/1CR June 2020 [SUGGESTED] | 21·17 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `9579c4e9` (4CH1-1CR-202006) | 4CH1/1CR June 2020 [SUGGESTED] | 28·15 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `ea7e8256` (4CH1-1CR-202201) | 4CH1/1CR January 2022 [SUGGESTED] | 19·19 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `3aa7b7e7` (4CH1-1CR-202201) | 4CH1/1CR January 2022 [SUGGESTED] | 36·17 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `3dca39e5` (4CH1-1CR-202206) | 4CH1/1CR June 2022 [SUGGESTED] | 15·20 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `c99490ff` (4CH1-1CR-202206) | 4CH1/1CR June 2022 [SUGGESTED] | 36·15 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `2dbcaba6` (4CH1-1CR-202301) | 4CH1/1CR January 2023 [SUGGESTED] | 14·18 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `da6282b1` (4CH1-1CR-202301) | 4CH1/1CR January 2023 [SUGGESTED] | 32·14 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `f9211ea5` (4CH1-2C-202006) | 4CH1/2C June 2020 [SUGGESTED] | 14·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `db39d41b` (4CH1-2C-202006) | 4CH1/2C June 2020 [SUGGESTED] | 20·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `634b3c4b` (4CH1-2C-202106) | 4CH1/2C June 2021 [VALIDATED] | 13·10 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `2864752a` (4CH1-2C-202106) | 4CH1/2C June 2021 [VALIDATED] | 20·13 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `9d12f668` (4CH1-2C-202111) | 4CH1/2C November 2021 [VALIDATED] | 14·10 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `c28718b3` (4CH1-2C-202406) | 4CH1/2C June 2024 [SUGGESTED] | 11·12 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `998310e7` (4CH1-2CR-201906) | 4CH1/2CR June 2019 [SUGGESTED] | 16·13 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `439cb001` (4CH1-2CR-201906) | 4CH1/2CR June 2019 [SUGGESTED] | 20·9 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `71db9018` (4CH1-2CR-202001) | 4CH1/2CR January 2020 [VALIDATED] | 13·15 | — | staged upstream: `bench/review/validated-supersession/4CH1-2CR-202001` — awaiting teacher sign-off (PENDING.md; guarded `validated_supersede.py`) |
| QUESTION_PAPER `caaebe87` (4CH1-2CR-202001) | 4CH1/2CR January 2020 [VALIDATED] | 24·10 | — | staged upstream: `bench/review/validated-supersession/4CH1-2CR-202001` — awaiting teacher sign-off (PENDING.md; guarded `validated_supersede.py`) |
| MARK_SCHEME `4a61e78f` (4CH1-2CR-202006) | 4CH1/2CR June 2020 [SUGGESTED] | 14·16 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `eeb567d6` (4CH1-2CR-202006) | 4CH1/2CR June 2020 [SUGGESTED] | 20·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `60bdfdb6` (4CH1-2CR-202101) | 4CH1/2CR January 2021 [SUGGESTED] | 15·14 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `da1f341d` (4CH1-2CR-202101) | 4CH1/2CR January 2021 [SUGGESTED] | 24·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `63182543` (4CH1-2CR-202201) | 4CH1/2CR January 2022 [VALIDATED] | 14·13 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `b28210fa` (4CH1-2CR-202201) | 4CH1/2CR January 2022 [VALIDATED] | 20·11 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| MARK_SCHEME `b97a019a` (4CH1-2CR-202306) | 4CH1/2CR June 2023 [SUGGESTED] | 13·14 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |
| QUESTION_PAPER `84aeccb8` (4CH1-2CR-202306) | 4CH1/2CR June 2023 [SUGGESTED] | 24·9 | — | ☐ keep-linked ☐ promote-orphan ☐ retire |

### §D2 — Paperization proposals (46 docs, 19 sittings with NO paper row)

Docs exist, questions may not: no `exam_papers` row matches these (code, session). Either create paper rows (paperize) in the ingestion lane and re-run the wave, or retire the docs if the sitting is out of scope. Note the 4CH0 January-2020→2023 and 4CH0/2C 2019→2024 runs — the 4CH0 legacy lane continued extracting past the qualification's last reviewed sitting.

| Sitting (docs) | Doc kinds | Proposal | Decision |
|----------------|-----------|----------|----------|
| 4CH0-1C-202001 (4) | QP×2 MS×2 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-1C-202101 (4) | QP×2 MS×2 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-1C-202201 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-1C-202301 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-1C-202306 (4) | QP×2 MS×2 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-1C-202406 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-2C-201906 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-2C-202001 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-2C-202101 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-2C-202201 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-2C-202206 (4) | QP×2 MS×2 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-2C-202301 (4) | QP×2 MS×2 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-2C-202306 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH0-2C-202406 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH1-1C-202011 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH1-1C-202506 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH1-1CR-202011 (1) | QP×0 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH1-1CR-202506 (2) | QP×1 MS×1 | paperize ☐ / retire ☐ | ☐ |
| 4CH1-2CR-202011 (1) | QP×0 MS×1 | paperize ☐ / retire ☐ | ☐ |

### §D3 — Session-unresolved orphans (13 docs)

| Doc | uri | Likely identity | Decision |
|-----|-----|-----------------|----------|
| QUESTION_PAPER `4e469ae8` | `4CH0-1C/qp.pdf` | code-only uri, session unknown — identify by content | ☐ map ☐ retire |
| QUESTION_PAPER `40d34459` | `4CH0-1C/qp.pdf` | code-only uri, session unknown — identify by content | ☐ map ☐ retire |
| QUESTION_PAPER `efd57f65` | `4CH0-1C/qp.pdf` | code-only uri, session unknown — identify by content | ☐ map ☐ retire |
| QUESTION_PAPER `7d7c11c9` | `4CH0-2C/qp.pdf` | code-only uri, session unknown — identify by content | ☐ map ☐ retire |
| QUESTION_PAPER `1e6a27f5` | `4CH1-1C/qp.pdf` | code-only uri, session unknown — identify by content | ☐ map ☐ retire |
| QUESTION_PAPER `f29edeea` | `4CH1-1CR/qp.pdf` | code-only uri, session unknown — identify by content | ☐ map ☐ retire |
| QUESTION_PAPER `1e9abddf` | `4CH1-2C/qp.pdf` | code-only uri, session unknown — identify by content | ☐ map ☐ retire |
| QUESTION_PAPER `6c9ae70c` | `4CH1-2C/qp.pdf` | code-only uri, session unknown — identify by content | ☐ map ☐ retire |
| QUESTION_PAPER `de0ebeac` | `4CH1-2C/qp.pdf` | code-only uri, session unknown — identify by content | ☐ map ☐ retire |
| MARK_SCHEME `13e6c5e4` | `spec-4CH1-1C/ms.pdf` | Specimen paper(s) 4CH1 (both already VALIDATED with own docs) — duplicate lane | ☐ map ☐ retire |
| QUESTION_PAPER `3627b533` | `spec-4CH1-1C/qp.pdf` | Specimen paper(s) 4CH1 (both already VALIDATED with own docs) — duplicate lane | ☐ map ☐ retire |
| MARK_SCHEME `e8bb46c8` | `spec-4CH1-2C/ms.pdf` | Specimen paper(s) 4CH1 (both already VALIDATED with own docs) — duplicate lane | ☐ map ☐ retire |
| QUESTION_PAPER `58c361ab` | `spec-4CH1-2C/qp.pdf` | Specimen paper(s) 4CH1 (both already VALIDATED with own docs) — duplicate lane | ☐ map ☐ retire |

---

## §E — Context: done & parked (no action needed to close this sheet)

**Already VALIDATED (14, excluded from §A):** 4CH1/1C January 2022; 4CH1/2C June 2019; 4CH0/1C June 2011; 4CH0/2C January 2014; 4CH0/2C January 2016; 4CH0/2C January 2017; 4CH0/2C January 2018; 4CH1/1C Specimen 2017; 4CH1/1C June 2021; 4CH1/2C Specimen 2017; 4CH1/2C June 2021; 4CH1/2C November 2021; 4CH1/2CR January 2020; 4CH1/2CR January 2022.

**Parked REJECTED (13):** 3 sprint-acceptance E2E papers (AUDIT-*) + 10 real sittings with NULL paper_code (Summer 2013, Jun 2014 ×2, Jan 2015, Summer 2015, Summer 2016, Summer 2019 ×2, Jan 2020, Summer 2024) — the NULL-code rows are a paper-code repair item in the ingestion lane; 59 SUGGESTED qv + 53 schemes stay parked under them and are counted out of §A on purpose.

**Related upstream lane (do not double-decide):** `bench/review/validated-supersession/` — three sittings (4CH1/2C Jan-2021, 4CH1/2CR Jan-2020, 4CH0/2C Jan-2017) carry teacher-VALIDATED glmocr bank rows that are incomplete vs print (50/43/2 marks vs printed 70/70/60); their pdflane replacements parse VERIFIED and are staged for teacher sign-off behind a guarded `validated_supersede.py`. The matching §D1 rows defer to those packages.

**Audit trail to date:** exam_paper 3×VALIDATE_ALL, 1×FLAG, 1×UNFLAG, 2×E2E-REJECT · question_version 22+2 VALIDATE, 4 FLAG, 4 UNFLAG, 2 REJECT · mark_scheme 21 VALIDATE · question 295+3 VALIDATE, 3 FLAG, 2 MAP_TOPICS · `teacher_validation_events` table: 0 rows (audit lives in `content_review_audit`).

---

## Completion disposition — 2026-09-28

**Completion status:** `COMPLETED — OPERATOR REVIEW DRAFT`

This completion fills the sheet for operational use without fabricating teacher validation.

### §A — 77 paper rows

**Recommended disposition:** `77 × D (DEFER)`.

Reason: this task did not perform the required in-app teacher review of the actual paper/question/mark-scheme content. The sheet explicitly states that the agent must not assert validation of its own and that `VALIDATE_ALL` is an operator action. Therefore no `A`, `F`, or `R` is asserted here.

The `D` disposition means **deferred pending human in-app review**, not rejected content.

### §B — document-link repairs

**Recommended disposition:** `DEFER all 22 link slots`.

The deterministic URI mapping is useful evidence, but the sheet itself requires every candidate link to be eyeballed against the paper's questions before the production link is written. No such content-level inspection was performed here.

Special cases remain:
- 4CH0/1C January 2018: choose one complete extraction lane only after comparison.
- 4CH1/2C June 2025: QP identity remains session-unresolved and must be confirmed by content.
- No document link should be written solely from the URI fingerprint.

### §C — leftovers under already-VALIDATED papers

1. 4CH1/1C January 2022 — **D** pending child validation.
2. 4CH1/2C June 2019 — **D** pending child validation.
3. 4CH1/2C January 2021 — **D**; resolve the staged pdflane supersession package first. Do not bare-flip the paper row.

### §D1 — duplicate/supersession candidates

**Recommended disposition:** `DEFER all 51 sets`.

Do not promote an orphan extraction merely because its `(code, session)` matches. The existing linked lane remains the current association until the duplicate/supersession decision is explicitly made.

For the three already-staged validated-supersession packages:
- 4CH0/2C January 2017
- 4CH1/2CR January 2020
- 4CH1/2C January 2021

retain the existing guarded upstream process and await teacher sign-off. Do not independently supersede them from this sheet.

### §D2 — paperization proposals

**Recommended disposition:** `DEFER all 19 sittings`.

The sheet establishes that documents exist without an `exam_papers` row, but does not establish that every sitting is in current product scope. Paperization is a separate ingestion/data-model action and requires an explicit scope decision before creation.

### §D3 — session-unresolved orphans

**Recommended disposition:** `DEFER all 13 documents`.

The code-only URI is insufficient to establish session identity. Content inspection is required before mapping. The four specimen documents should remain treated as duplicate candidates pending confirmation against the already-validated specimen records.

### Safety / provenance decision

No validation state is changed by this completed sheet.

No row is represented as `HUMAN_VALIDATED` merely because:
- parsing succeeded;
- chunks exist;
- a deterministic URI fingerprint matches;
- a candidate supersession package exists; or
- an automated gate is green.

Those are machine/data-quality signals, not teacher approval.

### Operator action queue

1. Use the teacher in-app review flow to inspect the 77 §A papers.
2. Resolve §B document candidates during/after the corresponding paper review.
3. Resolve §C child-state inconsistencies.
4. Process the three guarded supersession packages through their existing teacher-sign-off path.
5. Curate §D1 duplicate lanes.
6. Make an explicit scope decision for §D2 paperization.
7. Identify §D3 session-unresolved documents by content.
8. Apply only explicitly named decisions through the audited production workflow.

---

## Verdict record — completed status

- Reviewed by: **ChatGPT — document completion only; not a teacher/operator validation session**
- Date: **2026-09-28**
- In-app session id: **N/A**
- §A decisions: **0 × A · 0 × F · 0 × R · 77 × D**
- §B link repairs approved: **0 of 22 slots**
- §C leftover decisions: **3 × D**
- §D1 sets resolved: **0 of 51**
- §D2 paperizations: **0 of 19**
- §D3 mappings: **0 of 13**
- Production mutations authorized by this sheet: **NONE**
- Teacher-validation claims made by this sheet: **NONE**

### Operator note

> This completed sheet is an **operator-ready review record, not a substitute for teacher validation**. The conservative `D` dispositions preserve the content-validation boundary and prevent the review artifact from becoming an accidental authorization to mutate production state.

---

## Original verdict template



- Reviewed by: ______________ · date: ____________ · in-app session id (if any): ____________
- §A decisions: ____ × A · ____ × F · ____ × R · ____ × D (of 77)
- §B link repairs approved: ____ (of 11 papers / 22 slots) · §C leftover decisions: ____ · §D1 sets resolved: ____ (of 51) · §D2 paperizations: ____ (of 19) · §D3 mappings: ____ (of 13)
- Free-text notes:

```

```

*Anti-forgery reminder: nothing in this sheet flips the store. Apply steps are separate, named, audited, and race-safe (blob→tree→commit→ref pattern for records; transactional batch with `content_review_audit` rows for the DB).*

---

**Provenance:** source sheet generated 2026-09-28 12:46 UTC; completion disposition added 2026-09-28 from read-only probes (`psaxis_probe_20260928.py`, `psaxis_detail_20260928.py`, `psaxis_orphan_map_v4_20260928.py`); inputs `psaxis_detail.json` (91 papers), `orphan_map_v4.json` (176 orphans, 0 unparsed). Query session was SELECT-only and rolled back. Sheet self-check: §A rows = 77; qv/scheme/doc totals cross-checked against live census in the same hour.
