# Rifteemo

Rifteemo is a personal, **AI-assisted ("vibe-coded") hobby and research project** maintained by **Fargrim**. Its primary development goals are **experimental game-playing bots** and **automated software auditing, scenario generation and regression testing**. The Riftbound simulation engine and client provide the environment in which those experiments run.

## Primary development goals

### Bot research and local learning

The Fargrim Learning loop imports compatible local match episodes, gives additional weight to human demonstrations, and generates varied games against Monte Carlo Tree Search (MCTS), the active model and historical checkpoints. It rotates decks and seats, trains a candidate, and compares it with the active bot and a fixed MCTS reference before accepting or rejecting it. Approved successors retain their own name and generation; rejected candidates leave the active model unchanged.

Training is optional and runs on the owner's computer. Episodes, evaluation reports and checkpoint history persist locally across updates. A match uses fixed model weights; a later match can load a newly approved successor. More simulations or training cycles do not guarantee stronger play. This is experimentation with learned evaluation and search, not a claim of general intelligence or mastery of every rule.

### Automated QA and scenario research

The Card QA tools group cards by shared mechanics and code helpers, link reviewed behavioral contracts to tests, and generate variations of supported scenarios. Native regressions, deterministic replays and retained seeds/decision traces help reproduce failures and locate affected consumers. The owner-run overnight worker saves evidence and prepares review context so future fixes and audits can reuse verified work.

This automation is bounded by its implemented tests and reviewed scenario families. Passing a generated scenario does not certify an entire card, and the worker does not independently interpret every rule, approve FULL certification or automatically patch the engine. Uncovered clauses and human interpretation remain explicit review work.

## Hobby status, non-commercial intent and third-party rights

This is an informal educational/personal software experiment, not an institutional research program or an official Riot product. There is **no plan for a commercial launch, sale or profit**: no paid access, advertisements, subscriptions or real-money cosmetic purchases. In-client Trophies and cosmetic unlocks have no monetary value or cash redemption. Existing public downloads are experimental hobby builds; their availability does not imply Riot approval.

Rifteemo is an **independent, unofficial project with no official connection to Riot Games**. Riftbound, League of Legends, characters, card text, artwork and associated trademarks remain the property of Riot Games and their respective owners. Original artist and upstream contributor credits must be preserved. This repository does not grant rights to third-party assets.

**Requests from Riot Games:** If Riot Games requests it, the maintainer is willing to remove affected material, remove the project from GitHub or make the project repositories private without objection. This willingness does not imply that permission has already been granted.

The research/hobby description is a statement of intent, **not a license or a claim of policy compliance**. Riot's [Riftbound Digital Tools Policy](https://developer.riotgames.com/docs/riftbound), [Riftbound developer policies](https://developer.riotgames.com/policies/riftbound) and [Legal Jibber Jabber](https://www.riotgames.com/en/legal) still apply. In particular, Riot restricts standalone Riftbound clients with automated rule enforcement; a free or academic label does not remove those restrictions. No authorization for Rifteemo is asserted here.

The source remains private. This public repository contains experimental Windows packages, update instructions and preserved historical compatibility releases. The development checkout has additional QA tools; availability in a particular installer is described below.

## Downloads

**Rifteemo v0.4.4 — Overnight Card QA and optional local report handoff.** Download Setup for first installation; existing native clients can use Check Game Updates.

