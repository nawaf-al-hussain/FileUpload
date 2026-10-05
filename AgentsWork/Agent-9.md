Drain cycle received. **Sync first** — main moved 8 merges, so nothing I remember is current. Pulling ground truth: main tip, worklog tail, my T-MIG-031 yaml, PR #43 state, and the open-PR board.
Board reality differs from the operator snapshot: **6 open PRs** — mine (#43 tranche-1) plus #37/#38/#40/#41/#42/#44. Every queue item (W2-F1, W2-F3, T-MIG-002-R, and W2-F2 via T-MIG-023) already has a claim — so no new claims for me. My duty: **drive PR #43 to merge**, then review another lane's PR. Reading the worklog tail first per the directive.
Sync complete. R0's sweep-4 already ran; main = `0cd360b`. **PR #43 is mergeable=dirty** → intake required. Queue items all claimed (W2-F1→#42+r3c, W2-F3→R0's T-MIG-036, T-MIG-002-R→#44, W2-F2→T-MIG-023 lanes) — so no new claim for me. Executing: intake → re-gate → push → review request → then one independent review of another lane's PR.
PR #43 is mergeable=True (CI unstable = still running) and the intake comment is posted. Now **step 5: one independent review**. Pick: **PR #42 (W2-F1, r3c)** — the instant-rendering fix that directly unblocks the Wave-2 exit gate. Fetching and auditing it.
Clean fence (r3c's own content lane). Reading the fix sketch (receipts/T-MIG-022) and the port itself against Java's `Instant.toString()` law.
Implementation verified against the ISO_INSTANT law (0/3/6/9 fraction rule, exact whole-second UTC math, offset normalization, fail-fast on Date leakage, ORDER BY parity preserved). Now the gold-standard check: local test-merge onto current main + full gates.
Gates green on the test-merge (410/0/13skip, typecheck ×4, selftest OK — worklog conflict is the standard append-tail class their lane will intake). Cleaning up the throwaway and posting the verdict.
Review posted. Final step: the one-line status receipt, then stop.
PR #43 is now **mergeable=clean** — CI finished green on the new head. Appending the local worklog note and stopping.
**Drain cycle complete — all 7 steps executed, stopping as directed.**

- **Synced** at `0cd360b` (board reality: 6 open PRs, not zero).
- **Held claim driven to merge-ready**: PR #43 was dirty → intake from current main (zero code conflicts, worklog append-union), gates re-stamped (**421/0/13skip**, selftest OK), pushed → now **mergeable=clean**, independent review requested. Awaiting R0 merge-intake.
- **No new claim**: all four queue items already held by other lanes (W2-F1→#42, W2-F3→R0's T-MIG-036, T-MIG-002-R→#44, W2-F2→T-MIG-023) — zero-collision scan says hands off.
- **One review delivered**: independent **APPROVE on PR #42** (W2-F1 instant-rendering) — law verified against the ISO_INSTANT contract first-hand, test-merge gates green (410/0/13skip).
- Status receipt appended to the worklog; boundaries held throughout (read-only Neon/core, gates green before every push).

**One suggestion logged for you**: PR #40 (T-MIG-032 marking ports) could use a reviewer now so the Wave-3 train doesn't queue behind the W2 exit fixes — and there's still the T-MIG-023 dual-claim (#38 vs #41) needing R0 arbitration.
