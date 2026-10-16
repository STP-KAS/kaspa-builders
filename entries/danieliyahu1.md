# danieliyahu1: kas-odds, onlykas

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-12 (kaskama, formerly onlykas: rename, commits and issues since 11 Oct only; 8 Oct: onlykas commits since 6 Oct; the rest is the latest dated read in the moved text, 23 Sep).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** His kccs#35 draft in the "KCC still open" row.

## What

danieliyahu1's apps: kas-odds (SilverScript two-player game, testnet-10 default, a mainnet profile in network.js) and onlykas (image `8720f12` config says mainnet; names Kasware). His kccs#35 draft stays in the master's KCC row.

## Moved text (verbatim)

### README Now row "danieliyahu1" (whole row)

[kas-odds](https://github.com/danieliyahu1/kas-odds) tip [`876f064`](https://github.com/danieliyahu1/kas-odds/commit/876f06491a0f) (23 Sep). SilverScript `covenant/kasodds.sil`. [pins.json](https://github.com/danieliyahu1/kas-odds/blob/main/covenant/pins.json) binds compiler `3ed9733` (the v1.0.0 tag), template hash `ade3453c61ac5858b344b22ccf373e7e44ab18c14506f49b69e29f763057e27a`, and rusty-kaspa sourceCommit `a41a333`. A two-player game: each player locks at least 1 KAS, and two committed bits decide the winner. Default profile is testnet-10 (the covenant calls it a testnet-10 MVP); `network.js` also has a mainnet profile. [onlykas](https://github.com/danieliyahu1/onlykas) tip [`7cd476dd`](https://github.com/danieliyahu1/onlykas/commit/7cd476dd6) (23 Sep) pins image [`8720f12`](https://github.com/danieliyahu1/onlykas/commit/8720f12e4d3c), whose configmap sets `https://onlykas.app` and `KASPA_NETWORK: mainnet`. The app still names Kasware. This desk does not use Kasware. Payouts, fees, and commit detail: [SNAPSHOT-HISTORY.md](https://github.com/STP-KAS/kaspa-master-file/blob/cf10a0f53dc98279f12cd523be008879efff00fd/SNAPSHOT-HISTORY.md#moved-from-readme-on-26-sep-2026).

### master.json now row "danieliyahu1" (whole row; url https://github.com/danieliyahu1/kas-odds; chip experiment)

kas-odds tip 876f064 (23 Sep 08:01Z). Commits since 851e114 count a homepage visit when the app loads, via POST /api/visit, not when a client fetches /. The covenant file is not in those commits. kasodds.sil pragma ^0.1.0. pins.json binds SilverScript source 3ed9733 and template ade3453c61ac5858b344b22ccf373e7e44ab18c14506f49b69e29f763057e27a. It labels rusty-kaspa v2.0.1 while sourceCommit a41a333 is #1067, 8 commits ahead of tag cfafeb4c. The wasm URL is the v2.0.1 zip. Stake minimum 100000000 sompi. Creator wins when (creator_choice + joiner_choice) % 2 differs from creator_even. Fee is gross_pot / 100 only when gross_pot >= 10000000000 sompi. Default profile testnet-10. network.js also lists mainnet. onlykas tip 7cd476dd (23 Sep 21:28Z) pins image 8720f12. That image includes the four commits after 7e4e239: challenge logs store a prefix and a length bucket, the client redacts address keys, authenticate switches network and then calls getAccounts, and a post creator link drops its underline. deploy/configmap.yaml in that image sets PUBLIC_ORIGIN to https://onlykas.app, replacing https://onlykas.danieliyahu.com, and KASPA_NETWORK to mainnet. A dismissed, timed-out, or wrong switch ends quietly. The background listener still warns on an independent change. One toast slot. membership.sil is not in these commits. Fee (price + 50) / 100, zero under 1 KAS, and lifetime 25920000 DAA scores stay as read on 22 Sep. The app still names Kasware. The 22 Sep read said testnet-10. This production configmap says mainnet. kaspa-simple-mcp is a read-only api.kaspa.org wrapper, mainnet by default. He follows ezratameno. Those public repos are not Kaspa. kccs#24 notes stay on the KCC row.

## 8 Oct 2026 sweep (GitHub reads 8 Oct ~17:50 to 18:15 CEST; not desk-checked unless stated)

- [onlykas](https://github.com/danieliyahu1/onlykas) tip [`b8f28657`](https://github.com/danieliyahu1/onlykas/commit/b8f28657) (7 Oct 22:35Z) pins image `f15ab87a`. New in the 6 to 7 Oct commits: [`8080e5aa`](https://github.com/danieliyahu1/onlykas/commit/8080e5aa) "pay a referrer a share of the platform fee", [`7c00c3fd`](https://github.com/danieliyahu1/onlykas/commit/7c00c3fd) "credit a referral through a shared link", a creator directory rebuilt around creator profiles, and a Get KAS link when a payment lacks funds. Commit messages only; the fee split and network were not re-read.

## 12 Oct 2026 sweep (GitHub reads 12 Oct ~07:47 CEST; commit messages and issue titles only, not desk-checked)

- **Renamed:** `danieliyahu1/onlykas` is now [`danieliyahu1/kaskama`](https://github.com/danieliyahu1/kaskama) (the API for the old name returns `full_name` `danieliyahu1/kaskama`; default branch `master`). Older onlykas links above use the old name.
- Tip [`dce58809`](https://github.com/danieliyahu1/kaskama/commit/dce588091e75e6be6eca88c8c119b17d0e278f5a) (11 Oct 23:49:59Z, github-actions: "chore: pin image to 3e285447860755538131c6545003b9bd45738789"). Before it: [`833cb340`](https://github.com/danieliyahu1/kaskama/commit/833cb340) (23:45:52Z) "fix: settle attempts atomically so a failed effect stays retryable" and [`3e285447`](https://github.com/danieliyahu1/kaskama/commit/3e285447) (23:45:55Z) "refactor: drop the dead attempt terminal state".
- Issues [#5](https://github.com/danieliyahu1/kaskama/issues/5), [#6](https://github.com/danieliyahu1/kaskama/issues/6) (both opened by noralane) and [#7](https://github.com/danieliyahu1/kaskama/issues/7) (danieliyahu1) closed 11 Oct 23:47Z. noralane opened six more on 12 Oct 00:59–01:00Z, all open with no comments at this read: [#8](https://github.com/danieliyahu1/kaskama/issues/8) "Pending post payments allow a second signed payment for the same buyer/post"; [#9](https://github.com/danieliyahu1/kaskama/issues/9) "Broadcast tracking fix remains incomplete at the gateway evidence-write boundary"; [#10](https://github.com/danieliyahu1/kaskama/issues/10) "WRPC disconnect failure masks a successful broadcast and loses its transaction ID"; [#11](https://github.com/danieliyahu1/kaskama/issues/11) "Offer/update/cancel finalize retry can delete an already-submitted transaction"; [#12](https://github.com/danieliyahu1/kaskama/issues/12) "Concurrent finalize rejection can erase the winning payment submission"; [#13](https://github.com/danieliyahu1/kaskama/issues/13) "Pending payment UI loses the intent and never refreshes access after reconciliation". Reports, not desk-checked.

## Sources (every link in the moved text)

- https://github.com/danieliyahu1/kas-odds
- https://github.com/danieliyahu1/kas-odds/commit/876f06491a0f
- https://github.com/danieliyahu1/kas-odds/blob/main/covenant/pins.json
- https://github.com/danieliyahu1/onlykas
- https://github.com/danieliyahu1/onlykas/commit/7cd476dd6
- https://github.com/danieliyahu1/onlykas/commit/8720f12e4d3c
- https://onlykas.app
- https://github.com/STP-KAS/kaspa-master-file/blob/cf10a0f53dc98279f12cd523be008879efff00fd/SNAPSHOT-HISTORY.md#moved-from-readme-on-26-sep-2026
- https://onlykas.danieliyahu.com


## 16 Oct 2026 sweep

- onlykas/kaskama master tip [`781a550f`](https://github.com/danieliyahu1/onlykas/commit/781a550f) (15 Oct 19:55:55Z, chore image pin).
