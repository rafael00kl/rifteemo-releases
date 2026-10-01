# Rifteemo v0.2.8 — client startup and installer progress

Maintainer: **Fargrim**. Source commit: 497616c49c2b0eaeae682e145e3e59cbaaa63654. Version comes from VERSION.

The approved [PR #5](https://github.com/rafael00kl/rifteemo/pull/5) passed [GitHub CI](https://github.com/rafael00kl/rifteemo/actions/runs/36822379940). The merged master tree matches the validated PR tree, and the exact merge commit was revalidated locally before stable packaging.

The previous 15-second desktop heartbeat lease was reproduced expiring after 16.8 seconds. The new 90-second lease, independent heartbeat and busy-operation protection address that lifecycle failure. Startup waits for engine HTTP and Windows-side readiness; duplicate starts remain disabled until the first attempt completes. Error messages are actionable and a failed Human attempt can be retried as Bot.

Fargrim additionally reported an immediate failure and later reported that games worked again. That immediate failure was not independently reproduced. Human-first is a hypothesis, not a confirmed gameplay defect. Backlog #23 remains pending for real desktop acceptance; #14 is resolved for installer feedback. The in-match heartbeat still assumes client port 8090; custom client-port routing remains a known pre-existing follow-up in #23.

The existing Go bootstrapper now uses a WPF progress window. It shows current stage, active animation or measured download progress, elapsed time and log access. Success, error and restart-required states are rendered separately. Closing is prevented during installation; minimizing is supported. Installer and game runtime remain separate, so an older bootstrapper can still install a newer stable runtime.

Validation passed: 1,066 C++ tests in 117 suites (one pre-existing disabled), 37 Python tests, 36 Table UI DOM checks, six client DOM regressions and two deterministic smoke games. Real client JavaScript with Windows HTTP requests to the real WSL engine exercised Human/Human, Human/ISMCTS and MCTS/MCTS in that order in one client after an 18-second timer pause. Each engine started and served the Table UI.

Four WPF state/rendering checks passed; download and restart renderings were inspected. Actual Windows Setup.exe checks used isolated directories: public release download with 1–100% progress, resume without redownload, local 0.2.8 installation and corrupt-package rejection before activation. User deck/settings sentinels survived. Exact stable-package and public-network checks are appended after completion.

The Windows UI inspection helper was unavailable. State/render, HTTP and DOM checks do not certify every native Edge window or a fresh-machine WSL/UAC/reboot sequence. The existing prerequisite provisioning logic was retained.

Runtime package SHA-256: 85b62bad841c10bfce13cc26576ec1c002ba34d3ab6887d21188557d82e6a4c9. Checksums for the package, installer, launcher, manifest and documentation are in SHA256SUMS. Previous releases and user data are retained. No upstream push or source-code publication occurred. No gameplay/card implementation changes, redundant full-project backups or nested auxiliary repositories were introduced.

## Downloads

- [Rifteemo-Setup.exe — first installation](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.2.8/Rifteemo-Setup.exe)
- [Rifteemo.exe — launcher](https://github.com/rafael00kl/rifteemo-releases/releases/download/v0.2.8/Rifteemo.exe)
- [Package, manifest, checksums and notes](https://github.com/rafael00kl/rifteemo-releases/releases/tag/v0.2.8)
- [Private source release](https://github.com/rafael00kl/rifteemo/releases/tag/v0.2.8)

Rifteemo is built on the complete original [chorlick/alpharune](https://github.com/chorlick/alpharune) foundation, preserving original credits and history. Auxiliary card data: [LouisCourrian/riftbound-cards](https://github.com/LouisCourrian/riftbound-cards). Authentic card/artwork ownership and credits remain preserved.

## Exact stable package checks before publication

Actual Windows Setup passed download, resume, local stable install and corrupt-package rejection. The Windows launcher served the genuine 0.2.8 runtime and shut down correctly. The client HTML and JavaScript served from the genuine stable package also passed immediate Human/Human → Human/ISMCTS → MCTS/MCTS starts with Windows HTTP requests to the WSL engine. This complements the earlier delayed-timer regression; it does not certify every native Edge window.
