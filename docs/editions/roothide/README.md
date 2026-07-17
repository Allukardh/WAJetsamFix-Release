# WAJetsamFix — RootHide Edition

The RootHide Edition is the stable WAJetsamFix implementation for RootHide environments using RootHide PatchLoader.

Its primary fully validated environment is Dopamine 2 RootHide. The same package and source-side runtime path have also been independently confirmed on RootHide Bootstrap.

RootHide Bootstrap is an additional environment for the same RootHide Edition package, not a separate WAJetsamFix package edition.

## Current stable release

Version 0.7.1 intercepts the memory-limit assignment inside `runningboardd` through RootHide PatchLoader and changes only the exact WhatsApp notification `ServiceExtension` candidate from 24 MiB to 40 MiB.

The implementation is source-side, synchronous and event-driven. It has no polling enforcement daemon, periodic timer, process scan, repair loop or global Jetsam modification.

### Package

- Package ID: `com.allukardh.wajetsamfix`
- Stable version: `0.7.1`
- Architectures: arm64 and arm64e
- Minimum deployment target: iOS 15.0
- Integration: RootHide PatchLoader
- Hook dependency: ElleKit/Substrate `MSHookFunction`
- Fully validated environment: Dopamine 2 RootHide
- Additional confirmed runtime: RootHide Bootstrap

## Private 0.8 direction

A future private RootHide 0.8 Alpha is planned to evaluate a PreferenceLoader-based memory-profile layer without changing the proven source-side protection contract.

Planned manual profiles:

| Profile | Limit | Purpose |
|---|---:|---|
| **Recommended** | **48 MiB** | Planned default with modest headroom over the stable 40 MiB baseline. |
| **Expanded** | **72 MiB** | For environments where 48 MiB is insufficient. |
| **Extreme** | **96 MiB** | For unusually demanding restored databases or WhatsApp versions. |

The design will recommend the smallest stable profile, reject arbitrary values and require confirmation plus Userspace Reboot when the selected profile changes.

An optional automatic recommendation mode is under evaluation. Any accepted design must use bounded calibration outside the `runningboardd` hot path, show the observed ServiceExtension peak and choose only among validated profiles. No resident polling or unrestricted self-tuning is planned.

Version 0.8 is private planning only. It has no package, public release or release date. Even a technically successful private Alpha does not guarantee that 0.8 will be published.

The current public stable release remains 0.7.1 under its documented **as-is** support terms.

See the [public roadmap](../../shared/ROADMAP.md), [project sustainability policy](../../shared/SUSTAINABILITY.md) and [support policy](../../shared/SUPPORT.md).

## Publication and sustainability

RootHide 0.8, configurable profiles, automatic calibration and future compatibility updates are new work beyond the current stable release.

Publication depends on technical quality, support burden, available personal and family time, infrastructure costs and long-term sustainability. Private development may pause or remain private indefinitely.

Voluntary sponsorship helps make continued public development more viable, but it does not purchase support, private-build access, a feature or a release date.

## Documentation

- [Installation](INSTALLATION.md)
- [Compatibility](COMPATIBILITY.md)
- [Usage and diagnostics](USAGE.md)
- [Troubleshooting](TROUBLESHOOTING.md)
- [Uninstallation](UNINSTALLATION.md)
- [Changelog](CHANGELOG.md)