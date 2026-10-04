# KRC-20 incident detail (20 Sep)

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-09-23 (the latest dated read in the moved text).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** One history line: 20 Sep, off-chain Kasplex KRC-20 indexer signature bypass, not Kaspa L1 (third-party report).

## What

Detail of the 20 Sep KRC-20 incident as relayed by Recon: Kasplex KRC-20 indexer signature bypass; no exploit in ZealousSwap or Igra; ZealousSwap trading back on Igra L2, KRC-20 bridge routes closed (23 Sep). Third-party reports. The master keeps one line: off-chain indexer bypass, not L1.

## Moved text (verbatim)

### README Now row "KRC-20 incident" (full original text; one history line stays)

**Not an L1 exploit.** 20 Sep: the ZealousSwap post-mortem, as relayed by Recon [2101642546803863779](https://x.com/ReconProtocol/status/2101642546803863779), traces it to a signature bypass in the off-chain Kasplex KRC-20 indexer, with no exploit in ZealousSwap, Igra, or Kaspa L1. KRC-20 token state is interpreted by indexers, not by L1 consensus. Per ReconProtocol post [2102789086125658294](https://x.com/ReconProtocol/status/2102789086125658294) (23 Sep; X not re-read on 2 Oct), ZealousSwap trading is back on Igra L2 and the KRC-20 bridge routes stay closed. Third-party reports. The desk did not read the post-mortem itself.

### master.json now row "KRC-20 incident" (full original note)

20 Sep. Recon relays the ZealousSwap post-mortem: root cause a signature bypass in the off-chain Kasplex KRC-20 indexer; no exploit in ZealousSwap, Igra, or Kaspa L1. KRC-20 token state is interpreted by indexers, not L1 consensus. Per ReconProtocol post https://x.com/ReconProtocol/status/2102789086125658294 (23 Sep; X not re-read 2 Oct): ZealousSwap trading back on Igra L2, KRC-20 bridge routes closed. Third-party reports; the desk did not read the post-mortem itself.

## Sources (every link in the moved text)

- https://x.com/ReconProtocol/status/2101642546803863779
- https://x.com/ReconProtocol/status/2102789086125658294
