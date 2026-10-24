# Rifteemo 0.5.2 validation

Maintainer: Fargrim. Native Windows hobby/research release.

Manual Play PvP and local two-deck Goldfish are independent from automatic GameEngine play. Players resolve printed card effects and costs themselves. Structural turn procedures, Priority, Focus and Chain are managed by the manual table. Goldfish needs no Remote Play gateway.

Validated checks: 3,272 enabled C++ cases; 405 Python cases with zero skips; 12 frontend suites; Go gateway/bootstrapper tests; nine report-inbox unit cases; four WPF installer states. One pre-existing C++ case remains disabled. Exact-source native Setup, private Python, launcher, human/Normal/Learning/Fargrim starts, pending-decision reconnect, user-data preservation, eight restart/recovery/install cases and two synthetic own-inbox Client/Table receipts passed.

Actual browser acceptance completed a two-session TLS Manual PvP game and a client-lobby Goldfish game with private views, touch emulation, reload/save/resume and terminal concession. The exact final native binary completed an automatic PvP duel (941 frames), followed by exact recorded episode replay.

Release-gate corrections: the bundled Card Health checkpoint now declares 0.5.2. Existing rows, categories, summary, issues and semantic decisions are unchanged; timestamped art evidence was reused without new network probes. The full-game four-seat search gate now accepts the engine's valid max-turn draw and uses a bounded 180-second allowance for MCTS/ISMCTS only; random smoke keeps 60 seconds. Original failures and baseline diagnostics were retained. Native engine/card/bot algorithms and gameplay limits did not change.

Approved fallback: Iron Fox (28), sanitized inference weights and public lineage only. Existing private checkpoints, optimizer, episodes and progress take precedence.

The stable runtime's file set and bytes were compared against the installed acceptance candidate. Source, executable, weights and dependency files are byte-identical. BUILD_INFO.json changes channel (development to stable); generated NumPy bytecode caches differ only in headers and temporary build filenames, with recursively verified identical code objects. Exact source, executable and desktop hashes match; published package and every public asset have SHA-256 records.

Limits: physical-phone, external-network and independent clean-PC acceptance are not claimed. Test counts do not certify card semantics. Manual card-text interpretation, effects, costs and score adjustments remain the players' responsibility.

Independent, unofficial, non-commercial hobby/research project. Preserve original AlphaRune and card/artist credits; no authorization from Riot is asserted. Existing project-purpose and removal-request notices remain in the repository documentation.

Source commit: 3858acd52deee9f56175afba5b40699cb8d822dd

Runtime SHA-256: 5a8eeedce49f072a5382ed36d3411334340f1f4da3e1d3559c78f6ff9a89b777

The exact published stable archive was additionally installed and exercised directly through all four human/bot profiles, reconnect, training start/stop and data preservation. No additional synthetic reports were sent in this second archive-specific check.

Public update verification: the unmodified 0.5.1 client anonymously discovered/downloaded public 0.5.2, restarted and committed activation, preserved 54 synthetic deck/config files and the existing private checkpoint/optimizer, and then reported up to date. See PUBLIC-UPDATE-v0.5.2.json on the release. The owner installation was untouched.
