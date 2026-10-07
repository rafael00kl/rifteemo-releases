# Rifteemo v0.4.1 validation report

Maintainer: **Fargrim**. Source checkpoint: `ade5d44af038bbfa4e0c5224323235b65bd5aabc`. One native Windows client; source repository remains private.

## Delivery

[Release and assets](https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.4.1) · [First-install Setup](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.4.1/Rifteemo-Setup.exe) · [Source project](https://github.com/rafael00kl/rifteemo).

Existing native installations: **Client → Check Game Updates → Install Update & Restart**. `Rifteemo.exe` is the launcher; first installation requires Setup. Windows 10/11 x64 and Edge; no Ubuntu, global Python, compiler or reboot normally required.

## Changes

Shared card corrections cover Ambush, exhausted Gold, death replacement/Recall, Equipment-granted Deathknell, token cessation, enemy-choice history, optional/collective targeting, private Look/selected Draw, instructed permanent play and chosen damage trigger finalization. Public effect/target history and player-colored turn/phase presentation are clearer. Canonical mechanic contracts map helpers, affected cards and reusable tests.

Learning/Fargrim's tactical-v2 combines public strategic evaluation with learned scoring and uses the pending instruction context for target choices. Training retains the best held-out iterate, including the parent, and avoids arena evaluation of unchanged candidates. This does not reset or automatically replace an approved local model. Persistent decks, preferences, caches, episodes, training data, optimizer/checkpoints and generation names remain shared across runtime versions. Weights remain fixed during a match.

## Validation

- 2291 native C++ tests executed PASS; 1 pre-existing disabled test, no exclusions added.
- Backend client/report/episode/update/Card Health/Fargrim/QA suites PASS; 97 Table DOM, 44 Fargrim controller, 2 portable-trainer and 62 semantic QA checks also passed in targeted validation.
- Four actual multiplayer runtime cases and seeded random smoke games PASS.
- Exact stable archive passed actual native Setup/reinstall preservation, private Python/NumPy startup, launcher and native engine, all client bot profiles, episode capture, trainer start/stop and unchanged approved pointer.
- Eight native restart/recovery/install checks PASS; four WPF Setup progress/error state checks PASS.
- Installed Client and Table sent synthetic reports anonymously and verified their private ZIP hashes, exact receipts and idempotent retries. No player credential required.
- Package SHA-256: `6a124041ebf880bd8203acb4457456a430e495b56faadf4d43efc77a2ce46a16`. Public `native-acceptance.json` redacts temporary installation paths while retaining the exact binary/package/commit digests.
- The public 0.4.0→0.4.1 updater verification is attached separately after publication as `PUBLIC-UPDATE-v0.4.1.json`.

Hosted GitHub Actions did not start jobs and is **not** declared passed. The local native release pipeline passed. A second independent computer was not tested during this release.

## Bot evidence and limits

24 complete valid paired games with a frozen P5 checkpoint: tactical-v2 vs MCTS150 4W/4L; legacy-v1 vs MCTS150 2W/6L; tactical-v2 vs legacy-v1 3W/5L. Tactical-v2's MCTS panel had decision P95 2,686ms, maximum 7,524ms. Small samples do not establish general superiority or warrant automatic model promotion. The training experiment selected its unchanged parent when all measured iterates had worse validation loss. No OSS inference or weight fine-tuning included.

## Audit scope and remaining work

954 local compiled printings. Bundled audit: 881 FULL_CANDIDATE, 73 PARTIAL, zero STUB, two mapped BUGGED cards. No fresh artwork check: 954 ART_UNCHECKED. External counts include variants and do not represent unique unimplemented cards. Historical FULL reviews remain preserved, but shared component changes leave approvals stale until their exact scope is revalidated; this snapshot has zero current whole-card FULL approvals.

A fix or regression PASS approves its tested clauses, not every clause of a card. Valid source/rule/helper evidence and existing regressions are reused in subsequent audits; changed or uncovered clauses receive additional review. Stalking Wolf (#81), Repeat (#88), historical container replays (#75) and remaining backlog work stay pending.

## Credits

Rifteemo began from [chorlick/alpharune](https://github.com/chorlick/alpharune), retaining the original code/history/credits. [LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) supplies a separate auxiliary metadata/art source. Riftbound and artwork belong to Riot Games and their credited creators.
