# WAJetsamFix — Dopamine Edition status

Current private development stage: **0.3.0~alpha2.2 — high-ceiling functional validation passed; extended stabilization and private RC product work pending**.

No public package, RC or release date is available.

## Completed private gates

- regular ElleKit loading into live `/usr/libexec/runningboardd`;
- installation of the real `memorystatus_control` hook;
- real pass-through call with original arguments and return value preserved;
- exact supported 24 MiB -> 40 MiB rewrite on conventional Dopamine;
- matching Jetsam evidence proving that the target exhausted the 40 MiB ceiling;
- private Alpha 2.2 build and arm64/arm64e package audit;
- exact 24 MiB -> 96 MiB diagnostic policy operation on a real device;
- normal text, consecutive-message, image, audio-message and sticker notification delivery with WhatsApp closed and the device locked;
- more than 2,800 successful exact rewrites with zero failures and zero compatibility warnings;
- three useful on-demand physical-memory windows.

## Stable architecture inherited from RootHide 0.7.1

- exact WhatsApp notification `ServiceExtension` target only;
- exact supported 24 MiB candidate only;
- candidate-first process lookup;
- local-copy rewrite and caller buffer preservation;
- unrelated commands, processes and values unchanged;
- unknown layouts fail open;
- separate success, failure and compatibility diagnostics;
- no polling, timer, daemon, repair loop, automatic restart or global Jetsam change in the hook.

The conventional edition replaces only the RootHide-specific loading path with regular ElleKit integration.

## Current memory evidence

The private volunteer's unusually heavy restored-data workload operated above 40 MiB. A temporary 96 MiB diagnostic ceiling restored reliable delivery and provided useful measurement headroom.

The preserved kernel lifetime maxima increased across the first three windows:

```text
46.56 MiB -> 50.81 MiB -> 55.78 MiB
```

The 96 MiB Alpha value is not a final release policy.

## Planned private RC profile layer

The profile UI will not be mixed into the current Alpha stabilization cycle. If development advances to a private Dopamine RC, it is intended to receive the profile architecture only after that design is privately validated on RootHide.

Current planned profiles:

```text
Recommended: 48 MiB
Expanded:    72 MiB
Extreme:     96 MiB
```

The smallest stable profile is preferred. Larger values are not described as faster or better. No unrestricted slider or arbitrary value is planned.

An optional automatic recommendation mode is under evaluation. Any accepted implementation must:

- choose only among validated profiles;
- expose the observed ServiceExtension peak and recommendation;
- keep calibration outside the `runningboardd` hot path;
- avoid a resident monitor or polling daemon;
- require a safe confirmed Userspace Reboot apply path.

## Required passing configuration

Global Tweak Injection remained enabled while Choicy disabled injection in:

- `ServiceExtension`;
- `NotificationExtension`;
- `ShareExtension`.

## Remaining before a private RC

### A. Stabilization

- longer cold/idle, heavy-use and stabilized-database observation;
- sustained mixed-notification delivery;
- zero rewrite failures and compatibility warnings;
- idle CPU, heat, battery and naturally generated Jetsam review.

### B. Memory-profile integration

- complete the RootHide profile-layer validation first;
- port only the validated profile architecture to conventional Dopamine;
- prove selected, stored and live-loaded profile diagnostics;
- validate invalid-value fallback and reboot-required state.

### C. Lifecycle and recovery

- direct upgrade from the approved Alpha;
- Userspace Reboot and normal rejailbreak lifecycle;
- Safe Mode prevention and recovery;
- complete uninstall and clean reinstall;
- `runningboardd` lifecycle changes.

### D. Product work

- final build and arm64/arm64e package audit;
- complete installation, recovery and uninstallation documentation;
- sustained private RC use;
- exact checksum and compatibility scope.

Passing these gates may justify a private RC. It does not authorize a public RC or stable release.

## Separate public-publication and sustainability gate

After the technical work is complete, the maintainer separately decides whether publication is appropriate.

The decision considers:

- expected support burden;
- available personal and family time;
- infrastructure, device-testing and electricity costs;
- long-term compatibility and documentation work;
- whether continued public development is sustainable.

A technically successful RC may remain private indefinitely.

Voluntary sponsorship helps make public development more viable, but does not purchase support, private-build access, features, compatibility, influence over safety decisions or release dates.

See the [project sustainability policy](../../shared/SUSTAINABILITY.md).

## Current decision

```text
Private Alpha functional milestone: PASSED
Extended stabilization: PENDING
RootHide profile-layer validation: PENDING
Dopamine private RC profile port: PENDING
Private RC lifecycle gate: PENDING
Public publication decision: NOT AUTHORIZED / SEPARATE GATE
Public package: NOT AUTHORIZED
Release date: NONE
```

Development remains private. Technical readiness alone will not trigger publication.