# KASRANKS

**Chip:** `catalog`. Third-party. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-09-28 (the latest dated read in the moved text).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

## What

GitHub user KASRANKS: four browser apps (KASSWORD six-branch P2SH locker, Kasgenesiszero payload media, KasProof, KRC-721 gallery). Desk code read 28 Sep (notes moved with it). External.

## Moved text (verbatim)

### README Now row "KASRANKS" (whole row)

[KASRANKS](https://github.com/KASRANKS), GitHub user, created 23 Mar 2026, four public repos. Browser apps on the public resolver and on `api.kaspa.org`: [KASSWORD](https://github.com/KASRANKS/KASSWORD) `8af2e17` (six-branch P2SH locker), [Kasgenesiszero](https://github.com/KASRANKS/Kasgenesiszero) `41e930fb` (payload media, KIP-10 listing payment, client-side ownership replay), [KasProof](https://github.com/KASRANKS/KasProof) `31dbd5bd` (file hash as a Kaspa address), [kasranks](https://github.com/KASRANKS/kasranks) `2fff0ec` (KRC-721 indexer gallery). The README's first collection tx `e154964b049cdc8660e3b58a4cd5c9fcfdbc2316bfbdcf6688e6a82f9be213c6` is on mainnet, payload `genesis0-col`, 22 Apr 2026 13:57:12Z. Patterns for a later build: [`KASRANKS.md`](https://github.com/STP-KAS/kaspa-master-file/blob/cf10a0f53dc98279f12cd523be008879efff00fd/KASRANKS.md). External. Catalog.

### master.json now row "KASRANKS" (whole row; url https://github.com/KASRANKS; chip catalog)

GitHub user KASRANKS, created 23 Mar 2026, four public repos. Browser apps on kaspa.Resolver plus api.kaspa.org. KASSWORD 8af2e17 (28 Aug): six-branch P2SH locker, selectors 0x01 Schnorr, 0x02 HLMT, 0x03 HTLC, 0x04 DMS, 0x06 PQ-cold, 0x05 recovery. Keyless branches pin one input, one output, BLAKE2b of OpTxOutputSpk (version u16 big-endian plus script), and output amount >= input minus 0.05 KAS. DMS and recovery use absolute DAA via OpCheckLockTimeVerify, threshold 500000000000. Kasgenesiszero 41e930fb (29 Apr): media in payloads, 10000-byte chunks, KIP-10 listing script enforces the payment only. Ownership is a client replay of genesis0-* payloads. KasProof 31dbd5bd (3 Apr): SHA-256(file) is the private key of the proof address. History on REST survives the dust reclaim. The UTXO check does not. kasranks 2fff0ec reads krc721-indexer.kaspa.com for ticker KASRANKS. Desk check: mainnet tx e154964b049cdc8660e3b58a4cd5c9fcfdbc2316bfbdcf6688e6a82f9be213c6 is a genesis0-col payload, block_time 22 Apr 2026 13:57:12Z. Author mainnet-harness comments were not re-run. Patterns: KASRANKS.md. External. Catalog.

## Desk notes moved with it

- [`docs/KASRANKS.md`](../docs/KASRANKS.md) (copy of the master's [`KASRANKS.md`](https://github.com/STP-KAS/kaspa-master-file/blob/cf10a0f53dc98279f12cd523be008879efff00fd/KASRANKS.md); the master keeps its copy as a receipt).

## Sources (every link in the moved text)

- https://github.com/KASRANKS
- https://github.com/KASRANKS/KASSWORD
- https://github.com/KASRANKS/Kasgenesiszero
- https://github.com/KASRANKS/KasProof
- https://github.com/KASRANKS/kasranks
- https://github.com/STP-KAS/kaspa-master-file/blob/cf10a0f53dc98279f12cd523be008879efff00fd/KASRANKS.md
