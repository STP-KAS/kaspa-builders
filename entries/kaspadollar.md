# KaspaDollar (announced stablecoin initiative)

**Chip:** `claim`. Third-party initiative. **Not Kaspa core. Not a KIP. Not a KCC. Not an endorsement.**
**Last checked:** 2026-11-14 (X and public site reads).

**The master keeps:** the KaspaDollar current-state row because stp classified it as core on 25 Oct. This entry holds the third-party project detail.

## Original announcement (23–24 Oct 2026)

@KaspaDollar [2113601328975098237](https://x.com/KaspaDollar/status/2113601328975098237) (23 Oct 12:00:00Z): initiative led by core developer @asaefstroem for a decentralized, overcollateralized stablecoin, "with the support of the core team"; fundraiser target 5,000,000 KAS and return of contributions if the target is not reached by 1 January 2027.

- asaefstroem [2113842818326392875](https://x.com/asaefstroem/status/2113842818326392875): existing rust and DagKnight funds already allocated; community dev fund too small.
- michaelsutton [2114040191719444646](https://x.com/michaelsuttonil/status/2114040191719444646): "i’ll do everything in my power on the technical side to help this initiative move forward".
- asaefstroem [2113970020598632570](https://x.com/asaefstroem/status/2113970020598632570): "Covenants will issue it."

## 3–5 Nov 2026: website and preliminary design

@KaspaDollar [2117587606305206610](https://x.com/KaspaDollar/status/2117587606305206610) (3 Nov 12:00:02Z) announced the website update and proposed decentralized oracle using miners and KIP-21 sequencing commitments.

The public [How it works](https://kaspadollar.com/how-it-works) page, read 5 Nov, says all parameters are preliminary and subject to internal review:

- `KSD` is a reference label, not the final ticker.
- Minting or withdrawing requires at least 250% collateral. Below 200%, anyone including the owner may partially liquidate a vault toward 200%. Below 100%, part of its KSD is unbacked.
- Miners can post prices in coinbase payloads using KIP-21 sequence commitments. The proposed window is the last ten minutes and the median of votes; a valid window requires at least 50% of blocks to carry a vote.
- Anyone can post a price update with a ZK proof of the window votes and median. The page says the proof provider receives a small fee paid by liquidators.
- If no valid price is posted for 30 minutes, minting, withdrawing, liquidating and redeeming stop. Adding KAS, repaying and closing continue.
- The mint price rises by at most 10%/hour; the liquidation price falls by at most 25%/hour.

The [whitepaper page](https://kaspadollar.com/whitepaper) says **"Publishing on 8 November 2026"**; the whitepaper is not yet published.

The [roadmap/funding page](https://kaspadollar.com/docs) publishes fundraising address `kaspa:qpy0rvs9mkfa66vnhre4dwsc4c0nu8jhvk0jlfzvq7x8pejjezpujpyrwecl6`, target 5,000,000 KAS and close 1 January 2027. It states refund terms and also says no guarantees can be made and contributors accept the risk of losing the contribution in full. Testnet in May, audit in June–August and mainnet in September are future roadmap entries, not deployments.

## Attributed design answers (4–5 Nov)

- asaefstroem [2117912744426914091](https://x.com/asaefstroem/status/2117912744426914091): the ten-minute median is preliminary; roughly five minutes plus proving, roughly ten-minute updates.
- [2118285824022503531](https://x.com/asaefstroem/status/2118285824022503531): acknowledges insufficient backing if liquidators do not act; stress tests planned.
- [2118291388249096310](https://x.com/asaefstroem/status/2118291388249096310): a liquidator can mint KSD against its own KAS, liquidate and close the loan.
- [2117609455743627318](https://x.com/asaefstroem/status/2117609455743627318): proposed hashrate gate before covenant activation; percentage unspecified.

## 8 Nov 2026: whitepaper published (site read 9 Nov ~07:41 CET; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- @KaspaDollar [2119399540528726296](https://x.com/KaspaDollar/status/2119399540528726296) (8 Nov 12:00:01Z): "KaspaDollar whitepaper is now live! ... a working document that is subject to both internal and external review"; the post says there is no planned revenue or developer fee and that deployed contracts will have no admin key.
- [Whitepaper](https://kaspadollar.com/whitepaper) (HTTP 200): "KSD: A Dollar Token on Kaspa L1 Backed by KAS and Its Miners", author Alexander Säfström; "a working document that awaits peer review", "updated in place". Two components: covenant contracts and a decentralized miner oracle (DMO). Votes are 13 bytes in the coinbase payload, committed by KIP-21, read with `OpChainblockSeqCommit`, aggregated in a ZK proof checked with KIP-16 `OpZkPrecompile`. Parameter table: open ratio 250%, liquidation threshold 200%, penalty 5%, window 6,000 blocks, vote threshold 50%, launch gate 90% for 30 days, freeze 30 min, settlement 30 days, unbacked-issuance limit 50,000/day, reward tolerance 2%, oracle fee 0.1% (floor 1 KAS), 8 replicas, min debt 10 KSD. `/whitepaper.pdf` HTTP 404.
- [Design page](https://kaspadollar.com/how-it-works) changes since 8 Nov: window "the last 6,000 blocks, about ten minutes"; every priced action pays 0.1% of its dollar value in KAS (floor 1 KAS) to miners within 2% of the median, update posters and keepers; launch needs 90% of blocks carrying a vote, without a gap, for 30 days; all parameters still preliminary.
- Home page funding counter 569,040 of 5,000,000 KAS (11.3%) at the 9 Nov read (552,684, 11%, on 8 Nov).
- No public code repository or deployed KSD covenant was found. Kaspire 0.11.99 notes name a separate KaspaRocket "KDOLLAR" pool whose treasury leg uses the KaspaDollar donation recipient (see [wallets-kcc20](wallets-kcc20.md)); that is Kaspire's statement, not a KSD deployment.

## 9 to 10 Nov 2026: whitepaper unchanged; funding counter; oracle replies (site read 10 Nov ~07:47 CET; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- [Whitepaper](https://kaspadollar.com/whitepaper), [design page](https://kaspadollar.com/how-it-works) and [roadmap/funding](https://kaspadollar.com/docs) HTML bodies are byte-identical to the 9 Nov read. `/whitepaper.pdf` still HTTP 404.
- Home page funding counter 585,005 of 5,000,000 KAS (11.7%) at the 10 Nov read (569,040, 11.3%, on 9 Nov).
- asaefstroem [2119800173719429439](https://x.com/asaefstroem/status/2119800173719429439) (9 Nov 14:32:00Z): the SDK will include a small stratum proxy next to the ASIC (ASIC ↔ proxy ↔ pool); the pool builds a template variant per submitted price (extra data = base | KVOT | version | p) and recomputes the merkle root; the proxy alerts on a mismatch between expected vote, job id and the block on chain. Core-dev replies (Sutton on miner attestation oracles and a shared proving service) are in the master KaspaDollar cell.

## 10 to 11 Nov 2026: funding counter; opening-ratio and prover replies (site read 11 Nov 07:41 CET, server Date 06:41:35Z; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- [Whitepaper](https://kaspadollar.com/whitepaper), [design page](https://kaspadollar.com/how-it-works) and [roadmap/funding](https://kaspadollar.com/docs) HTML bodies are byte-identical to the 10 Nov read. `/whitepaper.pdf` still HTTP 404.
- Home page funding counter 592,963 of 5,000,000 KAS (11.8%) at the 11 Nov read (585,005, 11.7%, on 10 Nov).
- asaefstroem [2120198588538200413](https://x.com/asaefstroem/status/2120198588538200413) (10 Nov 16:55:09Z): "the 250% ratio is the opening ratio, i.e. the minimum ratio required to open a position. Nothing prevents you from keeping it at 900% by depositing extra collateral." [2120132962075148459](https://x.com/asaefstroem/status/2120132962075148459): "The GPU here is for solving zk proofs which gives you reward in KAS."; [2120142312688730129](https://x.com/asaefstroem/status/2120142312688730129): 6600 XT cards "wont run on cuda backend since theyre amd"; he would write an AMD port "only if there is sufficient interest". Sutton's 10 Nov aggregation reply is in the master KaspaDollar cell.

## 11 to 12 Nov 2026: funding counter; legal-status post (site read 12 Nov 07:40 CET, server Date 06:40:26Z; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- [Whitepaper](https://kaspadollar.com/whitepaper), [design page](https://kaspadollar.com/how-it-works) and [roadmap/funding](https://kaspadollar.com/docs) HTML bodies are byte-identical to the 11 Nov read. `/whitepaper.pdf` still HTTP 404.
- Home page funding counter 593,357 of 5,000,000 KAS (11.8% as shown on the page) at the 12 Nov read (592,963, 11.8%, on 11 Nov).
- asaefstroem [2120545083984584789](https://x.com/asaefstroem/status/2120545083984584789) (11 Nov 15:52:00Z), a reply that cites the GENIUS Act (Pub. L. 119-27 §2(22)(A), §3(a), §3(b), §14), 18 U.S.C. §§471–474 and §§485–486, FinCEN FIN-2013-G001 and FIN-2019-G001, and a DOJ memo of 7 April 2025, and concludes: "KaspaDollar is no issuer, nobody is obligated to redeem anything and it is not a custodian either thereby the aforementioned laws do not apply." His reading; not legal advice and not checked here.

## 12 to 13 Nov 2026: funding counter (site read 13 Nov 07:47 CET, server Date 06:47:47Z; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- [Whitepaper](https://kaspadollar.com/whitepaper), [design page](https://kaspadollar.com/how-it-works) and [roadmap/funding](https://kaspadollar.com/docs) HTML bodies are byte-identical to the 12 Nov read. `/whitepaper.pdf` still HTTP 404.
- Home page funding counter 596,380 of 5,000,000 KAS (11.9% as shown on the page) at the 13 Nov read (593,357, 11.8%, on 12 Nov).

## 13 to 14 Nov 2026: funding counter (site read 14 Nov 07:48 CET, server Date 06:48:00Z; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- [Whitepaper](https://kaspadollar.com/whitepaper), [design page](https://kaspadollar.com/how-it-works) and [roadmap/funding](https://kaspadollar.com/docs) pages show the same text as the 13 Nov read. `/whitepaper.pdf` still HTTP 404.
- Home page funding counter 627,520 of 5,000,000 KAS (12.5% as shown on the page) at the 14 Nov read (596,380, 11.9%, on 13 Nov). The home page now shows "Recent donations" and "Leaderboard" sections; asaefstroem on X: "Leaderboard and QR code has been added ser!" ([2121268742177128722](https://x.com/asaefstroem/status/2121268742177128722), 13 Nov 15:47:34Z).

## Limits and sources

No public code repository or deployed KaspaDollar covenant was found in this sweep. The site and answers are project statements, not desk tests. No price or investment judgement.

Sources: the linked X posts and public pages above; raw public reads retained in the watch desk's 5 Nov raw directory.
