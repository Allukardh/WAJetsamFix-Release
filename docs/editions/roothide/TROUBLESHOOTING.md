# RootHide Edition troubleshooting

Confirm all of the following before reporting a problem:

1. the original Release package checksum was verified before conversion;
2. the package was processed with RootHide Patcher;
3. the converted package was installed;
4. a Userspace Restart was performed from the Dopamine 2 RootHide app;
5. RootHide PatchLoader and ElleKit are installed;
6. at least one WhatsApp notification was received after restart;
7. `/var/jb/usr/bin/wajetsamfixctl status` was run as root.

In Safe Mode, either `PatchLoader: unavailable` or `PatchLoader: safe-mode-skipped` is acceptable when the source hook is unconfirmed and no rewrite occurs.

Do not attempt to compensate by enabling a global Jetsam multiplier, polling daemon or unrelated memory tweak as part of WAJetsamFix troubleshooting.
