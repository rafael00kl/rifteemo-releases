# Rifteemo 0.3.4 delivery report

Maintained by Fargrim; built on chorlick/alpharune. Source remains private; download assets are public.

## Bots and learning

- Only two client choices: Normal (preserved former Expert, MCTS 150) and Bot Learning experimental.
- P5 weight arrays exactly match the requested research checkpoint: original SHA-256 `b1fba7dc45b308a91c22108faca17a9bc77241c394e018b101b7193dde629441`.
- Healthy frozen Expert evaluation: 5 wins, 8 losses, 0 draws; 13 healthy / 15 completed / 16 planned, four seeds. Small and incomplete, not a proven superior bot.
- Duel search uses a masked policy/value model and belief-PUCT; fixed weights during play. Four-player selection uses MCTS-150 bootstrap and capture-only records. FFA4 training remains separately gated.
- Only matches containing Bot Learning record episodes. Human demonstrations and learner search targets can feed later offline checkpoints; oracle opponent actions are not imitated as policy targets.
- Private local records include source/model/schema, seed, deck snapshots, semantic decisions, masked features, logs and outcome. Import requires complete healthy duel episodes and exact native replay; unhealthy/unfinished episodes are quarantined. No automatic uploads or in-client training.
- Default Windows path: `%LOCALAPPDATA%\Rifteemo\runtime\shared\.alpharune-client\learning\episodes\duel` or `ffa4`; custom install roots may differ. Updates preserve shared data.

## Validation

1,468 C++ tests passed, including a complete production-match replay; one pre-existing test remains disabled. 20 client backend, 6 learning importer, 12 updater, 21 Card Health, 17 client DOM, 87 table DOM and 11 report DOM scenarios passed. Actual four-player smoke matches exercised existing MCTS/ISMCTS behavior.

Native Windows acceptance covers real Setup, private Python, launcher and game without developer PATH dependencies; human/Normal/Learning WebSocket choices and reconnection; private episode creation; reinstall preservation of decks/settings/cache/nested episodes; runtime restart/recovery; anonymous Client/Table report delivery; and installer progress/rendering. A complete Bot Learning match also replayed exactly and imported four valid search samples. This was an integration smoke, not a strength measurement.

Final stable acceptance and SHA-256 assets are bound to the exact source commit and engine/desktop binary bytes. GitHub-hosted Actions jobs did not start because of the account payment/spending gate; this report describes local checks, not successful hosted CI. Independent testing on another physical PC remains a human verification step.

## Card Health and scope

The audit uses the same external dataset and compiled registry, with previously checked artwork. Historical scoped approvals remain stored. A changed shared helper hash conservatively requires renewed review evidence: FULL 0, FULL_CANDIDATE 716, PARTIAL 72, STUB 0; candidates are not behavioral certification. No new cards/rules, Vendetta integration, automatic whole-card approvals or deferred gameplay fixes are included. New simulation findings were consolidated in Notion #72/#74/#77 for later review.

## Installation

Use **Rifteemo-Setup.exe** for first installation. Existing native clients use **Check Game Updates â†’ Install Update & Restart**. Rifteemo.exe is the launcher for an already configured installation. Historical assets and runtime versions remain available.

[Latest download](https://github.com/rafael00kl/rifteemo-releases/releases/latest) Â· [Private source](https://github.com/rafael00kl/rifteemo).

Validated source commit: `6ddb7575b8ff65fbb55d622eb0490fbe48ced265`. Stable package SHA-256: `06064854e1e6ae3a1843c581fc21b458cd6cfe15db350700bdd70f73b5e4f899`.
