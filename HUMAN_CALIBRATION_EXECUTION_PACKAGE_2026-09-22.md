# G-4 HUMAN CALIBRATION EXECUTION PACKAGE — 2026-09-22 (session 116 handover)

**This is the exact, decision-free package for the operator / pilot teacher to
execute the genuine human κ reference round** — the ONLY remaining action that
can produce a valid release-gate row (ADR-025 / ADR-027 D3, Master Spec §15
F-161). Everything machine-executable about G-4 is done: the agent calibration
round (evidence `evidence/g4-agent-calibration-2026-09-22/` in the syllabai
repo) measured κ, pinned the marker convention, and was audited in session 116
(read `CORRECTIONS_2026-09-22.md` there — two findings materially affect Step 0
below). The gate stays fail-closed until YOUR row exists.

**Provenance law:** this round's decisions are `TEACHER` / human evidence.
Mark blind (never read the AI breakdown first — §1 order below enforces it).
Never copy AI decisions into human decisions.

**Time:** ~30–60 minutes. **Where:** any machine with `python3` + `curl`.
**Credentials:** `pilot.teacher@syllabai-test.dev` (operator-held; ADR-025
forbids provisioning new teacher accounts).

---

## STEP 0 — Preflight (all five, in order; ~5 min)

```bash
export SYLLABAI_BASE="https://syllabai-core.onrender.com"
curl -s "$SYLLABAI_BASE/actuator/health"            # expect {"status":"UP"...}
```

**0.2 Login (teacher)**

```bash
TOKEN=$(curl -s -X POST "$SYLLABAI_BASE/api/v1/auth/login" \
  -H "Content-Type: application/json" \
  -d '{"email":"pilot.teacher@syllabai-test.dev","password":"<OPERATOR-PASSWORD>"}' \
  | python3 -c "import sys,json;print(json.load(sys.stdin)['accessToken'])")
echo "token len: ${#TOKEN}"    # sanity only; do not paste the token anywhere
```

**0.3 κ-row preflight — NEW, MANDATORY (session-116 finding)**

The agent round's captured responses prove the student surface returned
`authoritative=true` during the round, and the fail-closed
`kappaGatePassed()` code implies **a PASSED κ evaluation row already exists in
production** (created by operator-side teacher/admin activity between
2026-09-16 and 2026-09-22 — provenance unknown; full reasoning in
`CORRECTIONS_2026-09-22.md` §Correction 1). Check it first:

```bash
curl -s "$SYLLABAI_BASE/api/v1/teacher/marking/kappa/latest" \
  -H "Authorization: Bearer $TOKEN" | python3 -m json.tool
# and paper-scoped (resolve paperId from 0.4's queue output first if needed):
# curl -s "$SYLLABAI_BASE/api/v1/teacher/marking/kappa/latest?paperId=<paperId>" ...
```

Record: `kappa`, `observedAgreement`, `sampleSize`, `threshold`, `passed`,
`computedBy`, `computedAt`.

**DECISION GATE — stop here if:** a row exists with `passed=true` and
`computedBy`/`computedAt` you cannot vouch for. Then decide BEFORE marking:
(a) keep-and-document it, or (b) proceed with this round — your Step 3 writes
a NEWER row that supersedes it (the gate reads newest-by-computedAt; a failing
human round re-closes the gate). Do not skip this decision: it determines
whether the gate is currently open and why.

**0.4 Verify the sample (read-only)**

```bash
curl -s "$SYLLABAI_BASE/api/v1/teacher/marking/queue-v2?state=PENDING" \
  -H "Authorization: Bearer $TOKEN" > queue_pending.json
python3 -c "
import json;q=json.load(open('queue_pending.json'))
import collections
c=collections.Counter(a.get('learnerEmail','?') for a in (q if isinstance(q,list) else q.get('answers',q.get('items',[]))))
print(c)" 2>/dev/null || cat queue_pending.json | head -50
```

- **Path A (preferred):** `pilot.learner01@syllabai-test.dev`'s original
  session-96 sample is present (4 attempts × 26 parts, PENDING). Mark those 26
  answers — key on learner01's attempt ids, ignore other learners' rows (the
  queue is a documented global read, ADR-025 interim).
- **Path B (fallback, already exercised):** the original sample is gone. Use
  the round's regenerated sample instead: learner
  `pilot.g4agent@syllabai-test.dev`, **7 attempts × 26 part answers on the
  same 4CH1 cells (S1-c ×2, S2-e ×1, S1-f ×1)**. These parts are already
  SMART_MARKED (25) / PENDING-refused (1) — a human mark on a smart-marked
  answer is the normal authoritative marking (HUMAN_MARKED); nothing needs
  reverting. Record the substitution in your run notes.
- **Path C (if neither exists):** STOP — report back; do not improvise a new
  sample without deciding it consciously (regeneration recipe: runbook §0.4).

**0.5 Worksheet tool ready**

```bash
cd <this-package-dir>            # g4_worksheet.py lives here
python3 g4_worksheet.py dump --learner pilot.learner01@syllabai-test.dev   # Path A
# Path B: python3 g4_worksheet.py dump --learner pilot.g4agent@syllabai-test.dev
```

The dump carries part prompt, scheme points (+ acceptance criteria +
generalGuidance) and the learner answer — **never the AI breakdown** (blind by
default; keep it that way).

---

## STEP 1 — Human reference marking, BLIND, under the PINNED convention (~25–40 min)

**THE CONVENTION (runbook ADDENDUM 2026-09-22 — measured swing κ 0.31 ↔ 1.00
on identical judgments, so this is gate-critical):**

