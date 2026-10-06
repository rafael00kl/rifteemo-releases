# Rifteemo 0.4.0 validation report

Maintainer: **Fargrim**. Date: 2026-10-06. Channel: **stable**.

## Source and distribution

- Private source revision: `4b1141fb7598663bd3b670a2379383f5354b15e0`; [PR #17](https://github.com/rafael00kl/rifteemo/pull/17), source tag `v0.4.0`.
- Public assets: [Rifteemo v0.4.0](https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.4.0).
- Inputs SHA-256: `60baabca87d63c594024f334b20fe6439c41f0213161e0281a44afb517dd45c1`.
- Native engine SHA-256: `1ea45daf4755d992f2d4abb4f81e750576848ed3ec36718e0239efb677366ed7`.
- Runtime package SHA-256: `22ed896f5bf4f27b90a0091c9e170c8abcbad5810369fe249147734f757080db`.
- SHA256SUMS covers the distributed package, manifest, launcher, Setup, notes and acceptance report.
- Source history and original AlphaRune/chorlick credits are preserved. Upstream push remains disabled. No source GitHub Release object is created in the private repository.

## Executed validation

The full native pipeline ran on clean committed master for this exact source. It rebuilt the engine, test executable, native bot arena, launcher and Setup.

- 2,099 C++ tests from 220 suites passed. One existing Baron Nashor aura test is disabled and was not executed; it is not counted as passed.
- 122 UI behavior regressions passed (20 client, 91 table, 11 shared reporting); these are DOM/state tests rather than full visual certification.
- Nine inbox worker tests passed; 43 Fargrim tests passed without skips; 22 Card Health tests passed.
- Native build, platform, client, bug-report, episode, release-update and packaging checks passed.
- Four actual multiplayer runtime scenarios passed; two complete random smoke games finished with opposite winning seats.
- Eight native restart/recovery/data-preservation orchestration scenarios passed, plus Go bootstrapper checks and four WPF Setup state/rendering checks.
- The final stable archive was separately installed using actual Setup/private Python, with developer runtime/toolchain paths excluded. The client, bundled NumPy and all three bot profiles were exercised. Fargrim console/UI controls started and stopped the same worker and retained its pointer.
- Actual Client/Table anonymous synthetic reports were delivered with matching private receipts and idempotent retry. No human inbox triage was performed.

The installed-package evidence is in `native-acceptance.json`. This is isolated installation testing on the development Windows machine, not an independent clean-PC test. GitHub-hosted Actions did not start any jobs for this push; hosted CI is not claimed passed. Local exact-revision gates above passed.

After publication, public release discovery and an actual 0.3.5-client update will be checked separately. Its result will be attached as `PUBLIC-UPDATE-v0.4.0.json` with its own checksum; this report and the original release assets will remain immutable.

## Included scope and limits

All 166 Vendetta cards are integrated. Current individual certification is **12 FULL / 154 not fully certified**. Compilation, regression results and stable publication do not certify every clause or interaction. Deferred historical bugs and remaining individual reviews are not claimed completed. Stable distribution of this current state was explicitly authorized by Fargrim.

Fargrim Learning is integrated into the normal client. Eligible human-weighted episodes, varied duel generation, training, evaluation, rejection/promotion, persistent lineage and named successors are implemented. No universal strength or guaranteed promotion is claimed. Four-player capture remains separate, without four-player training.

The root [mechanics guide](https://github.com/rafael00kl/rifteemo/blob/master/mechanics/README.md) defines gradual documentation during future authorized card work. Only the guide is created in this release, with no individual mechanic certification.

Existing installations use Check Game Updates / Install Update & Restart. New users use Rifteemo-Setup.exe. Shared decks, configuration, episodes and local training state are retained. Ubuntu/WSL is not required.
