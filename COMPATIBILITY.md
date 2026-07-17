# Compatibility

WAJetsamFix editions have independent compatibility scopes. Installation, technical hook reach, private validation and public compatibility are different claims.

## RootHide Edition

### Fully validated baseline

WAJetsamFix 0.7.1 was fully validated with:

- **Device:** iPhone 14 Pro Max
- **iOS:** 16.4.1
- **Jailbreak:** Dopamine 2 RootHide 2.4.9.25
- **WhatsApp:** 26.26.73
- **Global Jetsam multiplier:** 3×
- **RootHide PatchLoader:** 0.0.8 or newer
- **Target:** `net.whatsapp.WhatsApp.ServiceExtension`

Final validation recorded 1,003 successful rewrites, zero failures, zero compatibility warnings and normal first-message, sequential and burst notification behavior.

### Additional confirmed runtime — RootHide Bootstrap

The same RootHide Edition 0.7.1 package and source-side runtime were independently confirmed on an iPhone 14 Pro Max running iOS 16.6.1 with RootHide Bootstrap and a Fouad-modified TrollStore WhatsApp IPA.

The report confirmed:

- PatchLoader and source hook installed;
- protection confirmed;
- 7 successful rewrites from 7 attempts;
- zero failures;
- zero compatibility warnings.

RootHide Bootstrap is an additional environment for the same RootHide Edition package, not a separate package edition. Its broader notification behavior was not tested to the same depth as the primary Dopamine 2 RootHide baseline.

The package is built for arm64 and arm64e with a minimum deployment target of iOS 15.0. This technical range does not guarantee that every device, iOS version, WhatsApp build or RootHide configuration has been field-tested.

The planned private RootHide 0.8 profiles and automatic recommendation research are not part of stable 0.7.1 and are not current compatibility claims.

See [RootHide Edition compatibility](docs/editions/roothide/COMPATIBILITY.md).

## Dopamine Edition

The intended environment is conventional rootless Dopamine 2 with regular ElleKit injection.

Private real-device development has confirmed:

- loading the final WAJetsam dylib into live `/usr/libexec/runningboardd`;
- installing the real `memorystatus_control` hook;
- exact pass-through behavior;
- exact target/candidate policy rewriting;
- successful notification delivery in a controlled high-ceiling field test;
- more than 2,800 exact rewrites with zero retained failures and zero compatibility warnings;
- bounded physical-memory telemetry outside the hook hot path.

The private environment was an `iPhone15,3` on iOS 16.3.1 with WhatsApp 26.26.73, Watusi 1.3.18 and WatusiTools 2.8.3. Successful testing required global tweak injection to remain enabled while Choicy disabled injection specifically in `ServiceExtension`, `NotificationExtension` and `ShareExtension`.

The heavy restored-data profile consumed more memory than the RootHide Edition's stable 40 MiB policy. The current Alpha used a temporary 96 MiB diagnostic ceiling; that value is not automatically the final Dopamine policy.

A future Dopamine RC is planned to receive 48/72/96 MiB profiles only after the profile layer passes private RootHide validation. Automatic recommendation remains under evaluation and is not yet a compatibility claim.

No conventional Dopamine combination is approved for public compatibility yet. A successful private Alpha on one environment does not establish universal support, RC readiness or a public package.

See [Dopamine Edition compatibility](docs/editions/dopamine/COMPATIBILITY.md).