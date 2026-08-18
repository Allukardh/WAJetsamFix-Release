# WAJetsamFix

WAJetsamFix 0.8.0 for RootHide is the current stable release.

[Download RootHide 0.8.0](https://github.com/Allukardh/WAJetsamFix-Release/releases/tag/v0.8.0)

WAJetsamFix provides manual memory-limit profiles for WhatsApp in supported RootHide environments. Version 0.8.0 includes:

- 48 MB, 72 MB and 96 MB profiles;
- a bounded calibration assistant for choosing among those profiles;
- a PreferenceLoader panel with the WAJetsamFix icon;
- explicit Userspace Reboot integration after changes;
- status and diagnostic information without automatic repair or background polling.

The tweak changes only the intended WhatsApp Jetsam configuration. It does not apply a global Jetsam override, continuously monitor processes, or silently select/apply a profile.

## Editions

- **RootHide:** 0.8.0 stable, with a public package.
- **Dopamine:** frozen private Alpha; no public package is distributed.

## Install

Read the [RootHide installation guide](docs/editions/roothide/INSTALLATION.md). RootHide Patcher is required before installing the package through Sileo.

## Integrity

Package:

`com.allukardh.wajetsamfix_0.8.0_iphoneos-arm64.deb`

SHA-256:

`6bb869201df4ab00c5fc5465f29c56fcd312ff213ae559167a5b963a64ec65ce`

See [CHECKSUMS.txt](CHECKSUMS.txt) and [release verification](docs/shared/RELEASE-VERIFICATION.md).

## Documentation and support

- [Documentation index](docs/README.md)
- [Compatibility](COMPATIBILITY.md)
- [Support](SUPPORT.md)
- [Security policy](docs/shared/SECURITY.md)
- [Donations](docs/shared/DONATIONS.md)

This public repository contains release documentation and approved binary packages only. Development sources and private validation material are not distributed here.
