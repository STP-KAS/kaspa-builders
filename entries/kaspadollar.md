# KaspaDollar (announced stablecoin initiative)

**Chip:** `claim`. Third-party initiative. **Not Kaspa core. Not a KIP. Not a KCC. Not an endorsement.**
**Last checked:** 2026-11-05 (X and public site reads).

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

## Limits and sources

No public code repository or deployed KaspaDollar covenant was found in this sweep. The site and answers are project statements, not desk tests. No price or investment judgement.

Sources: the linked X posts and public pages above; raw public reads retained in the watch desk's 5 Nov raw directory.
