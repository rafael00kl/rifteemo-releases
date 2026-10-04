# Rifteemo 0.3.5 validation report

Maintainer: Fargrim. Date: October 4, 2026.

## Shared trigger blocker

After staged Showdown/Combat, Conquer events queued effects without draining finalization/resolution before returning a Main decision. Closed legal actions belonged to the previous priority holder while the turn player was asked to choose; the viewer correctly filtered the other seat's actions, leaving an empty human decision. One engine lifecycle fix drains FEPR/cleanup and restores neutral turn priority/focus.

Nine permanent regressions cover mandatory, optional and simultaneous triggers across Deceiver/LeBlanc, Plundering Poro (normal/showcase), Zaun Warrens, Minefield, Seat of Power and Sunken Temple, in duels and four-player games. The original three scenarios failed before the fix. Tests assert viewer actions, effect completion, relevant results and return to ordinary Main actions. Original private reports are diagnostic snapshots, not full executable match replays.

## Validation

- 1,477 native C++ behavioral tests passed; one preexisting test remains disabled.
- Client/Table/report DOM and private inbox Worker suites passed, along with backend, learning episode, Card Health, updater and packaging tests.
- Four real multiplayer runtime tests and seeded smoke games passed.
- Actual isolated native installation exercised the packaged engine, launcher and Client/Table. Fresh synthetic Client/Table reports were accepted without player login from the validated master package. Stable-file acceptance prepares fresh diagnostic archives and retries those exact already-accepted synthetic reports through the installed Client/Table; this exercises the idempotent delivery path without creating additional reports. The reporting code and launcher/engine binary hashes match the validated master candidate. A first stable-file fresh send hit the configured inbox rate limit, so no quota was changed and no player/test reports were deleted.
- Eight restart/recovery/update tests preserve user data; four WPF Setup state/render checks passed.
- GitHub Actions did not start because of account billing/spending limits. Validation ran locally; hosted CI success is not claimed.

## Scope and audit

Related private reports are consolidated under Notion #71. Audit evidence is scoped to this shared lifecycle and preserved with component hashes in config/card_reviews.json. No whole-card FULL promotion is claimed. Card Health: 788 compiled cards, FULL 0, FULL_CANDIDATE 716, PARTIAL 72, STUB 0. Historical approvals are preserved and require revalidation when shared components change.

Unrelated bug leads remain deferred, including a separate Showcase Poro token-readiness discrepancy recorded as #78. This hotfix does not inspect or integrate Vendetta, change bot weights, enable additional learning capture or modify unrelated card implementations.

Decks, configuration, caches and private learning episodes remain persistent. Private player attachments, logs, credentials and local build inputs are not included in the public report. No push to upstream.

Source merge: c3972eacc5f565a102c00be436d473fecc841abe. PR: https://github.com/rafael00kl/rifteemo/pull/16.

Downloads: https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.3.5

For an existing native installation, use Check Game Updates. For first installation, download Rifteemo-Setup.exe. Rifteemo.exe is the launcher for an already configured installation.
