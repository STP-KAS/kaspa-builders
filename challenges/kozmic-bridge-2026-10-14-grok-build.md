# Challenge: build/kozmic-bridge-2026-10-14

- **Reviewed commit:** `9c651df`. The page commit under it is `18bcd74da76d9272fedd394eea9df1a118598a23`. Parent of that page commit is main `ade95033c3b8cabba558e45f4901fac7e499f660`.
- **Totals:** 12 HELD · 0 FAILED · 0 UNVERIFIABLE.
- **Verdict:** no open FAILED item. This note is Grok Build's check. It is not the kaspa master challenge bot, so it does not by itself authorize a merge. Main was not moved.
- **Reviewer:** Grok Build, 14 Oct 2026. Reads were the GitHub repo, commit, issue, and pull APIs, `README.md`, `LICENSE`, `vault/src/Vault.sol`, and `bridge/bridge.sil` at `1f18c7eb`, `kcc-0020.md` on kccs main, and post `2110320538308555017`. No compile, no node, no Etherscan, no comment on kasperolabs/kozmic-bridge.

**Key:** E = `entries/kozmic-bridge.md`.

## Repo

- **K1 HELD.** `18bcd74` and `9c651df` are commits by `STP-KAS <227352643+STP-KAS@users.noreply.github.com>`. The page diff is `README.md`, `SNAPSHOT-HISTORY.md`, `builders.json`, `entries/kozmic-bridge.md`, and `entries/kasperolabs-silverscript-studio.md`.
- **K2 HELD.** E L7. Default branch `main`. Created 2026-10-13T01:27:47Z. Tip `1f18c7eb832f7e754f4a37ea9780ffe42ae666c5`, committer date 2026-10-13T23:56:26Z, message "README: drop internal notes". `pushed_at` 2026-10-13T23:56:28Z. Issues list length 0. Pulls list length 0. `LICENSE` begins "MIT License" and names "Oz Steinemtz, Kaspero Labs".
- **K3 HELD.** E L12. The commits API returned 12 commits, all dated 13 Oct. The oldest is `fefbec24b3d4e6a30e677f07dbda89d8d756d6b0` at 2026-10-13T01:29:17Z.
- **K4 HELD.** E L10. The README says "Live on mainnet since 2026-10-12", "Kaspa reads Ethereum; Ethereum cannot read Kaspa yet", and that KBT is a self-minted test ERC-20 with no value and the vault has no withdraw function.

## Code and the author's deposit row

- **K5 HELD.** E L16. The README table names 0.5 KBT at 00:35:23 UTC, Ethereum tx `0x29e6f6a874164b38c556abd32dbcfb3adc262e06238b46bfb8f3ce4107a419b0`, block 26,180,018, and Kaspa tx `568bedc542e6ed51ce6ecbbef0968a730d43b049f95150d37960ca7a86f44aaf` at 00:53:52 UTC. 00:53:52 minus 00:35:23 is 18 minutes 29 seconds. The prose says "Eighteen and a half minutes." The measurements row says "18.5 min measured". Those tx ids were not opened on a node or on Etherscan.
- **K6 HELD.** E L18. The README reproduce comment quotes image id `4756d736d00cc0e5b813fd9bbb8fe586dbfe9cee524e61e79335cc2585413a50` beside `cat IMAGE_IDS.txt`. `IMAGE_IDS.txt` is not in the tree at 1f18c7eb (git tree API, recursive, not truncated; raw builders/kozmic-tree-1f18c7eb.json).
- **K7 HELD.** E L22. `vault/src/Vault.sol` L10 says "There is no owner, no withdraw". L58 is `function deposit(uint64 amount, bytes calldata kaspaSpk)`. L6 `transferFrom` is inside `interface IERC20`. The file was not compiled.
- **K8 HELD.** E L23. `bridge/bridge.sil` L40 is `byte[32] image_id`. L68–L70 are `MAX_DEPOSITS = 4`, `JOURNAL_FIXED_LEN = 230`, `DEPOSIT_LEN = 49`. L128 is `function advance`. L135 is `r0.g16.verify(sha256(journal), proof, image_id)`. The file was not compiled.

## Limits

- **K9 HELD.** E L27. kccs main is `1516a6c4cef59940fc3af3096dbcdd9c08690254` (2026-10-14T13:11:38Z). `kcc-0020.md` on that tip says `Status: Last Call`. The same header at `3fbec524` said `Status: Last Call`.
- **K10 HELD.** E L25 and E L31 and E L37. The README credits a zkSecurity audit to RISC Zero and r0vm-helios. Post `2110320538308555017` is @KaspaScopio at 2026-10-14 10:43:18 GMT and says the poster did not independently verify the Kaspa-side execution. The do-not-weld lines refuse KBT as KCC-20 Final, a two-way bridge, that audit as an audit of Kozmic, the author's tx ids as a desk check, #1074 as this bridge, and studio `e27a7c4e` as this repo.
- **K11 HELD.** `entries/kasperolabs-silverscript-studio.md` L54 points at this page and says the 12 Oct post had no txid. `builders.json` parses. The Kozmic entry chip is `catalog`, checked `2026-10-14`.
- **K12 HELD.** `SNAPSHOT-HISTORY.md` has a newest row for this branch from main `ade9503`. No public reply. No commit on kasperolabs/kozmic-bridge. This challenge commit does not move main.
