# WAJetsamFix

**Targeted Jetsam protection for WhatsApp notifications on Dopamine 2 RootHide.**

WAJetsamFix addresses delayed, missing or single-tick WhatsApp notifications caused by iOS terminating the WhatsApp notification `ServiceExtension` at its original **24 MB** memory limit.

The tweak changes **only that exact WhatsApp target** from **24 MB to 40 MB**. It does not change global Jetsam settings or the limits of unrelated processes.

## Download

Download the latest stable package from the [Releases](https://github.com/Allukardh/WAJetsamFix-Release/releases/latest) page:

```text
com.allukardh.wajetsamfix_0.7.1_iphoneos-arm64.deb
```

## Architecture

- source-side interception inside `runningboardd`;
- exact WhatsApp `ServiceExtension` executable validation;
- exact 24 MB → 40 MB rewrite policy;
- no polling daemon;
- no periodic process scan;
- no global Jetsam modification;
- no fallback enforcement or repair loop;
- event-driven local diagnostics;
- arm64 and arm64e support;
- minimum deployment target: iOS 15.0.

## Requirements

- Dopamine 2 RootHide environment;
- RootHide PatchLoader 0.0.8 or newer;
- ElleKit;
- iOS 15.0 or newer.

The wider version range above reflects the package build target. The fully validated environment is documented in [COMPATIBILITY.md](COMPATIBILITY.md).

## Installation

1. Download the `.deb` from the latest Release.
2. Open or share it with Sileo.
3. Confirm installation and allow the requested userspace restart or respring when prompted.

The package description shown by Sileo explains the target, behavior and limitations of the tweak.

## Diagnostics

WAJetsamFix includes an on-demand status command:

```sh
wajetsamfixctl status
```

The command reports the installed version, PatchLoader state, hook state, current source process, rewrite counters and protection health. It is not a resident monitoring process.

## Package integrity

The official SHA-256 checksum is published in [CHECKSUMS.txt](CHECKSUMS.txt) and in the Release notes.

## Support policy

WAJetsamFix is a personal project provided as-is. Installation does not include any promise of individual support, compatibility with every future WhatsApp or jailbreak release, or continued development. See [SUPPORT.md](SUPPORT.md).

## Repository scope

This repository is the official public distribution channel for WAJetsamFix. It contains release packages and user-facing documentation; it does not contain the project source code.
