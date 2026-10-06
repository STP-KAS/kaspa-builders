# Third-party node tools (26 Sep)

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-06 (Magma / Lava Kaspa spec only; KasNodes 5 Oct; the 26 Sep items were not re-read).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** rusty-kaspa #1140 and saefstroem's pool-concentration post (row renamed "26–30 Sep notes").

## What

supertypo/simply-kaspa-dnsseeder v0.9.6 (dead nodes kept alive by gossip alone; not kaspanet/dnsseeder) and getumbrel/umbrel-apps#6120 (Umbrel rusty-kaspad app to v2.1.0, open). Not kaspanet objects.

## Moved text (verbatim)

### README Now row "Third-party 26 Sep" (moved part)

[supertypo/simply-kaspa-dnsseeder v0.9.6](https://github.com/supertypo/simply-kaspa-dnsseeder/releases/tag/v0.9.6) (25 Sep 07:03Z): dead nodes were kept alive by gossip alone. Not kaspanet/dnsseeder. [getumbrel/umbrel-apps#6120](https://github.com/getumbrel/umbrel-apps/pull/6120) (elldeeone, 26 Sep 09:35Z) updates the Umbrel rusty-kaspad app to v2.1.0. Open. Not a kaspanet object.

### master.json now row "Third-party claims 26 Sep" (moved part)

supertypo/simply-kaspa-dnsseeder v0.9.6 (25 Sep 07:03Z): dead nodes were kept alive by gossip alone; not kaspanet/dnsseeder (https://github.com/supertypo/simply-kaspa-dnsseeder/releases/tag/v0.9.6). getumbrel/umbrel-apps#6120 (elldeeone, 26 Sep 09:35Z) updates the Umbrel rusty-kaspad app to v2.1.0, open (https://github.com/getumbrel/umbrel-apps/pull/6120).

## 5 Oct 2026 sweep (not desk-checked)

- **KasNodes.** elldeeone [2106703706003808697](https://x.com/elldeeone/status/2106703706003808697) (4 Oct 11:11Z): "https://t.co/XrEyPp2T17 is back" (link resolves to kasnodes.com). [kasnodes.com](https://kasnodes.com/) (read 5 Oct ~07:50 CEST, HTTP 200) titles itself "KasNodes — the Kaspa network, live" and describes itself as a map of every public Kaspa node (where they are, how well they run, who runs them). Its homepage then showed 290 public and 81 private nodes in 40 countries. The site's own counts, not recounted by the desk. Who runs the site is not stated in that read. Third-party crawler; not a kaspanet object.

## 6 Oct 2026 sweep (not desk-checked)

- **Magma / Lava Kaspa spec.** [Magma-Devs/lava-specs#181](https://github.com/Magma-Devs/lava-specs/pull/181) (opened by `magmadevs-bot`, merged 5 Oct 18:15Z as `90bad925`) adds `kaspa.json`, a Lava chain spec with index `KASPA` (mainnet) and `KASPAT` (Testnet 10), over the kaspa-rest-server REST API. The PR's reasons for REST: kaspad gRPC is one bidirectional stream with no unary methods, and wRPC is WebSocket-only and not JSON-RPC 2.0. The PR names its ticket "Add Kaspa spec (Kraken)" and says the ticket asked for mainnet only. vertex [2107194999163027711](https://x.com/KaspaScopio/status/2107194999163027711) (5 Oct 19:43Z) relayed it as Kaspa in Magma's Smart Router; [2107226972396917109](https://x.com/KaspaScopio/status/2107226972396917109) (21:50Z) adds that he does not claim Kraken deploys it, the name is only the ticket's. PR text; the desk did not test the spec or the router. Third-party RPC infrastructure, not a kaspanet object.

## Sources (every link in the moved text)

- https://github.com/supertypo/simply-kaspa-dnsseeder/releases/tag/v0.9.6
- https://github.com/getumbrel/umbrel-apps/pull/6120
