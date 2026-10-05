# Privacy initiative (KPI): olafweller/kaspa-privacy-initiative

**Chip:** `experiment`. Third-party community research. **Not Kaspa core, not a KIP, not a privacy pool.**
**Last checked:** 5 Oct 2026 (GitHub GETs ~07:45 CEST; the chain facts below are still the 4 Oct 18:01 and 18:18 CEST reads on the desk's own synced Testnet-10 node).

## Who

- X [@WellerOlaf](https://x.com/WellerOlaf), id `1370264912992346114`; GitHub user `olafweller`. His launch and update posts link the repo ([2106031612945199511](https://x.com/WellerOlaf/status/2106031612945199511), [2106458391107236016](https://x.com/WellerOlaf/status/2106458391107236016), [2106773440338247750](https://x.com/WellerOlaf/status/2106773440338247750)), and the repo README names him initiator and steward.
- He says he is not a developer by background, not a cryptographer and not a Kaspa core dev, and that he builds with ChatGPT and Codex agents ([2106523383844229492](https://x.com/WellerOlaf/status/2106523383844229492), 3 Oct 23:14:46Z).
- Opened on Kas-Smiths [topic 156](https://kas-smiths.org/t/kaspa-privacy-initiative-exploring-optional-privacy-for-native-kas/156).

## Pin

- Repo [olafweller/kaspa-privacy-initiative](https://github.com/olafweller/kaspa-privacy-initiative), main [`98aa99fa8230f5eb490e0af4e3da0291260581d6`](https://github.com/olafweller/kaspa-privacy-initiative/commit/98aa99fa8230f5eb490e0af4e3da0291260581d6) (4 Oct 11:24:38Z). Still the main tip at the 4 Oct ~19:05 CEST GET.
- Apache-2.0, created 2 Oct 13:55:36Z, not a fork, 11 commits, one contributor (`olafweller`, GitHub contributors API).
- At [`dc2f176d`](https://github.com/olafweller/kaspa-privacy-initiative/commit/dc2f176d440d1f96fb464c7e92219d3e1964d12e) (2 Oct) the repo was research only (Markdown, templates, one docs-check script). PoC code arrived in [`3a1efa8`](https://github.com/olafweller/kaspa-privacy-initiative/commit/3a1efa8db9672025f5282970703cb7256428c1be) (3 Oct 19:12Z, "PoC A0/A0.5: live TN10 proof-gated reserve release").
- Draft [PR #22](https://github.com/olafweller/kaspa-privacy-initiative/pull/22) (A1), head `2590e392ef97af6ea81aa8fc177a3996a7fa93a7`, open and draft at the 4 Oct ~19:05 CEST GET.

## What the code does (A0 / A0.5 at `98aa99fa`)

One proof-gated terminal payout from a native test-KAS reserve. **No privacy.**

- **Reserve:** a plain **P2SH** redeem script (576 bytes). It is linear (no `OpIf`), so there is no other spend path. It requires: input count 1, output count 1, input 0 amount 1,020,000,000 sompi, output 0 amount 1,000,000,000 sompi, output 0 script = a fixed recipient, and `OpOutputAuthorizingInput` on output 0 = −1 (the payout carries no covenant binding). It then rebuilds the spent outpoint's txid limbs and index and calls `OpZkPrecompile` with an embedded 424-byte verifying key. The spender supplies two 32-byte tag limbs and a 128-byte proof, so the proof is bound to the exact outpoint and the script to the exact payout.
- **Circuit:** Groth16 on BN254 (arkworks 0.6). The private witness is a 32-byte secret; it proves `SHA256(secret) == claim` and `tag == SHA256(prefix ‖ secret ‖ outpoint_txid ‖ outpoint_index)`. The prefix fixes TN10 genesis, a state id, the amounts, the recipient script and a terminal marker, so **every claim needs its own trusted setup**.
- **Opcodes and KIPs** (challenger wording, checked against kaspanet/kips `e4ae2332` and rusty-kaspa `01b532e8` = v2.1.0):
  - `OpZkPrecompile` (0xa6, Groth16 tag 0x20; KIP-16). kip-0016.md L35, L91–L93; rusty-kaspa `crypto/txscript/src/opcodes/mod.rs` L759, `crypto/txscript/src/zk_precompiles/tags.rs` L9.
  - Introspection from **KIP-10**: input/output count (0xb3, 0xb4), amounts (0xbe, 0xc2), output script (0xc3). kip-0017.md L45–L55 lists these as KIP-10 opcodes already active before Toccata.
  - From **KIP-17**: outpoint txid/index (0xba, 0xbb) and `OpCat`/`OpSubstr`/`OpNum2Bin` (0x7e, 0x7f, 0xcd). kip-0017.md L32–L33, L78, L79, L91.
  - From **KIP-20**: `OpOutputAuthorizingInput` (0xd6), used only to require −1, i.e. an unbound payout. kip-0020.md L250.
  - **No KIP-20 covenant id:** every output is `covenant=None`. Not used: KIP-21 lanes, vProgs, SilverScript.

## On-chain check (Testnet 10)

Desk node: kaspad 2.1.0, `isSynced: true`, read-only JSON wRPC, 4 Oct ~18:01 CEST (maker) and 18:18 CEST (challenger recheck, [note `43a3c64`](https://github.com/STP-KAS/kaspa-master-file/blob/43a3c64f5a72580cf54ab552699245b7a1481076/challenges/wellerolaf-2026-10-04-challenge.md) items C1–C8).

- Release tx `29d875bbdf31cb14205b6f429d63c475b9ad85e558e932b1c70ff1dbc0e2b554` is in chain block `c38a5439db59c5768e62a37d162f19cd04c4802a8a2e33a35a80050fa3c76210` (3 Oct 17:56:48Z) and is accepted by chain block `c8dc02dd15e6451ff328eb3708d00a1b638bd004e5ad98a2405a76a2de431a6f`.
- It is a v1 tx with one input `67aab5bfb85e9fb1fb6eaa08c6216ca44ed98c823d4d1141361ac75be0db004f:0` (compute budget 1700) and one output of 1,000,000,000 sompi (10 tKAS) to `kaspatest:qr33u5pn…s38lsrz4`, `covenant: null`. Compute mass 171,335, storage mass 20.
- Funding tx `67aab5bf…` is in block `8ec273b7be634625efe42c020d9e12895ae073084b5aed69ba1e7bc0a7dbcdf2`, accepted by chain block `bacfa5f142345086ad4568709810e2351088070bde654eb03b38c3d1b290334e`. Output 0 is 1,020,000,000 sompi (10.2 tKAS) to the P2SH `kaspatest:pqc9cdt4u94f4yf4lxxawr9mz6ypc53rypc72mm2phtulartxmvhw2lxjzegy`, `covenant: null`. Fee: exactly 0.2 tKAS.
- BLAKE2b-256 of the 576-byte redeem push is `305c3575e16a9a9135f98dd70cbb16881c52232071e56f6a0dd7cff46b36d977`, which is the funding script's hash (`0000 aa20 <hash> 87`).
- What this proves: a Groth16 proof verified inside consensus script validation released native test KAS from a script-locked reserve, with exact amounts. It proves nothing about privacy, multiple users or the trusted setup. The distinct-ID replay rejection is recorded only by the repo; not re-tested here.

## Desk build (log-based, 4 Oct)

Rust 1.91.0, rusty-kaspa at `01b532e8` (v2.1.0). From the desk's own run logs; the challenger read the logs but did not rerun them.

- A0 at `98aa99fa`: 7/7 Rust tests. Harness: 30 cases as documented: `valid_terminal_release` accepted, `exact_replay_stateless_boundary` accepted (stateless, as the repo documents), 28 invalid variants rejected.
- 13/13 Node tests on Node 22. On Node 20 the SDK test file fails to load; the repo and its CI pin Node 22.
- A1 (PR #22 head [`2590e392`](https://github.com/olafweller/kaspa-privacy-initiative/tree/2590e392ef97af6ea81aa8fc177a3996a7fa93a7)): 20/20 Rust tests passed in the desk's run (log `19 passed` + `1 passed`, [challenge note `43a3c64`](https://github.com/STP-KAS/kaspa-master-file/blob/43a3c64f5a72580cf54ab552699245b7a1481076/challenges/wellerolaf-2026-10-04-challenge.md) G4; build targets since deleted). At that head the crate has 19 `#[test]` functions in its library modules and 1 in `src/main.rs` (`mod transport_tests`), and `scripts/test_a1_*.py` holds 46 Python test functions (counted from the public source). By the desk's own run note, the Python tests and the G2–G5 evidence generators were not run; that is not independently verifiable.

## Limits (read these first)

- **Not a privacy pool.** No notes, nullifiers, commitment tree, private transfers or anonymity exist in code. Amounts, recipient, outpoints and timing are public. One terminal claim per setup.
- **P2SH reserve, no covenant id.** The repo's "covenant" wording means a P2SH script with introspection limits.
- **Single-party trusted setup** per claim (repo README L203 at `98aa99fa`: "Single-party setup provenance remains a trust assumption").
- BN254 Groth16 is not post-quantum (repo issue #19).
- **AI-written and unaudited.** The README says "AI-assisted adversarial review has occurred. It is not independent human security review." Its status line says "Do not use experimental code with real funds."
- A1 is a draft, unfunded and file-only: G5 (independent-machine recovery) is open, G6 (live TN10 run) has not run.

## X (6 Sep to 4 Oct 2026 backfill)

Read 4 Oct ~17:58–18:05 CEST, read-only: 63 of his posts, 19 kept (code, technical reasoning, Kaspa insight; no price talk). **Coverage caveat:** 6 Sep to 30 Sep 18:10 CEST was searched by Kaspa keyword only, not the full timeline. Times below are CEST.

- **A0.5 live result** ([2106458391107236016](https://x.com/WellerOlaf/status/2106458391107236016), 3 Oct 20:56): test KAS released only after a real ZK proof verified; "no privacy protocol yet, no notes/nullifiers". Checked on chain above.
- **A1 progress** ([2106519428741341529](https://x.com/WellerOlaf/status/2106519428741341529), [2106532082352873797](https://x.com/WellerOlaf/status/2106532082352873797), [2106700072159256895](https://x.com/WellerOlaf/status/2106700072159256895), 4 Oct 00:59–12:56): partial release with the remainder in a successor reserve, tested locally. Next: independent-machine recovery, then a live A1 run. Source is draft PR #22.
- **Architecture sketch** ([2106773440338247750](https://x.com/WellerOlaf/status/2106773440338247750), [2106770656452829663](https://x.com/WellerOlaf/status/2106770656452829663), [2106774728690065588](https://x.com/WellerOlaf/status/2106774728690065588), 4 Oct 17:37–17:53): notes, nullifier root, commitment root, relayer, batcher, untrusted indexer. He says "This is not a final design". **Design only;** none of it is in the code.
- **Post-quantum criterion** ([2106346055864352923](https://x.com/WellerOlaf/status/2106346055864352923), 3 Oct 13:30, reply to @aglovale0x [2106177235208020281](https://x.com/aglovale0x/status/2106177235208020281), who wrote that a Groth16 wrap trades future quantum resistance for proof/verifier costs): quantum resistance should be an explicit criterion when comparing proof systems, and he would not trade it away for efficiency without saying so. The repo tracks this as issue #19; A0/A1 use BN254 Groth16, which is not post-quantum.
- **Scope** ([2106341386127638831](https://x.com/WellerOlaf/status/2106341386127638831), [2106339130007285802](https://x.com/WellerOlaf/status/2106339130007285802), 3 Oct 13:02–13:11): native KAS first without blocking KCC-20 later; proving cost via a per-operation fee or a prover market (research option).
- **Launch** ([2106031612945199511](https://x.com/WellerOlaf/status/2106031612945199511), 2 Oct 16:40): community-led, no new token, no custodian, no fixed architecture. He folded three directions from core dev @Max143672 ([2105992874458235122](https://x.com/Max143672/status/2105992874458235122), 2 Oct 14:06) into the repo as candidates: Groth16 or RISC Zero user proofs, native UTXO scripts (shared-UTXO contention), or the vProgs route.
- The STP-KAS daily X sweep reads his original posts only (`-is:reply`), so it misses his technical replies.

## Left out on purpose

Third-party claims with no public code, repo or tx id: PhantomPool, the KASperiencexyz shielded-pool claim and the teoscure simnet proving numbers.

## 5 Oct 2026 sweep (GitHub reads ~07:45 CEST; not desk-checked)

- Draft [PR #22](https://github.com/olafweller/kaspa-privacy-initiative/pull/22) head moved to [`f4a4ddc5`](https://github.com/olafweller/kaspa-privacy-initiative/commit/f4a4ddc50a41aa5c640e0b43ff0962c9ed49e718) (commit 4 Oct 20:22Z, "docs(a1): record failed live G5 attempt and separate terminal exit"). Still open and draft. The desk's 20/20 Rust run above was at `2590e392`, not at this head.
- The author's [live attempt 1 record](https://github.com/olafweller/kaspa-privacy-initiative/blob/f4a4ddc50a41aa5c640e0b43ff0962c9ed49e718/docs/poc-a1-live-attempt-1.md) (4 Oct, Testnet 10 test KAS) says: S0 funding (txid `c0968d6206fe0f2f5c9f96bae6d13a9d4a4ae8078a50c9401cba56bc50f323bb`, 10.7 test KAS) and the S0 → S1 continuation (txid `5027a249234a139807657454055578f2c84ed31be85d027a0e2f4254f341d294`) passed; the boundary receipt failed, recovery machine B never armed, and independent recovery was not run. S1 was later exited by a separately authorized terminal tx (`c3e155010dacbdc5a367db183170a96df0ddf80efa34d1c73cbad4e08d2b8483`). Overall G5 attempt: **FAILED** (fail-closed, funds safe, per the author). Author's record; the desk did not check these txids on its node.
- New open issue [#23](https://github.com/olafweller/kaspa-privacy-initiative/issues/23) (4 Oct 07:56Z): A1's fixed branch fees can cost an owner practical exit liveness if relay or inclusion cost rises; the author calls it an open production-design blocker.
- X: his 4 Oct posts in the 5 Oct community read (2106773440338247750, 2106523383844229492) are at or below the per-account backfill marker, so they were already covered by the 4 Oct backfill.

## Provenance

- Row added to kaspa-master-file in [`25c96e4`](https://github.com/STP-KAS/kaspa-master-file/commit/25c96e40f989cee2bbe5c4f97f32a15a838f7793) (4 Oct 18:16 CEST), challenger pass at [`43a3c64`](https://github.com/STP-KAS/kaspa-master-file/blob/43a3c64f5a72580cf54ab552699245b7a1481076/challenges/wellerolaf-2026-10-04-challenge.md) (35 HELD, 0 FAILED, 1 UNVERIFIABLE), merged at `7a54145`.
- Moved out of the master on stp's instruction (4 Oct 19:01 CEST) by [`220fa36`](https://github.com/STP-KAS/kaspa-master-file/commit/220fa36b1fad7143ebd8ee28a4858b26ad60e7c1) on `master/community-move-2026-10-04`. The master keeps the research.kas.pa fact fix.
- No star, fork, issue, comment or PR on the source repo.
