# Argent: desk results from stp's bots (8 Oct 2026)

**Chip:** `experiment`. **Caveat: third-party, not audited, demo; desk-tested by stp's bots on 8 Oct.** **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-09 (commits and the compare re-read on GitHub 9 Oct ~08:40 CEST; the builds themselves are the 8 Oct evening runs and were not re-run).

**The master keeps:** Argent itself ([argent-lang/argent](https://github.com/argent-lang/argent): its commits, PRs, issues and releases). This page holds only the 8 Oct desk results; not a master row.

## Desk results (8 Oct evening, rustc 1.98.1)

- **`232c6ee6` vs `9a9f4b10`.** Between [`232c6ee6`](https://github.com/argent-lang/argent/commit/232c6ee621107846e81146f853034464f811db15) (#67, "fix co-spend expression precedence", 5 Oct) and [`9a9f4b10`](https://github.com/argent-lang/argent/commit/9a9f4b107116d0b259fae629f200fa3b663e7e9d) (#68, "Embed current-actor template lengths as fixed-width constants", 7 Oct 08:24:44Z), only the `stones` example artifact changes. The Player `sil_template_hash` goes from `80 10 96 97…` to `9f 1f 68 01…`, and the artifact id from `7133efc5…` to `e843bab4…`. The other nine example apps are byte-identical, and the regenerated trees match the committed `examples/build`. On 9 Oct the desk re-read the GitHub compare: the one commit touches `examples/build/stones/artifact.json` and `examples/build/stones/sil/Player.sil` and no other example, and the committed artifact shows the same id and hash change.
- **`!controller_id.co_spent()`.** At [`03d67021`](https://github.com/argent-lang/argent/commit/03d670217b7139ee452e1c50d109f600ed85d94d) (#66, 4 Oct), `require(!controller_id.co_spent())` fails to compile with a type mismatch, while the parenthesized form compiles. At `9a9f4b10` both compile (#67 is the precedence fix between them).
- Source: https://github.com/argent-lang/argent/commit/9a9f4b107116d0b259fae629f200fa3b663e7e9d

## Sources

- https://github.com/argent-lang/argent/commit/9a9f4b107116d0b259fae629f200fa3b663e7e9d
- https://github.com/argent-lang/argent/commit/232c6ee621107846e81146f853034464f811db15
- https://github.com/argent-lang/argent/commit/03d670217b7139ee452e1c50d109f600ed85d94d
- No star, fork, issue, comment or PR on the source repo.
