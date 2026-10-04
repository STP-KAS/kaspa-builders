# stroemnet, stroemwallet (saefstroem side projects)

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-09-22 (the latest dated read in the moved text).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** saefstroem's KIP-16, rusty-kaspa #775/#953/#861, KCC-0 and kccs drafts (row "saefstroem"; x handle @asaefstroem stays), plus one reasoning line there on the hand-built kaspa_txscript HTLC.

## What

saefstroem's unaudited, testnet-only HTLC swap channels across Kaspa TN10, Ethereum Sepolia and Igra Galleon (stroemnet `e60dc3e`), the stroemwallet kasware fork, and mcp-http. Not mainnet, not KCC-20, not SilverScript. His KIP-16, rusty-kaspa and KCC work stays in the master.

## Moved text (verbatim)

### master.json x row "@asaefstroem" (moved part; handle stays in x)

stroemnet tip e60dc3e (17 Jul 2026) is his unaudited TN10/Sepolia/Igra swap, not a product. stroemwallet is a kasware-wallet/extension fork. mcp-http is not Kaspa.

### README Now row "saefstroem" (moved part; KIP-16, rusty-kaspa and KCC lines stay)

[stroemnet](https://github.com/saefstroem/stroemnet) tip [`e60dc3e`](https://github.com/saefstroem/stroemnet/commit/e60dc3e815c6) (17 Jul 2026), MIT: unaudited, testnet-only HTLC swap channels across Kaspa TN10, Ethereum Sepolia, and Igra Galleon. Not mainnet. Not KCC-20. Not a `.sil` file. [stroemwallet](https://github.com/saefstroem/stroemwallet) is a fork of `kasware-wallet/extension`. Channel and script detail: [SNAPSHOT-HISTORY.md](https://github.com/STP-KAS/kaspa-master-file/blob/cf10a0f53dc98279f12cd523be008879efff00fd/SNAPSHOT-HISTORY.md#moved-from-readme-on-26-sep-2026).

### master.json now row "saefstroem / stroemnet" (full original note; url https://github.com/saefstroem/stroemnet; chip experiment)

Catalog, not a pin. saefstroem authored KIP-16 (Active). stroemnet tip e60dc3e (17 Jul 2026), MIT, README unaudited and testnet only. ChannelId: Kaspa TN10 byte 0, hand-built HTLC in kaspa_txscript, SHA256, exactly 2 inputs and 2 outputs, CLTV, output 0 must be at least the spent input minus 10000000 sompi (SOLVER_REWARD) on both paths. The script does not name a solver output. Channel default lock 180s; the script timelock is an argument. Ethereum Sepolia byte 1, StroemHTLCV1.sol. Igra Galleon byte 2, iKAS, 18 decimals, synthetic clock, lock 3600s. Swap id and destination sit in an OpFalse/OpIf branch. Not mainnet. Not KCC-20. Not SilverScript. stroemwallet forks kasware-wallet/extension (last push 8 Mar 2026). mcp-http pushed 22 Sep is an HTTP MCP server, not a Kaspa object. Of his nine follows, the Kaspa-relevant accounts are aspect, biryukovmaxim, and 1bananagirl.

## Sources (every link in the moved text)

- https://github.com/saefstroem/stroemnet
- https://github.com/saefstroem/stroemnet/commit/e60dc3e815c6
- https://github.com/saefstroem/stroemwallet
- https://github.com/STP-KAS/kaspa-master-file/blob/cf10a0f53dc98279f12cd523be008879efff00fd/SNAPSHOT-HISTORY.md#moved-from-readme-on-26-sep-2026
