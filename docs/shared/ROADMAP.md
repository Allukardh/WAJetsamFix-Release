# WAJetsamFix roadmap

This roadmap describes validated milestones and possible future work. It is not a release schedule, support commitment or promise that every planned feature will be published.

## Status language

| Label | Meaning |
|---|---|
| **Available now** | Publicly released and documented for its approved compatibility scope. |
| **Validated privately** | Demonstrated in controlled private testing, but not offered as a public package. |
| **Under evaluation** | A design direction being researched; details may change, pause or be abandoned. |

## Publication is a separate gate

Technical completion does not automatically authorize public release.

A private Alpha, completed engine or future RC may remain private after successful testing. Publication is a separate maintainer decision based on technical safety, support burden, available personal and family time, infrastructure costs and whether continued public development is sustainable.

The current public RootHide Edition 0.7.1 package remains available. Everything beyond it is additional work, not an owed continuation.

See the [project sustainability policy](SUSTAINABILITY.md).

## Available now — RootHide Edition 0.7.1

The current stable RootHide Edition:

- uses RootHide PatchLoader to place the source-side hook in `runningboardd`;
- rewrites only the exact WhatsApp notification `ServiceExtension` candidate from 24 MiB to 40 MiB;
- preserves unrelated requests unchanged and fails open on unknown layouts;
- contains no polling enforcement daemon, periodic scan, repair loop or global Jetsam modification;
- was fully field-validated on Dopamine 2 RootHide;
- had the same package and runtime path independently confirmed on RootHide Bootstrap.

The deeper stable field baseline remains Dopamine 2 RootHide. RootHide Bootstrap is an additional confirmed runtime environment for the same RootHide Edition package, not a separate package edition.

## Validated privately — Dopamine Edition

The separate Dopamine Edition targets conventional rootless Dopamine 2 with regular ElleKit integration.

It is not a redesign of WAJetsamFix. It inherits the stable RootHide 0.7.1 protection contract:

- exact WhatsApp `ServiceExtension` target;
- exact supported 24 MiB candidate;
- candidate-first target inspection;
- local-copy rewrite with the caller buffer preserved;
- fail-open compatibility behavior;
- no global Jetsam change or polling fallback.

Private testing has confirmed target loading in live `runningboardd`, the real pass-through hook, the exact memory-policy path and successful notification delivery in a controlled high-memory field profile.

More than 2,800 exact rewrites were retained with zero failures and zero compatibility warnings in the successful private epoch. No public Dopamine package, RC or release date is currently available.

The existence of a working private engine demonstrates technical progress. It does not guarantee that the edition will be published.

## Planned private RootHide 0.8 Alpha

A future private RootHide 0.8 Alpha is planned to evaluate a user-facing memory-profile layer without replacing the proven source-side architecture.

Planned manual profiles:

| Profile | Limit | Intended role |
|---|---:|---|
| **Recommended** | **48 MiB** | Default starting point with modest headroom over the historical 40 MiB policy. |
| **Expanded** | **72 MiB** | For environments where the recommended profile is insufficient. |
| **Extreme** | **96 MiB** | For unusually demanding restored databases or WhatsApp versions. |

Design rules:

- the smallest stable profile should always be preferred;
- a larger limit does not reserve that memory and does not improve performance by itself;
- no unrestricted slider, arbitrary value or undefined maximum;
- profile changes require confirmation and a Userspace Reboot;
- invalid or missing configuration must fall back safely to 48 MiB;
- no preference lookup, disk access or monitoring may be added to the `runningboardd` hot path.

The profile layer will be developed and privately validated on RootHide first. If it succeeds and development advances to a private Dopamine RC, the validated design may be adapted there.

Neither RootHide 0.8 nor a Dopamine profile build is promised for public release.

## Automatic profile selection — under evaluation

An optional automatic mode is being researched, but no implementation is approved yet.

A safe automatic design must remain bounded to the same validated profiles and must not introduce a resident polling daemon. The preferred direction is a separate, time-bounded calibration or diagnostic helper that:

1. observes the exact `ServiceExtension` physical-memory peak outside the hook;
2. stores the highest valid observed peak and its test context;
3. recommends one of the validated 48/72/96 MiB profiles with a deliberate safety margin;
4. shows the observed peak and recommendation in Preferences;
5. applies a changed profile only after confirmation and Userspace Reboot.

Continuous silent self-modification, an unrestricted calculated limit and per-call monitoring inside `runningboardd` are outside the accepted architecture.

## Before a private Dopamine Edition RC

### A. Extended stabilization

- cold first-message delivery after a longer idle period;
- sustained normal and heavy WhatsApp use;
- ordinary, sequential, burst, image, audio and sticker notifications;
- zero rewrite failures and zero compatibility warnings;
- review of heat, battery use, CPU behavior and naturally generated Jetsam evidence.

### B. Final memory policy

- determine whether the current measured memory curve stabilizes;
- select and justify the RC profile behavior;
- port the already validated RootHide profile layer only at the RC stage;
- keep the current private Alpha fixed while its stabilization gate is completed.

### C. Lifecycle and recovery

- direct upgrade from the approved Alpha;
- Userspace Reboot and normal rejailbreak lifecycle;
- Safe Mode prevention and recovery;
- complete uninstall and clean reinstall;
- `runningboardd` lifecycle changes;
- preference persistence and safe fallback behavior.

### D. Product and release work

- final arm64/arm64e build and package audit;
- diagnostics showing the selected and actually loaded profile;
- reviewed installation, recovery and uninstallation documentation;
- exact package checksum and compatibility scope;
- sustained RC field use.

Passing A/B/C/D may justify a private RC. It does not authorize a public RC or stable release.

## Public publication decision

After the technical gates, the maintainer separately evaluates:

- whether the support burden is acceptable;
- whether enough personal and family time is available;
- whether infrastructure and testing costs are sustainable;
- whether the public documentation and recovery path are complete;
- whether continued maintenance can be offered without creating an unhealthy obligation.

Possible outcomes include a private RC, a controlled public RC, a stable public release, a documentation-only update, postponement or indefinite private retention.

No outcome is promised in advance.

## Project sustainability

WAJetsamFix is independently developed in personal time. Research, private testing, build infrastructure, package auditing, diagnostics, documentation and compatibility maintenance require substantial effort.

The work also competes with family, rest and paid responsibilities and creates direct infrastructure, device-testing and electricity costs.

Voluntary sponsorship helps make continued public development more viable. It does not purchase support, access to private builds, specific features, compatibility, influence over safety decisions or release dates.

There is no sponsor threshold or pay-to-release promise.