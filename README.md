# WAJetsamFix

WAJetsamFix provides targeted Jetsam protection for WhatsApp's notification `ServiceExtension` on supported jailbroken iOS environments.

The project is maintained as two independent editions. Each edition has its own implementation, package identity, compatibility scope and release lifecycle.

## Editions

| Edition | Environment | Package | Status |
|---|---|---|---|
| **WAJetsamFix — RootHide Edition** | Dopamine 2 RootHide | `com.allukardh.wajetsamfix` | **Stable — 0.7.1** |
| **WAJetsamFix — Dopamine Edition** | Conventional Dopamine 2 | `com.allukardh.wajetsamfix.dopamine` | **In development — no public package** |

## WAJetsamFix — RootHide Edition

The stable RootHide Edition intercepts the system memory-limit assignment inside `runningboardd` and changes only the exact WhatsApp notification-extension limit from **24 MB to 40 MB**.

Its active path is synchronous, source-side and event-driven. Unrelated requests pass directly to iOS. There is no polling enforcement daemon, periodic process scan, repair loop or global Jetsam modification.

- [Edition overview](docs/editions/roothide/README.md)
- [Installation](docs/editions/roothide/INSTALLATION.md)
- [Compatibility](docs/editions/roothide/COMPATIBILITY.md)
- [Usage and diagnostics](docs/editions/roothide/USAGE.md)
- [Troubleshooting](docs/editions/roothide/TROUBLESHOOTING.md)
- [Uninstallation](docs/editions/roothide/UNINSTALLATION.md)

Download the current stable package from the [official Releases page](https://github.com/Allukardh/WAJetsamFix-Release/releases/latest).

## WAJetsamFix — Dopamine Edition

The Dopamine Edition is a separate implementation for conventional Dopamine 2 using regular ElleKit tweak injection.

Development begins with a diagnostic loader-only Alpha. That first Alpha will not install a `memorystatus_control` hook and will not modify any Jetsam limit. Hook pass-through and the exact 24 MB → 40 MB policy will be introduced only after the previous validation gate succeeds.

- [Edition overview](docs/editions/dopamine/README.md)
- [Development status](docs/editions/dopamine/STATUS.md)
- [Compatibility target](docs/editions/dopamine/COMPATIBILITY.md)
- [Changelog](docs/editions/dopamine/CHANGELOG.md)

Do not install the RootHide package on conventional Dopamine. No Dopamine Edition package is publicly available yet.

## Shared design principles

Both editions are governed by the same conservative policy:

- only the exact WhatsApp `ServiceExtension` target may be considered;
- only an exact supported 24 MB candidate may be rewritten to 40 MB;
- unrelated commands, processes and values must pass through unchanged;
- unknown layouts must never be guessed, truncated or rewritten;
- no edition may introduce a global Jetsam change or polling fallback;
- a successful build alone is never sufficient for stable publication.

## Documentation

- [Documentation index](docs/README.md)
- [Complete public changelog](CHANGELOG.md)
- [Compatibility overview](COMPATIBILITY.md)
- [Support policy](SUPPORT.md)
- [Package checksums](CHECKSUMS.txt)

## Distribution

The official public repository contains user-facing documentation and release packages only. Development source, internal architecture records, test evidence and build history remain private.

Only the latest stable release is intended to retain a downloadable package. Older Releases remain available as a descending, changelog-only history so users can follow the project's evolution without being offered obsolete packages.

## Support

WAJetsamFix is a personal project shared as a courtesy and provided **as-is**. No fixed maintenance schedule, guaranteed individual support or universal compatibility is promised.

## 💙 Support the project

WAJetsamFix is free to use and independently maintained.

Voluntary sponsorships help support continued testing, maintenance and compatibility work when needed.

[**Sponsor WAJetsamFix**](https://github.com/sponsors/Allukardh)
