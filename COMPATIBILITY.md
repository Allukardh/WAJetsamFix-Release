# Compatibility

WAJetsamFix editions have independent compatibility scopes. A build target is not the same as field validation.

## RootHide Edition

WAJetsamFix 0.7.1 was fully validated with:

- **Device:** iPhone 14 Pro Max
- **iOS:** 16.4.1
- **Jailbreak:** Dopamine 2 RootHide 2.4.9.25
- **WhatsApp:** 26.26.73
- **Global Jetsam multiplier:** 3×
- **RootHide PatchLoader:** 0.0.8 or newer
- **Target:** `net.whatsapp.WhatsApp.ServiceExtension`

The package is built for arm64 and arm64e with a minimum deployment target of iOS 15.0. This technical range does not guarantee that every device, iOS version, WhatsApp build or RootHide configuration has been field-tested.

See [RootHide Edition compatibility](docs/editions/roothide/COMPATIBILITY.md).

## Dopamine Edition

The intended environment is conventional rootless Dopamine 2 with ElleKit. The edition is not yet field-validated and no public package exists.

Compatibility claims will be added only after diagnostic injection, pass-through hook and exact rewrite gates have succeeded on a real device.

See [Dopamine Edition compatibility](docs/editions/dopamine/COMPATIBILITY.md).
