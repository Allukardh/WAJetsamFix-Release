# RootHide Edition usage and diagnostics

WAJetsamFix operates automatically after the required Userspace Restart.

Run the non-resident status command as root:

```sh
/var/jb/usr/bin/wajetsamfixctl status
```

A healthy state after at least one matching WhatsApp notification resembles:

```text
WAJetsamFix version: 0.7.1
PatchLoader: hook-installed
Source hook: installed
Protection: confirmed
Successful rewrites: > 0
Failed rewrites: 0
Compatibility warnings: 0
Polling fallback: absent
```

Immediately after a new `runningboardd` instance begins, waiting state and zero counters are expected until the first matching request.

The runtime log is stored at:

```text
/var/mobile/Library/Logs/WAJetsamFix-source.log
```
