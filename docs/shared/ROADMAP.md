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

## Validated privately — RootHide 0.8 Alpha

RootHide 0.8.0 Alpha 2.1 is in private on-device testing. It adds a user-facing memory-profile and bounded calibration layer without replacing the proven source-side architecture.

Manual profiles in the private Alpha:

| Profile | Limit | Intended role |
|---|---:|---|
| **Recommended** | **48 MiB** | Smallest profile, used after a validated recommendation when sufficient. |
| **Expanded** | **72 MiB** | For environments where the recommended profile is insufficient. |
| **Extreme** | **96 MiB** | Safe initial and calibration ceiling for unusually demanding environments. |

Design rules:

- the smallest stable profile should always be preferred;
- a larger limit does not reserve that memory and does not improve performance by itself;
- no unrestricted slider, arbitrary value or undefined maximum;
- profile changes require confirmation and a Userspace Reboot;
- new or recalibrated environments use the 96 MiB ceiling before a smaller profile is recommended;
- no preference lookup, disk access or monitoring may be added to the `runningboardd` hot path.

Automatic calibration is bounded to an exact rewritten `ServiceExtension` PID and runs outside `runningboardd`. One distinct valid instance provides a preliminary result; three validate the smallest supported recommendation. The recommendation is never applied automatically.

The current private evidence records a 26.59 MiB highest observed peak and a validated 48 MiB recommendation on the maintainer's test environment. See the [RootHide 0.8.0 Alpha 2.1 evidence page](../editions/roothide/evidence/0.8.0-alpha2.1/README.md).

The profile layer is being privately validated on RootHide first. If development later advances to a private Dopamine RC, the validated design may be adapted there.

Neither RootHide 0.8 nor a Dopamine profile build is promised for public release.

## Automatic calibration — validated privately

The private RootHide Alpha implements the approved bounded design:

1. an observer starts only for the exact rewritten `ServiceExtension` PID while the 96 MiB calibration ceiling is loaded;
2. each observer exits with the target process or after 120 seconds;
3. the highest valid peak and its local environment are retained;
4. one distinct PID provides a preliminary result and three validate it;
5. only 48, 72 or 96 MiB can be recommended;
6. a profile change still requires explicit confirmation and Userspace Reboot.

Continuous silent profile changes, an unrestricted calculated limit and per-call monitoring inside `runningboardd` remain outside the accepted architecture.

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
