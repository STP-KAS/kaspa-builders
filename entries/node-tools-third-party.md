# Third-party node tools (26 Sep)

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-08 (lava-specs#181 merge time only; Magma / Lava spec 6 Oct; KasNodes 5 Oct; the 26 Sep items were not re-read).

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

## 2 Nov 2026: aspectron/khost #5 covenant index flag (GitHub read 2 Nov ~19:25 CET)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- IzioDev opened [aspectron/khost#5](https://github.com/aspectron/khost/pull/5) "feat(p2p): add covenant index arg to systemd" (2 Nov 15:34Z, head `4a373bb9`, 1 file, +1/−0, open). Body: "to be merged after RK is released with the covenant index feature (https://github.com/kaspanet/rusty-kaspa/pull/1152)"; "it will enable the covenant index on the freshly created systemd services"; existing operators then update khost, rebuild configuration and restart all services.

## 9 Nov 2026: elldeeone's hole-punching branch, named by rusty-kaspa #1165 (Core R&D Telegram export read 9 Nov ~21:30 CET)

**Caveat: third-party, not audited, not desk-checked; the authors' own words.**

- Kaspa Core R&D Telegram ([15610](https://t.me/kasparnd/15610), 6 Aug 2026 02:52Z): "automatic TCP hole punching between private/NATed nodes is now working (on devnet)"; the post calls branch `rk-with-tcp` of [elldeeone/rusty-kaspa](https://github.com/elldeeone/rusty-kaspa) "my public branch" and asks for mainnet testers. That branch tip is [`09fc0ba5`](https://github.com/elldeeone/rusty-kaspa/commit/09fc0ba5c03f5c4a1c3b981be50f1e10606024c8) (25 Aug 02:44:45Z, "fix(libp2p): allow DCUtR after private probe"; GitHub read 9 Nov). Fork branch, no pull on kaspanet/rusty-kaspa.
- Ori Newman ([16463](https://t.me/kasparnd/16463), 9 Nov 18:02Z) says his [rusty-kaspa#1165](https://github.com/kaspanet/rusty-kaspa/pull/1165) "Support hole punching via LibP2p" is "Inspired by @elldeeone's implementation" and uses UDP hole punching instead.
- The master keeps: #1165 (kaspanet pull) in its "P2P hole punching" row.
