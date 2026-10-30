# KaspaKii: Impulse (delivery versus payment)

**Chip:** `catalog`. Third-party builder. **Not desk-tested, not built here. The author's README says it holds value on a public chain; use small values only.**
**Last checked:** 30 Oct 2026 ~08:15 CET (GitHub repo, tag and README; one X relay).

## Who

- GitHub [KaspaKii/impulse](https://github.com/KaspaKii/impulse). Its README: "Impulse by WarpCore." and "Impulse is a KiiLabs product." Apache-2.0, created 18 Oct 2026 08:54:14Z, last push 21 Oct 07:42:18Z. The same GitHub account holds [KaspaKii/Portrait](https://github.com/KaspaKii/Portrait) (named in the master's intel pack).

## What the README says (read 30 Oct)

- "Impulse is a standalone, open-source delivery-versus-payment (DvP) primitive for Kaspa mainnet." Two parties agree terms, derive the escrow addresses from them, fund their own legs by plain transfer, "and the trade settles in one transaction".
- "There is one contract template (`ImpulseVault`), a Rust core, a command line, a TypeScript/WASM SDK and a reference watcher."
- "A per-trade value cap applies (10 KAS by default)." The quickstart is "testnet, offline", and "Mainnet is used only when you pass `--network mainnet`." The TN10 walkthrough is in its `docs/USER-GUIDE.md`.
- Release table: v0.1 (settle and refund, four settlement modes, KAS or KCC-20 legs), v0.2 (basket, partial and cross-chain hashlock settlement), v0.3 (proof-carrying settlement) and v0.4: "v0.4.0 supersedes v0.3.0 (whose templates carry L20; do not fund them)."
- Tag [`v0.4.0`](https://github.com/KaspaKii/impulse/commit/cbbd51b4d59e7daed04c4b01cc12291699b94eea) (annotated, points to `cbbd51b4`, commit "Impulse v0.4.0", 21 Oct 07:02:32Z). 0 GitHub releases.

## Relay

- [@KASPAglobal 2115733621050876059](https://x.com/KASPAglobal/status/2115733621050876059) (29 Oct 09:12:58Z): "@KaspaKii open-sourced Impulse, delivery versus payment on kaspa L1. the deal terms hash into the escrow address, so no deployed program or upgrade key to trust. v0.4.0 is on main." A relay, not the author.
