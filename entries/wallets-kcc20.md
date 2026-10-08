# Wallets and KCC-20 (Kastle, Kaspire)

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-08 (kastle #372, #387, #388, #389 and releases only; the rest is the latest dated read in the moved text, 4 Oct).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** nothing; the whole row moved.

## What

Third-party wallet work on KCC-20: forbole/kastle KCC-20 UI merged into a feature branch, #372 into main still open (head `ddfaf373`); Kaspire KCC-20 swaps on TN10 Android and release v0.11.46 (extension 0.5.5). Not verified: swaps in the extension. No mainnet KCC-20 swap claimed.

## Moved text (verbatim)

### README Now row "Wallets and KCC-20" (whole row)

[forbole/kastle](https://github.com/forbole/kastle): [#369](https://github.com/forbole/kastle/pull/369) (KCC-20 UI surface) merged 1 Oct 13:48Z into the feature branch `feat/kron-token-ui`, **not main**. [#372](https://github.com/forbole/kastle/pull/372) KCC20-Integration into main is open, head [`ddfaf373`](https://github.com/forbole/kastle/commit/ddfaf373) (3 Oct 15:02Z, merge of main into the PR after UAT fix pulls #373–#375 and fee-model test pull #377, all merged 2 Oct). Only bot comments and reviews (CodeRabbit, Copilot); GitHub says `blocked`. [#357](https://github.com/forbole/kastle/pull/357) Stage 0 token display closed unmerged (1 Oct 13:44Z). On main, [#356](https://github.com/forbole/kastle/pull/356) KCC-12 provider prep landed as [`909bdf8c`](https://github.com/forbole/kastle/commit/909bdf8c02) (13:32Z) and was reverted by [`4bb38e01`](https://github.com/forbole/kastle/commit/4bb38e0184) (13:34Z). Per kaspirewallet post [2104215772717281321](https://x.com/kaspirewallet/status/2104215772717281321) (27 Sep; X not re-read on 2 Oct), KaspaRocket KCC-20 swaps are in the Kaspire Android app on TN10 only, with a testnet-only PSKT profile, and the Chrome extension update would follow "within the next days". Since then, Kaspire's GitHub [README L47](https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/blob/505d70611fc6cbd264d5d1dc299988de928941ad/README.md#L47) lists TN10 among the extension networks (it already did at [`77d906f2`](https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/blob/77d906f20932da096406bac5928905f330af5335/README.md#L47), 28 Sep 13:57Z). Release [v0.11.46](https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/releases/tag/v0.11.46) (1 Oct 12:50Z) is "Kaspire Android 0.11.46 and Extension 0.5.5", with strict typed validation for known KCC20, KRON and Kaspire covenant flows. Not verified: whether KaspaRocket swaps run in the extension, and whether the Chrome Web Store serves 0.5.5. No KCC-20 swap is claimed on mainnet. Catalog.

### master.json now row "Wallets and KCC-20" (whole row; url https://github.com/forbole/kastle/pull/372; chip catalog)

forbole/kastle #369 KCC-20 UI surface merged 2026-10-01T13:48:30Z into feature branch feat/kron-token-ui, not main. #372 KCC20-Integration into main is open, head ddfaf373 (3 Oct 15:02Z, merge of main into the PR after UAT fix pulls #373-#375 and fee-model test pull #377, all merged 2 Oct). Only bot comments and reviews (CodeRabbit, Copilot); GitHub says blocked. #357 Stage 0 closed unmerged 1 Oct 13:44Z. On main #356 KCC-12 provider prep 909bdf8c (13:32Z) was reverted by 4bb38e01 (13:34Z). Per kaspirewallet post https://x.com/kaspirewallet/status/2104215772717281321 (27 Sep; X not re-read 2 Oct): KaspaRocket KCC-20 swaps in the Kaspire Android app on TN10 only, testnet-only PSKT profile; the Chrome extension update would follow within the next days. Since then the Kaspire GitHub README L47 lists TN10 among the extension networks (https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/blob/505d70611fc6cbd264d5d1dc299988de928941ad/README.md#L47; already at 77d906f2, 28 Sep 13:57Z), and release v0.11.46 (1 Oct 12:50Z, Kaspire Android 0.11.46 and Extension 0.5.5) keeps strict typed validation for known KCC20, KRON and Kaspire covenant flows (https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/releases/tag/v0.11.46). Not verified: KaspaRocket swaps in the extension, and whether the Chrome Web Store serves 0.5.5. No KCC-20 swap claimed on mainnet.

## 5 Oct 2026 sweep

- kastle [#372](https://github.com/forbole/kastle/pull/372) still open at head `ddfaf373` (`blocked`, GET ~07:45 CEST). Kastle's new DOTK pulls #378/#379 (4 Oct) are on the [name-services](name-services.md) entry.

## 6 Oct 2026 sweep (GitHub reads ~07:45 CEST; not desk-checked)

- kastle [#372](https://github.com/forbole/kastle/pull/372) (KCC20-Integration, Stage 0) still open, head now `84ebe285` (5 Oct 16:27Z), `blocked`.
- [#387](https://github.com/forbole/kastle/pull/387) (open, head `3f5ab29b`, PR opened 5 Oct 19:49Z, base `KCC20-Integration`): KCC-20 transfers (Stage 1) through `@kronsdk/kron-sdk` 0.18.2; ADDRESS-owned pieces only, 3 token inputs per send, Ledger gated. The PR says a live mainnet transfer is still owed before merge.
- [#388](https://github.com/forbole/kastle/pull/388) (open, head `3a51a07b`, PR opened 5 Oct 22:05Z, stacked on #387): KCC-20 swaps (Stage 2) through the KRON bonding curve as a third swap provider, with a 0.75% Kastle fee (`KASTLE_SWAP_FEE_BPS`).
- Release [v2.61.0](https://github.com/forbole/kastle/releases/tag/v2.61.0) (5 Oct 16:22Z) ships swap + bridge (mobile parity) and gates Swap and Bridge for Ledger accounts; no KCC-20 code (#372, #387 and #388 are all unmerged).

## 8 Oct 2026 sweep (GitHub reads 8 Oct ~17:50 to 18:15 CEST; not desk-checked unless stated)

- **Correction to the 6 Oct notes:** the 19:49Z and 22:05Z times next to #387 and #388 are the PR open times, not head-commit times (now labelled so).
- [#372](https://github.com/forbole/kastle/pull/372), [#387](https://github.com/forbole/kastle/pull/387) and [#388](https://github.com/forbole/kastle/pull/388) were **closed unmerged** on 6 Oct at 07:21:22Z, 07:21:25Z and 07:21:29Z (heads `84ebe285`, `3f5ab29b`, `3a51a07b`). The 6 Oct reads (~05:45Z) were before that.
- They are replaced by [#389](https://github.com/forbole/kastle/pull/389) (opened 6 Oct 07:21:11Z, base `main`, open, head `fc7b6497`, 4 commits, 35 files): the whole KCC-20 feature in one PR, Stage 0 display, Stage 1 transfers through `@kronsdk/kron-sdk` (signs only the wallet's funding inputs) and Stage 2 KRON bonding-curve swaps with the 0.75% fee. The PR says Stage 1 and 2 passed review by "Fable" after fix rounds. Not merged; not in a release.
- Latest release still [v2.61.0](https://github.com/forbole/kastle/releases/tag/v2.61.0) (5 Oct). Kastle's dotK integration #381 merged on 7 Oct; see [name-services](name-services.md).

## Sources (every link in the moved text)

- https://github.com/forbole/kastle
- https://github.com/forbole/kastle/pull/369
- https://github.com/forbole/kastle/pull/372
- https://github.com/forbole/kastle/commit/ddfaf373
- https://github.com/forbole/kastle/pull/357
- https://github.com/forbole/kastle/pull/356
- https://github.com/forbole/kastle/commit/909bdf8c02
- https://github.com/forbole/kastle/commit/4bb38e0184
- https://x.com/kaspirewallet/status/2104215772717281321
- https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/blob/505d70611fc6cbd264d5d1dc299988de928941ad/README.md#L47
- https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/blob/77d906f20932da096406bac5928905f330af5335/README.md#L47
- https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/releases/tag/v0.11.46
