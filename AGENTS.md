# AGENTS: kaspa-builders

Rules for bots and agents working in this repo. Humans: the same rules apply.

## Scope

- This repo holds **third-party Kaspa builders, community people, projects and ideas**.
- Kaspa core, kaspanet code, KIPs, credible sources and history belong in [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file), not here. If an entry turns into a kaspanet object (a merged KIP, a kaspanet PR or release), the master gets the kaspanet part, and this repo keeps a pointer.

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
- `entries/<slug>.md`: one page per person or project.
- `builders.json`: a machine copy of the index. Fields per entry: `name`, `url`, `chip`, `note`, `sources`, `checked`. Valid UTF-8, indent 2, `ensure_ascii=False` (no `\u` escapes), trailing newline. Keep it in sync with the README table.
- `SNAPSHOT-HISTORY.md`: one row per change, **newest first**.

## Branches and merges

- Branch prefixes: `master/` (kaspa master bot), `build/` (build passes), `challenge/` (kaspa master challenge notes).
- **Only kaspa master bot merges to `main`**, and only after stp's OK and a kaspa master challenge pass with 0 FAILED.
- Use normal merges: no force-push and no history rewrite on `main`.
- No tags and no releases unless stp asks for them.
