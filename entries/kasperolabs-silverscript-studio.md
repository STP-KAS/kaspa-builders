# KasperoLabs: SilverScript Studio

**Chip:** `catalog`. Third-party builder. **Not desk-tested. AI contract code needs review before real KAS.**
**Last checked:** 12 Oct 2026 ~07:45 CEST (two X posts of 11 Oct only). Repo, issue and demo page GETs: 4 Oct 2026 ~19:05 CEST. The backfill X items come from the 3 Oct backfill (read ~19:20 CEST).

## Who

- X [@KasperoLabs](https://x.com/KasperoLabs) ("Kaspero Labs"), id `1883537666429313025`, joined 26 Jan 2025. Profile link kasperolabs.com. Also runs KasperoPay / KasperoConnect (@kasperopay).
- GitHub user [`kasperolabs`](https://github.com/kasperolabs) (a user, not an org). Its profile names X `KasperoLabs` and the blog kasperolabs.com, and kasperolabs.com links the GitHub account, so the two accounts point to each other.

## SilverScript Studio

- **Mainnet claim** ([2103564787686793710](https://x.com/KasperoLabs/status/2103564787686793710), 25 Sep 19:18Z): Studio (silverscriptstudio.com) is live on mainnet. You write a covenant by hand, with a wizard, or by describing it to a SilverScript-only AI. Deposit and withdraw work with Kasware, Kasla or Kastle (Kastle can deposit only; signing "coming"). **Author's claim, not desk-tested.**
- **Relay:** vertex ([@KaspaScopio 2103759384694185988](https://x.com/KaspaScopio/status/2103759384694185988), 26 Sep 08:11Z). This was the source the master cited first.
- **Source:** [kasperolabs/silverscript-studio](https://github.com/kasperolabs/silverscript-studio). MIT, created 28 Sep 21:28:34Z, not a fork, tip [`e27a7c4ec91d5b33eed8c51c9dfef8fbb45f6f0b`](https://github.com/kasperolabs/silverscript-studio/commit/e27a7c4ec91d5b33eed8c51c9dfef8fbb45f6f0b) (3 Oct 22:39:10Z). Still the main tip at the 4 Oct ~19:05 CEST GET. Not built or run here.
- **KasDash demo** ([kasdash.html](https://silverscriptstudio.com/kasdash.html), HTTP 200 on 4 Oct; [post 2106350037680988279](https://x.com/KasperoLabs/status/2106350037680988279), 3 Oct 11:45Z, pinned): a covenant "DoorDash" demo. Payment locks at checkout, and the dasher's scan at the door pays restaurant, dasher and taxes in one transaction. It runs in demo mode or with your own wallets ("Run it for real"), and the page text mentions "mainnet through the Studio". **A demo, not an L1 product.**

## kaspanet

- [rusty-kaspa #1140](https://github.com/kaspanet/rusty-kaspa/issues/1140), filed by `kasperolabs` 30 Sep 04:43Z: "SDK v2.1.0 findings from mainnet: createTransactions dust change on drains, npm package, docs". Open, 0 comments at the 4 Oct ~19:05 CEST GET. Because it is a kaspanet object, it stays on the master board as well.

## X backfill (3 Sep to 3 Oct 2026)

Full timeline, replies included: 24 posts, one page, no `next_token`. There were **no posts from 3 to 22 Sep** (checked with a `from:KasperoLabs` search that returned 0). Times are UTC. The items below are the author's own posts: they are sourced, but none was desk-tested.

- **Wallets** ([2103711944033329489](https://x.com/KasperoLabs/status/2103711944033329489), [2103949832285204582](https://x.com/KasperoLabs/status/2103949832285204582), [2103892568010641563](https://x.com/KasperoLabs/status/2103892568010641563), [2103946939226034614](https://x.com/KasperoLabs/status/2103946939226034614) quoting [@kasperopay 2103946374647873794](https://x.com/kasperopay/status/2103946374647873794); 26 Sep 05:03–20:48): Kaspire was added to Studio and to the KasperoPay widget builder / KasperoConnect. Kaspium is not supported for signing because it has no dApp signing hook; deposits into a covenant from Kaspium work.
- **"Describe to AI" walkthrough** ([2103811612079800547](https://x.com/KasperoLabs/status/2103811612079800547), 26 Sep 11:39): video of an Employer/Employee contract with arbitration, compiled, deployed, funded and released with 2 signatures.
- **Freelancer contract demo** ([2104543100634886578](https://x.com/KasperoLabs/status/2104543100634886578), [2104554999015694827](https://x.com/KasperoLabs/status/2104554999015694827), [2105805703776477569](https://x.com/KasperoLabs/status/2105805703776477569); 28 Sep 12:05 / 12:53, 1 Oct 23:42): pays on a schedule or on milestone delivery, with the delivery notarized on chain, and the client deposits up front. The posts do not state the network.
- **KCC-20 "gas tank" idea** ([2104917837257339059](https://x.com/KasperoLabs/status/2104917837257339059), [2104936671674605775](https://x.com/KasperoLabs/status/2104936671674605775), [2104941680344657993](https://x.com/KasperoLabs/status/2104941680344657993); 29 Sep 12:54–14:29): a small KAS reserve that travels with the token and pays its transfer fees. **Idea only:** a GitHub search of kaspanet/kccs for "gas tank" found 0 hits on 3 Oct, and the account's only kaspanet issue is rusty-kaspa #1140.

## 11 Oct 2026 posts (X, read in the 12 Oct sweep, ~07:45 CEST)

Both are the author's own posts. Each ends with a media link (`t.co`) that was not opened. Neither post gives a txid, a repo, a commit or a program image id, so **nothing here is desk-checked**.

- **ZK covenant on mainnet, claim** ([2109422238277493065](https://x.com/KasperoLabs/status/2109422238277493065), 11 Oct 23:13:47Z): "Opened a Kaspa mainnet covenant with a ZK proof from my own RISC Zero program. The covenant pins the program’s image id; the proof says ‘this melody is in C major’ and never reveals the melody. Same proof with one bit of the public input flipped: rejected by the node." asaefstroem replied in the same conversation ([2109513092463747119](https://x.com/asaefstroem/status/2109513092463747119), 12 Oct 05:14:48Z): "Cool that you like it!" That reply answers a KasperoLabs post in the thread (2109422940911468746) that this sweep did not read.
- **KCC-20 launchpad with a miner covenant, announcement** ([2109291008584540535](https://x.com/KasperoLabs/status/2109291008584540535), 11 Oct 14:32:19Z): "KCC-20 launchpad with a built-in miner covenant. Pays Kaspa miners on an emission schedule, and you can pledge above the minimum to show your token backs the network from day one. The pledge is in the genesis itself: no metadata, nothing to fake." and, as a separate paragraph, "Opens when KCC-20 goes final." Not live: KCC-20 is still Last Call, not Final. elldeeone replied ([2109483421944963099](https://x.com/elldeeone/status/2109483421944963099), 12 Oct 03:16:54Z): "love the idea, this is seriously cool"
- **MinerDrip draft** ([`MineDrip.md` at `b767e346`](https://github.com/kasperolabs/silverscript-studio/blob/b767e3461cd869ccb178e7d097ff4dabc2c96434/MineDrip.md), commit 11 Oct 19:38:04Z, "Added MineDrip.md", 198 lines, MIT): the convention behind the launchpad post. Per the file, a launch fee goes into a keyless covenant created in the token's genesis transaction that pays Kaspa miners on a halving schedule as transaction fees; it carries the KCC-20 covenant ID in its script; SilverScript (silverc v1, kaspanet/silverscript 1.0.0). The file says it is "Proven on Kaspa mainnet" and lists four transactions (claims 4a3b35ba…, b45b339a…, reveal b33fb379…, claim c1d8710e…). Desk read 12 Oct 06:03:18Z–06:03:19Z (server `Date`): [api.kaspa.org](https://api.kaspa.org) returns all four as `is_accepted` true, block times 10 Oct 15:27:57Z, 15:29:34Z, 11 Oct 13:06:06Z, 13:16:19Z. That is a public indexer read, not a node check; the scripts, the refusal cases and the schedule were not desk-checked.

## Limits

- Third-party. Not desk-tested: no Studio covenant, deposit or withdrawal was run here, on mainnet or Testnet 10.
- The Studio's AI writes contract code. **Review it before locking real KAS.**
- "Live on mainnet" is the author's claim.

## Provenance

- These items were on the master's *Third-party 26 Sep* row and its master.json entry *Third-party claims 26 Sep* (text before [`b567a48`](https://github.com/STP-KAS/kaspa-master-file/commit/b567a4898dfd485bd91cb5204d864465c806384b)).
- Moved out of the master on stp's instruction (4 Oct 19:01 CEST) by `b567a48` on `master/community-move-2026-10-04`. The master keeps the rusty-kaspa #1140 line.
- No star, fork, issue, comment or PR on kasperolabs repos.

## 12–13 Oct 2026 (X, read in the 13 Oct sweep)

- **L1 bridge to Ethereum, claim** ([2109766022790066442](https://x.com/KasperoLabs/status/2109766022790066442), 12 Oct 21:59:52Z): "Kaspa is about to get a L1 bridge to Ethereum with no signers, approvers or admins anywhere in the path. Already proven on mainnet with a test token: deposit an ERC-20 into an Ethereum vault, mint a KCC-20 on Kaspa from a ZK proof of Ethereum’s own consensus." **Author's claim:** no txid, image id, vault address or repo in the post; not desk-checked. asaefstroem replies in-thread (13 Oct): GHOSTDAG in Solidity or a ZK program verified on Ethereum is the hard part ([2109856156055437458](https://x.com/asaefstroem/status/2109856156055437458)); "the impl of ghostdag in rk is not really zk optimized" ([2109859288718172454](https://x.com/asaefstroem/status/2109859288718172454)); "Unfortunately, that is the easy part. :)" ([2109849344400666805](https://x.com/asaefstroem/status/2109849344400666805)). Third-party / talk; not a master pin.
- **14 Oct:** the repo for that claim is now public. [kasperolabs/kozmic-bridge](entries/kozmic-bridge.md) tip [`1f18c7eb`](https://github.com/kasperolabs/kozmic-bridge/commit/1f18c7eb832f7e754f4a37ea9780ffe42ae666c5) (13 Oct 23:56:26Z). The 12 Oct post still had no txid. The new page records the author's deposit #3 ids. Not desk-checked. Studio tip `e27a7c4e` is a different repo.

## 29 to 30 Oct 2026: kaspa-redteam (GitHub and X read 30 Oct ~08:15 CET)

**Caveat: third-party, not audited, not desk-checked, not built here; the author's own words.**

- [@KasperoLabs 2115900996316725748](https://x.com/KasperoLabs/status/2115900996316725748) (29 Oct 20:18:03Z): "I made kaspa-redteam, a tool for builders: drop a .sil, it attacks every spend path it can reach with known exploits and reports what Kaspa consensus let through."
- Source [kasperolabs/kaspa-redteam](https://github.com/kasperolabs/kaspa-redteam): MIT, not a fork, created 29 Oct 15:26:49Z, main tip [`01590e62`](https://github.com/kasperolabs/kaspa-redteam/commit/01590e628b96df2186c979aa6a2f9d4f2035b7c4) (30 Oct 02:19:31Z), 0 tags. Its README: "Every hostile transaction is signed for real and judged by rusty-kaspa's own consensus validator." and "A finding is reported only when consensus **accepted** a transaction the attack expected it to reject". It names a browser version at redteam.kasperolabs.com (not opened here). Install is `cargo install --git`, which this desk does not run.

## 30 Oct 2026: kaspa-redteam v0.4.0 to v0.14.2 (GitHub read 31 Oct ~08:00 CET)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- [kasperolabs/kaspa-redteam](https://github.com/kasperolabs/kaspa-redteam) main got 31 commits on 30 Oct (07:42:24Z to 23:43:59Z), their messages numbered v0.4.0 ("projects, several contracts tested as one program") to v0.14.2 ([`5b2eb5a5`](https://github.com/kasperolabs/kaspa-redteam/commit/5b2eb5a5d7f9cf3adb2090f8301854bf3b862ae9), "optional usage log for the web page"); v0.11.0 ([`9239f33d`](https://github.com/kasperolabs/kaspa-redteam/commit/9239f33d)) is "KCC-20 borrowed receive attacks; sorted attack list; honest verdicts". Still 0 git tags. Author's post [@KasperoLabs 2116119876720803840](https://x.com/KasperoLabs/status/2116119876720803840) (30 Oct 10:47:48Z): "got some great user feedback, and already implementing it. Multi-file projects, fill in your own args ... zk proofs, more human readable explanations about the findings, and advice on how to fix it." Not run here.
