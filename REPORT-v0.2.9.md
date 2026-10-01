# Rifteemo v0.2.9 validation report

Maintainer: **Fargrim**. Released source commit: 4cc261e7b267842792e6ab19354c99c489864061. VERSION is the single version source.

The approved [PR #6](https://github.com/rafael00kl/rifteemo/pull/6) passed [Linux and Windows CI](https://github.com/rafael00kl/rifteemo/actions/runs/36842305685). The exact approved master was recompiled and validated before stable packaging. The code remains private; public releases carry runtime artifacts, not the private C++ source repository.

## Fixed behavior

- Floating domain/universal Power is consumed correctly; Repeat and ability Energy use shared payment. SFD Seal of Strength generates Body Power.
- Overzealous Fan moves the selected attacker to its Base, with legal target choice and attached Equipment movement.
- Lillia remains in play when her Temporary Sprites expire. Sprite creation uses the movement trigger's original location.
- Both Jax, Grandmaster at Arms abilities select valid Equipment and friendly units and maintain attachment bonuses.
- Units played to a controlled battlefield remain visible. Legend artwork aliases and generated Recruit/Sprite artwork are resolved consistently.
- Base units precede compact runes and stay within the available card area.
- Settings -> Check Card Health shows searchable categories, checkpoint counts and known issues, distinguishing confirmed defects, resolved fixes and unverified upstream reports.

## Card Health

Dataset: [LouisCourrian/riftbound-cards v2026-09-29](https://github.com/LouisCourrian/riftbound-cards/releases/tag/v2026-09-29), 1,188 records. Current compiled metadata and source coverage were compared with this reference, existing official-gallery data, local errata and original AlphaRune issue/audit reports. Rules references include the [official Rules Hub](https://playriftbound.com/en-us/rules-hub/) and Core Rules dated 16 July 2026.

| Category | Checkpoint |
|---|---:|
| Compiled local cards | 787 |
| FULL | 0 |
| FULL_CANDIDATE | 693 |
| PARTIAL | 94 |
| STUB | 0 |
| MISSING | 190 |
| ART_MISSING / ART_BROKEN / ART_UNCHECKED | 0 / 0 / 0 |
| CARD_ID_MISMATCH | 23 |
| ERRATA_CHANGED | 8 |
| NEW_OFFICIAL | 189 |
| BUGGED | 13 |
| NEEDS_REVIEW | 977 |

Categories overlap and include external records. FULL_CANDIDATE is structural coverage, not complete gameplay/rule certification. Thirteen BUGGED local records are twelve Seal printings sharing an existing resource-timing gap and Scrapheap's missing discarded trigger. NEW_MECHANIC flags are heuristic review candidates, not confirmed new engine mechanics. Metadata/errata are not applied silently and cards were not imported in bulk.

The client loads cards/card_health_snapshot.json and cards/card_issues.json from its immutable runtime. Checkpoints must match version, registry, issue manifest and pinned dataset identity; stale counts are hidden. Per-version audit files are not retained as shared user preferences during an update.

## Validation

- 1,083 C++ tests executed; one pre-existing disabled test remains disabled.
- 42 Python tests across client, audit, release update and managed runtime.
- 39 Table UI and eight client DOM scenarios.
- Isolated real Edge rendering at 1280x800 and 1920x1080. Ahri with twelve compact runes remained inside Base bounds; Recruit and Sprite were visible.
- Two random smoke games with seed 42 and coverage checks.
- Windows CI passed installer protocol and four WPF state/rendering checks.
- Exact stable package upgrade 0.2.8 -> 0.2.9 preserved user decks/preferences, retained the old runtime and loaded AUDIT_READY without development reports: 787 local cards, 1,188 rows, fourteen curated issue entries.
- Real packaged client started/stopped a human-versus-random match and served the actual Table UI.
- Actual Windows Setup installed the stable package, resumed the installation with preserved sentinels and rejected a corrupt archive before activation. Actual launcher served the genuine 0.2.9 client and shut down correctly.

Fresh-machine WSL provisioning/UAC/reboot and all native Edge interactions were not re-certified. Existing installer logic is preserved. Custom client-port heartbeat routing remains a known follow-up; the default port is the supported existing flow.

Runtime package SHA-256: cec91d8b20600fa177aefdd242be43133d9547505b577d40690387716c65a2ad.
Checksums of all distributed files are in SHA256SUMS. Previous releases are retained; none of their artifacts are overwritten. No upstream push, engine rewrite or bulk card additions occurred.

## Downloads

- [Setup — first installation](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.2.9/Rifteemo-Setup.exe)
- [Launcher — existing configured installation](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.2.9/Rifteemo.exe)
- [Release, runtime package, manifest and checksums](https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.2.9)
- [Private source release](https://github.com/rafael00kl/rifteemo/releases/tag/v0.2.9)

Rifteemo began with the complete original [chorlick/alpharune](https://github.com/chorlick/alpharune) codebase. Its engine, architecture, cards, tests and tools remain the foundation; original credits and Git history are preserved. The separate [LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) dataset supports card metadata, artwork and errata audits. Riftbound, its cards and artwork belong to Riot Games and the credited creators.

[Public project](https://github.com/rafael00kl/rifteemo-releases) · [Private source](https://github.com/rafael00kl/rifteemo) · [Validation report](https://github.com/rafael00kl/rifteemo-releases/blob/main/REPORT-v0.2.9.md).
