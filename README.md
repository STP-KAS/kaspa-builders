# kaspa-builders

Third-party Kaspa builders, projects and community research, with sources. Companion to [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file).

**What lives where.** The master file keeps Kaspa core, kaspanet code, KIPs, credible sources and history. This repo holds everything else worth tracking: third-party builders, community people, their projects and ideas. An entry here is **not** Kaspa core, **not** a KIP and **not** an endorsement. A tweet is not a pin.

## Rules

- **A source on every claim:** a pinned commit sha, a post id, a tx id or block hash, or a file and line at a pinned sha.
- An author's own claim is labelled as a claim. "Desk-checked" means it was checked on the desk's own node or build, and the entry says how.
- No price talk.
- No home paths, local usernames or private repo names.
- No public reactions on other people's repos: no stars, forks, issues, comments or PRs. Reads only.
- Times are UTC (`Z`) unless labelled CEST.
- Changes go through branches and a challenge pass. See [`AGENTS.md`](AGENTS.md).

## Status chips

| Chip | Meaning |
| --- | --- |
| `experiment` | Code exists and part of it was checked (on chain or by a build), but it is research and not a product. |
| `catalog` | Tracked and sourced, not desk-tested. |
| `claim` | Only the author's word so far: no public code, repo or tx id. |

## Index

| Entry | What | Status chip | Key sources | Last checked |
| --- | --- | --- | --- | --- |
| [Privacy initiative (KPI)](entries/olaf-weller-kpi.md) | @WellerOlaf's community research on optional privacy for native KAS. A0.5 is one Groth16-gated payout from a **P2SH reserve** on Testnet 10 (`OpZkPrecompile` 0xa6, Groth16 tag 0x20, plus introspection; no KIP-20 covenant id). **Not a privacy pool**: no notes, nullifiers or private transfers yet. Single-party trusted setup per claim. AI-written, unaudited. | `experiment` | [olafweller/kaspa-privacy-initiative `98aa99fa`](https://github.com/olafweller/kaspa-privacy-initiative/commit/98aa99fa8230f5eb490e0af4e3da0291260581d6); TN10 tx `29d875bb…b554` in chain block `c38a5439`; [challenge note `43a3c64`](https://github.com/STP-KAS/kaspa-master-file/blob/43a3c64f5a72580cf54ab552699245b7a1481076/challenges/wellerolaf-2026-10-04-challenge.md); X [2106458391107236016](https://x.com/WellerOlaf/status/2106458391107236016) | 2026-10-04 |
| [KasperoLabs: SilverScript Studio](entries/kasperolabs-silverscript-studio.md) | A covenant-writing studio (by hand, wizard, or SilverScript-only AI) that the author says is live on mainnet, plus the KasDash demo (a demo, not an L1 product). Not desk-tested. AI contract code needs review before real KAS. | `catalog` | X [2103564787686793710](https://x.com/KasperoLabs/status/2103564787686793710); [kasperolabs/silverscript-studio `e27a7c4e`](https://github.com/kasperolabs/silverscript-studio/commit/e27a7c4ec91d5b33eed8c51c9dfef8fbb45f6f0b); [rusty-kaspa #1140](https://github.com/kaspanet/rusty-kaspa/issues/1140) | 2026-10-04 |

Machine copy of this table: [`builders.json`](builders.json). Change log, newest first: [`SNAPSHOT-HISTORY.md`](SNAPSHOT-HISTORY.md).

## License

Apache-2.0 ([`LICENSE`](LICENSE)) for the text in this repo. Linked projects keep their own licenses.
