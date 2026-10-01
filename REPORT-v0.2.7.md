# Rifteemo v0.2.7 branding migration

Status: development candidate; stable merge/tag/publication require explicit approval.

Rifteemo is maintained by **Fargrim**. Public pages, documentation and UI use English. The original AlphaRune engine, codebase, architecture and history remain credited in [CREDITS.md](../CREDITS.md). No gameplay/card implementations are changed by this migration.

## Repositories

- Private source: https://github.com/rafael00kl/rifteemo (renamed; history preserved).
- Public distribution: https://github.com/rafael00kl/rifteemo-releases.
- Legacy update bridge: https://github.com/rafael00kl/alpharune-releases.
- Read-only upstream: https://github.com/chorlick/alpharune.
- External dataset: https://github.com/LouisCourrian/riftbound-cards, kept outside this repository.

GitHub account identifiers remain in routing URLs. Local workspace paths, historical Git provenance, original project credit and legacy installation/protocol IDs are compatibility exceptions. Third-party card artist names remain authentic; they are not maintainer identity.

## Changes

Menu, in-game table, splash, client/server identity, launcher, Setup, icon, version banner, current documentation and release configuration use Rifteemo. Version is `0.2.7` in `VERSION`. New primary Windows names are `Rifteemo.exe` and `Rifteemo-Setup.exe`. Credits display Fargrim.

Old v0.2.6 clients require the original `AlphaRune/` archive root, `alpharune-client`, desktop aliases, `alpharune-runtime-v1`, `alpharune-install-v1`, cache/preference keys and an additional legacy version-smoke line. These interfaces are retained. The same validated v0.2.7 package must be published through both distribution endpoints; old clients transition to the new endpoint after update. Old v0.2.6 assets/checksums are never overwritten.

The new Setup detects an old managed Windows configuration, reuses its WSL installation/shared data, browser profile and configured ports and requires the old game to be closed before migration. Developer checkouts remain protected. The new launcher can also use a legacy config directory. Installing the renamed Windows shell once is separate from normal game updates.

## Validation

Local validation passed: 1,066 C++ tests (one pre-existing disabled test), 8 client tests, 11 card-health tests, 8 release/update tests, 7 runtime-install/recovery tests, coverage and two deterministic smoke games. All 36 Table UI DOM behavior tests passed; DOM tests do not certify visual rendering.

Actual Windows Setup and launcher EXEs were checked in isolated directories/ports with the validated development package. Setup exited successfully, and the launcher reported version 0.2.7, 767 name-deduplicated registry entries and no registry error.

The actual v0.2.6 client, release helper and restart worker migrated an isolated installation to the Rifteemo package. A user deck and the old runtime were preserved; the new menu displayed Rifteemo/Fargrim and the new updater consulted the new distribution repository. Stable discovery/download was injected locally because v0.2.7 is not published yet; package bytes, old engine/helper and new runtime were genuine.

Interactive clean-machine WSL provisioning/UAC/reboot and browser visual acceptance are not certified by these tests. Stable distribution remains unavailable until those checks and approval are complete. The previously published v0.2.6 installation was reported working on a second notebook by its maintainer.

The final Windows Setup migration was also exercised using a genuine staged v0.2.6 runtime and an isolated legacy Windows configuration. Setup and launcher both exited 0; the shared user deck, old configuration, browser-profile sentinel and custom client/game ports were preserved. No user installation or shortcut was modified during verification.

Public GitHub READMEs, the historical v0.2.6 report and release descriptions, and existing PR descriptions were translated to English. The public migration bridge clearly points to the new distribution. Existing binary/checksum assets and historical Git authorship remain immutable. No RiftRune branding was introduced.

Work-branch checkpoint: `54aab14`. Source review: https://github.com/rafael00kl/rifteemo/pull/3.
