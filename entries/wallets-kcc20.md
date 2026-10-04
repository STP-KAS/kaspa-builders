# Wallets and KCC-20 (Kastle, Kaspire)

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-04 (the latest dated read in the moved text).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** nothing; the whole row moved.

## What

Third-party wallet work on KCC-20: forbole/kastle KCC-20 UI merged into a feature branch, #372 into main still open (head `ddfaf373`); Kaspire KCC-20 swaps on TN10 Android and release v0.11.46 (extension 0.5.5). Not verified: swaps in the extension. No mainnet KCC-20 swap claimed.

## Moved text (verbatim)

### README Now row "Wallets and KCC-20" (whole row)

[forbole/kastle](https://github.com/forbole/kastle): [#369](https://github.com/forbole/kastle/pull/369) (KCC-20 UI surface) merged 1 Oct 13:48Z into the feature branch `feat/kron-token-ui`, **not main**. [#372](https://github.com/forbole/kastle/pull/372) KCC20-Integration into main is open, head [`ddfaf373`](https://github.com/forbole/kastle/commit/ddfaf373) (3 Oct 15:02Z, merge of main into the PR after UAT fix pulls #373–#375 and fee-model test pull #377, all merged 2 Oct). Only bot comments and reviews (CodeRabbit, Copilot); GitHub says `blocked`. [#357](https://github.com/forbole/kastle/pull/357) Stage 0 token display closed unmerged (1 Oct 13:44Z). On main, [#356](https://github.com/forbole/kastle/pull/356) KCC-12 provider prep landed as [`909bdf8c`](https://github.com/forbole/kastle/commit/909bdf8c02) (13:32Z) and was reverted by [`4bb38e01`](https://github.com/forbole/kastle/commit/4bb38e0184) (13:34Z). Per kaspirewallet post [2104215772717281321](https://x.com/kaspirewallet/status/2104215772717281321) (27 Sep; X not re-read on 2 Oct), KaspaRocket KCC-20 swaps are in the Kaspire Android app on TN10 only, with a testnet-only PSKT profile, and the Chrome extension update would follow "within the next days". Since then, Kaspire's GitHub [README L47](https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/blob/505d70611fc6cbd264d5d1dc299988de928941ad/README.md#L47) lists TN10 among the extension networks (it already did at [`77d906f2`](https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/blob/77d906f20932da096406bac5928905f330af5335/README.md#L47), 28 Sep 13:57Z). Release [v0.11.46](https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/releases/tag/v0.11.46) (1 Oct 12:50Z) is "Kaspire Android 0.11.46 and Extension 0.5.5", with strict typed validation for known KCC20, KRON and Kaspire covenant flows. Not verified: whether KaspaRocket swaps run in the extension, and whether the Chrome Web Store serves 0.5.5. No KCC-20 swap is claimed on mainnet. Catalog.

### master.json now row "Wallets and KCC-20" (whole row; url https://github.com/forbole/kastle/pull/372; chip catalog)

forbole/kastle #369 KCC-20 UI surface merged 2026-10-01T13:48:30Z into feature branch feat/kron-token-ui, not main. #372 KCC20-Integration into main is open, head ddfaf373 (3 Oct 15:02Z, merge of main into the PR after UAT fix pulls #373-#375 and fee-model test pull #377, all merged 2 Oct). Only bot comments and reviews (CodeRabbit, Copilot); GitHub says blocked. #357 Stage 0 closed unmerged 1 Oct 13:44Z. On main #356 KCC-12 provider prep 909bdf8c (13:32Z) was reverted by 4bb38e01 (13:34Z). Per kaspirewallet post https://x.com/kaspirewallet/status/2104215772717281321 (27 Sep; X not re-read 2 Oct): KaspaRocket KCC-20 swaps in the Kaspire Android app on TN10 only, testnet-only PSKT profile; the Chrome extension update would follow within the next days. Since then the Kaspire GitHub README L47 lists TN10 among the extension networks (https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/blob/505d70611fc6cbd264d5d1dc299988de928941ad/README.md#L47; already at 77d906f2, 28 Sep 13:57Z), and release v0.11.46 (1 Oct 12:50Z, Kaspire Android 0.11.46 and Extension 0.5.5) keeps strict typed validation for known KCC20, KRON and Kaspire covenant flows (https://github.com/KaspaHUB21/Kaspire-Kaspa-Wallet/releases/tag/v0.11.46). Not verified: KaspaRocket swaps in the extension, and whether the Chrome Web Store serves 0.5.5. No KCC-20 swap claimed on mainnet.

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
