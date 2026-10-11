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
