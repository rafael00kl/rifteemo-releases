# Rifteemo v0.3.0 validation report

Maintainer: **Fargrim**. Milestone: native Windows port. Source revision: ce341a6c3cf7d31efd28058dd322ef19ee991f94.
[Source PR #8](https://github.com/rafael00kl/rifteemo/pull/8).
The private source retains the original AlphaRune history and shared rules/cards/UI.

## Validation and scope

1,097 C++ tests passed on Windows and Linux (one pre-existing disabled test).
Client, Card Health, updater, platform adapters, packaging identity, deterministic seeds 42/43,
native MCTS/ISMCTS smoke games and client/Table behavior suites passed.
Actual Setup, launcher, private Python, native engine, HTTP/WebSocket actions/reconnect,
WSL data import/conflict preservation, eight native restart/recovery tests,
four WPF state/render checks and Edge screenshots were verified.
A corrupted archive was rejected before activation without changing user files.
The final distributed master revision was rebuilt and revalidated locally.
Independent clean-CI implementation results and focused packaging-fix validation are recorded in the release notes.
An independent second-notebook acceptance test is still recommended.

Rules, the 787-card pool and previously pending card bugs are unchanged.
Card Health: FULL 0, FULL_CANDIDATE 695, PARTIAL 92, STUB 0, BUGGED 5.
Structural coverage is not gameplay certification; cached artwork probes were reused.

## Installation, updates and data

Use Rifteemo-Setup.exe for first installation or the one-time WSL-to-Windows migration.
Close the old client/match first. The native package bundles private Python and required DLLs.
Windows 10/11 x64 with Edge is required; Ubuntu/WSL, developer compilers and global Python are not needed to play.
Normally no administrator access or reboot is required.
Later updates use Settings -> Check Game Updates -> Install Update & Restart.
Separate Windows and Ubuntu 26.04 manifests prevent wrong-platform installation.
Decks/settings/cache/browser profile and old runtime versions are preserved.
The developer checkout and external card dataset still live in WSL: do not unregister Ubuntu before moving/verifying them.

## Packages

- Rifteemo-v0.3.0-windows-10+-x86_64.tar.gz: SHA-256 71bb2d39fc3b4aa7c92ca447ac5eebb32eb291bd8546f65c0da26efc512b4e9c (77083891 bytes).
- Rifteemo-v0.3.0-ubuntu-26.04-x86_64.tar.gz: SHA-256 7ce353dbcf15f894b6fb39ec03111371fbe7994a8cd12c4dd90dd6532ad01bc4 (63914310 bytes).

## Public verification

The local stable artifacts and uploaded draft asset digests are checked before publication.
Anonymous latest-release download, native Setup network installation and the actual WSL 0.2.10 -> 0.3.0 client update are checked immediately afterward.
Their completed results are recorded on [the project report page](https://github.com/rafael00kl/rifteemo-releases/blob/main/REPORT-v0.3.0.md) and the central backlog.

## Credits

Rifteemo started with the complete [chorlick/alpharune](https://github.com/chorlick/alpharune) codebase: engine, architecture, cards, tests and tools. Original credits/history are preserved.
The separate [LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) repository supports metadata, artwork and errata audits.
Riftbound/cards/artwork belong to Riot Games and the credited creators.
The source remains private; this public project contains documentation and release artifacts only. No upstream push was made.

## Completed public acceptance

The anonymous v0.3.0 Setup and Windows manifest were downloaded and SHA-256 checked.
The actual public Setup discovered latest stable and installed the native runtime through GitHub HTTPS,
with developer tools excluded from runtime PATH. Visible download progress, resume with unchanged
deck/settings/cache bytes, launcher readiness, Card Health and genuine native human/human and
human/bot WebSocket actions passed. The installed client reports v0.3.0 as up to date and selects the native manifest.

An actual managed WSL 0.2.10 client discovered the public 0.3.0 compatibility package,
downloaded/verified it, restarted into the real 0.3.0 client and retained its previous runtime,
deck/settings/cache bytes. Human/human and human/ISMCTS Table starts passed afterward.
The WSL client reports up to date and advertises the separate native migration package.
These checks used isolated installations and unused ports; the existing user's installation was not overwritten.

The Windows game now runs without Ubuntu/WSL. The source workspace and external card-data repository
still live inside WSL and must be migrated independently before unregistering that distribution.
An independent second-notebook test remains recommended.
