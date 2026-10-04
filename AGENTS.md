# AGENTS: kaspa-builders

Rules for bots and agents working in this repo. Humans: the same rules apply.

## Scope

- The split follows the master's rule (AGENTS.md of [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file), section "What belongs in the master (since 4 Oct 2026)").
- This repo holds: third-party wallets, indexers, name services, apps, pools, payment rails, research repos and essays; products built with kaspanet crates or SilverScript (name services, indexers, swap channels, payment rails, DNS seeders), even when a core contributor writes them; community X accounts; a core contributor's side projects that do not build on kaspanet code; stp's own apps and experiments (1984, KUSDT, AgenC); and desk tests of third-party projects, which go on that project's entry.
- The master keeps kaspanet repos and their PRs, issues and releases; KIPs and KCCs, plus a reference implementation that a KIP or KCC merged on main names in a status gate or waits on; core contributors' statements about kaspanet code or the protocol and their own repos that extend kaspanet code itself (kdapp, vprog-tictactoe, kaspa-xmss, Argent); credible source lists; network history; and stp's desk results on kaspanet code, KIPs or KCCs.
- Technical reasoning from a project here that explains Kaspa itself (protocol, consensus, covenants, SilverScript, KIP/KCC behaviour) also stays in the master as a short sourced line with a pointer to this repo. Each entry says what the master keeps ("The master keeps:").
- If an entry turns into a kaspanet object (a merged KIP, a kaspanet PR or release), the master gets the kaspanet part, and this repo keeps a pointer. Nothing leaves the master without landing here.

## Sourcing

- **A source on every claim.** Use pinned commit shas (not branch names), X post ids, tx ids and block hashes, or file and line at a pinned sha.
- Label an author's own statement as a claim. Write "desk-checked" only when the desk ran the check itself (own node, own build), and say how and when.
- Leave out third-party claims that have no public code, repo or tx id, or mark them `claim`.
- **No price talk**: no prices, targets, buy calls or market commentary.
- Times: UTC with `Z`, or CEST when labelled.

## Privacy and leaks

- No home paths, local usernames, box-local paths or private repo names.
- No personal e-mail addresses, even when a source repo's commit metadata shows one.
- Commit only as `STP-KAS <227352643+STP-KAS@users.noreply.github.com>`.

## Other people's repos

- **No public reactions:** no stars, forks, watches, issues, comments, reviews or PRs on repos you write about. Read-only clones and GETs only.

## Files

- `README.md`: purpose, rules, and the index table (entry | what | status chip | key sources | last checked).
- `entries/<slug>.md`: one page per person or project. Slugs use handles or project names, never display names.
- `builders.json`: a machine copy of the index. Fields per entry: `name`, `url`, `page` (the entry's path, `entries/<slug>.md`), `chip`, `note`, `sources`, `checked`. Valid UTF-8, indent 2, `ensure_ascii=False` (no `\u` escapes), trailing newline. Keep it in sync with the README table.
- `people.md` / `people.json`: community X accounts, chip `community`. Fields per entry: `name`, `url`, `chip`, `note`, `sources`, `checked` (null when the master gave no date), `moved_from`.
- `do-not-weld.md`: third-party claims not to weld together.
- `docs/`: desk notes that moved with an entry, linked from that entry.
- `SNAPSHOT-HISTORY.md`: one row per change, **newest first**.

## Branches and merges

- Branch prefixes: `master/` (kaspa master bot), `build/` (build passes), `challenge/` (kaspa master challenge notes).
- **Only kaspa master bot merges to `main`**, and only after stp's OK and a kaspa master challenge pass with 0 FAILED.
- Use normal merges: no force-push and no history rewrite on `main`.
- No tags and no releases unless stp asks for them.
