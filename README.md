# WAJetsamFix

WAJetsamFix provides targeted Jetsam protection for WhatsApp's notification `ServiceExtension` on supported jailbroken iOS environments.

The project is maintained as independent editions. Each edition has its own implementation, package identity, compatibility scope and release lifecycle, while sharing the same conservative protection principles.

## Editions

| Edition | Environment | Integration | Package | Status |
|---|---|---|---|---|
| **WAJetsamFix — RootHide Edition** | Dopamine 2 RootHide and RootHide Bootstrap | RootHide PatchLoader | `com.allukardh.wajetsamfix` | **Available now — stable 0.7.1** |
| **WAJetsamFix — Dopamine Edition** | Conventional rootless Dopamine 2 | Regular ElleKit injection | `com.allukardh.wajetsamfix.dopamine` | **Validated privately — no public package** |

RootHide Bootstrap uses the same RootHide Edition package. It is an additional confirmed runtime environment, not a third package edition.

> [!IMPORTANT]
> RootHide Edition 0.7.1 is the only current public package. A private milestone, roadmap entry, completed engine or future RC does **not** guarantee public release. Technical readiness and publication are separate maintainer decisions.

## WAJetsamFix — RootHide Edition

The stable RootHide Edition intercepts the system memory-limit assignment inside `runningboardd` and changes only the exact WhatsApp notification-extension candidate from **24 MiB to 40 MiB**.

Its active path is synchronous, source-side and event-driven. Unrelated requests pass directly to iOS. There is no polling enforcement daemon, periodic process scan, repair loop or global Jetsam modification.

The primary full field-validation baseline is Dopamine 2 RootHide. The same 0.7.1 package, PatchLoader path, source hook and exact rewrite were also independently runtime-confirmed on RootHide Bootstrap under iOS 16.6.1.

- [Edition overview](docs/editions/roothide/README.md)
- [Installation](docs/editions/roothide/INSTALLATION.md)
- [Compatibility](docs/editions/roothide/COMPATIBILITY.md)
- [Usage and diagnostics](docs/editions/roothide/USAGE.md)
- [Troubleshooting](docs/editions/roothide/TROUBLESHOOTING.md)
- [Uninstallation](docs/editions/roothide/UNINSTALLATION.md)

Download the current RootHide stable package from the official public Releases history.

## WAJetsamFix — Dopamine Edition

The Dopamine Edition is a separate implementation for conventional rootless Dopamine 2 using regular ElleKit injection.

It is **not a redesign** of WAJetsamFix. It inherits the protection contract proven by RootHide Edition 0.7.1:

- exact WhatsApp notification `ServiceExtension` target only;
- exact supported 24 MiB candidate only;
- candidate-first target inspection;
- local-copy rewrite with the caller buffer preserved;
- unrelated requests unchanged;
- unknown layouts fail open;
- no polling fallback or global Jetsam modification.

Only the jailbreak-specific integration path is replaced: RootHide PatchLoader becomes conventional ElleKit loading while the source-side policy remains inside `runningboardd`.

Private development has completed:

- direct target loading confirmation inside live `runningboardd`;
- real pass-through-hook validation;
- exact memory-policy validation;
- successful notification delivery in a controlled high-memory field profile;
- more than 2,800 successful exact rewrites with zero retained failures and zero compatibility warnings;
- separate, bounded, on-demand physical-memory telemetry outside the hook hot path.

The private test passed ordinary, consecutive, image, audio-message and sticker notifications with WhatsApp closed and the device locked. The unusually heavy restored-data workload exceeded 40 MiB during successful ServiceExtension operation, so the final release policy is still being selected conservatively.

No Dopamine Edition release candidate, public package or release date is currently available. The working private engine may remain private unless a later publication is technically justified and sustainable.

- [Edition overview](docs/editions/dopamine/README.md)
- [Development status](docs/editions/dopamine/STATUS.md)
- [Compatibility target](docs/editions/dopamine/COMPATIBILITY.md)
- [Changelog](docs/editions/dopamine/CHANGELOG.md)

Do not install the RootHide package on conventional Dopamine.

## Project continuity and sustainability

WAJetsamFix is independently developed in personal time. Research, private testing, build infrastructure, package auditing, diagnostics, documentation and compatibility work require substantial effort and direct resources.

