# WAJetsamFix — Dopamine Edition changelog

No Dopamine Edition package has been publicly released.

## Unreleased — future private RC direction

- Complete extended Alpha 2.2 stabilization without changing its fixed 96 MiB diagnostic policy.
- Port the memory-profile layer only after it is privately validated on RootHide.
- Planned RC profiles: Recommended 48 MiB, Expanded 72 MiB and Extreme 96 MiB.
- Keep the smallest stable profile as the recommended choice.
- Reject unrestricted sliders, arbitrary values and undefined maxima.
- Require confirmation and Userspace Reboot before a profile change becomes active.
- Plan diagnostics for the selected profile, profile loaded by the current `runningboardd` epoch and latest valid observed ServiceExtension peak.
- Evaluate an optional bounded automatic recommendation mode without introducing resident polling.
- Complete direct upgrade, Safe Mode, uninstall, clean reinstall, lifecycle, stress and final audit gates.

Status: planning only. No RC, public package or release date is authorized.

## 0.3.0~alpha2.2 — private high-ceiling Alpha candidate

### Architecture and diagnostics

- Preserves the exact-target, candidate-first and fail-open policy inherited from stable RootHide 0.7.1.
- Recognizes only an exact supported 24 MiB request for the WhatsApp notification `ServiceExtension`.
- Uses a temporary 96 MiB diagnostic ceiling without changing unrelated processes, commands, values or global Jetsam settings.
- Keeps monitoring outside the `runningboardd` hook hot path.
- Adds a separate on-demand memory utility that follows only the exact target PID, records physical-memory information and exits after a bounded interval.
- Extends portable tests and package auditing for arm64 and arm64e.

### Reason for the private high ceiling

- Alpha 2.1 correctly applied 40 MiB with zero rewrite failures and zero compatibility warnings.
- A matching system JetsamEvent proved the ServiceExtension consumed the entire 40 MiB ceiling and was terminated by `per-process-limit`.
- The volunteer's clean WhatsApp 26.26.73 installation works, while the unusually heavy restored-data state does not.
- A high private ceiling was used to measure actual demand before choosing the lowest reliable final policy.

### Private field milestone

- Global tweak injection remained enabled so WAJetsamFix stayed active in `runningboardd`.
- Choicy disabled injection in `ServiceExtension`, `NotificationExtension` and `ShareExtension`.
- Notifications worked with WhatsApp fully closed and the device locked.
- Text, multiple messages, images, audio messages and stickers delivered normally.
- Heavy subsequent use remained functional.
- More than 2,800 successful exact rewrites were retained with zero failures and zero compatibility warnings.
- Three useful on-demand memory windows showed successful ServiceExtension operation above 40 MiB.
- No matching new JetsamEvent or target crashloop was reported.

Status: private Alpha functional milestone passed. Extended stabilization and RC product gates remain pending. The diagnostic ceiling is not a public release commitment.

## 0.3.0~alpha2.1 — private exact-policy candidate

- Completed target-loading and pass-through-hook gates on conventional Dopamine 2.
- Added the exact WhatsApp notification `ServiceExtension` protection policy.
- Rewrites only an exact supported 24 MiB candidate to 40 MiB.
- Preserves unrelated commands, processes, values, caller buffers and unaffected fields.
- Uses candidate-first target inspection.
- Fails open on unknown request layouts and related but non-exact target paths.
- Added separate rewrite-success, rewrite-failure and compatibility-warning diagnostics.
- Passed private policy tests, Linux arm64/arm64e build and package-audit gates.
- Contains no polling, timer, resident enforcement daemon, automatic restart or global Jetsam modification.

### Private device milestone

- Observed 23 exact command-7 rewrites.
- Recorded zero rewrite failures and zero compatibility warnings.
- A system Jetsam event confirmed that the target received and exhausted the 40 MiB ceiling.
- Notification delivery did not pass at that ceiling.

Status: exact rewrite technically confirmed; superseded by Alpha 2.2. Not available for public download.

## 0.2.0~alpha1.1 — completed private pass-through-hook candidate

- Replaced the diagnostic loader probe with the real `runningboardd` hook entry.
- Added exact pass-through interception of `memorystatus_control`.
- Preserved all original arguments and the original return value.
- Added retained hook-installation, hook-failure and first-call diagnostics.
- Passed private argument-forwarding tests, Linux arm64/arm64e build and package-audit gates.
- Device testing confirmed the hook and a real pass-through call.

Status: technical hook gate completed. Not publicly released.

## 0.1.0~alpha0.3 — completed private injection-path inspector

- Added exact live `runningboardd` PID/path discovery.
- Added read-only loaded-image inspection of the target process.
- Directly confirmed the WAJetsam probe image inside `runningboardd`.

Status: completed and superseded by Alpha 1. Not publicly released.

## 0.1.0~alpha0.2 — superseded private diagnostic candidate

- Added a SpringBoard control, direct Darwin Notify checks and manual dylib-loading tests.
- Confirmed the control path and established the need for read-only target-image inspection.

Status: superseded by Alpha 0.3. Not publicly released.

## 0.1.0~alpha0.1 — superseded private field-test candidate

- Prepared the independent conventional Dopamine 2 rootless package.
- Added the initial filtered loader probe and on-demand report command.
- Confirmed the environment but could not distinguish loading failure from diagnostic-state loss.

Status: superseded by later Alpha diagnostics. Not publicly released.