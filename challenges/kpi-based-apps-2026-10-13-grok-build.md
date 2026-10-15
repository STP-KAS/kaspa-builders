# Challenge: build/kpi-based-apps-2026-10-13

- **Reviewed tree:** the commit that adds this file. Parent is main `ade95033c3b8cabba558e45f4901fac7e499f660`.
- **Totals:** 12 HELD · 0 FAILED · 0 UNVERIFIABLE.
- **Verdict:** no open FAILED item. This note is Grok Build's check. It is not the kaspa master challenge bot, so it does not by itself authorize a merge. Main was not moved.
- **Reviewer:** Grok Build, 13 Oct 2026. Reads were the public post, Sutton's quote post, KPI commit `e7c4dc13` and the three files it names, KIP-21 `proving-spec.md` at `e4ae233`, Toccata Based Apps at docs `0ac77d04`, and vprogs `state_transition.rs` at `f9b84a86`. No build, no node, no broadcast.

**Key:** E = `entries/olafweller-kpi.md`.

## Sources

- **B1 HELD.** E L99. Post `2109944191547793911` is @WellerOlaf at 2026-10-13T09:47:50Z. Sutton's quote `2109947914025844796` at 2026-10-13T10:02:38Z is the sentence "you're doing good and valuable work. godspeed".
- **B2 HELD.** E L100. Default-branch tip at the read was `e7c4dc133dabce25346e55499bc431132b0ca14a`, committer date 2026-10-13T09:47:01Z, message "docs: record Michael Sutton feedback on Based Apps and KPI (#30)". The message says no PoC, prover, node, funding, or TN10 broadcast was run. `research/README.md` at that commit links `technical-discussion-michael-sutton-based-apps-2026-10.md`.
- **B3 HELD.** E L101. The note's opening says the text paraphrases Michael's advice as reported by Olaf, is not an approved transcript, contains no direct quotations, and has not been represented as reviewed by Michael. RFC-0001 at the same commit says `Status: Open`, date "2026-10-02; comparison updated 2026-10-08; external input recorded 2026-10-13", and "no architecture accepted by this draft."
- **B4 HELD.** E L102 and E L103. The note's ten reported points, the extra questions with no number attributed to him, the four source pins, and the inspection limits match the note's sections "Michael's advice as reported by Olaf" and "Independently checked primary sources".
- **B5 HELD.** E L104. `kip-0021/proving-spec.md` at `e4ae233` begins "Status: Reserved companion document" and says it is not itself a consensus specification unless the main KIP incorporates it. Based Apps at docs `0ac77d04` says "The current vprogs aggregate ABI uses a 320-byte `StateTransition` journal" and lists ten fields ending in `lane_key`. `state_transition.rs` at `f9b84a86` has `deposit_spk_hash` and `assert_eq!(StateTransition::WIRE_SIZE, 352)`, with the test comment placing that field at 288..320 and `lane_key` at 320..352. The test was not run.
- **B6 HELD.** E L105 through E L107. The interval statement, the four failure cases, the C-then-A-then-deferred-B order, the ten-operation plan with omissions at positions 3, 6, and 9, and the separate TN10 authorization are in the note. The post's "No architecture has been finalized" and the graphic title "NEW DIRECTION: BASED APPS" with the caption "Kaspa anchors the ordered input set, so an executor cannot quietly skip operations while claiming a full batch" match the post and its image.

## Index

- **B7 HELD.** README KPI row names `#30`, `e7c4dc13`, Open RFC-0001, the unrun PoC, quote `2109947914025844796`, and checked date `2026-10-13`. Chip stays `experiment`.
- **B8 HELD.** `builders.json` KPI `checked` is `2026-10-13`. The note names `e7c4dc13`, the quote sentence, the reserved proving companion, the 320-byte guide line, and `WIRE_SIZE` 352. Sources include the post, the quote, `e7c4dc13`, the research note, `proving-spec.md`, the Based Apps page, and `state_transition.rs`.
- **B9 HELD.** `do-not-weld.md` section "Added 13 Oct 2026 (KPI Based Apps note)" matches B1 through B6. The older sentence that refuses welding the repo into a KIP or Core product is still the end of the verbatim paragraph.
- **B10 HELD.** E L108. The chip line in the entry header is still `experiment`. The 4 Oct through 9 Oct sections are still in the file.

## Decision

- **B11 HELD.** `SNAPSHOT-HISTORY.md` has a newest row for this branch from main `ade9503`. It names the post, `e7c4dc13`, the open RFC, the unrun PoC, and the 320/352 journal read.
- **B12 HELD.** No new STP-KAS repository. No star, fork, issue, comment, or pull on olafweller/kaspa-privacy-initiative or on kaspanet. kaspa-builders `main` was not moved. No personal email address was copied into these files.
