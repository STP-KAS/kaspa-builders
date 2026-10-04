# Kaspa-World-Eater/quorum (KCC-3/4/5 reference)

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-09-22 (the latest dated read in the moved text).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** kccs#29 status (README row "KCC-3/4/5", master.json "kccs#29 KCC-3/4/5"), with a one-line pointer here.

## What

Reference repo for draft kccs#29 (KCC-3 Reputation Deed, KCC-4 Slashable Bond, KCC-5 Deed Identity Registry), a verified-compute experiment on the kaspa-x402 rail. 21 tests stay off chain; the chain is one injected SlashSubmitter, proven once on TN10 (api-tn10 data). "Audit" is the author's own pass. The kccs#29 status stays in the master.

## Moved text (verbatim)

### master.json now row "Kaspa-World-Eater/quorum" (whole row; url https://github.com/Kaspa-World-Eater/quorum; chip tn10)

Verified-compute experiment on the kaspa-x402 rail. Tip 4e87c6b (22 Sep 11:33Z). As of that tip the Status section and the bond section still agree with faa1a31: 21 tests do not touch the chain; the chain is one injected SlashSubmitter, proven once on TN10. Each linked transaction is archived under docs/proofs, because the public TN10 index kept about six days when measured on 22 Sep. npm test fails if a linked id has no file or was cut short. Full txid 81c3008f1fe5d79508105ada9b0760f4de52651de8b38a5039f549aeffaf172d, accepted at blue score 565268486. The forum links kaspahttp402/quorum redirect here, and docs/kcc-reputation-deed.md, kcc-slashable-bond.md, and kcc-identity-registry.md are in the tree. Honest limits remain: public deterministic audit sample; agreement is not a proof. Not an adopted KCC. Not a third-party audit. Not mainnet.

### README Now row "KCC-3/4/5" (moved part; kccs#29 status stays in the master)

Reference: [Kaspa-World-Eater/quorum](https://github.com/Kaspa-World-Eater/quorum), tip [4e87c6b](https://github.com/Kaspa-World-Eater/quorum/commit/4e87c6b3ab40) (22 Sep). Its 21 tests stay off chain. The chain is one injected `SlashSubmitter`, proven once on TN10 in `81c3008f1fe5d79508105ada9b0760f4de52651de8b38a5039f549aeffaf172d`. “Audit” is the author’s own pass.

### master.json now row "kccs#29 KCC-3/4/5" (moved part)

21 Sep the quorum README contradicted itself. Author fixed both leftovers in quorum@faa1a31 (comment 5768054535): 21 tests stay chain-free; the chain is one injected SlashSubmitter, proven once. Tip 4e87c6b (22 Sep 11:33Z) archives each linked transaction under docs/proofs. The public TN10 index kept about six days when measured on 22 Sep. npm test fails if a linked id has no file or was cut short. The status section still says the same thing. Full txid 81c3008f1fe5d79508105ada9b0760f4de52651de8b38a5039f549aeffaf172d. api-tn10 accepted it, blue score 565268486, 1 KAS in, 0.99 KAS out. Audit means the author's own pass.

## Sources (every link in the moved text)

- https://github.com/Kaspa-World-Eater/quorum
- https://github.com/Kaspa-World-Eater/quorum/commit/4e87c6b3ab40
