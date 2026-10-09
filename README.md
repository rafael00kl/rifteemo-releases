# Rifteemo

An independent Riftbound game project maintained by **Fargrim**. The source remains private; this public repository distributes validated native Windows packages and preserves historical WSL compatibility releases.

## Downloads

**Rifteemo v0.4.2 - shared card audit fixes, chained Equip and Fargrim tactical-v3.** Download Setup for first installation; existing native clients can use Check Game Updates.

- [Latest stable release](https://github.com/rafael00kl/rifteemo-releases/releases/latest)
- [Rifteemo-Setup.exe](https://github.com/rafael00kl/rifteemo-releases/releases/latest/download/Rifteemo-Setup.exe)
- [Private source project](https://github.com/rafael00kl/rifteemo)
- [Historical AlphaRune v0.2.6 downloads](https://github.com/rafael00kl/alpharune-releases/releases/tag/v0.2.6)

## Installation and updates

For first installation, use **Rifteemo-Setup.exe**. **Rifteemo.exe** is the launcher for an existing configured installation. Setup displays the current stage, download percentage, elapsed time and clear success/error messages.

Run Setup on Windows 10/11 x64 with Microsoft Edge. It installs private Python and the native game runtime per user, downloads the latest validated Windows package and verifies SHA-256. Ubuntu, WSL, MSYS2, compilers and global Python are not required to play. Installation normally needs no administrator access or reboot. Public downloads require no GitHub login.

In the game, open Settings -> Check Game Updates -> Install Update & Restart. Finish matches and save decks first. Updates retain shared decks, configuration/cache and previous runtime versions. Developer source checkouts are protected.

Existing WSL users should close the old client and any match, then run the new Rifteemo Setup once to migrate. Decks, settings, cache and the browser profile are preserved; the old WSL runtime is left intact. Later native updates use the client update flow. Version 0.4.2 is native Windows only. The historical [0.3.0 WSL compatibility release](https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.3.0) remains available; migrate with Setup before subsequent native updates. Existing AlphaRune clients retain their original branding migration bridge. Historical release assets are never overwritten.

Do not remove or unregister Ubuntu until any development checkout, external card dataset and local-only files inside it have been moved and verified. The native game no longer needs WSL, but removing the distribution can delete files used for development.

## Latest update

Version 0.4.2 retains all 166 Vendetta cards and adds shared fixes for play costs, Repeat, Flow, trigger/Showdown timing, Rune choices, Reveal/private inspection, Vision/Predict, Base movement restrictions and paid Trash/linked Banishment play. Equip now pays its chosen costs before a response window and attaches on Chain resolution, including re-equipping. Last Rites, Blade of the Ruined King and Hextech Gauntlets use their correct chosen or target-dependent costs.

Fargrim tactical-v3 improves public point/Battlefield strategy, movement groups, rescue/reinforcement/displacement and combat tricks. Decision ceilings are 15/38 seconds; simple choices may finish sooner. Generation and evaluation rotate **all decks available in the client equally**, including custom and Vendetta lists, without numbered-deck restrictions or ranked preference. Cancelled games remain excluded from evidence but do not independently veto a sufficiently validated candidate. Model/checkpoint/optimizer history and successor lineage are preserved.

Card Health currently contains 954 printings: **28 FULL, 828 structural FULL_CANDIDATE and 98 PARTIAL**. Forty Gear consumers have a reviewed shared Equip scope; a PARTIAL scope is not a newly discovered bug. Whole-card certification requires all printed clauses and current rule/metadata/behavior evidence. Historical unresolved reports and the remaining audit stay pending. This release does not claim every card or bug is finished.

The client offers **Normal** (MCTS 150), **Bot Learning (Original)** and the locally approved **Fargrim Bot**. Run **Fargrim-Learning.cmd** in the installed active runtime folder to start, inspect, stop or resume its local learning loop. Default installation path: `%LOCALAPPDATA%\Rifteemo\runtime\versions\0.4.2\Fargrim-Learning.cmd`. Use the active version folder after later updates. This is the same game client, engine and persistent storage. New matches use the latest approved local checkpoint; weights remain fixed during each match. Stop the existing training loop safely and restart it after updating to load the new trainer; this preserves its history.

The loop imports eligible records, prioritizes human decisions, generates varied duels, trains a candidate and evaluates it against the active checkpoint and Normal/MCTS before approval or rejection. It keeps the active model when a candidate fails the gates. An approved successor receives a name and generation number; episodes, lineage and approved checkpoints survive game updates. There is no guarantee of improvement in every cycle.

All client matches can save private local episodes under persistent `.alpharune-client/learning/episodes/duel` or `ffa4`. Incomplete, incompatible and four-player records are preserved but excluded from current duel training. Four-player learning remains pending; those records stay separate. Training is local and starts only when you activate the loop; records are not automatically uploaded.

**Report a Bug sends directly from the Client or the table without player login**, GitHub navigation or manual ZIP attachment. A private inbox receives version/seed/log context. Players can review optional private diagnostics and screenshot before sending; owner credentials are never included in the game. Reports remain local if delivery fails. Reports are reviewed only when Fargrim requests a bug-review block.

Automated Card QA / Card Health / regression / simulation remains a fundamental development pillar. The source project's [mechanics guide](https://github.com/rafael00kl/rifteemo/tree/master/mechanics) defines one gradual contract format for future labs and authorized card work. The guide alone does not certify mechanics or cards, and the release adds scoped contracts linking reviewed rules, helpers, affected cards and reusable regressions. Existing valid clause evidence is reused; changed or uncovered clauses are reviewed separately.
## Card Health

Settings -> Check Card Health shows the bundled audit checkpoint, searchable categories and known issues. It distinguishes confirmed defects, fixes in this release and upstream reports that still need reproduction. This is not a live official-data fetch or whole-card gameplay certification. Audit data is versioned with the game while user decks/preferences remain preserved.

## Credits

Rifteemo began with the complete codebase of [chorlick/alpharune](https://github.com/chorlick/alpharune). Its original engine, architecture, card implementations, rules, tests and tools are the foundation of this project; credit belongs to the original creator and contributors. The existing Git history is preserved.

[LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) supplies a separate auxiliary reference for card metadata, images, sets and errata. Dataset changes are reviewed and do not automatically change gameplay. Riftbound, its cards and artwork belong to Riot Games and the credited creators. Rifteemo is an independent community project.

The maintainer name is Fargrim. 
[Current release validation report](REPORT-v0.4.2.md) · [Branding migration report](REPORT-v0.2.7.md).