> `perPointDecisions[point] = 1` if the learner's answer earns **ANY credit**
> on that point (any one of its sub-marks); `0` only when **NO part** of the
> point is earned. Partial credit = 1, not 0. Example from the agent round's
> cells: 3 of 4 sub-items correct → **1**; method mark earned but final value
> wrong → **1**; unit-conversion missed so nothing is creditable → **0**.

Judge ONLY from the scheme text against the learner answer. Do not open the
Smart Mark breakdown for any sample answer before your decisions are
submitted (the gate measures agreement, not agreement-seeking).

Fill the worksheet CSV (`marks_awarded`, `decision_<markPointId>` per point —
cover EVERY in-scope point of every part; a missing point silently drops from
pairing), then submit explicitly:

```bash
python3 g4_worksheet.py submit --worksheet g4_worksheet_<date>.csv
```

(Or per-answer via the API if you prefer:
`POST /api/v1/teacher/marking/answers/{id}/human-mark` with
`{"marksAwarded": n, "perPointDecisions": {"<markPointId>": 0|1, ...},
"comments": "..."}` — bounded by the part marks; 409 outside.)

Every submitted mark is authoritative and fires the BKT evidence contract
exactly once per attempt (at the completing mark). This is expected and is
the point: the sample becomes genuinely human-referenced data.

## STEP 2 — Smart Mark on the same answers

```bash
python3 g4_worksheet.py submit --worksheet g4_worksheet_<date>.csv   # if not done in 1
# then the batch (≤50 ids — one call):
curl -s -X POST "$SYLLABAI_BASE/api/v1/teacher/marking/smart-mark-batch" \
  -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" \
  -d "{\"answerIds\": [\"<id1>\", \"<id2>\", ...]}" | python3 -m json.tool
```

- Already-smart-marked answers (Path B: 25 of 26) come back `SKIPPED` —
  idempotent by design; their existing validation-passed results pair as-is.
- **Path B's one refused part** (`q7|b`, `UNPARSEABLE_OUTPUT`, attempt
  `7ad844d9…`) has NO validation-passed result, so the batch genuinely re-runs
  it. That is correct behavior (append-only run rows; the refusal stays in
  history). Under pipeline 1.2.0 it may parse now — record whatever happens,
  including a second refusal (see the investigation doc's watch item).
- Expect honest rows: `SCHEME_NOT_VALIDATED` / `PROVIDER_UNAVAILABLE` /
  `VALIDATION_FAILED` cannot pair — do not retry into a different outcome,
  record them. Deployed pipeline is **1.2.0** (partial marks within compound
  points, prompt v3) — the runbook's "1.1.0" line predates 2026-09-21.

## STEP 3 — Compute κ (the gate)

```bash
python3 g4_worksheet.py kappa --paper-id <paperId>    # paper scope
# and/or ALL scope:
curl -s -X POST "$SYLLABAI_BASE/api/v1/teacher/marking/kappa/evaluate" \
  -H "Authorization: Bearer $TOKEN" -H "Content-Type: application/json" -d '{}'
```

Read the row: `kappa`, `observedAgreement`, `sampleSize`, `threshold` (0.60),
`passed`. **Small-sample honesty:** ~26 parts ≈ 40–60 point decisions; read
the verdict WITH that width. κ < 0.60 → gate re-closes (fail-closed); honest
next moves are marker-calibration review (ambiguous acceptance criteria,
convention drift) and a fresh sample — never threshold adjustment. Note the
pairing silently drops: answers without per-point human decisions, answers
without a validation-passed smart run, points the human didn't cover. Check
`sampleSize` against expectations.

## STEP 4 — Closed-loop verification

1. `GET /teacher/marking/kappa/latest` (+ `?paperId=`) — your row is newest.
2. Student-surface check: from a STUDENT account on the same paper, submit a
   structured attempt and run Smart Mark — `authoritative` must now reflect
   the new gate state (true if your row passed).
3. Telemetry: `SMART_MARK_COMPLETED` events carry `authoritative`; Step 1
   fired `HUMAN_MARK_RECORDED` per mark.
4. Evidence-once: no duplicate BKT evidence rows for the sample attempts.

## STOP CONDITIONS (halt and report instead of improvising)

- 0.3 finds a passed κ row whose provenance you cannot vouch for (decide
  explicitly per 0.3 before continuing).
- Neither sample exists (Path C) and you do not want to regenerate today.
- Any 401/403 on teacher endpoints → credential/role problem, do not work
  around it.
- Step 3 returns 409 "no paired decisions" → nothing paired (fail-closed);
  check the drops, do not force it.

## Keep these artifacts

`queue_pending.json`, the filled worksheet CSV, all API responses (Step 2
batch + Step 3 κ row + Step 4 checks), and your run notes (which path, the
0.3 preflight row, any refusals). They are the human half of the calibration
record and belong next to `evidence/g4-agent-calibration-2026-09-22/` in the
syllabai repo (commit them or hand them back — either preserves the chain).

## Reference documents

- Runbook (rebuilt): `G4_KAPPA_CALIBRATION_RUNBOOK.md` + its ADDENDUM (the
  convention pin) in this directory.
- Agent round + audit: `syllabai` repo `evidence/g4-agent-calibration-2026-09-22/`
  (README, round_record, frozen decisions, smart_results, κ both conventions,
  `CORRECTIONS_2026-09-22.md`, `UNPARSEABLE_OUTPUT_INVESTIGATION.md`).
- Convention regression pin (code side): syllabai-core `e7a55fe`
  (`TeacherMarkingServiceTest` — partial credit pairs as 1; wrong-convention
  reading pairs as honest disagreement).
