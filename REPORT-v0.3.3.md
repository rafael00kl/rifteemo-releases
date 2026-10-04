# Rifteemo v0.3.3 — validation and distribution report

Maintainer: **Fargrim**. Built on [chorlick/alpharune](https://github.com/chorlick/alpharune); separate card reference: [LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards). Existing history and third-party credits are preserved. No upstream push.

## Downloads

- [Release v0.3.3](https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.3.3)
- [Rifteemo-Setup.exe](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.3.3/Rifteemo-Setup.exe) — first installation; existing native clients use Check Game Updates.
- [Rifteemo.exe](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.3.3/Rifteemo.exe) — launcher for a configured installation.
- [Private source](https://github.com/rafael00kl/rifteemo)

## Delivered behavior

Recorded gameplay/engine bugs now have permanent regressions. Shared targeting and Deflect payment paths reserve base costs, pay per explicit chosen occurrence, respect resource restrictions and keep implicit event references separate from chosen targets. Triggers use actual event/source/zone context, paid additional costs and first-event snapshots. Stun attribution reaches the correct controller; Vex retains each event destination; Radiant Dawn groups simultaneous enemy Stuns. Buffed-death eligibility, Legion Play counts and special activation choices are validated.

Battlefield effects use dynamic control and individual source instances rather than physical owner/contributor. Score context carries the actual field, excess damage, attacking status and prior control. Ambush arrivals participate in combat; cleanup reconciles actual opposing presence, including after the original attacker leaves. Token Play follows normal entry/events and optional replacement, then explicit continuation/copy choices. Deceiver uses the scored Battlefield while Mirror Image stays in the controller's Base. Temporary stays on the proper created object.

Standard Move offers the Yes/No group extension before moving, paying/exhausting or opening Showdown. Eligible additional Units, Base return and Ganking follow the existing legal-action rules. Stack entries/logs identify source/controller and each public target, with per-target previews and privacy protection. Seat colors identify turns and active phases; redundant Battlefield lane labels are removed.

Report a Bug sends privately without player login. Synthetic installed reports from Client and Table were received, retried idempotently and owner-downloaded with exact SHA-256. Only those synthetic IDs were deleted; no player reports/Issues were automatically reviewed. Bundles include code identity/commit and available logs/context, not private source code or a complete executable decision replay. Optional diagnostics and screenshots remain player-reviewed.

## Validation

- 1,436 native behavioral tests passed; one preexisting disabled test.
- Four actual multiplayer runtime checks passed, including deterministic seeds and both bot classes.
- 87 Table DOM, 17 Client DOM, 11 report DOM and nine inbox-worker tests passed.
- 26 report backend, 19 Client backend and 21 Card Health tests passed, along with platform/update/package checks and deterministic smoke games.
- Native Setup, private Python/engine, launcher, real WebSocket actions and reconnect passed without developer dependencies on PATH.
- Repeated installation preserved custom decks, configuration and cache. Eight recovery/update tests, Go desktop tests and four WPF progress/rendering states passed.
- Target rendering reviewed at 1280×800 and 1920×1080; individual hover/focus/Hidden behavior has DOM coverage.
- GitHub Actions jobs could not start because of the account billing/spending limit. Release validation ran locally; this is not a successful hosted-CI claim or an independent new-PC certification.

## Audit and limits

Compiled pool: 788. FULL 5; FULL_CANDIDATE 711; PARTIAL 72; STUB 0. These are confidence categories, not a claim that all cards are completely certified. Corrected clauses carry hashes and evidence. Review hashes normalize only Git CRLF/LF differences; actual source/helper changes revoke approval. Verified artwork has zero missing/broken and one unchecked; eight ID and eight effective-text leads remain for the next whole-pool review. No new set was imported and the historical whole-card review inventory is preserved.

Version comes from VERSION. Packages/manifests/checksums are bound to clean validated master; prior assets are immutable. Windows 10/11 x64 and Microsoft Edge are required; Ubuntu/WSL, global Python and developer compilers are not needed. Updates preserve shared user data and use immutable version directories with startup recovery. Current releases deliver the complete runtime atomically; card metadata never silently hot-patches compiled rules.

## Published delivery verification

Source tag `v0.3.3` points to validated master `19479da36b00775fa0c26711d8d68ccd172f1107` ([main patch PR #13](https://github.com/rafael00kl/rifteemo/pull/13), [audit portability PR #14](https://github.com/rafael00kl/rifteemo/pull/14)). The public stable manifest uses that exact commit. Runtime package SHA-256: `d8765301ee2985803ed2c0bfa22160e662e1be7ca2684cf240bc2282b86bb9e0`. Setup SHA-256: `8618f553c2292516bb88532f83542a75ff8a9e983b5dea3829e5c5c94a9bfa8b`. All seven initial uploaded assets matched GitHub size and SHA-256 digests.

After publication, an actual isolated 0.3.2 Client detected 0.3.3 from the public latest-release endpoint, downloaded and verified the public runtime, restarted into 0.3.3 and preserved custom deck/configuration/cache sentinels and the previous runtime. The downloaded public Setup independently fetched and installed latest stable 0.3.3, started its private runtime without developer dependencies, returned 788 compiled cards and confirmed the new Client is up to date. No reboot was required. This is local isolated acceptance, not an independent physical new-PC certification.

All currently recorded Notion bug items are closed; the pending roadmap is whole-pool QA/audit, bot intelligence and tournament mode. This does not claim the software cannot contain undiscovered bugs. The historical card review inventory remains open for Fargrim’s next audit proposal.