This work competes with time reserved for family, rest and paid responsibilities, while also creating infrastructure, device-testing and electricity costs.

The current public RootHide 0.7.1 package remains available under its documented **as-is** terms. Everything beyond it — RootHide 0.8, memory profiles, automatic calibration, the Dopamine Edition and future compatibility work — is new work and is not guaranteed.

A technically complete private build does not automatically become a public release. Publication depends on technical safety, expected support burden, available personal time and whether continued public development is sustainable.

Voluntary sponsorship helps offset the work and costs required to turn private engineering into reviewed public releases. It does not purchase support, access to private builds, a feature, compatibility, influence over safety decisions or a release date.

See the [project sustainability policy](docs/shared/SUSTAINABILITY.md) and [support policy](SUPPORT.md).

## Private RootHide 0.8 development

RootHide 0.8.0 Alpha 2.1 is now in private on-device testing. It adds a memory-profile and bounded calibration layer while preserving the proven 0.7.1 runtime architecture.

Manual profiles in the private Alpha:

| Profile | Limit | Role |
|---|---:|---|
| **Recommended** | **48 MiB** | Smallest profile, used after a validated recommendation when sufficient. |
| **Expanded** | **72 MiB** | For environments where the recommended profile is insufficient. |
| **Extreme** | **96 MiB** | Safe initial and calibration ceiling for unusually demanding environments. |

The smallest stable profile should always be used. A larger ceiling does not reserve memory and does not improve performance by itself. No unrestricted slider or arbitrary value is used.

The private Alpha automatically calibrates the exact rewritten WhatsApp `ServiceExtension` outside `runningboardd`. One distinct valid instance provides a preliminary result; three validate the smallest supported recommendation. Calibration never applies its recommendation automatically, and every profile change still requires explicit confirmation and Userspace Reboot.

Current private device evidence records a 26.59 MiB highest observed peak and a validated 48 MiB recommendation. See the [RootHide 0.8.0 Alpha 2.1 evidence page](docs/editions/roothide/evidence/0.8.0-alpha2.1/README.md).

The profile layer is being validated privately on RootHide first. If approved, it may later be adapted for a future private Dopamine Edition RC rather than being mixed into the current Dopamine Alpha stabilization work.

This work may change, pause or remain private. It is not a release promise.

See the [public roadmap](docs/shared/ROADMAP.md) for the remaining stabilization, lifecycle, recovery and product gates.

## Shared design principles

Both editions are governed by the same conservative architecture:

- only the exact WhatsApp `ServiceExtension` target may be considered;
- only an exact supported 24 MiB candidate may be rewritten;
- each edition uses only a target value or profile validated for its own environment;
- unrelated commands, processes and values pass through unchanged;
- unknown layouts are never guessed, truncated or rewritten;
- no edition may introduce a global Jetsam change or polling fallback;
- a successful build or technical rewrite alone is never sufficient for stable publication.

## Documentation

- [Documentation index](docs/README.md)
- [Public roadmap](docs/shared/ROADMAP.md)
- [Project sustainability](docs/shared/SUSTAINABILITY.md)
- [Complete public changelog](CHANGELOG.md)
- [Compatibility overview](COMPATIBILITY.md)
- [Support policy](SUPPORT.md)
- [Voluntary sponsorships](docs/shared/DONATIONS.md)
- [Package checksums](CHECKSUMS.txt)

## Distribution

The official public repository contains user-facing documentation and approved release packages only. Development source, internal architecture records, raw test evidence and build history remain private.

Historical Releases remain available as a descending changelog. While only the RootHide Edition is public, its current stable Release retains the downloadable package. If both editions later become public and stable, the distribution policy will retain one current stable package per supported edition while superseded releases remain notes-only.

## Support

WAJetsamFix is a personal project shared as a courtesy and provided **as-is**. No fixed maintenance schedule, guaranteed individual support, future release or universal compatibility is promised.

## 💙 Support the project

WAJetsamFix is free to use and independently maintained.

Voluntary sponsorships help support continued testing, maintenance and compatibility work when needed.

[**Sponsor WAJetsamFix**](https://github.com/sponsors/Allukardh)
