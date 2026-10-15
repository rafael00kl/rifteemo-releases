# Rifteemo 0.4.4 validation report

Stable native Windows release: owner-controlled Overnight Card QA and optional local report handoff.

## Source and behavior

Exact validated private master/tag v0.4.4: 1f4fd97521facb67dd6828b528731d74af243cb1. PR #27 implements the controller/report integration; PR #28 fixes safe cancellation during calibration. Public distribution remains in this repository; private source has a tag, not a GitHub Release.

QA-Night.cmd in the development checkout reuses the existing reviewed native scenario/replay/reducer, regression planner, whole-pool helper/mechanic inventory, context preparation, execution-scope index and advanced QA console. It provides adjustable duration, cases, measured workers and retained-disk budget, persistent seeds/session evidence and linked HTML status/review queues. Temporary idle-sleep prevention is released at exit and does not edit the power plan. The default is eight hours and 2,000 generated cases per round; no overnight workload starts automatically.

Report a Bug shows an unchecked optional local copy/card selector only while a fresh local QA heartbeat is active. Public Legends, additional Legends, Champion and board cards are available; hidden/private card identities are excluded. The original ZIP/seed/context and normal anonymous inbox submission are preserved. Mapped tests run before the next ordinary batch; missing adapters stay UNMAPPED. Related helpers, cards, mechanics and keywords are candidates for review. Diagnostic context plus a seed is not a complete executable match replay; exact_match_reproduced remains false.

The owner tool needs the development test executable. The public installer remains one game client and does not bundle compilers/native test executables. No gameplay/card behavior, Fargrim lineage or approved model was changed by this release.

## Executed validation

- Final source Windows build and complete relevant validation passed: 3,120 enabled C++ tests; one historical disabled test remains disabled. Four real multiplayer checks and two random smoke games passed.
- Owner/controller tests (29), local bridge tests (10), scenario tests (19), bug-report tests (26), client tests (22), Fargrim tests (65) and Card Health tests (24) passed in final validation. A separate overlapping focused suite of 104 checks exercised controller, cancellation, bridge and related QA behavior; counts are not added together as independent coverage.
- Shared form DOM checks (13) and table DOM checks (104) passed; actual shadow-root report form and the HTML status page were inspected through rendered Edge images.
- Final bounded owner run: one round of 2,000 generated fixture configurations passed, including deterministic replay, native regression gate, grouping/context preparation and dashboard refresh. These are the ten configured reviewed scenario families and 27 configured cards, not 2,000 whole-card certifications.
- Calibration tested 1/2/4/6/8 workers with memory reserve on the current detected hardware. The final workload recommended four for unattended use; eight was the highest tested passing count. Recommendations vary with workload and concurrent load. No thermal/GPU or whole-PC universal safety guarantee is claimed.
- A real native match exposed sanitized public board choices, queued an explicitly selected card locally, preserved the original ZIP/64-bit seed and executed mapped checks. No inbox upload occurred in this dedicated local-handoff probe; the heartbeat cleared at exit.
- Exact final master development and stable archives passed real isolated native Setup/launcher/private-Python, game/WebSocket/reconnect, Card Health, bundled training start-stop and persistent-data checks. Eight runtime recovery tests passed against both candidates; unchanged installer rendering/state checks passed earlier against the same desktop binaries.
- Installed Client and Table reports sent without player credentials; exact synthetic private receipts were verified and only those test reports removed.
- The public 0.4.3 client actually downloaded 0.4.4, restarted, reported up to date and accepted four-seat actions. Decks, configuration/cache, checkpoint weights, optimizer and succession history were preserved byte for byte. Metadata/download requests used no player credentials. See PUBLIC-UPDATE-v0.4.4.json.
- All ten immutable release asset sizes and GitHub SHA-256 digests were verified against local bytes. SHA256SUMS covers the other nine assets.

## Scope and limits

The nightly program executes known assertions and prepares evidence; it does not invent reliable rule interpretations, patch cards, approve canonical mechanics, poll the private inbox/Issues, upload local audit records, call a paid API, train OSS or promote cards to FULL. More seeds explore configured domains rather than certify unmapped behavior. All original campaign receipts are retained; the materialized execution index bounds itself to the latest ten campaigns of a session.

Failures are grouped as hints and bounded reductions retain their original context. Aborted trials/shards are incomplete evidence. Source/binary/reference changes invalidate reuse and stop active work. Whole-card clause gaps and unrelated bugs remain pending; this infrastructure release does not claim that the complete backlog is resolved. Human rule/gameplay/UX review remains essential. Audit-time savings will be assessed from actual review work rather than inferred from passing counts.

Validation was performed locally on Windows and isolated installed runtimes. No independent second-PC or successful remote Actions result is claimed. Historical assets and upstream are unchanged. Maintained by Fargrim; original AlphaRune, Riot and artist credits remain preserved.
