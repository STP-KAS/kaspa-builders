# Ross Ku (RossKU/kob): Argent port notes and 8 Oct replies

**Chip:** `catalog`. Third-party. **Caveat: third-party, not audited, demo, not desk-tested.** Everything below is Ross Ku's own account and his own figures. Nothing here was compiled, measured or run by the desk. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-20 (GitHub commit read 20 Oct ~07:55 CEST: the 19 to 20 Oct section below; the 8 Oct notes and Telegram replies are still the 9 Oct reads).

**The master keeps:** one sentence in its Argent cell, tied to [argent#69](https://github.com/argent-lang/argent/pull/69) (with an artifact import the interface fingerprint excludes the handle; his item 12 pin is open #69), with a pointer to this page ([kaspa-master-file Argent row](https://github.com/STP-KAS/kaspa-master-file), since `cb8b0df`). Argent itself (argent-lang/argent, its PRs and issues) stays in the master. This page holds the rest of his 8 Oct material, trimmed from the master's `build/ross-ku-argent-2026-10-08` branch on 9 Oct.

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

## 19 to 20 Oct 2026: KCC-23 tokens and TN10 attack notes (author's record)

Read 20 Oct ~07:55 CEST from the commit list (31 commits on `master` from 19 Oct 08:30Z to 20 Oct 05:00:56Z). His claims, not desk-checked.

- **KCC-23 token creation.** From [`c4b5e89a`](https://github.com/RossKU/kob/commit/c4b5e89a) to [`218fdc10`](https://github.com/RossKU/kob/commit/218fdc10) (19 Oct 16:16:57Z to 17:41:38Z): a KOB token creation is two transactions under KCC-23, a preparation that declares the token details, then a genesis that spends it; a launch proof (`kob-kcc23-proof/1`) recomputes both ids and the covenant id; the indexer keeps a declaration only when its launch proof verifies. [`910398e6`](https://github.com/RossKU/kob/commit/910398e6c9ff23d13e37bd1a32d9df7512343a04) adds `docs/spec/token-metadata.md` (commit message excerpt: "spec: token-metadata.md: KCC-23 (pinned Draft 1516a6c) as KOB adopts it"). KCC-23 is a Draft on kccs main `1516a6c4` (master file, KCC still open).
- **Audit fixes.** [`6276d5ca`](https://github.com/RossKU/kob/commit/6276d5ca) "trigger evidence compares the KCC-20 extension commitment (AUD-EXT), both pair scales positive (AUD-NP)", and [`d368ded9`](https://github.com/RossKU/kob/commit/d368ded9) (AUD-RT), with docs commits marking them closed in `docs/security/AUDIT-2026-10.md` (the audit file itself not read; who wrote it not checked).
- **Live TN10 attacks.** [`633c06a1`](https://github.com/RossKU/kob/commit/633c06a182241ffcca40b3afff1fd161147e27b3) (20 Oct 05:00:56Z), commit message: "live TN10 attacks on KobCondPair and KobIfdPair (2026-10-20, main 9ff613b1): 11 single-change attacks, all rejected by the engine and the node, both honest controls accepted"; files `docs/testing/TN10-TEST-2026-10.md` and `docs/security/AUDIT-2026-10.md` (not read beyond the commit).
- Also `fdb38fc7` "kob-x402: conformance vectors of the Kaspa x402 binding v1.0.1" (see [x402](x402.md)).

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

## 21 Oct 2026 (r2 sweep)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Four commits on master after `d4f1b4ee`, to [`a02345f8`](https://github.com/RossKU/kob/commit/a02345f8) (10:31:29Z). [`c1800bf2`](https://github.com/RossKU/kob/commit/c1800bf2) (05:55:37Z) shows the KAS on the wallet's token UTXOs as its own Balances line; [`6f7b0010`](https://github.com/RossKU/kob/commit/6f7b0010) moves the web app to vite 8.3.5 (author: earlier 8.3.x pulled a launch-editor with high advisories); the rest are e2e/CI test changes. No release.

## 22 to 23 Oct 2026 (GitHub read 23 Oct ~08:15 CEST)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- 22 commits on master after `a02345f8`, to [`aec11a5f`](https://github.com/RossKU/kob/commit/aec11a5f) (23 Oct 01:58:04Z). Among them: [`f50a5b32`](https://github.com/RossKU/kob/commit/f50a5b32) (11:26:30Z) "registry: KOB makes no per-token judgement (founder 2026-10-19, legal review 2026-10-21)": token entries lose listed/delisted status, `official` and the maintainer warning text; [`2abc1f47`](https://github.com/RossKU/kob/commit/2abc1f47) (14:59:44Z) "registry: no ticker uniqueness", because "the covenant id beside the ticker is the identity"; [`5c27aee1`](https://github.com/RossKU/kob/commit/5c27aee1) public Kaspa nodes as the executor default, "always a cross-checked pair"; [`ec71e142`](https://github.com/RossKU/kob/commit/ec71e142) a release workflow for prebuilt `kob-executor` / `kob-cli` binaries on a `v*` tag; [`ca4ae33c`](https://github.com/RossKU/kob/commit/ca4ae33c) a Cloudflare Pages deploy workflow for the web app; the rest are web layout and docs. No tag or release.

## 23 to 24 Oct 2026 (GitHub read 24 Oct ~07:45 CEST)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- 6 commits on master after `aec11a5f` (compare, every commit), to [`8979408f`](https://github.com/RossKU/kob/commit/8979408f0373b0643255f7a6d6ec11a9fbdefafa) (23 Oct 21:03:35Z) "deps: tokio 1.54.1 (RUSTSEC-2026-0386 ...), which failed cargo deny". Among them: [`424cb430`](https://github.com/RossKU/kob/commit/424cb430) (15:36:25Z) "release: aarch64-linux-android (bionic) builds of kob-executor and kob-cli for Termux on a phone"; `1f2185f7`, `8d544ca2` and `d9c7bf80` (06:43Z–07:17Z) on the web private-key signer's anti-clickjacking wait ("Android Chrome reported three of five rows as covered ... so Approve never opened on that phone"); [`bdb892e5`](https://github.com/RossKU/kob/commit/bdb892e5) (10:13:21Z) an e2e guard for that signer on Android-like phones.

## 24 Oct 2026 (GitHub read 25 Oct ~07:50 CET)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- 9 commits on `master`, 07:47:16Z to 10:00:33Z, tip [`fd105ec6`](https://github.com/RossKU/kob/commit/fd105ec6). [`a8fd5da5`](https://github.com/RossKU/kob/commit/a8fd5da5) "android: testnet-10 executor app (foreground service, setup/run/status screens), CI builds the debug-signed APK"; [`49b3a104`](https://github.com/RossKU/kob/commit/49b3a104) `setup --non-interactive` and `address-balance` for the app; [`540dac0c`](https://github.com/RossKU/kob/commit/540dac0c) writer lock with flock on Unix ("std's File::try_lock is unsupported on Android"); [`7d955f8b`](https://github.com/RossKU/kob/commit/7d955f8b) "fast start" on a tip store while the full book is indexed; [`fd105ec6`](https://github.com/RossKU/kob/commit/fd105ec6) "lean storage - the live book plus 30 days of closed orders and a 500 MB cap"; four Android UI commits (gradlew, balance read, selectable text, dark mode).

## 26 to 27 Oct 2026 (GitHub read 27 Oct ~07:50 CET)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- 26 commits on `master` since 26 Oct 04:54Z, from 08:25:39Z to 27 Oct 06:19:16Z, tip [`4fa33bbc`](https://github.com/RossKU/kob/commit/4fa33bbc). Among them: [`011d8059`](https://github.com/RossKU/kob/commit/011d8059) "executor operator: kob-executor withdraw (KAS out of the operator key over the configured node, …"; [`4913dfe8`](https://github.com/RossKU/kob/commit/4913dfe8) "android: stable release signing (the ANDROID_* repository secrets, else a loud debug-signed fallback), …"; [`6c34c261`](https://github.com/RossKU/kob/commit/6c34c261) "ci: production is deployed only from refs/heads/master and the deploy job runs in the environment production, …"; [`69a9717a`](https://github.com/RossKU/kob/commit/69a9717a) "web: reach the resolver-picked node over Borsh: the public Kaspa resolvers answer 404 for the json path, …".

## 27 to 28 Oct 2026: KOB 0.1.0 (GitHub read 28 Oct ~07:50 CET)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Tag [`v0.1.0`](https://github.com/RossKU/kob/releases/tag/v0.1.0) (annotated, tagger date 28 Oct 06:45:34Z, "KOB 0.1.0: first release, testnet-10 only, pre-audit") points to [`945f574a`](https://github.com/RossKU/kob/commit/945f574a6fcfbf50dafeabfe04c040ccddc6dacb) "kob-protocol: golden vectors carry protocol version 0.1.0"; 0 GitHub releases. [`2d4d0d35`](https://github.com/RossKU/kob/commit/2d4d0d35ce149ef2d9dd12e4ae870869e7486e7e) "Release 0.1.0": "First release: testnet-10 only, pre-audit."
- 19 commits on `master` since 27 Oct 06:42:59Z, tip [`250513c2`](https://github.com/RossKU/kob/commit/250513c20f23f7bded4d1aef88850ac90c0a0673) (28 Oct 05:15:39Z). Among them: [`e0d49412`](https://github.com/RossKU/kob/commit/e0d49412) "KaspaRocket token program on mainnet: reviewed, genesis-only, default decimals 3 (the KaspaRocket convention)"; [`75db5385`](https://github.com/RossKU/kob/commit/75db5385) "Pin the KCC-20 reference issuers of 27f8403 beside c8a0871: …"; [`4da4979e`](https://github.com/RossKU/kob/commit/4da4979e) "web: indexer failover. …".

## 31 Oct 2026: kob#1 QA notes from KasperoLabs (GitHub read 1 Nov ~07:45 CET)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- [RossKU/kob#1](https://github.com/RossKU/kob/issues/1) "QA notes from testnet: UX and balance findings", opened by kasperolabs 31 Oct 11:44:32Z, open, 0 comments: "Tested on testnet-10 with KasWare and Kaspire. Ranked by user impact, highest first." Items include "One market buy left 3.47 KAS on my token UTXOs" and "About 0.5 KAS per cell is enough under storage mass"; "Token image not shown"; "Default indexer and node use a trycloudflare quick tunnel. Fine for the canary; a stable domain will be needed before mainnet users rely on it."; "Kastle is hidden behind an experimental checkbox." The tester's notes; not desk-checked.

## 2 to 3 Nov 2026: kob#1 reply; terminal bid refund (GitHub read 3 Nov ~07:40 CET)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- RossKU on [RossKU/kob#1](https://github.com/RossKU/kob/issues/1) (2 Nov 22:33:20Z): "Fixed on master (ff3cd288, b7929f73)". Listed as not changed: "The trycloudflare tunnel is a canary setup and will be replaced by a stable domain before mainnet." and "Kastle stays behind the experimental option, by decision." Token-cell KAS is listed under "In progress". The issue is still open.
- 8 commits on `master` from 2 Nov 21:06:34Z to 3 Nov 04:49:06Z, tip [`5ceee157`](https://github.com/RossKU/kob/commit/5ceee15749c2129c27b3ed10394c7bb4dbca9930). Among them: [`ff3cd288`](https://github.com/RossKU/kob/commit/ff3cd288) "web: issue 1 fixes: …"; [`acf39cf1`](https://github.com/RossKU/kob/commit/acf39cf1) "contracts: a terminal bid fill returns the spare KAS to its maker as a plain output"; [`2767de34`](https://github.com/RossKU/kob/commit/2767de34) "kob-protocol: builders lay out the terminal bid refund; matcher, x402, executor and docs follow"; [`5ceee157`](https://github.com/RossKU/kob/commit/5ceee157) "kob-tests: attack and regression tests for the terminal bid refund, ablation catalogs, audit section 17". Tag still `v0.1.0`.


## 3 to 5 Nov 2026: kob#1 follow-ups and current master (GitHub read 5 Nov)

**Caveat: third-party, not audited, not desk-tested; the author's own records.**

- Current master [`dc91c8c3`](https://github.com/RossKU/kob/commit/dc91c8c3c9fafad3cc17560d957bac6ce1cf7dc5) (5 Nov 16:43:11Z); [kob#1](https://github.com/RossKU/kob/issues/1) remains open.
- Default delivered-cell carrier changed from 2 to 1 KAS in `984ef9ee`, with web/unit expectations in `c0ae129d`. In the #1 discussion the author reports 1,635 builder shapes still build at 1 KAS and 75 fail at 0.5 KAS. These are the author's measurements, not a desk run.
- Other substantive follow-ups: PublicMint becomes the default issuance program; KCC-23 image/image_hash metadata and hash verification; compact storage and indexer schema migrations; x402 settlement/rival-keeper fixes; standalone/mock mode with node-followed blocks and docs; public indexer/deployment and CLI documentation.
- Tag remains v0.1.0, Testnet-10 only, pre-audit. The commit list was not itemized exhaustively.

## 5 to 6 Nov 2026: master tip `29c09092` (GitHub read 6 Nov ~07:45 CET)

**Caveat: third-party, not audited, not desk-tested; the author's own records.**

- Current master [`29c09092`](https://github.com/RossKU/kob/commit/29c090922877813e783d16e98b2c9514fff65c3f) (6 Nov 06:36:07Z); [kob#1](https://github.com/RossKU/kob/issues/1) remains open.
- 31 commits since [`dc91c8c3`](https://github.com/RossKU/kob/commit/dc91c8c3c9fafad3cc17560d957bac6ce1cf7dc5) (5 Nov 16:43:11Z). Among them: kobd role-flag starts (`kobd`, `kobd --executor`, `kobd --indexer`); Activity page; landing/web header and palette; CI/Pages Node 24; Android kobd index schema migrate 5→9; docs. Not exhaustively itemised.
- Tag remains v0.1.0, Testnet-10 only, pre-audit.

## 6 to 7 Nov 2026: master tip `3e7f867f` (GitHub read 7 Nov ~07:50 CET; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Current master [`3e7f867f`](https://github.com/RossKU/kob/commit/3e7f867fcb1bbf65dd3ec2fb44801caeb5cf0a61) (7 Nov 06:33:02Z); 41 commits ahead of prior tip `29c09092`.
- Themes in the window (author commit messages): kobd `db` subcommands replace `kobd index`; cancel-only table for retired order templates; activity log and market list pagination/favourites/pair picker; contracts path cleanup (`orders/` vs prototypes); docs/registry/soak/repository-root moves; bell live status; token naming on ticket/pair pages.
- [kob#1](https://github.com/RossKU/kob/issues/1) remains open. Tag remains v0.1.0. Third-party; not desk-checked.

## 7 to 8 Nov 2026: master tip `3a5f082b` (GitHub read 8 Nov ~07:50 CET; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Current master [`3a5f082b`](https://github.com/RossKU/kob/commit/3a5f082b1e062a2ff432a0729ae5cca4d0d2319e) (8 Nov 06:39:01Z); 44 commits ahead of prior tip `3e7f867f`.
- Themes in the window (author commit messages): Activity log scoping, two-line rows, owner lookup, and a 1D/7D/1M/1Y summary with volume chart; custom dropdowns, header/tab spacing, two-column settings, two-ended IDs, zero-subscript, ticker from the token list; pair-chart empty candles / one-token-not-traded; a disclaimer page and pre-audit wording replaced by "open review" (specification is not final; no review can show the code is free of bugs; later notices drop "no third party has checked"); Support page and a feedback section that says there is no bug bounty; landing trust rows (Closed source / Trust us: None; SilverScript and Argent named); SVG token logos hash-checked then drawn to a canvas and shown as WEBP (an unreadable or unhashed SVG is never shown); e2e and tagline matching the static title.
- [kob#1](https://github.com/RossKU/kob/issues/1) remains open. Tag remains v0.1.0, Testnet-10 only.

## 8 Nov 2026: master tip `74c449c4` (GitHub/site read 9 Nov ~07:45 CET; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Current master [`74c449c4`](https://github.com/RossKU/kob/commit/74c449c4ef14) (8 Nov 14:04:57Z); 16 commits ahead of prior tip `3a5f082b`.
- Themes in the window (author commit messages): pair orders of the two orientations of one pair net against each other in the matcher; one pair book and one fill record by id for both orientations; hide a token from the market list with the eye beside its star; checked token logos in common formats, and no code in a picture (SVGs with scripts, event handlers or outside references refused); landing page says the bundled executor is a reference and its trust model gains "Off switch: None"; fetch-sdk retries the release download up to five times with the zip still held to its pinned hash; kobd uses kobd.toml and kobd.log and its Indexer start answers --version.
- New branches opened 8–9 Nov: `ci/kobd`, `ui-polish`, `ci/boot-mark`, `ci/no-ghpages`, `ci/lp-copy`, `ci/merge-four`, `ci/acl-tmpname`, `ui/hide-scroll-fit` (not on master). [kob#1](https://github.com/RossKU/kob/issues/1) remains open. Tag remains v0.1.0, Testnet-10 only.

## 9 to 10 Nov 2026: master tip `73ce3d90` (GitHub/site read 10 Nov ~07:45 CET, tip re-read ~08:05 CET; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Current master [`73ce3d90`](https://github.com/RossKU/kob/commit/73ce3d90) (10 Nov 06:53:20Z); 84 commits ahead of prior tip `74c449c4` (54 of them `web:` UI commits). The last five (`4f72ef90`, `76499dae`, `1b01b14b`, `ab1aa1c3`, `73ce3d90`, after `1fa1a95b` of 05:56:10Z) show read-only KAS values in dollars when the web app's display currency is USD.
- Non-UI commit messages include: `a05555c3` kobd `GET /v1/stats?since=` (orders placed, traders, fees paid to fillers, KAS locked in live orders) and `8398956e` schema 10 (stats from trigger-kept aggregates); `33ab3383` gzip for JSON answers of 512 bytes or more; `5711379b` Cache-Control by route class; `e3041db3` RUSTSEC-2026-0459 (bundled SQLite before 3.54) accepted, then `d5922bc4` rusqlite 0.41 (bundled SQLite 3.54.1) fixes it; `c276a005` x402: default `max_extra` of a KasToToken intent is what the shape's execution needs; `82b3aad4` CLI pair order with no `--tip` carries the pair's keeper tip; `ef4758bc` no GitHub Pages mirror; `c088e0f8` domains: kob-tn10.kaspa.ag and kob-api-tn10.kaspa.ag (Testnet-10), kob.kaspa.ag and kob-api.kaspa.ag production; `f61874c0`/`00dad858` mainnet site is a landing-only build, "mainnet in preparation"; `7fc6bae1` kobd `GET /v1/price/kas-usd` for an optional USD display (opt-in: `[api] usd_price`, `--usd-price`, `KOB_USD_PRICE`; off by default).
- [kob#1](https://github.com/RossKU/kob/issues/1) remains open (RossKU comment 9 Nov 09:22:30Z). Tag remains v0.1.0.

## 10 to 11 Nov 2026: master tip `1e5f3890` (GitHub/site read 11 Nov ~07:45 CET; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Current master [`1e5f3890`](https://github.com/RossKU/kob/commit/1e5f38902264da6b12a23b3d709b0e0dd6867339) (11 Nov 06:06:15Z); 73 commits ahead of `73ce3d90`.
- Non-UI commit messages include: `9409b212` "kobd: public resolver pair as the default node, Indexer failover from a configured node"; `47acbed8` "kobd nodes: both nodes of the pair are judged by their answers, and an abnormal one is cut off"; `ad643b6f` "kobd --executor: a pending transaction is never forgotten while a mempool holds it, in-flight state survives a restart, …"; `b1ee61e9` kobd indexer storage-error handling; `6f2c518f` "kobd key: on Windows a key file another account may read is refused by default, named accounts included" (then `48438fe8` accepts the built-in Administrator and TrustedInstaller); `05b6806b` "release: build provenance attestations for every archive, the APK and SHA256SUMS; CI rebuilds the mainnet build twice"; `44e0410e` release workflow runs `kobd --indexer` (the index subcommand is gone since `74c449c4e`); `53da9234` "Drop the word DEX: KOB is not one, …".
- [kob#1](https://github.com/RossKU/kob/issues/1) closed as completed by RossKU on 11 Nov 06:50:09Z (still open at the ~07:45 CET read). Tag remains v0.1.0.

## 11 to 12 Nov 2026: master tip `803d6c08` (GitHub read 12 Nov ~07:45 CET; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Current master [`803d6c08`](https://github.com/RossKU/kob/commit/803d6c08568f7d5469c235939c74c92a09847e2c) (12 Nov 03:23:02Z); 110 commits ahead of `1e5f3890`.
- Non-UI commit messages include: `e950ac8a` "kobd nodes: a node is judged by the DAG and the local monotonic clock, never by a block timestamp; …"; `15a421bc` "executor: halt at a store-side contradiction once two public authorities on different hosts agree against the store (aud…"; `83ecd85c` "kobd keepers: the fee subsidy is at most 1 KAS in any 24 hours by default"; `50fe1ec9` "kob-protocol: placements announce the release of the build that wrote them (optional RELEASE record 0x84, …"; `284070ea` "kobd: the update notice: a release newer than this build seen on 3 accepted placements of at least 2 makers is reported …"; `4fad4752` Windows archive ships `kobd-supervise.cmd`; `5a8b5edb` Linux archive ships a sample `kobd.service`; `035e0968` "/v1/stats adds depth_2pct_bid_sompi and depth_2pct_ask_sompi"; `0566fa34` "docs: no paid code signing, and template re-versions come with a published migration window (founder decisions)"; `e0971bfe` "docs: the executor audit's accepted risks (founder 2026-11-12)".
- Web UI: kascov price as an optional chart overlay (`0d73ecac`, off by default) and many layout changes.
- [kob#1](https://github.com/RossKU/kob/issues/1) closed 11 Nov 06:50:09Z. Tag remains v0.1.0.

## 12 to 13 Nov 2026: master tip `9c0bd2fa` (GitHub read 13 Nov ~07:55 CET; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Current master [`9c0bd2fa`](https://github.com/RossKU/kob/commit/9c0bd2fa37030a5e5e49a4ca7169e30dd2b59231) (13 Nov 06:47:11Z, "web: follow the network in force; tighten server URLs"); 39 commits ahead of `803d6c08`.
- Non-UI commit messages include: `ebc39ccf` "kobd: executor income and miner fees per KOB transaction (schema 11) …"; `389c4236` "kobd: schema 12 and archive pruning: a store that keeps its history deletes, once final, the spent UTXO rows of orders that are no longer live, …"; `a29c6c44` "kobd: schema 13 for recorded_outputs: kobd db migrate takes a store of schema 9 to 12 the short way to 13 …"; `fdcfa82c` "kobd: own trades are not paid to executors …"; `5bb4c3c0` "kobd: the 24 h change is measured against the price 24 h ago"; `a3f2b4b7` "kobd: kobd db replay and replay --onto-database stream the record log: the whole chain is verified first without decoding …"; `2c59571f` "repo: GitHub highlights SilverScript (.sil) as JavaScript and Argent (.ag) as Rust"; `3e0d3e97` "docs: the Kaspero Labs red team report of 2026-11-09 (kaspa-redteam, published with their permission) …"; `d8a4bdaa` "docs: add the code style rules and a comment-only checker".
- Tag remains v0.1.0.
