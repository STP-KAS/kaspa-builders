# KRC-20 mechanics, next to KCC-20 (11 Oct)

**Chip:** `catalog`. Third-party protocol and wallet docs, plus stp's own KNS desk runs on Testnet 10. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-11 (all sources below read that day, 17:10-17:20Z).

Added on 11 Oct 2026, branch `master/builders-update-2026-10-11-krc20`, on stp's request via TN10 ops. The comparison page that asked for it, [STP-KAS/tn10-storm-plan-mint-rush `docs/KCC20-VS-KRC20.md`](https://github.com/STP-KAS/tn10-storm-plan-mint-rush/blob/262d1bccd57aa739342fa04272a2570900e96bab/docs/KCC20-VS-KRC20.md) at `262d1bcc` (public), was checked item by item against the sources below; only what those sources say is kept.

**The master keeps:** the KCC-20 side (the `public_mint.ag` rules at `c8a08711`, the split-tree arithmetic, stp's 11 Oct TN10 mint masses and fees, the single 7 Oct rejected-mint case) in its "KCC20 reference" row, and a one-line pointer here from "KCC20 reference" and "KRC-20 to KCC". Sutton's 20 Sep line that KRC-20 is off-chain interpretation stays in the master's "KCC-20 wording" row.

## Where the rules live

- A KRC-20 mint is JSON (`p`, `op`, `tick`) placed inside a script, in the form `<public_key> OP_CHECKSIG OP_FALSE OP_IF <protocol_id> <0> <data> OP_ENDIF`, with `kasplex` as the KRC20 protocol identifier, paid to a P2SH address ([KasWare KRC20 API docs](https://docs.kasware.xyz/wallet/developer-documentation/kaspa/kaspa-krc20), `buildScript`; third-party wallet docs, read 11 Oct).
- Desk reading of the script form above (not stated by either source): the JSON sits in an `OP_FALSE OP_IF … OP_ENDIF` branch that never executes, so consensus treats these as ordinary script-hash spends, and whether a mint counts is decided by the KRC-20 indexer. A status check reads the indexer's operation endpoint for the reveal id and looks for `"opAccept": "1"` ([codecustard/kaspa `examples/krc20_example/README.md` at `272e8ebf`](https://github.com/codecustard/kaspa/blob/272e8ebfb8b89c803d3d790eb664b082748668be/examples/krc20_example/README.md), third-party TN10 example).
- The Kasplex KRC-20 mint docs (`docs-kasplex.gitbook.io/krc20/technical-overview/krc-20-ops/mint`) were **not readable** on 11 Oct (GitBook returned a redirect and sign-in page, not the docs). The cap behaviour the comparison page cites from them (a mint past the cap gets the remainder) is therefore **not verified** here.

## Shape: two transactions

- "Every KRC20 operation requires **two transactions**": a commit to a P2SH output, then a reveal that spends it (codecustard README, L73 at `272e8ebf`).
- KasWare describes the same two phases: the commit sends funds to the P2SH address; once it is confirmed, the reveal spends from it and shows the inscription data. The reveal id is the primary id for the KRC20 operation (KasWare docs, `submitCommitReveal` and `signKRC20Transaction`).

## 2024 KRC-20 beta (third-party account, mainnet)

From [kaspa-ng/kaspa-ecosystem-updates README, "KRC20 Beta in the past"](https://github.com/kaspa-ng/kaspa-ecosystem-updates/blob/f23dc374088c85ac15a9b65837e6c645e83d42c3/README.md#krc20-beta-in-the-past) at `f23dc374` (17 Nov 2024): Kasware sent 0.2 KAS per deploy or mint; under KIP-9 "a typical transaction mass was approximately 25,000 grams", "no more than about 20 similar transactions could fit in each Kaspa block" (500,000-gram limit); the mempool backlog peaked "around 37,000 transactions"; "the mining fee is set at 1 KAS in accordance with KRC-20 rules", about "4000 sompi/gram, whereas typical values range from 1 to 4 sompi/gram", so ordinary low-fee transactions had almost no chance of inclusion. Third-party numbers, not desk-measured; 2024 conditions, not current mainnet.

## KNS on Testnet 10 (same commit/reveal pattern; stp's desk)

From stp's public repo [STP-KAS/kns-tn10-testing](https://github.com/STP-KAS/kns-tn10-testing/tree/327350442fbef38fcf554c61b8eaa37df1494d29) at `32735044`:

- "Uniqueness is the KNS indexer, first valid reveal wins. A losing reveal still pays." ([README.md L21](https://github.com/STP-KAS/kns-tn10-testing/blob/327350442fbef38fcf554c61b8eaa37df1494d29/README.md#L21))
- Network fees per create (commit + reveal) were about 0.035 tKAS per name; "The commit locks 1 TKAS in the P2SH, and the reveal returns it." ([docs/runs/R1.md L23](https://github.com/STP-KAS/kns-tn10-testing/blob/327350442fbef38fcf554c61b8eaa37df1494d29/docs/runs/R1.md#L23)); the KNS protocol fee is on top ([README.md L98](https://github.com/STP-KAS/kns-tn10-testing/blob/327350442fbef38fcf554c61b8eaa37df1494d29/README.md#L98)).

KNS is not KRC-20; it only shares the inscription pattern.

## Not tested

- The desk has **not minted KRC-20** itself. What a KRC-20 mint past the cap costs the minter is **untested**.
- No KRC-20 or KCC-20 numbers here come from a storm or from mainnet.

## 23 to 24 Oct 2026: KRC-20 archive cutoff (kasplex/go-krc20d#1) (GitHub read 24 Oct ~07:45 CEST)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- [kasplex/go-krc20d#1](https://github.com/kasplex/go-krc20d/issues/1) (Silentpartnercoding, opened 23 Oct 13:40:01Z, open): NACHO mint `80d736ba…4795` (DAA 90,114,862) is "L1-accepted and rules-valid but not indexed (\"op not found\")"; the author's replay says "Every one of the 10,385,075 Kasplex-accepted NACHO ops matches L1".
- 5bb55b ([15:11:32Z](https://github.com/kasplex/go-krc20d/issues/1#issuecomment-6368112677)): "the L1 archive db used by KRC-20 does not contain the full dataset; it begins at daa-score 83,403,399", so a fee cannot be computed when an input UTXO is older. [15:41:19Z](https://github.com/kasplex/go-krc20d/issues/1#issuecomment-6368712733): "This was a deliberate design choice in the initial protocol ... please do not \"fix\" it; it is already part of the KRC-20 consensus." [24 Oct 03:57:01Z](https://github.com/kasplex/go-krc20d/issues/1#issuecomment-6379564532): "the op is ignored (rather than failing)"; it "can only happen with op that require additional transaction fees"; "An op will be ignored if any of its inputs have a `daa-score` < `83,403,399`"; from DAA 408,300,500 (`HfDaaScore2026Q1`) "the rpc-vspc2 api is applied, ensuring that transaction fees are always calculated correctly."
- Silentpartnercoding ([18:38:58Z](https://github.com/kasplex/go-krc20d/issues/1#issuecomment-6372142886)): he found no written version of the 83,403,399 rule in the KRC-20 docs or go-krc20d history and asks for it in the spec. In his [15:24:37Z](https://github.com/kasplex/go-krc20d/issues/1#issuecomment-6368378865) comment his replay "finds 317 operation-status differences and 144 affected addresses at the October 20 checkpoint" (his own numbers, "not been independently confirmed by Kasplex"). argonmining ([18:51:17Z](https://github.com/kasplex/go-krc20d/issues/1#issuecomment-6372365137)): "NACHO won't migrate to KCC20 as a snapshot but rather a 'turnstile'".

## 24 to 25 Oct 2026: go-krc20d#1 follow-up (GitHub read 25 Oct ~07:50 CET)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Silentpartnercoding ([24 Oct 19:20:30Z](https://github.com/kasplex/go-krc20d/issues/1#issuecomment-6388471139)): "an op that needs an additional fee is ignored (not failed) if any of its inputs has a DAA score below 83,403,399, and from DAA 408,300,500 (HfDaaScore2026Q1) fees come from rpc-vspc2, so it can't recur. I've added that rule to krc20-verifier with boundary tests."
- 5bb55b ([25 Oct 02:26:13Z](https://github.com/kasplex/go-krc20d/issues/1#issuecomment-6392440403)), pointing to [`sequencer/archive.go#L354`](https://github.com/kasplex/go-krc20d/blob/main/sequencer/archive.go#L354): "This is an adjustment for KIP-15: when the `daa-score` < `110,165,000`, transactions are sorted by their transaction ID; otherwise, the original VSPC ordering is used." Issue still open.

## 25 Oct 2026: go-krc20d#1, transaction order (GitHub read 26 Oct ~07:45 CET)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Silentpartnercoding ([25 Oct 09:21:10Z](https://github.com/kasplex/go-krc20d/issues/1#issuecomment-6395881149)): "The L354 rule only applies below DAA 110,165,000, and all 74 blocks are above it (256,890,845 to 569,981,356), so they use the VSPC order." Checking `acceptedIdMerkleRoot` in block headers (KIP-15): "That's 11 of 11 checkable blocks matching Kasplex and none matching mine. The cause is on my side: the public REST API's `/virtual-chain` lists txids in ascending order (73 of the 74 blocks), not in acceptance order." He asks Kasplex to confirm the canonical order for DAA ≥ 110,165,000 in the KRC-20 spec, and says `/v1/archive/vspc/:daascore` on api.kasplex.org returns "api disabled". Issue still open, no reply at this read.
