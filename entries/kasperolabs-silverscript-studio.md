# KasperoLabs: SilverScript Studio

**Chip:** `catalog`. Third-party builder. **Not desk-tested. AI contract code needs review before real KAS.**
**Last checked:** 4 Oct 2026 ~19:05 CEST (repo, issue and demo page GETs). The X items come from the 3 Oct backfill (read ~19:20 CEST).

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

## Limits

- Third-party. Not desk-tested: no Studio covenant, deposit or withdrawal was run here, on mainnet or Testnet 10.
- The Studio's AI writes contract code. **Review it before locking real KAS.**
- "Live on mainnet" is the author's claim.

## Provenance

- These items were on the master's *Third-party 26 Sep* row and its master.json entry *Third-party claims 26 Sep* (text before [`b567a48`](https://github.com/STP-KAS/kaspa-master-file/commit/b567a4898dfd485bd91cb5204d864465c806384b)).
- Moved out of the master on stp's instruction (4 Oct 19:01 CEST) by `b567a48` on `master/community-move-2026-10-04`. The master keeps the rusty-kaspa #1140 line.
- No star, fork, issue, comment or PR on kasperolabs repos.
