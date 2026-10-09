# Rifteemo v0.4.2 validation report

Maintainer: **Fargrim**. Source revision: `bcbe22096adaaafada74d4ea65b8cf5a21541181`.

[Release and downloads](https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.4.2) · [Source PR #23](https://github.com/rafael00kl/rifteemo/pull/23) · [Detailed change notes](https://github.com/rafael00kl/rifteemo/blob/master/docs/release-0.4.2.md).

## Delivered changes

The release includes the accumulated shared card fixes and scoped mechanic audits since 0.4.1, plus chained Equip. Equip chooses its friendly Unit and pays its costs before ordinary responses; attachment occurs on resolution. Existing attachments survive until then. Chosen costs, invalidated identities, counters, cost-trigger order, re-equipping and the Gear's other abilities have permanent regressions. Last Rites, Blade of the Ruined King and Hextech Gauntlets exercise the special costs through shared infrastructure.

Fargrim tactical-v3 emphasizes public points, Battlefield capture/denial, useful movement groups, rescue/reinforcement/displacement and combat tricks. Ordinary/complex decision ceilings are 15/38 seconds; choices may finish sooner. Excluded games are not wins, losses or training evidence and do not independently veto an otherwise sufficiently evaluated candidate. Valid-match, predecessor, MCTS150, latency and group gates remain. Generation and evaluation rotate all client decks equally, including custom/Vendetta decks; paired evaluation freezes the chosen panel and swaps assignments/seats. Checkpoint, optimizer, episodes, cycle history and named lineage are preserved.

## Executed acceptance

- 2,468 native tests PASS; one historical disabled test is not passing evidence.
- 132 focused Equip/card tests and 30 mapped QA executions PASS. Forty compiled Equip Gear consumers exercise the common activation path.
- Python client, data/audit, updater, platform, learning/import, scenario and Fargrim suites PASS. Fargrim controller: 53 PASS; installed-runtime acceptance separately verifies the actual training start/stop and controls. Seven all-deck generation scenarios PASS.
- Client/table/report DOM checks and nine inbox-worker cases PASS.
- Four multiplayer runtime scenarios and two random smoke games PASS.
- Exact stable archive: actual native Setup installation/resume, private Python, launcher startup, all three bot profiles, episode capture, restored pending decisions, bundled Fargrim start/stop and visible controls PASS.
- Anonymous Client/Table reports: exact receipts, idempotent retry and downloaded private-bundle integrity PASS. Only synthetic acceptance reports are involved.
- Real-process update/restart/recovery suite and visual Setup progress checks PASS.

Package SHA-256: `4870e9f570c9fba901b20580978d543c105fefeadac33cb00e508127d044d004`. Exact revision, input hashes and runtime digests are in release-manifest-windows.json and native-acceptance.json; published assets have SHA256SUMS. Public acceptance evidence redacts temporary local paths, retaining all result and digest fields.

Public 0.4.1-to-0.4.2 updater verification runs after publication. Its separate immutable PUBLIC-UPDATE-v0.4.2.json evidence will record the actual old client's detection, download, restart and preservation checks. This report's pre-publication acceptance does not claim that later check has already passed.

## Audit scope and remaining work

Current compiled pool: 954 printings; 28 FULL, 828 structural FULL_CANDIDATE and 98 PARTIAL. Forty Gear entries have an explicitly reviewed shared Equip scope; that alone does not certify every printed clause. Eighty-six previously current scopes were revalidated without reviving unrelated stale evidence. Last Rites was reviewed against the pinned snapshot and official Riot image, including text omitted by the snapshot. The full artwork pool was not re-probed.

Historical unresolved reports and the remaining whole-card audit stay open. The user authorized delivery of this validated current checkpoint. No claim that every known bug or card is finished, no clean second-PC acceptance in this run, no automatic promotion and no guaranteed Fargrim superiority. Short diagnostic panels are recorded in change notes but are not production promotion evidence. GitHub Actions is not claimed as passed; validation is local on Windows.

## Update and persistent data

Existing native clients: Client → Check Game Updates → Install Update & Restart. First installation: Rifteemo-Setup.exe. Native Windows 10/11 x64 and Edge; no Ubuntu/WSL required. Decks, settings, previous runtime and shared learning data are preserved. Stop and resume an already-running Fargrim loop after updating so it loads the new trainer, without resetting history.

## Credits

Rifteemo began from [chorlick/alpharune](https://github.com/chorlick/alpharune); original history and credits remain. [LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) is a separate auxiliary source. Riftbound and artwork belong to Riot Games and credited creators. No push to upstream.

## Post-publication updater verification

The actual isolated 0.4.1 client detected the public 0.4.2 release, downloaded it through its update API and restarted the actual new client with private Python and no developer PATH. Decks, preferences, episodes, training data, approved checkpoint/optimizer and lineage were preserved byte-for-byte. The previous runtime was retained; the new client reports 954 registry cards and AUDIT_READY, and the public latest version matches its local version. This isolated test used maintainer authentication only for GitHub release metadata because repeated pre-publication probes exhausted the shared IP's unauthenticated quota. Package downloads stayed public without player credentials. No distributed runtime or game code was modified; the unauthenticated live API recheck is pending the quota reset at 20:34:14 on 9 October 2026 (UTC-03:00).

[Immutable public updater evidence](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.4.2/PUBLIC-UPDATE-v0.4.2.json), with separate SHA-256 sidecar. The release report asset records pre-publication acceptance; this repository report adds the subsequent public verification without overwriting historical release assets.
