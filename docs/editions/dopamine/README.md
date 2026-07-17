# WAJetsamFix — Dopamine Edition

The Dopamine Edition is a separate WAJetsamFix implementation for conventional rootless Dopamine 2 with regular ElleKit injection.

No public Dopamine Edition package, RC or release date is currently available.

> [!IMPORTANT]
> The conventional-Dopamine engine has reached successful private validation, but technical success does not guarantee public release. Any future RC may remain private unless publication is technically justified and sustainable.

## Built from the stable RootHide foundation

The Dopamine Edition is not a redesign of WAJetsamFix. It inherits the protection contract proven by RootHide Edition 0.7.1:

- exact WhatsApp notification `ServiceExtension` target only;
- exact supported 24 MiB candidate only;
- candidate-first target lookup;
- local-copy rewrite with the caller buffer preserved;
- unrelated requests unchanged;
- unknown layouts fail open;
- no polling fallback or global Jetsam modification.

The primary difference is the jailbreak integration path:

```text
RootHide Edition: RootHide PatchLoader -> runningboardd
Dopamine Edition: regular ElleKit/TweakInject -> runningboardd
```

Its implementation, package identity, diagnostics, compatibility scope and release lifecycle remain independent from the RootHide Edition.

## Current private milestone

Private development completed the staged technical path:

1. direct confirmation of the WAJetsam image inside live `runningboardd`;
2. real pass-through-hook validation;
3. exact source-side memory-policy validation;
4. a successful high-ceiling field test with normal notification delivery and on-demand memory telemetry.

The successful private test used conventional Dopamine on iOS 16.3.1 with WhatsApp 26.26.73. Notifications worked with WhatsApp fully closed and the device locked, including:

- ordinary text;
- multiple consecutive messages;
- images;
- audio messages;
- stickers.

The exact-policy diagnostics retained more than 2,800 successful rewrites with zero failures and zero compatibility warnings.

The tested restored-data workload exceeded 40 MiB during successful ServiceExtension operation. A temporary 96 MiB private diagnostic ceiling provided measurement headroom, but it is not the final release policy.

## Required isolation principle

The passing private configuration kept global Tweak Injection enabled while Choicy disabled injection in:

- `ServiceExtension`;
- `NotificationExtension`;
- `ShareExtension`.

WAJetsamFix remained active because it runs in `runningboardd`, not inside those WhatsApp extensions.

## What remains before a private RC

### A. Extended stabilization

- cold first-message delivery after longer idle periods;
- sustained normal and heavy use;
- mixed notification testing;
- zero rewrite failures and compatibility warnings;
- CPU, heat, battery and naturally generated Jetsam review.

### B. Final memory-profile behavior

If development advances to a private Dopamine RC, the profile layer is intended to be ported only after that design is privately validated on RootHide.

Current planned profiles:

| Profile | Limit |
|---|---:|
| **Recommended** | **48 MiB** |
| **Expanded** | **72 MiB** |
| **Extreme** | **96 MiB** |

The current Dopamine Alpha remains fixed during stabilization. No intermediate profile build is planned for the volunteer before the RC stage.

An optional automatic recommendation mode is under evaluation, but any accepted design must remain bounded to validated profiles, display the observed ServiceExtension peak, avoid resident polling and use a safe Userspace Reboot apply path.

### C. Lifecycle and recovery

- direct Alpha-to-RC upgrade;
- Userspace Reboot and normal rejailbreak lifecycle;
- Safe Mode prevention and recovery;
- complete uninstall and clean reinstall;
- `runningboardd` lifecycle changes;
- profile persistence and safe fallback behavior.

### D. Product work

- final arm64/arm64e build and package audit;
- diagnostics showing the selected and actually loaded profile;
- installation, recovery and uninstallation documentation;
- sustained private RC use;
- exact checksum and compatibility scope.

Passing A/B/C/D would justify a private RC. It would not authorize public publication.

## Separate public-publication decision

After the technical gates, the maintainer separately evaluates:

- expected support burden;
- available personal and family time;
- infrastructure, device-testing and electricity costs;
- the effort required to maintain future WhatsApp and jailbreak compatibility;
- whether continued public development is sustainable.

Possible outcomes include a private RC, a controlled public RC, a stable release, postponement or indefinite private retention.

The existence of a working engine does not create a promise that it will be published.

## Development and sustainability

WAJetsamFix is developed in personal time. Reverse engineering, testing, build infrastructure, package auditing, diagnostics and documentation require substantial effort and resources.

The current RootHide stable package remains available. The Dopamine Edition is new work and may remain private even after further technical completion.

Voluntary sponsorship helps make continued public development more viable, but it does not purchase support, access to private builds, features, compatibility, influence over safety decisions or a release date.

See the [public roadmap](../../shared/ROADMAP.md), [project sustainability policy](../../shared/SUSTAINABILITY.md) and [support policy](../../shared/SUPPORT.md).

## Documentation

- [Development status](STATUS.md)
- [Compatibility target](COMPATIBILITY.md)
- [Installation status](INSTALLATION.md)
- [Troubleshooting](TROUBLESHOOTING.md)
- [Uninstallation](UNINSTALLATION.md)
- [Changelog](CHANGELOG.md)