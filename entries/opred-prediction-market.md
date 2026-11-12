# OPred prediction market (Manyfest, maxibitcat)

**Chip:** `claim`. An app announced by its authors; no public code read here. **Not Kaspa core. Not a KCC. Not desk-tested. Not an endorsement.**
**Last checked:** 2026-11-12 (X reads and Kas-Smiths topic 57).

**The master keeps:** Sutton's 11 Nov KIP-21 randomness and clock idea from the same discussion (KIPs row). Argent itself is in the master.

## 11 Nov 2026: announcement (X read 12 Nov ~07:42 CET; not desk-checked)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Manyfest [2120491015853551931](https://x.com/manyfest_/status/2120491015853551931) (11 Nov 12:17:09Z): "TLDR- A fully open, decentralized and permissionless prediction market application on Kaspa." He has been "working with @maxibitcat mapping and coding his proposal for a permissionless prediction market into an Argent app". maxibitcat proposed "a voting resolution mechanism that utilizes a lottery to incentivize the losing side of a binary market to vote honestly". "A prediction is held as a tradable, fungible KCC20 token representing the prediction asset, with extended logic to support voting."
- Same post: "There will be no owner and no beneficiary." "The system’s openness and current implementation tie the security of a market to its size. Small-cap markets could be manipulated more easily." "I aim to release a mainnet version around the end of this year."
- Manyfest [2120491109730459717](https://x.com/manyfest_/status/2120491109730459717) links Kas-Smiths [topic 57](https://kas-smiths.org/t/permissionless-covenant-based-prediction-markets-high-level-sketch/57) "Permissionless Covenant-Based Prediction Markets – High-Level Sketch" (opened by forum user bitcat, 10 Jul 2026 16:00:53Z; 9 posts, last 27 Aug).
- Manyfest [2120506350421848372](https://x.com/manyfest_/status/2120506350421848372) (13:18:05Z): "I am thinking calling it OPred, open prediction market".
- maxibitcat [2120525427563241689](https://x.com/maxibitcat/status/2120525427563241689) (reply to asaefstroem asking whether KAS is used for dispute voting): "The main idea was to have token holders vote", with an optimistic resolution "like UMA" that "should make voting unnecessarily in most cases".
- Sutton [2120497332407894432](https://x.com/michaelsuttonil/status/2120497332407894432) (12:42:15Z) names "how naturally a complex app like this, with its distinct market phases, maps onto argent’s actor state machine". His randomness and clock idea for the lottery (KIP-21 sequencing commitments) is in the master KIPs row.

## Limits and sources

- X posts and one forum topic only. No repository, contract address or deployment was found or read. Raw X reads: watch raw `raw/2026-11-12/x/core.json`.
