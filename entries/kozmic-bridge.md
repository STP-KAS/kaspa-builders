# Kozmic (kasperolabs/kozmic-bridge)

**Chip:** `catalog`. Third-party. **Not desk-tested. Not Kaspa core. Not a KIP.**
**Last checked:** 2026-10-14 (tip `1f18c7eb`; no node, no Etherscan, no compile).

## What the author publishes

[kasperolabs/kozmic-bridge](https://github.com/kasperolabs/kozmic-bridge) default branch `main`, created 2026-10-13T01:27:47Z. Tip [`1f18c7eb`](https://github.com/kasperolabs/kozmic-bridge/commit/1f18c7eb832f7e754f4a37ea9780ffe42ae666c5) (2026-10-13T23:56:26Z, "README: drop internal notes"). GitHub `pushed_at` is 2026-10-13T23:56:28Z. No issues. No pull requests. `LICENSE` is MIT and names "Oz Steinemtz, Kaspero Labs". This is not [kasperolabs/silverscript-studio](https://github.com/kasperolabs/silverscript-studio) (`e27a7c4e`).

The README says the bridge is "Live on mainnet since 2026-10-12." It also says Kaspa reads Ethereum and Ethereum cannot read Kaspa yet. KBT is a self-minted test ERC-20 with no value. The Ethereum vault has no withdraw function. Those sentences are the author's.

Twelve commits, all on 13 Oct, oldest [`fefbec24`](https://github.com/kasperolabs/kozmic-bridge/commit/fefbec24b3d4e6a30e677f07dbda89d8d756d6b0) (01:29:17Z, "Kaspa L1 ZK bridge from Ethereum: v1 code and mainnet evidence"). Later subjects include the prover GPU mode, a docs pass, an npm test fix, a reproducible image-id note, and two "README: drop internal notes" commits. This pass did not rebuild any of them.

## Deposit #3, as the README records it

The README table for 2026-10-13 names deposit #3: 0.5 KBT at 00:35:23 UTC, Ethereum tx [`0x29e6f6a874164b38c556abd32dbcfb3adc262e06238b46bfb8f3ce4107a419b0`](https://etherscan.io/tx/0x29e6f6a874164b38c556abd32dbcfb3adc262e06238b46bfb8f3ce4107a419b0), block 26,180,018. It names the Kaspa mint at 00:53:52 UTC, tx [`568bedc542e6ed51ce6ecbbef0968a730d43b049f95150d37960ca7a86f44aaf`](https://explorer.kaspa.org/txs/568bedc542e6ed51ce6ecbbef0968a730d43b049f95150d37960ca7a86f44aaf). The clock difference is 18 minutes 29 seconds. The prose says "Eighteen and a half minutes." The measurements table says "18.5 min measured (13.8 min Ethereum finality, 4.5 min proving and submitting)." 18:29 is 18.48 minutes. This pass did not open Etherscan or a Kaspa node.

The README's reproduce comment quotes image id `4756d736d00cc0e5b813fd9bbb8fe586dbfe9cee524e61e79335cc2585413a50` from a command `cat IMAGE_IDS.txt`. That file is not at the repo root (`GET` 404) and a code search did not find it. The proof bundle path in the table is `eth-prover/out-deposit-3/`. The README says the journal is 230 bytes plus 49 per deposit and the Groth16 proof is 128 bytes. It says tooling is rusty-kaspa 2.1.0. That pin is not rusty-kaspa #1074.

## What this pass read in the tree

- [`vault/src/Vault.sol`](https://github.com/kasperolabs/kozmic-bridge/blob/1f18c7eb832f7e754f4a37ea9780ffe42ae666c5/vault/src/Vault.sol) L10: "One-way. Tokens sent here stay here. There is no owner, no withdraw". The contract's only public transition besides the constructor is `deposit(uint64 amount, bytes calldata kaspaSpk)` at L58. L6 `transferFrom` is the `IERC20` interface, not a vault withdraw. Not compiled. Not deployed by this desk.
- [`bridge/bridge.sil`](https://github.com/kasperolabs/kozmic-bridge/blob/1f18c7eb832f7e754f4a37ea9780ffe42ae666c5/bridge/bridge.sil) L128 is `function advance`. L135 is `r0.g16.verify(sha256(journal), proof, image_id)`. L68–L70 set `MAX_DEPOSITS = 4`, `JOURNAL_FIXED_LEN = 230`, `DEPOSIT_LEN = 49`. `image_id` is a covenant field (L40), not a hex constant in this file. The comment at L132 names the compiler helper `append_r0_groth16_verifier_dynamic_image_id` and "SDK 2.1.0". Not compiled.

The README says `eth-prover/` derives from RISC Zero's [r0vm-helios](https://github.com/risc0/r0vm-helios) and that RISC Zero and r0vm-helios were audited by zkSecurity. That sentence is about those projects. It is not an audit of this repository.

KCC-20 on kaspanet/kccs `3fbec524` is Last Call, not Final. The README calling the Kaspa token KCC-20 does not move that status.

## Relay

KaspaScopio [2110320538308555017](https://x.com/KaspaScopio/status/2110320538308555017) (14 Oct 10:43:18Z) points at this repo. The post says 0.5 KBT on 13 Oct, 18 minutes 29 seconds, a Kaspa covenant verifying a zero-knowledge proof of Ethereum finality, a test token, one-way, no vault withdraw, not independently audited, and that the poster did not independently verify the Kaspa-side execution. The 18:29 figure matches the README clock times. The post's audit sentence is the poster's. This catalog did not commission or read an audit of Kozmic.

The 12 Oct claim [2109766022790066442](https://x.com/KasperoLabs/status/2109766022790066442) is on the [Studio page](entries/kasperolabs-silverscript-studio.md). That post had no txid and no repo. This page is the later repo.

## Do not weld

KBT into KCC-20 Final. This one-way vault into a two-way bridge. The RISC Zero / r0vm-helios zkSecurity audit into an audit of Kozmic. The author's mainnet tx ids into a desk node check. rusty-kaspa #1074 into this bridge. silverscript-studio `e27a7c4e` into this repository.
