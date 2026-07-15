# Changelog

All notable WAJetsamFix releases and validated development milestones are documented here.

Historical entries are retained to show how the project progressed from early experiments to the current stable architecture. Only the latest stable Release provides a downloadable package.

## [0.7.1] — 2026-07-14

### Final stable release

- Promoted the field-approved 0.7.1 RC1 runtime without changing the protection logic.
- Restored the minimal candidate-first path: unrelated requests pass through before target inspection.
- Retained the diagnostics, safety checks and lifecycle hardening developed throughout the 0.7 line.
- Preserved the exact WhatsApp notification `ServiceExtension` target and exact 24 MB → 40 MB policy.
- Contains no polling daemon, periodic scan, timer, repair loop, fallback enforcement or global Jetsam modification.

### Final field validation

- 1,003 successful rewrites from 1,003 attempts.
- Zero rewrite failures.
- Zero compatibility warnings.
- Normal first-message, sequential and burst notification delivery.
- No observed delay or single-tick episode attributable to Jetsam.
- Approximately 0.0% diagnostics-bridge CPU while idle.

## [0.7.1-rc1] — 2026-07-14

### Conservative runtime correction

- Removed the unnecessary broad compatibility inspection retained by 0.7.0.
- Ensured that non-24 MB requests return directly to iOS before target-path validation.
- Kept malformed and unrelated requests unchanged.
- Preserved safe handling of known and unknown request layouts.
- Retained the complete 0.7 diagnostics and hardening foundation.

### Field gate

- Installed over 0.7.0 after a full reboot and fresh jailbreak session.
- First-message, sequential and burst delivery remained normal.
- Extended testing reached 1,003 successful rewrites with zero failures and zero warnings.
- Approved for stable promotion without runtime changes.

## [0.7.0] — 2026-07-14

### Hardening foundation

- Consolidated runtime version, target and diagnostic state handling.
- Made hook-install reporting authoritative and resistant to false-positive states.
- Added safer request validation and independently testable policy behavior.
- Added sparse success, failure and compatibility diagnostics.
- Corrected diagnostic state across `runningboardd` lifecycle changes.
- Added the non-resident `wajetsamfixctl status` command.
- Hardened the local log with restricted permissions, symbolic-link protection and event-driven rotation.
- Removed unnecessary resident dependencies and background relaunch behavior.
- Expanded automated policy tests and package auditing.

### Superseded behavior

- Included a bounded compatibility inspection path for unexpected requests.
- No deterministic failure was proven, but post-release review found the extra synchronous work unnecessary for the supported scope.
- Superseded by 0.7.1, which retained the hardening while restoring the narrower candidate-first runtime.

## [0.7.0-rc1] — 2026-07-14

- Promoted the Alpha 2 runtime without redesigning the protection path.
- Validated direct upgrade from Alpha 2.
- Validated Safe Mode prevention and normal recovery.
- Validated complete uninstall and clean reinstall.
- Completed a mixed-notification gate exceeding 50 rewrites.
- Recorded zero rewrite failures, zero unexpected warnings and no notification loss, delay or single-tick episode during the gate.
- Confirmed approximately 0.0% idle CPU.

## [0.7.0-alpha2] — 2026-07-14

- Corrected retained diagnostic state across new `runningboardd` instances.
- Cleared hook, rewrite, failure and compatibility state for each new source lifecycle.
- Required current-process state before reporting confirmed protection.
- Validated two consecutive source-process changes.
- Confirmed clean zero counters before the first matching request of a new lifecycle.
- Recorded 16 successful rewrites from 16 attempts, with zero failures and zero warnings.
- Confirmed approximately 0.0% idle CPU.

## [0.7.0-alpha1] — 2026-07-14

