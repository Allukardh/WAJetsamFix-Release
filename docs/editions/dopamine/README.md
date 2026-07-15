# WAJetsamFix — Dopamine Edition

The Dopamine Edition is a separate WAJetsamFix implementation for conventional rootless Dopamine 2.

It is designed to use regular ElleKit tweak injection rather than RootHide PatchLoader. The implementation, package identity, diagnostics and release lifecycle remain independent from the RootHide Edition.

## Current state

No public package is available. Development begins with a loader-only diagnostic Alpha that confirms whether the edition is injected into `runningboardd`.

The first Alpha will not install a `memorystatus_control` hook and will not modify any Jetsam limit.

- [Development status](STATUS.md)
- [Compatibility target](COMPATIBILITY.md)
- [Installation status](INSTALLATION.md)
- [Changelog](CHANGELOG.md)
