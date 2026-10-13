# KRC-20 incident detail (20 Sep)

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-13 (go-krc20d release section, API 13 Oct 06:04:29Z); the 20 Sep moved text was last read 2026-09-23.

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** One history line: 20 Sep, off-chain Kasplex KRC-20 indexer signature bypass, not Kaspa L1 (third-party report).

## What

Detail of the 20 Sep KRC-20 incident as relayed by Recon: Kasplex KRC-20 indexer signature bypass; no exploit in ZealousSwap or Igra; ZealousSwap trading back on Igra L2, KRC-20 bridge routes closed (23 Sep). Third-party reports. The master keeps one line: off-chain indexer bypass, not L1.

## Moved text (verbatim)

### README Now row "KRC-20 incident" (full original text; one history line stays)

**Not an L1 exploit.** 20 Sep: the ZealousSwap post-mortem, as relayed by Recon [2101642546803863779](https://x.com/ReconProtocol/status/2101642546803863779), traces it to a signature bypass in the off-chain Kasplex KRC-20 indexer, with no exploit in ZealousSwap, Igra, or Kaspa L1. KRC-20 token state is interpreted by indexers, not by L1 consensus. Per ReconProtocol post [2102789086125658294](https://x.com/ReconProtocol/status/2102789086125658294) (23 Sep; X not re-read on 2 Oct), ZealousSwap trading is back on Igra L2 and the KRC-20 bridge routes stay closed. Third-party reports. The desk did not read the post-mortem itself.

### master.json now row "KRC-20 incident" (full original note)

20 Sep. Recon relays the ZealousSwap post-mortem: root cause a signature bypass in the off-chain Kasplex KRC-20 indexer; no exploit in ZealousSwap, Igra, or Kaspa L1. KRC-20 token state is interpreted by indexers, not L1 consensus. Per ReconProtocol post https://x.com/ReconProtocol/status/2102789086125658294 (23 Sep; X not re-read 2 Oct): ZealousSwap trading back on Igra L2, KRC-20 bridge routes closed. Third-party reports; the desk did not read the post-mortem itself.

## Fix release: kasplex/go-krc20d krc20d-3.01.260930 (added 13 Oct 2026)

Moved from the kaspa-master-file Build branch `build/2026-10-13` at `f0c55f0` (README.md L73, the paragraph Build appended to the "KRC-20 incident" row), on kaspa master challenge's request; the master keeps only its one history line. Text copied verbatim, not merged or cherry-picked.

**Fix release (primary source, GitHub):** [kasplex/go-krc20d](https://github.com/kasplex/go-krc20d) release [krc20d-3.01.260930](https://github.com/kasplex/go-krc20d/releases/tag/krc20d-3.01.260930), "Fixed a vulnerability in the script parser", published 3 Oct 02:41:33Z (04:41 CEST). Its tag points at [`ba3ab6f3`](https://github.com/kasplex/go-krc20d/commit/ba3ab6f36d3f99ce4d29f0839bca1538acfb85b7) ("script paser fix", 3 Oct 02:29:15Z). That commit sets `Version = "3.01.260930"` and `HfDaaScoreScriptParserFix = 97539090` ([`config/load.go` L19–L21](https://github.com/kasplex/go-krc20d/blob/ba3ab6f36d3f99ce4d29f0839bca1538acfb85b7/config/load.go#L19-L21)). In `explorer/script.go` it adds an OP_NOT (`0x91`) check on redeem scripts that logs a warning ([L57–L116](https://github.com/kasplex/go-krc20d/blob/ba3ab6f36d3f99ce4d29f0839bca1538acfb85b7/explorer/script.go#L57-L116)), and a new P2SH input parse used from that DAA score on ([L768](https://github.com/kasplex/go-krc20d/blob/ba3ab6f36d3f99ce4d29f0839bca1538acfb85b7/explorer/script.go#L768), [L845](https://github.com/kasplex/go-krc20d/blob/ba3ab6f36d3f99ce4d29f0839bca1538acfb85b7/explorer/script.go#L845)). A later commit [`a9754ffd`](https://github.com/kasplex/go-krc20d/commit/a9754ffd976254263d8e5bdc9ce166691c0dabb5) ("bugfix", 12 Oct 10:24:17Z) bumps the version to 3.01.261012; no release for it (API 13 Oct 06:04:29Z). Kasplex's X timeline (API pause, state revert, API restored) and the recovery status are not verified here (no X reads). Desk read of the repo; indexer not run.

Third-party indexer; desk read of the repo; indexer not run; not desk-tested.

## Sources (every link in the moved text)

- https://x.com/ReconProtocol/status/2101642546803863779
- https://x.com/ReconProtocol/status/2102789086125658294
- https://github.com/kasplex/go-krc20d
- https://github.com/kasplex/go-krc20d/blob/ba3ab6f36d3f99ce4d29f0839bca1538acfb85b7/config/load.go#L19-L21
- https://github.com/kasplex/go-krc20d/blob/ba3ab6f36d3f99ce4d29f0839bca1538acfb85b7/explorer/script.go#L57-L116
- https://github.com/kasplex/go-krc20d/blob/ba3ab6f36d3f99ce4d29f0839bca1538acfb85b7/explorer/script.go#L768
- https://github.com/kasplex/go-krc20d/blob/ba3ab6f36d3f99ce4d29f0839bca1538acfb85b7/explorer/script.go#L845
- https://github.com/kasplex/go-krc20d/commit/a9754ffd976254263d8e5bdc9ce166691c0dabb5
- https://github.com/kasplex/go-krc20d/commit/ba3ab6f36d3f99ce4d29f0839bca1538acfb85b7
- https://github.com/kasplex/go-krc20d/releases/tag/krc20d-3.01.260930
