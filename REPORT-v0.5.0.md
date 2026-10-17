# Rifteemo 0.5.0 validation report

Exact validated private source tag v0.5.0: 6d15376997c6c880c4c8eb402514432aa5fdddcf. One integrated release:
tournaments, native MD1/MD3 and sideboarding, Trophy/Shop/Collection, Legend-first
deck editing and Tourney import, authenticated Remote Play, private MD1 rooms
and mobile PWA controls. Existing Radiance cards remain included.

## Validation

- 3,140 enabled C++ regressions passed; one historical disabled test remains.
- Client, Table, reports, economy, tournament, series, remote and mobile DOM passed,
  including 127 Table cases. Real Edge touch/mouse and HTTP checks cover the
  portrait dock, legal drags, Rune choices, Might details, Battlefield totals,
  Collection, deck editor and private-room saved selection/encoded clipboard.
- Exact Windows package passed isolated Setup/private Python/launcher, repeated
  installation, native game/capture, Fargrim start/stop and same-worker console
  controls. Eight runtime restart/recovery checks passed. No compiler, global
  Python, WSL or paid model API is needed by players.
- Owner-confirmed PC/iPhone gameplay through 5G, independent player seats and
  successful reconnection. This is not a test on every mobile device.
- Actual native MD3/MD1 championships verified lifecycle and 19/9 exact game
  replays. Positive fixtures use legal power-mismatched decks and do not measure
  bot strength. Complete native gateway duels/replay and seat/privacy guards passed.
- Seventy-two Fargrim regressions passed. Atomic status tolerates transient Windows
  reader locks while preserving the preceding file on persistent failure.
  Stop requests submitted during worker initialization/bootstrap remain effective.
  New installs receive Amber Compass (13); existing private checkpoint/optimizer
  history remains authoritative. Exported weights omit private training data.

## Scope and limitations

The final clean-master four-seat runtime suite recheck passed all four tests in 34.330
seconds (an earlier complete run took 14.455 seconds). Three MCTS/ISMCTS
smoke runs exceeded their unchanged 60-second deadline; failed runs are retained. The unchanged isolated case
subsequently passed in 56.572 seconds. A separately captured four-seat match
completed in 14.69 seconds (462 decisions), with exact replay PASS; the previous
stable comparison completed in 31.56 seconds. These timings vary and do not
measure bot strength or promise a fixed response duration.

The catalog has 239 verified art variants; unsupported individual promotions
remain unavailable under the owner's approved scope decision. Import is Tourney
only. Scenario/test counts are scoped evidence, not whole-card FULL certification.
Remaining card clauses and ordinary grouped audits continue after publication.

Private rooms use Funnel rather than direct P2P. The host stays on/connected.
Guest invitations are single use and short-lived. Ordinary guests cannot read
the host library/profile/admin; prior explicit owner pairing is required to use
the host library while occupying a guest seat.

Nightly QA remains local, retained and subject to the selected 100 GB ceiling
and free-space reserve. No automatic purge, audit-record upload, autonomous rule
interpretation or blanket certification is added. The development worker needs
its built test executable, which is outside the public installer.

Runtime package SHA-256: 6591b9ddd1891f872db8e342d2b58a601c922b2e5cbbab3054aee2327d556d92.
Engine SHA-256: 521ca42f08e01f85b9a7bd538e55be9c48e1efefd50a86503b143c4302492c87.
Public native-acceptance.json retains sanitized source/package/binary provenance.
PUBLIC-UPDATE-v0.5.0.json separately records real public updater verification
after publication; a staged local package does not establish public discovery.

Maintained by Fargrim as AI-assisted, non-commercial hobby bot/QA research.
Original AlphaRune, Riot and artist credits remain preserved. Rights-holder
requests and distribution-policy context remain documented in the README.
