# Rifteemo

An independent Riftbound game project maintained by **Fargrim**. The source remains private; this public repository distributes validated Windows/WSL packages.

## Downloads

**Rifteemo v0.2.10 is available.** Download Setup below for the Windows launcher and the latest validated WSL runtime.

- [Latest stable release](https://github.com/rafael00kl/rifteemo-releases/releases/latest)
- [Rifteemo-Setup.exe](https://github.com/rafael00kl/rifteemo-releases/releases/latest/download/Rifteemo-Setup.exe)
- [Private source project](https://github.com/rafael00kl/rifteemo)
- [Historical AlphaRune v0.2.6 downloads](https://github.com/rafael00kl/alpharune-releases/releases/tag/v0.2.6)

## Installation and updates

For first installation, use **Rifteemo-Setup.exe**. **Rifteemo.exe** is the launcher for an existing configured installation. The new Setup displays the current stage, download percentage, elapsed time and clear success/error/restart messages.

Run Setup on Windows x64. It checks Microsoft Edge, prepares Ubuntu 26.04 x86_64 in WSL and runtime prerequisites when needed, downloads the latest stable package and verifies SHA-256. WSL may request administrator permission and a restart. No GitHub login is needed for public downloads.

In the game, open Settings -> Check Game Updates -> Install Update & Restart. Finish matches and save decks first. Updates retain shared decks, configuration/cache and previous runtime versions. Developer source checkouts are protected.

Existing AlphaRune clients keep their original update endpoint as a migration bridge. Close the old game and run the new Rifteemo Setup once for the renamed Windows launcher and shortcuts. Existing managed WSL data is reused. Historical release assets are never overwritten.

## Latest update

Version 0.2.10 fixes immediate resource resolution, discard triggers and Unit destinations. The Table UI gains clearer status/Equipment indicators, persistent stack, hover zoom and larger Runes. The client gains match-end return, six clear bot difficulties and correct custom-port routing. Existing users can update from Settings without reinstalling their environment.

## Card Health

Settings -> Check Card Health shows the bundled audit checkpoint, searchable categories and known issues. It distinguishes confirmed defects, fixes in this release and upstream reports that still need reproduction. This is not a live official-data fetch or whole-card gameplay certification. Audit data is versioned with the game while user decks/preferences remain preserved.

## Credits

Rifteemo began with the complete codebase of [chorlick/alpharune](https://github.com/chorlick/alpharune). Its original engine, architecture, card implementations, rules, tests and tools are the foundation of this project; credit belongs to the original creator and contributors. The existing Git history is preserved.

[LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) supplies a separate auxiliary reference for card metadata, images, sets and errata. Dataset changes are reviewed and do not automatically change gameplay. Riftbound, its cards and artwork belong to Riot Games and the credited creators. Rifteemo is an independent community project.

The maintainer name is Fargrim. The GitHub account identifier appears only where required for repository/download routing.

[Current release validation report](REPORT-v0.2.10.md) · [Branding migration report](REPORT-v0.2.7.md).
