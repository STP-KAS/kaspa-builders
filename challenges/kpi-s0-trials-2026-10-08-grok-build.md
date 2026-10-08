# Challenge: build/kpi-s0-trials-2026-10-08

- **Reviewed commit:** `84c3d78b5930beab44bf3006a5a49043a3bb923b`.
- **Base:** main `5487e1f7bea8bec35917ed3ba41ce022f8290e55`. It is the parent.
- **Totals:** 12 HELD · 0 FAILED · 0 UNVERIFIABLE.
- **Verdict:** no open FAILED item. Under AGENTS.md this branch is not blocked.
- **Reviewer:** Grok Build, 8 Oct 2026, about 23:15 CEST. This note is not the kaspa master challenge bot.

**How this pass checked:**

- GitHub REST for the S0 file blob at `e4a10390` and at main `ccbdfbc7`, for commit `e4a10390`, for commit `c541dd51`, for pull #22, and for the compare `c541dd51...e4a10390`.
- The S0 report, the evidence README, the public-record JSON, and the trial-runner design file, all at `e4a10390`. No node read. No submit.

**Key:** E = `entries/olafweller-kpi.md` at `84c3d78`.

## Branch shape

- **S1 HELD.** One content commit, `84c3d78`, author `STP-KAS <227352643+STP-KAS@users.noreply.github.com>`. Parent is main `5487e1f`.
- **S2 HELD.** The diff is five files: `README.md`, `SNAPSHOT-HISTORY.md`, `builders.json`, `do-not-weld.md`, and E. 29 insertions, 6 deletions.

## Page

- **S3 HELD.** E L90. Blob `9f2453c1748405ef8adc074e0a1961a4c0c2748e` at both `e4a10390` and `ccbdfbc7`. Merge `e4a10390` is 2026-10-08T18:22:45Z. Pull #22 state is MERGED, merge commit that oid, mergedAt that time. Main tip at the read was `ccbdfbc7` at 2026-10-08T19:52:31Z.
- **S4 HELD.** E L90. The S1 file at `e4a10390` still contains the sentence "PR #22 remains draft."
- **S5 HELD.** E L91 through L96. The report's PASS line, the three scoped cases, the 1.4 second wording, the sompi amounts, the four payout txids, the rejected candidate `804f7d16…f78a`, the three failure causes, and the accounting identity are in the report. The public record stores the same txids, `allowOrphan=false`, exit codes 0, intent gap `1.425701759`, and the sompi totals 22470000000, 8840000000, 4000000000, 9630000000 and 5044700. The observed-second floats on E L93 and E L94 match that JSON.
- **S6 HELD.** E L97. Commit `c541dd51` exists, message "a1: retain mature selected-chain prefixes and exact reorg evidence", committer date 2026-10-08T15:38:40Z. Compare to `e4a10390` is `diverged`, ahead 3, behind 27.
- **S7 HELD.** E L98 and E L99. The report's exclusion list includes the full G5/G6 set, independence from C, trust-free setup, anonymity, and fixed-fee exit liveness. The evidence directory at that commit is `README.md`, `SHA256SUMS`, and `public-record.json`. The runner design file's opening says the phase B results were awaiting publication.
- **S8 HELD.** E L57. The old "G6 has not run" sentence is no longer the current-limits line. The 4 Oct and earlier 8 Oct sections are still in the file as dated reads.

## Index

- **S9 HELD.** The README KPI row names blob `9f2453c1`, merge `e4a10390`, main `ccbdfbc7`, and the S1 pin `fb8a5017`. Its checked date is `2026-10-08`. It says the txids are not desk-checked and that G5/G6 stays open.
- **S10 HELD.** `builders.json` KPI `checked` is `2026-10-08`. The note names the same payout and rejected txids, the intent gap, the accounting, and the diverged runner pin. Sources include `e4a10390`, the S0 report, the public record, `c541dd51`, and `ccbdfbc7`.
- **S11 HELD.** `do-not-weld.md` section "Added 8 Oct 2026 (KPI S0 trials)" matches S5 through S7. The older sentence that refuses welding the repo into a KIP or Core product is still in the verbatim paragraph.

## Decision

- **S12 HELD.** No new STP-KAS repository. No star, fork, issue, comment or pull on olafweller/kaspa-privacy-initiative. Main of kaspa-builders was not moved. The 8 Oct txids were not read on a node.
