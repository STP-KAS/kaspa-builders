# KUSDT split (stp's experiment)

**Chip:** `experiment`. stp's own app or experiment. **Not Kaspa core. Not a KIP. Not an endorsement.**
**Last checked:** 2026-10-01 (the latest dated read in the moved text).

Moved from [STP-KAS/kaspa-master-file](https://github.com/STP-KAS/kaspa-master-file) main [`cf10a0f`](https://github.com/STP-KAS/kaspa-master-file/commit/cf10a0f53dc98279f12cd523be008879efff00fd) on 4 Oct 2026, branch `master/builders-split-2026-10-04`, under the master/builders split rule stp approved on 4 Oct 2026 (19:06 CEST). Text below is verbatim from the master; relative links were made absolute to that commit. Nothing here was re-checked on 4 Oct unless the text says so.

**The master keeps:** A one-line pointer in "This desk".

## What

stp's SilverScript lock with one redeem entry, plus a local program that freezes only the KUSDT tag. Guest tests 5 passed, script-engine tests 6 passed. No broadcast, no Asset ID, no Testnet 10 txid. Not a dollar.

## Moved text (verbatim)

### README Now row "KUSDT split" (whole row)

[STP-KAS/kusdt-split](https://github.com/STP-KAS/kusdt-split) [`38365b1`](https://github.com/STP-KAS/kusdt-split/commit/38365b14827725ff9d1974bde758c5aa566c04bd) is a SilverScript lock with one entry, redeem. Output 0 pays the holder the full locked amount. The fee is another input. A local program freezes only the KUSDT tag, a POCencept step can still land, and the tag is refused as gas. Draft KCC-0020 field order is mapped and the scheme fields are unset. Guest tests 5 passed. Script-engine tests 6 passed. No broadcast. No Asset ID. No Testnet 10 txid. Not BitCoffee. Not a vProg settlement. The 1984 square does not attach it to a shop buy. The spend gate stays shut. Map: [kaspa-dapps `5e756f6`](https://github.com/STP-KAS/kaspa-dapps/commit/5e756f682572c7b3ed0130a81a57ad8989c29c58). Ceiling: a private note, not linked here.

### master.json now row "KUSDT split" (whole row; url https://github.com/STP-KAS/kusdt-split; chip experiment)

1 Oct 2026. STP-KAS/kusdt-split 38365b14827725ff9d1974bde758c5aa566c04bd. KusdtLock.sil has one entry, redeem. The holder signs. Output 0 pays that key the full locked amount. The miner fee is another input. No freeze and no blacklist in the script. guest/split.mjs is a local program. One declared step lands. A freeze blocks only the KUSDT tag. A POCencept step in that batch can still land. The tag as gas is refused. The program holds no sompi and does not spend the lock. KCC.md maps Draft KCC-0020 field order. Scheme fields are unset. The freeze is outside that draft. Guest tests 5 passed. Script-engine tests 6 passed, rusty-kaspa a41a333, silverscript v1.0.0 3ed9733. The artifact stamps compiler_version 0.1.0. No broadcast. No Asset ID. No Testnet 10 txid. Not BitCoffee KUSD. Not Maxim tic-tac-toe. Not a vProg settlement. The 1984 square does not attach this lock to a shop buy. The spend gate stays shut. Map kaspa-dapps 5e756f682572c7b3ed0130a81a57ad8989c29c58. Ceiling: a private note, not linked here. Catalog. Not a product.

## Sources (every link in the moved text)

- https://github.com/STP-KAS/kusdt-split
- https://github.com/STP-KAS/kusdt-split/commit/38365b14827725ff9d1974bde758c5aa566c04bd
- https://github.com/STP-KAS/kaspa-dapps/commit/5e756f682572c7b3ed0130a81a57ad8989c29c58
