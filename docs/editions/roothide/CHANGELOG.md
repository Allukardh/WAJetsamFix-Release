# WAJetsamFix — RootHide Edition changelog

This file contains RootHide Edition history only. The Dopamine Edition has a separate changelog and release lifecycle.

## Unreleased — private 0.8 development direction

- Plan a PreferenceLoader-based memory-profile layer while preserving the stable 0.7.1 source-side architecture.
- Planned finite profiles: Recommended 48 MiB, Expanded 72 MiB and Extreme 96 MiB.
- Keep 48 MiB as the default and fallback; recommend the smallest profile that provides stable delivery.
- Reject unrestricted sliders, arbitrary values and undefined maxima.
- Require confirmation and Userspace Reboot before a changed profile becomes active.
- Plan diagnostics for the stored profile, profile loaded by the live source epoch and latest valid observed ServiceExtension peak.
- Evaluate an optional bounded automatic recommendation mode without adding resident polling or monitoring to `runningboardd`.
- Preserve the same RootHide Edition package path for Dopamine 2 RootHide and RootHide Bootstrap.

Status: private planning only. No 0.8 Alpha package, public release or release date is available.

## [0.7.1] — 2026-07-14

### Final stable release

- Promoted the field-approved 0.7.1 RC1 runtime without changing the protection logic.
- Restored the minimal candidate-first path: unrelated requests pass through before target inspection.
- Retained the diagnostics, safety checks and lifecycle hardening developed throughout the 0.7 line.
- Preserved the exact WhatsApp notification `ServiceExtension` target and exact 24 MiB -> 40 MiB policy.
- Contains no polling daemon, periodic scan, timer, repair loop, fallback enforcement or global Jetsam modification.

### Final field validation

- 1,003 successful rewrites from 1,003 attempts.
- Zero rewrite failures.
- Zero compatibility warnings.
- Normal first-message, sequential and burst notification delivery.
- No observed delay or single-tick episode attributable to Jetsam.
- Approximately 0.0% diagnostics-bridge CPU while idle.

### Post-release compatibility confirmation

- The same 0.7.1 package and source-side protection path were independently runtime-confirmed on RootHide Bootstrap under iOS 16.6.1.
- The Bootstrap report recorded 7 successful rewrites from 7 attempts, zero failures and zero compatibility warnings.
- The primary full field-validation baseline remains Dopamine 2 RootHide.

## [0.7.1-rc1] — 2026-07-14

- Removed the unnecessary broad compatibility inspection retained by 0.7.0.
- Ensured that non-24 MiB requests return directly to iOS before target-path validation.
- Kept malformed and unrelated requests unchanged.
- Preserved safe handling of known and unknown request layouts.
- Extended testing reached 1,003 successful rewrites with zero failures and zero warnings.

## [0.7.0] — 2026-07-14

- Consolidated runtime version, target and diagnostic state handling.
- Made hook-install reporting authoritative and resistant to false-positive states.
- Added safer request validation, sparse diagnostics and an on-demand status command.
- Corrected diagnostic state across `runningboardd` lifecycle changes.
- Hardened the local log and removed unnecessary background relaunch behavior.
- Superseded by 0.7.1 after review found an extra synchronous compatibility inspection unnecessary for the supported scope.

## [0.7.0-rc1] — 2026-07-14

- Promoted the Alpha 2 runtime without redesigning the protection path.
- Validated direct upgrade, Safe Mode prevention and recovery, complete uninstall and clean reinstall.
- Completed a mixed-notification gate exceeding 50 rewrites with zero failures or unexpected warnings.

## [0.7.0-alpha2] — 2026-07-14

- Corrected retained diagnostic state across new `runningboardd` instances.
- Required current-process state before reporting confirmed protection.
- Recorded 16 successful rewrites from 16 attempts with zero failures and zero warnings.

## [0.7.0-alpha1] — 2026-07-14

- Introduced explicit PatchLoader and source-hook states.
- Added safer request handling, sparse compatibility diagnostics and the non-resident status command.
- Completed more than 300 successful source-side rewrites with zero failures and zero compatibility warnings.

## [0.6.2] — 2026-07-13

- Final stable release of the original pure source-side candidate-first design.
- Corrected diagnostic state across `runningboardd` restarts and source lifecycles.
- Preserved the exact target and exact 24 MiB -> 40 MiB policy.
- Became the proven fallback baseline used to evaluate the later 0.7 work.

## [0.6.1] — 2026-07-13

- Removed the polling enforcement daemon, watchdog and recurring repair loops.
- Retained only the PatchLoader entry, source hook and event-driven diagnostics bridge.
- Confirmed reliable delivery and approximately 0.0% diagnostics-bridge CPU.

## [0.6.0] — 2026-07-13

- Introduced RootHide PatchLoader integration and early source-side interception inside `runningboardd`.
- Added dynamic jailbreak-root discovery and Safe Mode checks.
- Established the architecture that replaced polling-based enforcement.

## [0.5.1] — 2026-07-12

- Replaced sandbox-dependent diagnostic file writes with event-driven state delivery.
- Added a lightweight root diagnostics bridge.
- Confirmed that ordinary tweak loading did not place the source hook inside `runningboardd`.
- Produced the evidence needed for the PatchLoader architecture.

## [0.5.0] — 2026-07-12

- Introduced the first filtered source-side interception attempt through ordinary tweak loading.
- Retained the working compatibility path until source-side ownership could be proven.
- Demonstrated that a working compatibility layer could conceal an inactive experimental source path.

## [0.4.1] — 2026-07-12

- Produced the stable polling compatibility baseline for the tested environment.
- Reduced diagnostic overhead while retaining rapid targeted enforcement.
- Delivered reliable notifications, but resident CPU use remained because polling was still required.

## [0.4.0] — 2026-07-11

- Raised the target active and inactive limits from 32 MiB to 40 MiB.
- Confirmed that the original 24 MiB ceiling was insufficient.
- Delivered reliable notifications, but continuous diagnostics and polling were too expensive for the final design.

## [0.3.0] — 2026-07-11

- Replaced fixed global monitoring with adaptive enforcement tied to the active target process.
- Applied and verified a 32 MiB limit when iOS restored the original 24 MiB value.
- Greatly improved delivery reliability, although an occasional single-tick episode remained.

## [0.2.0] — 2026-07-11

- Replaced the unsuccessful injected-client design with a standalone root process.
- Added direct discovery of the exact WhatsApp notification `ServiceExtension`.
- Restored notifications with targeted 32 MiB enforcement and proved the central memory-limit hypothesis.
- Fixed 100 ms polling was effective but too expensive for long-term use.

## [0.1.0] — 2026-07-11

- Initial rootless injected-client and privileged-process architecture.
- The privileged component started, but the client connection did not complete.
- No memory-limit change reached the target.
- Established the first experimental baseline for the investigation.