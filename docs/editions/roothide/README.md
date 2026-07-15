# WAJetsamFix — RootHide Edition

The RootHide Edition is the stable WAJetsamFix implementation for Dopamine 2 RootHide.

Version 0.7.1 intercepts the memory-limit assignment inside `runningboardd` through RootHide PatchLoader and changes only the exact WhatsApp notification `ServiceExtension` candidate from 24 MB to 40 MB.

The implementation is source-side, synchronous and event-driven. It has no polling enforcement daemon, periodic timer, process scan, repair loop or global Jetsam modification.

## Package

- Package ID: `com.allukardh.wajetsamfix`
- Stable version: `0.7.1`
- Architectures: arm64 and arm64e
- Minimum deployment target: iOS 15.0
- Injection integration: RootHide PatchLoader
- Hook dependency: ElleKit/Substrate `MSHookFunction`

## Documentation

- [Installation](INSTALLATION.md)
- [Compatibility](COMPATIBILITY.md)
- [Usage and diagnostics](USAGE.md)
- [Troubleshooting](TROUBLESHOOTING.md)
- [Uninstallation](UNINSTALLATION.md)
- [Changelog](CHANGELOG.md)
