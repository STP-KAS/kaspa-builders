# Covenant-id tooling: kascov, CAIP namespace

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-09-29 (the latest dated read in the moved text).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** IzioDev's RPC statement, rusty-kaspa #991/#969, the kips.dev/kccs.dev mirrors and elldeeone's `rk-with-tcp` rusty-kaspa fork branch (row "Covenant-id lookup"), with a one-line pointer here. The tictactoe row keeps its kaspanet/vprogs pins.

## What

Third-party covenant-id tooling while the rusty-kaspa RPC endpoint does not exist: Knitser's off-chain kascov decoder (`kascov-decode`), its outage report, free public API claim and tictactoe settlement counts; ChainAgnostic/namespaces#193 (Kaspa CAIP-2/CAIP-10 profiles). Author claims; the desk did not verify the reorg or the counts. Not L1 consensus. elldeeone's `rk-with-tcp` rusty-kaspa fork branch stays in the master.

## Moved text (verbatim)

### README Now row "Covenant-id lookup" (moved part)

**27 Sep:** [Knitser/kascov](https://github.com/Knitser/kascov) published `kascov-decode` ([`ad251ddf`](https://github.com/Knitser/kascov/commit/ad251ddfb002c80e8e152c001b8777ebeb7e9bc8) 24 Sep; CLI+WASM [`1805a780`](https://github.com/Knitser/kascov/commit/1805a780b47a32a85340e149e3b1ee584c926eb8) 25 Sep): off-chain decoder that checks a revealed covenant program against the L1 commitment and names known SilverScript/Argent builds. Local check; not L1 consensus. Catalog via [KaspaScopio](https://x.com/KaspaScopio/status/2104124941775823222). The [kascov README](https://github.com/Knitser/kascov/blob/ab306fce78/README.md) says the rest of the codebase went private for a rebuild; explorer, indexer and API are to return, and a trading terminal stays private. Author's words.

### README Now row "Covenant-id lookup" (moved part)

**Kascov outage (author's report):** [0xKnitser 2103505094532866269](https://x.com/0xKnitser/status/2103505094532866269) (25 Sep 15:21Z): a 907-block TN10 reorg on 17 Sep took kascov down, and its watchdog restarted a 19-minute rollback 44 times; "fixed now". Kascov follows KCC-1 as SilverScript 1.0 emits it and will re-pin once kccs #27/#30/#31 land (#30 merged 27 Sep, #27 merged 28 Sep; #31 still open). The condition is not met while #31 is open. There has been no public kascov commit since [`ab306fce`](https://github.com/Knitser/kascov/commit/ab306fce) (25 Sep), so no re-pin can be seen. The desk has not checked the 17 Sep reorg itself: kascov's [reorgs.json](https://kascov.io/data/testnet-10/reorgs.json) only covers the last ~2 h (largest rollback on 28 Sep: 7 blocks).

### README Now row "Covenant-id lookup" (moved part)

[ChainAgnostic/namespaces#193](https://github.com/ChainAgnostic/namespaces/pull/193) still open.

### master.json now row "Covenant-id lookup and tooling" (moved part)

ChainAgnostic/namespaces#193 https://github.com/ChainAgnostic/namespaces/pull/193 (Kaspa CAIP-2 and CAIP-10 profiles) is open (https://x.com/elldeeone/status/2099316438704312512, 14 Sep). 27 Sep: Knitser/kascov kascov-decode open-sourced (ad251ddf 24 Sep; CLI+WASM 1805a780 25 Sep). Off-chain: verifies revealed covenant program against L1 commitment and names known SilverScript/Argent builds. Not consensus. https://github.com/Knitser/kascov · https://x.com/KaspaScopio/status/2104124941775823222 kascov README (ab306fce78): the rest of the codebase went private for a rebuild; explorer, indexer and API to return; trading terminal stays private. Author's words. https://github.com/Knitser/kascov 25 Sep 15:21Z author's report https://x.com/0xKnitser/status/2103505094532866269: a 907-block TN10 reorg on 17 Sep took kascov down; watchdog restarted a 19-minute rollback 44 times; fixed now. Kascov follows KCC-1 as SilverScript 1.0 emits it; re-pin once kccs #27/#30/#31 land (#30 merged 27 Sep, #27 merged 28 Sep; #31 open). Desk did not verify the 17 Sep reorg; https://kascov.io/data/testnet-10/reorgs.json covers only ~2 h (max rollback 7 on 28 Sep). 29 Sep: #27 merged 28 Sep, #31 still open, so kascov's re-pin condition is not met. No public kascov commit since ab306fce (25 Sep) https://github.com/Knitser/kascov/commits/main

### README Now row "Kas-Smiths" (moved: KasCov API claim on topic 142)

On [#142](https://kas-smiths.org/t/wallet-utxo-covenant-id-lookup/142) (covenant-id lookup), post [391](https://kas-smiths.org/t/wallet-utxo-covenant-id-lookup/142/7) (25 Sep): 0xKnitser says the KasCov free public API he runs answers it. Catalog.

### master.json now row "Kas-Smiths archive" (moved: KasCov API claim)

Post 391 (25 Sep 13:19Z): 0xKnitser says the KasCov free public API answers both topic 142 lookups on mainnet and testnet-10. He runs it.

### README Now row "tictactoe" (moved: kascov count of the tictactoe covenant)

**Kascov count (third party, not a pin):** [kascovio 2103528866312802567](https://x.com/kascovio/status/2103528866312802567) (25 Sep 16:55Z) counted 264 proven transitions on TN10, each checked by OpZkPrecompile, and asked Max whether the layout is stable enough to pin. No answer from Max found. Covenant [`85165a6f…`](https://kascov.io/#/testnet-10/c/85165a6f453dbbd1e968c238966e297046b8f1d22c00fee1bc208de00c3fb097): on 28 Sep ~10:02Z the [kascov API](https://kascov.io/data/testnet-10/c/85165a6f453dbbd1e968c238966e297046b8f1d22c00fee1bc208de00c3fb097.json) showed 603 settlements and 0 recheck failures.

### master.json now row "vprog-tictactoe tip" (moved: kascov count)

Third-party count, not a pin: kascovio https://x.com/kascovio/status/2103528866312802567 (25 Sep 16:55Z) 264 proven transitions on TN10, each checked by OpZkPrecompile; asked Max if the layout is stable to pin; no answer found. Covenant 85165a6f453dbbd1e968c238966e297046b8f1d22c00fee1bc208de00c3fb097: kascov API 28 Sep ~10:02Z 603 settlements, 0 recheck failures. https://kascov.io/data/testnet-10/c/85165a6f453dbbd1e968c238966e297046b8f1d22c00fee1bc208de00c3fb097.json

## Sources (every link in the moved text)

- https://github.com/Knitser/kascov
- https://github.com/Knitser/kascov/commit/ad251ddfb002c80e8e152c001b8777ebeb7e9bc8
- https://github.com/Knitser/kascov/commit/1805a780b47a32a85340e149e3b1ee584c926eb8
- https://x.com/KaspaScopio/status/2104124941775823222
- https://github.com/Knitser/kascov/blob/ab306fce78/README.md
- https://x.com/0xKnitser/status/2103505094532866269
- https://github.com/Knitser/kascov/commit/ab306fce
- https://kascov.io/data/testnet-10/reorgs.json
- https://github.com/ChainAgnostic/namespaces/pull/193
- https://x.com/elldeeone/status/2099316438704312512
- https://github.com/Knitser/kascov/commits/main
- https://kas-smiths.org/t/wallet-utxo-covenant-id-lookup/142
- https://kas-smiths.org/t/wallet-utxo-covenant-id-lookup/142/7
- https://x.com/kascovio/status/2103528866312802567
- https://kascov.io/#/testnet-10/c/85165a6f453dbbd1e968c238966e297046b8f1d22c00fee1bc208de00c3fb097
- https://kascov.io/data/testnet-10/c/85165a6f453dbbd1e968c238966e297046b8f1d22c00fee1bc208de00c3fb097.json
