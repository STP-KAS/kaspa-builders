# kaspa-core (Flux)

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-09-27 (the latest dated read in the moved text).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** nothing; the whole row moved.

## What

RunOnFlux/kaspa-core: a pure-TypeScript Kaspa transaction library for Flux's SSP and ZelCore wallets, v1.0.0 (npm `@runonflux/kaspa-core`). Not a rusty-kaspa fork and not a node. Mainnet-proof claims are the author's. Not desk-tested.

## Moved text (verbatim)

### README Now row "kaspa-core (Flux)" (whole row)

[RunOnFlux/kaspa-core](https://github.com/RunOnFlux/kaspa-core) (Flux, author TheTrunk). A pure-TypeScript Kaspa transaction library for Flux's SSP and ZelCore wallets: addresses, M-of-N P2SH multisig, sighash, BIP340 signing, KIP-9 mass and fees, input selection, KRC-20 and Igra entry builders, REST and JSON-wRPC clients. No WASM. MIT. **Not a rusty-kaspa fork and not a node**: GitHub `fork: false`, one commit [`4cf8f35b`](https://github.com/RunOnFlux/kaspa-core/commit/4cf8f35be6e3bec696e784f4b3656d9feaa15bf6) (25 Sep 13:58Z), tag and release [v1.0.0](https://github.com/RunOnFlux/kaspa-core/releases/tag/v1.0.0) (14:10Z), npm `@runonflux/kaspa-core` 1.0.0. A dev-only [oracle](https://github.com/RunOnFlux/kaspa-core/blob/main/oracle/Cargo.toml) links rusty-kaspa crates at `01b532e8` (v2.1.0) to check it byte for byte. No open issues or pulls on 27 Sep. No Dockerfile. The wRPC client takes `networkId: 'testnet-10'` (`kaspatest:`) and fixed URLs, so it can point at a TN10 kaspad started with `--utxoindex --rpclisten-json` (testnet JSON port 18210); its live tests are mainnet only. Mainnet-proof claims are the author's ([AUDIT.md](https://github.com/RunOnFlux/kaspa-core/blob/main/AUDIT.md)). Not desk-tested. Catalog.

### master.json now row "kaspa-core (Flux)" (whole row; url https://github.com/RunOnFlux/kaspa-core; chip catalog)

RunOnFlux/kaspa-core (Flux, author TheTrunk). Pure-TypeScript Kaspa transaction library for Flux's SSP and ZelCore wallets: addresses, M-of-N P2SH multisig, sighash, BIP340 signing, KIP-9 mass and fees, input selection, KRC-20 and Igra entry builders, REST and JSON-wRPC clients. No WASM. MIT. Not a rusty-kaspa fork and not a node: GitHub fork false, one commit 4cf8f35b (25 Sep 13:58Z), tag and release v1.0.0 (14:10Z) https://github.com/RunOnFlux/kaspa-core/releases/tag/v1.0.0 , npm @runonflux/kaspa-core 1.0.0. Dev-only oracle links rusty-kaspa crates at 01b532e8 (v2.1.0). No open issues or pulls on 27 Sep. No Dockerfile. wRPC client takes networkId testnet-10 (kaspatest:) and fixed URLs, so it can point at a TN10 kaspad with --utxoindex --rpclisten-json (testnet JSON port 18210); live tests are mainnet only. Mainnet-proof claims are the author's (AUDIT.md). Not desk-tested. Catalog.

## Sources (every link in the moved text)

- https://github.com/RunOnFlux/kaspa-core
- https://github.com/RunOnFlux/kaspa-core/commit/4cf8f35be6e3bec696e784f4b3656d9feaa15bf6
- https://github.com/RunOnFlux/kaspa-core/releases/tag/v1.0.0
- https://github.com/RunOnFlux/kaspa-core/blob/main/oracle/Cargo.toml
- https://github.com/RunOnFlux/kaspa-core/blob/main/AUDIT.md