- Introduced explicit PatchLoader and source-hook states.
- Prevented a successful library load from masking a hook-install failure.
- Added safer request handling and sparse compatibility diagnostics.
- Added the non-resident status command.
- Hardened and bounded the runtime log.
- Removed unnecessary relaunch behavior from the diagnostics bridge.
- Reduced resident dependencies and expanded automated validation.
- Completed more than 300 successful source-side rewrites with zero failures and zero compatibility warnings.
- Observed no delay or single-tick episode and approximately 0.0% idle CPU.

## [0.6.2] — 2026-07-13

- Final stable release of the original pure source-side candidate-first design.
- Corrected diagnostic state across `runningboardd` restarts and source lifecycles.
- Tied source readiness and counters to the active source process.
- Preserved the exact WhatsApp notification-extension target and exact 24 MB → 40 MB policy.
- Removed obsolete polling-era source files from the active project tree.
- Became the proven fallback baseline used to evaluate the later 0.7 work.

## [0.6.1] — 2026-07-13

- Removed the polling enforcement daemon, watchdog and recurring repair loops.
- Retained only the PatchLoader entry, source hook and event-driven diagnostics bridge.
- Validated more than 30 messages with zero loss, delay or single-tick episodes.
- Confirmed 25 source-side rewrites for the exact target.
- Confirmed approximately 0.0% diagnostics-bridge CPU.

## [0.6.0] — 2026-07-13

- Introduced RootHide PatchLoader integration and early source-side interception inside `runningboardd`.
- Added dynamic jailbreak-root discovery and Safe Mode checks.
- Proved that the source-side path applied the target correction before the temporary compatibility path detected the process.
- Validated 32 source-side rewrites for the exact WhatsApp target.
- Established the architecture that replaced polling-based enforcement.

## [0.5.1] — 2026-07-12

- Replaced sandbox-dependent diagnostic file writes with event-driven state delivery.
- Added a lightweight root diagnostics bridge.
- Confirmed that ordinary tweak loading did not place the source hook inside `runningboardd`.
- Preserved working notifications through the compatibility path while the early-loading problem was investigated.
- Provided the diagnostic evidence needed for the PatchLoader architecture introduced in 0.6.0.

## [0.5.0] — 2026-07-12

- Introduced the first filtered source-side interception attempt through ordinary tweak loading.
- Retained the complete 0.4.1 compatibility path until source-side ownership could be proven.
- No source-side rewrite was confirmed in this version.
- Demonstrated that a working compatibility layer could conceal an inactive experimental source path.

## [0.4.1] — 2026-07-12

- Produced the stable polling compatibility baseline for the tested environment.
- Removed continuous metrics and repeated identity checks while retaining rapid targeted enforcement.
- Added event-driven process-exit tracking and sparse diagnostics.
- Recorded 164 successful applications or corrections and zero failures over approximately 53 minutes.
- Delivered reliable notifications, but visible resident CPU use remained because polling was still required.

## [0.4.0] — 2026-07-11

- Raised the target active and inactive limits from 32 MB to 40 MB.
- Added focused process metrics to validate memory headroom, lifecycle and resource behavior.
- Confirmed that the original 24 MB ceiling was insufficient for the affected environment.
- Delivered reliable notifications, but continuous diagnostics and polling were too expensive for the final design.

## [0.3.0] — 2026-07-11

- Replaced fixed global monitoring with adaptive enforcement tied to the active target process.
- Applied and verified a 32 MB limit when iOS restored the original 24 MB value.
- Reduced unnecessary global work.
- Greatly improved delivery reliability, although an occasional single-tick episode remained.

## [0.2.0] — 2026-07-11

- Replaced the unsuccessful injected-client design with a standalone root process.
- Added direct discovery of the exact WhatsApp notification `ServiceExtension`.
- Restored notifications with targeted 32 MB enforcement.
- Proved the central memory-limit hypothesis.
- Fixed 100 ms polling was effective but too expensive for long-term use.

## [0.1.0] — 2026-07-11

- Initial rootless injected-client and privileged-process architecture.
- The privileged component started, but the client connection did not complete.
- No memory-limit change reached the target.
- Established the first experimental baseline for the investigation.
