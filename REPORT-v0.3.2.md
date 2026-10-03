# Rifteemo 0.3.2 — Match setup and automated QA foundation

Maintained by **Fargrim**. [Source project](https://github.com/rafael00kl/rifteemo) remains private.
[Source PR #10](https://github.com/rafael00kl/rifteemo/pull/10).
Exact distributed master/source tag: 416b4166c9e6e48910854a273999ce4751d87929 / v0.3.2.

## Delivered gameplay and UI

- Duel and four-player FFA use a visible D20 roll-off. Only tied highest seats reroll.
  The winner chooses any first seat, including an opponent.
- Seats remain fixed. Turn order is clockwise: selecting P3 in FFA4 gives P3 → P4 → P1 → P2.
- BO1 shows all seats' three battlefield candidates for inspection, then uses the engine's
  Random Choose action. Clicking a candidate only inspects it.
- The first FFA4 seat contributes no battlefield and receives a clear explanation.
  Battlefield setup states whether you go first, second, third or fourth.
- A gold table outline and Current turn label mark the turn owner independently of
  priority/focus and another player's decisions.

No mass card implementation, unrelated gameplay fixes, engine rewrite or network multiplayer.

## Fundamental QA pillar: first planning delivery

Automated Card QA / Card Health / regression / simulation is a fundamental project pillar
in Notion #13. The existing audit, fixtures, registry, dataset, legal actions and replay/search
foundations are reused. The first delivery is inventory, dependency candidates, architecture
and small execution blocks, not the entire proposed QA implementation.

[Technical architecture and reusable tools](https://github.com/rafael00kl/rifteemo/blob/master/docs/automated-card-qa.md)
and [initial card/helper/test/historical-bug map](https://github.com/rafael00kl/rifteemo/blob/master/docs/qa/initial-inventory.json).
787 source cards; 78 C++ test files; raw declarations are not behavioral coverage.
Direct candidates include 117 pickTarget, 84 confirmOptional, 48 readyObject and 64 dealDamage uses.
Static extraction may miss inherited/indirect calls or include comments; it is not certification.

Planned blocks: inventory/evidence → mechanic/dependency map → semantic/suspicious-pattern audit →
reviewed scenario generator and FAST/FULL mechanic suites → boundary-aware invariants →
native mass simulations/failure capture → portable deterministic replay/minimization →
incremental health/coverage/report integration and structured logs.

First recommendation: a small QA-1/QA-2 selection/Ready/repeated-instruction batch related
to #41/#46, then restricted/delayed resources #37/#38. Investigate shared causes, reproduce,
fix and retain minimal regressions plus representative sibling tests. Human rules/gameplay/UX
testing remains essential. New GitHub Issue triage only happens in an expressly authorized
bug-review block; no automatic Issue monitor was added.

Card Health revalidated: 787 local / 1,188 pinned auxiliary printing records;
FULL 0, FULL_CANDIDATE 699, PARTIAL 88, STUB 0, BUGGED 5 currently recorded,
MISSING 190, NEW_OFFICIAL 189, ID mismatches 23, errata-text differences 8, NEEDS_REVIEW 977.
Categories overlap; newly reported pending bugs are not all included in the old BUGGED count.
Art 0/0/0 reuses dated September 30 probes, not a fresh scan of all remote images.
FULL requires current hash-bound rule/test evidence; compiling or having tests is insufficient.
Broader QA tools, pending card bugs, semantic certifications and Teach Mode remain pending.

## Validation

The exact master passed 1,174 C++ tests (one pre-existing disabled test), backend/infra checks,
17 client + 59 table + 9 report DOM scenarios, deterministic bot simulations and four complete
real-executable multiplayer scenarios including full UInt64 repeated seeds and MCTS/ISMCTS.
Real isolated Edge checks at 1280×800 and 1920×1080 exercised duel/FFA4, read-only candidates,
all candidates in view, starting-seat choices, order explanations, turn outlines and public
report privacy. Paths selecting the opponent in duel and P3 in FFA4 were exercised.

Native package acceptance passed Setup/launcher/private Python, real HTTP/WebSocket actions,
reconnection, preserved shared data, eight restart/recovery tests and four WPF rendering states.
Package, source inputs, executable and shell hashes are bound to the distributed revision.
An independent second-PC exploratory test is still recommended.

Hosted Actions jobs did not start because GitHub reported account billing/spending-limit
restrictions. No hosted CI pass is claimed and no paid usage was enabled.
The full local Windows pipeline is the release gate.

## Download and update

First installation: [Rifteemo-Setup.exe](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.3.2/Rifteemo-Setup.exe).
Existing native installation: Settings → Check Game Updates → Install Update & Restart.
Rifteemo.exe is the launcher for an already configured installation.

Windows 10/11 x64 with Edge; no Ubuntu/WSL, global Python or compiler needed to play.
Normally no administrator access or reboot. Public downloads require no GitHub login.
Decks, preferences, cache and previous runtime versions remain preserved.
Older Setup versions can continue installing the latest native stable game package.

Package: Rifteemo-v0.3.2-windows-10+-x86_64.tar.gz
SHA-256: 484d9d7bb74d1569bbf11b86b712e990474289e74bebb03108481caa5821af06 (77215683 bytes).
Historical release assets are not overwritten. Actual anonymous stable downloads, Setup and
public 0.3.1 → 0.3.2 update results are recorded afterward on this report page.

## Credits

Rifteemo started from the complete [chorlick/alpharune](https://github.com/chorlick/alpharune)
engine, architecture, cards, tests and tools. Original history and credits are preserved.
[LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards) is the separate
auxiliary metadata/art reference; official current rules and errata take precedence.
Riftbound/cards/artwork belong to Riot Games and the credited creators.
No push to upstream.
