# Ross Ku (RossKU/kob): Argent port notes and 8 Oct replies

**Chip:** `catalog`. Third-party. **Caveat: third-party, not audited, demo, not desk-tested.** Everything below is Ross Ku's own account and his own figures. Nothing here was compiled, measured or run by the desk. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-09 (GitHub reads 9 Oct ~08:37 CEST and again ~08:40 CEST; the 8 Oct Telegram replies were read in the thread on 8 Oct and not re-read).

**The master keeps:** one sentence in its Argent cell, tied to [argent#69](https://github.com/argent-lang/argent/pull/69) (with an artifact import the interface fingerprint excludes the handle; his item 12 pin is open #69); it does not link to this page. Argent itself (argent-lang/argent, its PRs and issues) stays in the master. This page holds the rest of his 8 Oct material, trimmed from the master's `build/ross-ku-argent-2026-10-08` branch on 9 Oct.

## Who and where

- Ross Ku, GitHub user `RossKU`. Repo [RossKU/kob](https://github.com/RossKU/kob) (public, not a fork, ISC, default branch `master`; tip [`fdb92b63`](https://github.com/RossKU/kob/commit/fdb92b63d3d91748d98920af91e679efe3e92356), 9 Oct 05:22:58Z, web UI commits after the notes). KOB uses Argent for its swap-and-pay router; its order contracts are hand-written SilverScript. KOB is tracked here as a source of notes, not as a product.
- Public Core R&D Telegram thread: his questions in [16113](https://t.me/kasparnd/16113) (29 Sep 22:56Z), IzioDev's reply [16114](https://t.me/kasparnd/16114), Sutton's 1 Oct answers [16118](https://t.me/kasparnd/16118). The 29 Sep thread names no repository.

## Argent port notes (8 Oct 2026)

Stable anchor for links from the master: `entries/rossku-kob.md#argent-port-notes-8-oct-2026`.

Sources: notes commit [`9d8030c9`](https://github.com/RossKU/kob/commit/9d8030c9b1aca370af2315230c15920c021e39a2) (8 Oct 13:12:28Z, "docs: argent port comparison, shorter"): [docs/argent-port-compare.md](https://github.com/RossKU/kob/blob/9d8030c9b1aca370af2315230c15920c021e39a2/docs/argent-port-compare.md) and [docs/argent-feedback.md](https://github.com/RossKU/kob/blob/9d8030c9b1aca370af2315230c15920c021e39a2/docs/argent-feedback.md) (both re-read 9 Oct; byte-identical to the 08:37 CEST read). Prior commit `7405d44c` (8 Oct 11:05:16Z) holds the opcode listings. His replies in the thread were at 13:14Z, 13:23Z, 13:51Z and 13:56Z on 8 Oct; the desk recorded no message ids for them.

All of the following is **his claim, not desk-checked**:

- **Size, hand-written vs Argent (correcting the ~500 B in 16113 point 10).** With the same constructor arguments, hand-written `KobAsk.sil` is **1,684 B** and an idiomatic Argent port is **2,705 B** (+1,021). With the rows he lists removed (hand-written: 79 B continuation check, 21 B own output-count checks; port: 591 B `become` state literal of 20 fields, 514 B `validateOutputState` and `cont.length == count`, 16 B generated bounds and `cancel ... emits none`), both are the same 1,584 B script. He says most of the gap is `become` rebuilding and comparing the whole state, not duplicated checks. His feedback note says every compiler-dependent result is against pinned argent `b312deda` (SilverScript v1.0.0) plus his two patches, not against argent master `9a9f4b10`.
- **Splice idea.** If `become` compiled "self with only these fields changed" to a splice of those fields, the port would be close to the hand-written one. His hand-made sketch `KobAsk.splice1.sil` is 1,713 B (+29). He says it only seems sound for fixed-width fields, the same actor, and fields not reassigned before `become`. His idea; not an upstream change.
- **Behaviour.** He says `cancel ... emits none` (it refuses a cancel that re-creates the order under the same covenant id) is the only behavioural difference in his 1,004 test cases.
- **Importer id pin (Sutton's question 4, 13:23Z; his item 12).** He means the importer of another app's published artifact: with an artifact import, argentc does not check a linked handle against the exporter's template receipt and the interface fingerprint excludes the handle, so whoever supplies the artifact chooses which template the importer accepts. His patch adds `import "./x/artifact.json" id "<id>";` and refuses any other artifact. That pull is [argent#69](https://github.com/argent-lang/argent/pull/69) "Load pinned app artifacts through module imports" (from his fork, head `435fa89ae4e717e0e8df627e36f372cc106c1bab`, opened 8 Oct 14:52:06Z, after the message; 9 files, 0 reviews, open and unmerged on 9 Oct). The pull body describes the pin and does not mention the fingerprint. argent master is still [`9a9f4b10`](https://github.com/argent-lang/argent/commit/9a9f4b107116d0b259fae629f200fa3b663e7e9d) (7 Oct 08:24:44Z).
- **Outputs.** He says they already allocate one output per input (his item 3, a hand-written positional rule).
- **The 244 limit (13:51Z; his item 6).** On SilverScript v1.0.0, and, he says, the same on argent master with #68: the router fits, and only adding the continuation pin to the 2+2 swap goes over the 244 live stack bindings (his table: `TokenSwap_swap2` 227 shipped, 248 with the ask pin, 250 with the bid pin). They leave that pin out because the orders check their own continuation. His measurement.
- **Stored `actor_type` (13:56Z; his item 7).** Until [argent#61](https://github.com/argent-lang/argent/issues/61) (open, last updated 16 Sep) lets an entry compare a stored `actor_type` with an imported template, they store the raw template hash and lengths.
- He accepts Sutton's answers on items 1, 2, 5, 8 and 9.

## Limits

- Pre-audit code on his side and pre-1.0 Argent, in his own words. No numbers here were reproduced by the desk.
- The Telegram replies have no recorded message ids; the commit and the pull above are the pinned sources.

## Sources

- https://github.com/RossKU/kob
- https://github.com/RossKU/kob/commit/9d8030c9b1aca370af2315230c15920c021e39a2
- https://github.com/RossKU/kob/blob/9d8030c9b1aca370af2315230c15920c021e39a2/docs/argent-port-compare.md
- https://github.com/RossKU/kob/blob/9d8030c9b1aca370af2315230c15920c021e39a2/docs/argent-feedback.md
- https://github.com/RossKU/kob/commit/fdb92b63d3d91748d98920af91e679efe3e92356
- https://github.com/argent-lang/argent/pull/69
- https://github.com/argent-lang/argent/issues/61
- https://github.com/argent-lang/argent/commit/9a9f4b107116d0b259fae629f200fa3b663e7e9d
- https://t.me/kasparnd/16113
- https://t.me/kasparnd/16114
- https://t.me/kasparnd/16118
- No star, fork, issue, comment or PR on the source repos.
