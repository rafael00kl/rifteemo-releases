# Rifteemo v0.3.1 validation report

Maintainer: **Fargrim**. Source revision: 6e1218b70dfd97b23b373c89d33bdfe805c06c4b.
[Source PR #9](https://github.com/rafael00kl/rifteemo/pull/9).

## Delivered scope

Player-selected simultaneous trigger ordering, reviewed Report a Bug from Client/Table and local four-player Free-for-All with one human and three bots. Four-deck setup, priority, combat participants, opponent choices, elimination and actual MCTS/ISMCTS adapters share the existing engine. Duel remains available.
Opposing hands and all deck orders are masked on the wire; private diagnostic output is not exposed through the table. Aspirant's Climb uses the same effective victory goal for scoring, Burn Out and the scoreboard.
Development migrated to the permanent native Windows workspace with original Git history and selectively preserved local-only files. Ubuntu removal is a separate final safety step after delivery and workspace detachment.

## Validation

The exact distributed master was rebuilt and passed 1,169 C++ tests (one pre-existing disabled test), backend/DOM suites, four complete executable scenarios (different decks, UInt64 deterministic replay, actual MCTS/ISMCTS and rejected unsupported configurations).
Actual isolated Edge acceptance at 1280×800 and 1920×1080 exercised Client → four-seat engine → mulligan/priority → public report context → restored preferences, both in development and the installed runtime.
Complete native pipeline passed: Setup, launcher, private Python, real HTTP/WebSocket actions and reconnection, eight restart/recovery tests, four WPF state/rendering checks and immutable package/acceptance SHA-256 binding.
Hosted Actions jobs did not start: GitHub reported account billing/spending-limit restrictions. No hosted CI pass is claimed and no paid usage was enabled. Local native validation is the release gate.
An independent second-PC test of this version is still recommended.

Card Health: 787 local cards; FULL 0, FULL_CANDIDATE 699, PARTIAL 88, STUB 0, BUGGED 5, missing candidates 190, new-set candidates 189, identity mismatches 23 and errata-text differences 8. Structural candidates are not semantic certification. Art 0/0/0 reuses the explicitly dated September 30 cache; not every remote URL was fetched again.
Known PARTIAL clauses, additional backlog bugs, four-human networking, teams and the separate ISMCTS resampler remain pending.

## Install and update

Use [Rifteemo-Setup.exe](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.3.1/Rifteemo-Setup.exe) for first installation or migration. Rifteemo.exe is the launcher for an already configured installation.
Installed native clients use Settings → Check Game Updates → Install Update & Restart.
Windows 10/11 x64 and Edge; no Ubuntu/WSL, global Python or compiler required to play. Normally no administrator/reboot required.
Shared decks, configuration, cache and previous runtimes are preserved. Version 0.3.1 is native Windows only; older WSL installations must migrate with Setup. The historical 0.3.0 compatibility package remains available.

Package: Rifteemo-v0.3.1-windows-10+-x86_64.tar.gz
SHA-256: 26952464a3a656deb2656a409d26793cd881b2da541838743e3c20f6271c254d (77203631 bytes).

The draft asset sizes/digests are checked before publication. Actual anonymous latest-release download, Setup and native 0.3.0 → 0.3.1 update results are recorded afterward on the project report page.

## Credits

Rifteemo started from the complete [chorlick/alpharune](https://github.com/chorlick/alpharune) codebase, including engine, architecture, cards, tests and tools. Original history/credits are preserved. [LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) remains the separate metadata/art/errata reference.
Riftbound/cards/artwork belong to Riot Games and credited creators. Code remains private, releases public. No push to upstream; historical release assets unchanged.

## Completed public verification — October 2, 2026

Anonymous Setup/manifest downloads passed SHA-256 verification. Both the new Setup 0.3.1 and the previous Setup 0.3.0 discovered and installed stable 0.3.1. Download progress reached 100%; resume preserved user files, launcher started the native client and real WebSocket actions passed in duel and four-player modes.
The actual native client 0.3.0 downloaded 0.3.1, restarted, activated after readiness, preserved decks/settings/cache and retained the previous runtime. The new client reported up to date, Card Health AUDIT_READY, and opened four-player play with the exact UInt64 seed.
Test isolation excluded developer tools while retaining standard Windows PowerShell. An initial incorrectly restricted test environment exercised safe rollback; the final standard-Windows public update passed.
Historical release asset IDs, sizes and digests remain unchanged.

## Development cleanup status

The permanent Windows checkout, separate card dataset and toolchain are operational. All old Git objects and 342 preserved local files were rechecked; 341 retain their original hashes, with only the generated registry cache refreshed.
Ubuntu-26.04 was removed after its data inventory. The original Ubuntu distribution remains because this existing chat is still anchored to its UNC workspace and reactivates it; final removal must continue from a chat opened in C:/Projects/Rifteemo. Unique historical patches/local data are selectively preserved outside the distribution. No Ubuntu/WSL is required to play or run the native development commands.
