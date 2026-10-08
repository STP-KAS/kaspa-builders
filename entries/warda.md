# ArtyKOMarkets/warda

**Chip:** `catalog`. Third-party grant protocol. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-08. The covenant source was not compiled. The transaction ids in DEPLOYED.md were not read as included transactions.

**The master keeps:** nothing from this repository. The mass and fee sentences in DEPLOYED.md stay the author's claims.

## What

[ArtyKOMarkets/warda](https://github.com/ArtyKOMarkets/warda) is the one public repository of GitHub user ArtyKOMarkets (account created 2026-06-01T10:05:44Z, no profile name). Tip [`7beecde96d34`](https://github.com/ArtyKOMarkets/warda/commit/7beecde96d349c282c9822cadb3def2d584f2473), committed 2026-09-26T14:35:12Z by mystic108. The mystic108 profile name field is Artautas. License MIT. Homepage `https://wardamcp.vercel.app`.

`package.json` at that tip names `@warda_protocol/core` version `0.3.2` and calls it a reference implementation of an agent-grant protocol whose rules a Toccata covenant must enforce. That sentence is the package's own description.

[DagitUser69/warda](https://github.com/DagitUser69/warda) compares identical to this tip, ahead 0. That fork is not authorship. The account page is on kaspa-builders branch `build/dagituser69-2026-10-08`, not on this repo's main.

## Source at the tip

[`covenant/warda_grant.sil`](https://github.com/ArtyKOMarkets/warda/blob/7beecde96d349c282c9822cadb3def2d584f2473/covenant/warda_grant.sil) is 30,361 bytes. It opens with `pragma silverscript ^0.1.0`, the words "v0.1 DRAFT", and "NOT YET COMPILE-VERIFIED."

[`covenant/warda_grant_v5.sil`](https://github.com/ArtyKOMarkets/warda/blob/7beecde96d349c282c9822cadb3def2d584f2473/covenant/warda_grant_v5.sil) is 40,151 bytes. It opens with the same pragma and the words "v5 WORKING DRAFT". Its header calls `covenant/warda_grant.sil` v4 and names fingerprint `b3e5eeefacf2021f`. That fingerprint string is not in `warda_grant.sil`.

[`covenant/deploy/Cargo.toml`](https://github.com/ArtyKOMarkets/warda/blob/7beecde96d349c282c9822cadb3def2d584f2473/covenant/deploy/Cargo.toml) pins silverscript `84eb797abdae4a67a46bcd1e7b97e4393e07e3b6` (2026-08-24T07:39:44Z). Comparing that commit to the v1.0.0 tag `3ed9733` gives ahead 14, behind 0, so the pin is 14 commits behind the tag. The same file pins rusty-kaspa `a41a333b08848f41bf737b72592e463a6011b8ac` (2026-08-02T10:25:50Z). This pass did not check whether that rev is the v2.0.1 tag.

## What DEPLOYED.md says

[DEPLOYED.md](https://github.com/ArtyKOMarkets/warda/blob/7beecde96d349c282c9822cadb3def2d584f2473/DEPLOYED.md) says a grant is on testnet-10, the node was rusty-kaspa v2.0.1, and the covenant is 3,036 bytes. It names grant address `kaspatest:prm79fmfrrw80r5mrf5a0ltzsnskxutu77996xh0zajhygusylpkzhemc2zpl`, covenant id `f7947f65000b60e59819b02b93b5fd1761772f4edcf07010268ab7eefad375f8`, genesis `626736a3a202e838e4d0adca095c8660cb46638da3910bf89f589deb571343d4`, accepted spend `36f3dff2e5218651d80e62f1c7e620313a58fbc6ecd18a81d68050a33544fb55`, refused injection `e251a20effea166c90f9cf4f19e28073856e57b3dc9ef0209269347e7a1396f1`, and a JavaScript spend `7dbc957fbf87ca26bc9b83ec81849f4f713c255fa6d39f44a53301813ceb86ba`. It says the refused transaction failed signature-script verification, that a local `TxScriptEngine` predicted both results, and that the project is still testnet-only, unaudited, and Silverscript pre-v1. Those are the file's claims.

The 3,036-byte figure is not the source file. The source file is 30,361 bytes. This pass did not measure a compiled script.

## Desk read

8 Oct 2026, desk Testnet-10 node, server version 2.1.0, synced, virtual DAA score 591380221. Read with the wasm RPC client on local Borsh port 17210. No transaction was submitted.

The grant address balance was 0 sompi and `getUtxosByAddresses` returned 0 entries. `getMempoolEntry` for the genesis id and the three spend ids returned "Transaction … not found". This client has no accepted-transaction lookup. A mempool miss does not show whether a past transaction was included, and an empty address does not show whether the spends in DEPLOYED.md happened. DEPLOYED.md itself says a successful spend moves the grant to a new address.

## Sources

- https://github.com/ArtyKOMarkets/warda/commit/7beecde96d349c282c9822cadb3def2d584f2473
- https://github.com/ArtyKOMarkets/warda/blob/7beecde96d349c282c9822cadb3def2d584f2473/README.md
- https://github.com/ArtyKOMarkets/warda/blob/7beecde96d349c282c9822cadb3def2d584f2473/DEPLOYED.md
- https://github.com/ArtyKOMarkets/warda/blob/7beecde96d349c282c9822cadb3def2d584f2473/covenant/warda_grant.sil
- https://github.com/ArtyKOMarkets/warda/blob/7beecde96d349c282c9822cadb3def2d584f2473/covenant/warda_grant_v5.sil
- https://github.com/ArtyKOMarkets/warda/blob/7beecde96d349c282c9822cadb3def2d584f2473/covenant/deploy/Cargo.toml
- https://github.com/kaspanet/silverscript/commit/84eb797abdae4a67a46bcd1e7b97e4393e07e3b6
- https://github.com/kaspanet/silverscript/commit/3ed973335b59269293564805cc2c58a14595ec03
- https://github.com/kaspanet/rusty-kaspa/commit/a41a333b08848f41bf737b72592e463a6011b8ac
- https://github.com/DagitUser69/warda
