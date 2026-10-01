# Rifteemo v0.2.10 validation report

Maintainer: **Fargrim**. Approved merge commit: 90d86a69a51a1f42e35525125d9420ba35d8cb5e. VERSION is the single version source.

[PR #7](https://github.com/rafael00kl/rifteemo/pull/7) and its final head 099f60d passed [Linux and Windows CI](https://github.com/rafael00kl/rifteemo/actions/runs/36923625398). Fargrim explicitly authorized the merge, source tag and stable publication. The exact merged master was recompiled and validated before stable packaging. Private source remains private; the public repository hosts distribution documentation and release artifacts.

## Fixed behavior


| Backlog | Result |
| --- | --- |
| #2 | Public Stunned badge and preview; tested zero combat damage and Ending cleanup. Stun alone does not prohibit movement; Vex's extra restriction remains #34. |
| #5 | Hidden card backs align inside ready and exhausted faces without disclosing identity. |
| #19 | Persistent visual stack, newest item first, next-to-resolve highlight, ability type, controller, targets and preview. |
| #20 | Detached hover enlargement for public cards on the board, Base and battlefields; Runes excluded; click/selection preserved. |
| #21 | Gear names its attached unit; unit attachment count and linked hover highlight come from authoritative public state. |
| #32 | Readable Rune sizes of 48×67 or 54×76; Rune count still does not scale troops down. |
| #6 | Victory/Defeat with Back to Client; the client verifies the engine's terminal state, stops that session and can start another match. Active matches and foreign ports/origins cannot be stopped through the return route. |
| #7 | Human/Bot selection and exactly Very Easy, Easy, Normal, Hard, Very Hard, Expert. Semantic settings migrate legacy preferences. Mapping: ISMCTS 50/100/150, then MCTS 50/100/150. Technical details stay in developer diagnostics/CLI. No ISMCTS determinization redesign. |
| #28 | Table URL carries the configured client port. Heartbeat and return links use that loopback port; malformed values fall back to 8090. |
| #30 — destinations | Hand and Champion Zone share normal Unit destinations, including all controlled, unblocked battlefields; existing card and location restrictions remain. |
| #30 — Scrapheap | Played, discarded and killed Gear branches draw exactly once through shared event dispatch. Jinx and Flame Chompers also receive their existing discard triggers. |
| #31 | Explicit shared Add classification and immediate resolution before pending finalization, without transferring Priority/Focus or reacting to the resource ability. Ordinary spells and secondary triggers remain reactable; resumable conversion choices remain supported. |

Both existing #30 IDs are retained and distinguished by title. #17 was moved to Completed after Fargrim's acceptance. #13 remains an ongoing workstream.

The Step API also reported the turn owner instead of the actual actor when an opponent had a pending choice. It now reports the player on the legal decision, covered by opponent-priority and combat regressions.

A final regression reproduced Malzahar destroying Scrapheap during Showdown: Add must resolve first, then Scrapheap must finalize normally before Focus returns. The shared path now preserves those secondary triggers and callbacks that enqueue items during finalization.


## Validation

- 1,097 C++ tests executed, including fourteen targeted gameplay/protocol regressions. One pre-existing disabled test remains disabled.
- 44 Python tests: client 13, card health 14, release/update 9, managed-runtime installation 8.
- 58 DOM scenarios on the final revision: Table UI 48 and client 10.
- Real isolated Edge rendering at 1280×800 and 1920×1080: Runes, Hidden, Stunned, Equipment, stack, board/Battlefield hover and terminal screen.
- Real Windows → WSL match flow on custom ports 18124/18088: engine victory, Table UI return, real client boot, stopped old session, new match and heartbeat. Active-match, wrong-port and foreign-origin return requests were rejected.
- Two complete random smoke games, seeds 42/43.
- Windows CI and four WPF state/rendering checks. Launcher/bootstrapper compiled through the normal validation script.
- Exact stable package upgrade 0.2.9 → 0.2.10 preserved decks/preferences, retained the previous runtime and returned AUDIT_READY: 787 local cards, 1,188 rows and 22 curated known-problem entries.
- Actual packaged client started/stopped a match and served the Table UI.
- Actual Windows Setup installed the stable candidate, resumed with preserved sentinels and rejected a corrupt archive before activation. Actual launcher served the genuine 0.2.10 client and shut down correctly.

These checks include actual packaged Windows executables on an already provisioned WSL host. Fresh-machine WSL/UAC/reboot and every native browser interaction were not repeated in this patch. Post-publication anonymous-download/updater/old-Setup results will be recorded in this public report's version history; they are not claimed by the immutable pre-publication artifact.

## Card Health


External source: LouisCourrian/riftbound-cards v2026-09-29, pinned SHA-256 9a2c6d06fee5142a48b4efe148fd1de3cfcd63052178814a60c0540ca4042c5d; 1,188 records. Compiled registry: 787 cards.

| Category | Count |
| --- | ---: |
| FULL | 0 |
| FULL_CANDIDATE | 695 |
| PARTIAL | 92 |
| STUB | 0 |
| MISSING | 190 |
| NEW_OFFICIAL | 189 |
| ART_MISSING / ART_BROKEN / ART_UNCHECKED | 0 / 0 / 0 |
| CARD_ID_MISMATCH | 23 |
| ERRATA_CHANGED | 8 |
| BUGGED | 5 |
| NEEDS_REVIEW | 977 |
| NEW_MECHANIC candidates | 67 |

Categories overlap. Art counts reuse the dated verified probe cache; they are not a new full network art crawl. FULL_CANDIDATE is structural coverage, not semantic certification. The previous 13 confirmed card records (twelve Seal printings and Scrapheap) are resolved; five different confirmed records remain from newly documented restricted-resource and delayed-timing gaps.

Versioned cards/card_health_snapshot.json and cards/card_issues.json update the client checkpoint with this candidate. Known Problems separates resolved/confirmed entries from unverified upstream reports and newly reported local issues.


Twenty-two curated known-problem entries distinguish resolved/confirmed defects, upstream leads and reported issues needing reproduction. They are not a count of unresolved cards. Versioned audit data remains inside each runtime; decks and shared user settings are preserved.

## Remaining work


- #33 simultaneous trigger ordering, #34 Vex movement restriction, #35 live Gold legality/payment windows and #36 Charm destinations remain separate pending reports. This patch does not claim they are fixed.
- #37: resources from Daughter of the Void/Lux (spell-only), Fire Below the Mountain (Gear-only) and Scorn of the Moon (showdown-only) enter unrestricted scalar pools. Source audit confirms missing enforcement. Shared resource provenance/payment validation needs a separate change.
- #38: Blue Sentinel adds Power at Hold, while its text defers it to the next Main Phase. The old source explicitly approximates the timing. Add a proper delayed effect with phase regressions.
- Special activation windows during Pay Costs (CR 429.3) are not implemented by this immediate-timing patch; tracked with #35/resource follow-up.
- Semantic FULL certification, identity/metadata discrepancies, PARTIAL batches, errata review, deterministic replay/Teach Mode and safe expansion remain #13.


The backlog #13 stays pending. No whole-card FULL certification, mass card additions, architecture rewrite or upstream push occurred.

## Package and downloads

Runtime package SHA-256: f396c54cff9319cd1207cfd5d8a8655e05ec0ad0f037da1e6ece2881943b9da8.
All seven distributed files are listed in SHA256SUMS. Previous releases remain available without overwriting their artifacts.

- [Setup — first installation](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.2.10/Rifteemo-Setup.exe)
- [Launcher — configured installation](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.2.10/Rifteemo.exe)
- [Release, package, manifest and checksums](https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.2.10)
- [Private source tag](https://github.com/rafael00kl/rifteemo/releases/tag/v0.2.10)


Rifteemo began with the complete original [chorlick/alpharune](https://github.com/chorlick/alpharune) foundation. Its engine, architecture, cards, tests and tools remain the foundation; original credits and Git history are preserved. The separate [LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) dataset supports card metadata, artwork and errata audits. Riftbound, its cards and artwork belong to Riot Games and the credited creators.

[Public project](https://github.com/rafael00kl/rifteemo-releases) · [Private source](https://github.com/rafael00kl/rifteemo) · [Validation report](https://github.com/rafael00kl/rifteemo-releases/blob/main/REPORT-v0.2.10.md).


## Post-publication distribution validation

- All seven assets downloaded anonymously from GitHub and matched the local SHA-256 and expected size.
- The actual installed 0.2.9 client discovered stable 0.2.10, downloaded/verified it through the public endpoint, applied it and restarted into the new runtime.
- Decks, preferences and cache sentinels survived; the old runtime remained available. The updated client reported Up to date and AUDIT_READY with 787 local cards, 1,188 records and 22 known-problem entries.
- Human/Human and Human/Bot matches started after the update and served the genuine Table UI.
- New Setup 0.2.10 and old Setup 0.2.9 both downloaded the latest stable 0.2.10, installed/resumed it and served the genuine client through the Windows launcher. Actual download progress reached 100%; sentinels were preserved.
- Previous 0.2.9 asset IDs, sizes and hashes are unchanged. Source remains private and public distribution remains public.