- [Latest stable release](https://github.com/rafael00kl/rifteemo-releases/releases/latest)
- [Rifteemo-Setup.exe](https://github.com/rafael00kl/rifteemo-releases/releases/latest/download/Rifteemo-Setup.exe)
- [Private source project](https://github.com/rafael00kl/rifteemo)
- [Historical AlphaRune v0.2.6 downloads](https://github.com/rafael00kl/alpharune-releases/releases/tag/v0.2.6)

## Installation and updates

For first installation, use **Rifteemo-Setup.exe**. **Rifteemo.exe** is the launcher for an existing configured installation. Setup displays the current stage, download percentage, elapsed time and clear success/error messages.

Run Setup on Windows 10/11 x64 with Microsoft Edge. It installs private Python and the native game runtime per user, downloads the latest validated Windows package and verifies SHA-256. Ubuntu, WSL, MSYS2, compilers and global Python are not required to play. Installation normally needs no administrator access or reboot. Public downloads require no GitHub login.

In the game, open Settings -> Check Game Updates -> Install Update & Restart. Finish matches and save decks first. Updates retain shared decks, configuration/cache and previous runtime versions. Developer source checkouts are protected.

Existing WSL users should close the old client and any match, then run the new Rifteemo Setup once to migrate. Decks, settings, cache and the browser profile are preserved; the old WSL runtime is left intact. Later native updates use the client update flow. Version 0.4.4 is native Windows only. The historical [0.3.0 WSL compatibility release](https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.3.0) remains available; migrate with Setup before subsequent native updates. Existing AlphaRune clients retain their original branding migration bridge. Historical release assets are never overwritten.

Do not remove or unregister Ubuntu until any development checkout, external card dataset and local-only files inside it have been moved and verified. The native game no longer needs WSL, but removing the distribution can delete files used for development.

## Latest update

Version 0.4.4 adds **all 167 Radiance main-set cards**, plus the registered Bomb token, alongside the existing card pool. Shared Deploy, Show Off, Disarm, combat-lifetime grants, targeting and token play use the current engine. Neeko, Blending In supports up to three private deckbuilding Legend choices, source-bound additional Legends and visible, inspectable Legends on the table.

Card Health contains 1,122 registered printings. Radiance registration and scoped shared-mechanic reviews are recorded with source/test evidence; the expansion is **not fully certified clause by clause**. Historical reviews are preserved, and changed shared dependencies remain visible for revalidation. Known reports and the remaining audit are not declared finished.

The client displays **only the current approved bot's exact name and generation**. New installations receive **Amber Anchor (8)**. An existing private active checkpoint and training lineage take precedence; later locally approved successors appear by their own names in new matches, without resetting the client or a match in progress. Internal Normal/MCTS 150 and Original agents remain available to training and test tools.

Run **Fargrim-Learning.cmd** in the installed active runtime folder to start, inspect, stop or resume the local learning loop. Default path: %LOCALAPPDATA%\Rifteemo\runtime\versions\0.4.4\Fargrim-Learning.cmd. Stop training safely and restart it after updating to load the current trainer. Episodes, optimizer, approved checkpoints and succession history persist. Only portable approved weights are distributed; private training records are not uploaded.

The loop imports eligible records, prioritizes human decisions, generates varied duels, trains a candidate and evaluates it against the active checkpoint and Normal/MCTS before approval or rejection. It keeps the active model when a candidate fails the gates. An approved successor receives a name and generation number; episodes, lineage and approved checkpoints survive game updates. There is no guarantee of improvement in every cycle.

All client matches can save private local episodes under persistent `.alpharune-client/learning/episodes/duel` or `ffa4`. Incomplete, incompatible and four-player records are preserved but excluded from current duel training. Four-player learning remains pending; those records stay separate. Training is local and starts only when you activate the loop; records are not automatically uploaded.

**Report a Bug sends directly from the Client or the table without player login**, GitHub navigation or manual ZIP attachment. A private inbox receives version/seed/log context. Players can review optional private diagnostics and screenshot before sending; owner credentials are never included in the game. Reports remain local if delivery fails. Reports are reviewed only when Fargrim requests a bug-review block.

Automated Card QA / Card Health / regression / simulation remains a fundamental development pillar. The source project's [mechanics guide](https://github.com/rafael00kl/rifteemo/tree/master/mechanics) defines one gradual contract format for future labs and authorized card work. The guide alone does not certify mechanics or cards, and the release adds scoped contracts linking reviewed rules, helpers, affected cards and reusable regressions. Existing valid clause evidence is reused; changed or uncovered clauses are reviewed separately.
## Owner-controlled overnight QA

The development checkout provides **QA-Night.cmd**: start/resume, safe stop, progress dashboard, editable limits, measured worker calibration and the existing advanced QA tools. It runs native regressions and varied reviewed fixtures, checks deterministic replay, groups findings, prepares shared context and stores local evidence for later review. A built native test executable is required; the public game installer does not include the development test build or compiler.

While that local worker is active, **Report a Bug** offers an optional unchecked private-copy checkbox and a public-card selector. Normal anonymous report delivery remains unchanged. Local copies preserve context/seed and run applicable mapped checks; seed alone does not recreate the original match. Unmapped behavior stays pending.

No local audit uploads or paid model API are needed. The script does not automatically fix cards, approve FULL, poll the inbox or change canonical mechanics. See the private source [overnight guide](https://github.com/rafael00kl/rifteemo/blob/master/docs/overnight-qa.md) for controls, resource limits and evidence locations.

## Card Health

Settings -> Check Card Health shows the bundled audit checkpoint, searchable categories and known issues. It distinguishes confirmed defects, fixes in this release and upstream reports that still need reproduction. This is not a live official-data fetch or whole-card gameplay certification. Audit data is versioned with the game while user decks/preferences remain preserved.

## Credits

Rifteemo began with the complete codebase of [chorlick/alpharune](https://github.com/chorlick/alpharune). Its original engine, architecture, card implementations, rules, tests and tools are the foundation of this project; credit belongs to the original creator and contributors. The existing Git history is preserved.

[LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) supplies a separate auxiliary reference for card metadata, images, sets and errata. Dataset changes are reviewed and do not automatically change gameplay. Riftbound, its cards and artwork belong to Riot Games and the credited creators. Rifteemo is an independent community project.

**Requests from Riot Games:** If Riot Games requests it, the maintainer is willing to remove affected material, remove the project from GitHub or make the project repositories private without objection. This willingness does not imply that permission has already been granted.

The maintainer name is Fargrim. 
[Current release validation report](REPORT-v0.4.4.md) · [Branding migration report](REPORT-v0.2.7.md).

