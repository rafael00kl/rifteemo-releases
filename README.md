# Rifteemo

An independent Riftbound game project maintained by **Fargrim**. The source remains private; this public repository distributes validated native Windows packages and preserves historical WSL compatibility releases.

## Downloads

**Rifteemo v0.3.4 - Normal and experimental Bot Learning, with private local learning records.** Download Setup for first installation; existing native clients can use Check Game Updates.

- [Latest stable release](https://github.com/rafael00kl/rifteemo-releases/releases/latest)
- [Rifteemo-Setup.exe](https://github.com/rafael00kl/rifteemo-releases/releases/latest/download/Rifteemo-Setup.exe)
- [Private source project](https://github.com/rafael00kl/rifteemo)
- [Historical AlphaRune v0.2.6 downloads](https://github.com/rafael00kl/alpharune-releases/releases/tag/v0.2.6)

## Installation and updates

For first installation, use **Rifteemo-Setup.exe**. **Rifteemo.exe** is the launcher for an existing configured installation. Setup displays the current stage, download percentage, elapsed time and clear success/error messages.

Run Setup on Windows 10/11 x64 with Microsoft Edge. It installs private Python and the native game runtime per user, downloads the latest validated Windows package and verifies SHA-256. Ubuntu, WSL, MSYS2, compilers and global Python are not required to play. Installation normally needs no administrator access or reboot. Public downloads require no GitHub login.

In the game, open Settings -> Check Game Updates -> Install Update & Restart. Finish matches and save decks first. Updates retain shared decks, configuration/cache and previous runtime versions. Developer source checkouts are protected.

Existing WSL users should close the old client and any match, then run the new Rifteemo Setup once to migrate. Decks, settings, cache and the browser profile are preserved; the old WSL runtime is left intact. Later native updates use the client update flow. Version 0.3.4 is native Windows only. The historical [0.3.0 WSL compatibility release](https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.3.0) remains available; migrate with Setup before subsequent native updates. Existing AlphaRune clients retain their original branding migration bridge. Historical release assets are never overwritten.

Do not remove or unregister Ubuntu until any development checkout, external card dataset and local-only files inside it have been moved and verified. The native game no longer needs WSL, but removing the distribution can delete files used for development.

## Latest update

Version 0.3.4 offers only **Normal** (the former Expert/MCTS 150) and **Bot Learning**. The experimental P5 model plays duels with masked belief search; its small healthy Expert evaluation was 5 wins / 8 losses and does not establish superiority. Four-player Bot Learning currently uses MCTS-150 bootstrap with capture-only records stored separately; multiplayer training is pending.

Matches containing Bot Learning automatically save private local episodes under the persistent `.alpharune-client/learning/episodes/duel` or `ffa4` folder. The laboratory imports replay-verified, healthy duel data for later offline checkpoints; weights stay fixed during play. No automatic uploads or training occur, and matches using only Normal are outside this capture scope. Updates preserve the episode folder. Existing gameplay fixes from 0.3.3 remain in place; this release does not integrate Vendetta or fix the deferred gameplay backlog.

**Report a Bug now sends directly from the Client or the table without player login**, GitHub navigation or manual ZIP attachment. A private inbox receives the report with version/seed/log context. Players can review optional private diagnostics and screenshot before sending; owner credentials are never included in the game. Reports remain local if delivery fails. Reports are reviewed only when Fargrim requests a bug-review block.

Automated Card QA / Card Health / regression / simulation remains a fundamental development pillar. Corrected clauses have current source/dependency hashes and behavioral regressions. Structural candidates are not whole-card certification; the next complete card-pool audit and expansion work remain separate phases.

## Card Health

Settings -> Check Card Health shows the bundled audit checkpoint, searchable categories and known issues. It distinguishes confirmed defects, fixes in this release and upstream reports that still need reproduction. This is not a live official-data fetch or whole-card gameplay certification. Audit data is versioned with the game while user decks/preferences remain preserved.

## Credits

Rifteemo began with the complete codebase of [chorlick/alpharune](https://github.com/chorlick/alpharune). Its original engine, architecture, card implementations, rules, tests and tools are the foundation of this project; credit belongs to the original creator and contributors. The existing Git history is preserved.

[LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) supplies a separate auxiliary reference for card metadata, images, sets and errata. Dataset changes are reviewed and do not automatically change gameplay. Riftbound, its cards and artwork belong to Riot Games and the credited creators. Rifteemo is an independent community project.

The maintainer name is Fargrim. 
[Current release validation report](REPORT-v0.3.4.md) · [Branding migration report](REPORT-v0.2.7.md).
