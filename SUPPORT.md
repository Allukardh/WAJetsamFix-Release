# Support policy

WAJetsamFix is a personal project distributed voluntarily and provided **as-is**.

## What this means

- No individual or immediate technical support is guaranteed.
- No response time is promised.
- Compatibility with every device, iOS version, WhatsApp release, tweak combination or jailbreak configuration is not guaranteed.
- No fixed maintenance schedule, continuous development or compatibility with every future release is promised.
- Installation and use remain the user's responsibility.

The absence of guaranteed support does not reduce the care taken in development, testing, packaging and documentation. It only makes clear that distributing the tweak does not create an ongoing service obligation.

## Future updates

WAJetsamFix is stable for the documented environment, so updates are expected to be infrequent.

The author actively uses WhatsApp and WAJetsamFix. If a future WhatsApp, iOS, Dopamine or RootHide change makes an update necessary in the author's own environment, the tweak will be reviewed and updated accordingly.

This does not guarantee compatibility with every future release, establish a fixed maintenance schedule, create an individual support obligation or imply that feature requests will be implemented.

## Before reporting a problem

Confirm that:

1. the environment matches the documented requirements;
2. RootHide Patcher, RootHide PatchLoader and ElleKit are installed;
3. the checksum of the original downloaded package matches the official checksum before conversion;
4. the downloaded `.deb` was processed with RootHide Patcher;
5. the converted package, not the original package, was installed through Sileo;
6. a Userspace Restart was performed manually from the Dopamine 2 RootHide app;
7. `wajetsamfixctl status` has been checked.

## Diagnostic information

Useful technical information includes:

```sh
wajetsamfixctl status
```

When sharing diagnostics publicly, review the output first and remove any information you consider private.

Reports may be reviewed at the author's discretion, but submission does not create an obligation to investigate, reproduce or fix the reported behavior.