# DagitUser69

**Chip:** `catalog`. Third-party GitHub account. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-08 (GitHub API and the issue page). The warda parent was not built and its transaction ids were not read on a node.

**The master keeps:** [kaspanet/silverscript#258](https://github.com/kaspanet/silverscript/issues/258). The desk `silverc` check is on [kaspa-master-file `4a466ea`](https://github.com/STP-KAS/kaspa-master-file/commit/4a466ea8bd247dbb96a820bb541317fa635a79a4), branch `build/silverscript-258-2026-10-07`. That branch is not on kaspa-master-file main. An unread constructor parameter is left out of the v1.0.0 script. Copying it into a state field is not a desk run of the job-escrow covenant named in the issue.

## What

GitHub user [DagitUser69](https://github.com/DagitUser69). The profile name field is `amacbuilds`. A user lookup for `amacbuilds` returned 404 on 8 Oct 2026. Account id 24513981, created 2016-12-12T00:44:41Z, profile updated 2026-10-07T13:54:55Z. The public profile has no bio, blog, company, location, email, or X handle, and the orgs list is empty. Two public repositories, both forks. The following list is empty. The followers list is one account, STP-KAS.

## Public GitHubs

### silverscript#258

Opened 2026-10-07T13:57:55Z. Still open on 8 Oct 2026, with no comments. Title: "Unused constructor parameters are silently dropped, so the P2SH address does not commit to them." The body says a constructor parameter that no entry or function reads is omitted from the bytecode, so the P2SH address does not commit to that value. It names compiler master `3ed9733` and says both sample compilations produce `760414559d2487637557579c6951676a68`, with no warning. The master keeps the desk check of that bytecode.

The body says this showed up in a job-escrow covenant: a `byte[32] jobSpec` did not change the escrow address, and the workaround they name is to copy it into contract state (`byte[32] spec = jobSpec`). **Claim.** Neither public repository on this account is that covenant. The warda fork tip is the parent tip, and MagicPlugins is not a covenant.

The body points at silverscript #169 (unused local initializers). #169 is closed (2026-08-03T14:18:09Z). #258 is a different issue and is still open. The master keeps that distinction.

### warda fork

[DagitUser69/warda](https://github.com/DagitUser69/warda) is a fork of [ArtyKOMarkets/warda](https://github.com/ArtyKOMarkets/warda). The fork event is 2026-10-07T19:48:48Z. The fork tip [`7beecde96d34`](https://github.com/DagitUser69/warda/commit/7beecde96d349c282c9822cadb3def2d584f2473) is the parent tip, committed 2026-09-26T14:35:12Z by mystic108. No commit on that tip is by DagitUser69.

The parent README at that commit calls Warda an open protocol for cryptographic economic grants for software agents, with enforcement in a Toccata covenant. It says the project is experimental, unaudited, and has nothing on mainnet, and it names two Testnet-10 transaction ids as an allowlist check. Those sentences are the README's own claims. This pass did not build the repo and did not read those transactions on a node. License MIT. Homepage `https://wardamcp.vercel.app`. The fork is not authorship of Warda.

### Not Kaspa

- [spectre-project/rusty-spectre#13](https://github.com/spectre-project/rusty-spectre/issues/13), opened 2024-08-06T17:09:29Z by this account, still open on 8 Oct 2026. Title: "Thread 'main' panic during wallet sweep." A Spectre CLI wallet. Not Kaspa.
- [DagitUser69/MagicPlugins](https://github.com/DagitUser69/MagicPlugins) is a fork of nhubbard/MagicPlugins. Tip [`dabc5f21`](https://github.com/DagitUser69/MagicPlugins/commit/dabc5f215d97ca935577bf13374906b3992bc70e) is by nhubbard, 2016-05-02T00:14:52Z, message "Create the Snow script." The description says Magic Mirror 2 plugins. Not Kaspa.

## Sources

- https://github.com/DagitUser69
- https://api.github.com/users/DagitUser69
- https://github.com/kaspanet/silverscript/issues/258
- https://github.com/kaspanet/silverscript/issues/169
- https://github.com/STP-KAS/kaspa-master-file/commit/4a466ea8bd247dbb96a820bb541317fa635a79a4
- https://github.com/DagitUser69/warda
- https://github.com/ArtyKOMarkets/warda
- https://github.com/ArtyKOMarkets/warda/commit/7beecde96d349c282c9822cadb3def2d584f2473
- https://github.com/ArtyKOMarkets/warda/blob/7beecde96d349c282c9822cadb3def2d584f2473/README.md
- https://github.com/spectre-project/rusty-spectre/issues/13
- https://github.com/DagitUser69/MagicPlugins
- https://github.com/DagitUser69/MagicPlugins/commit/dabc5f215d97ca935577bf13374906b3992bc70e
