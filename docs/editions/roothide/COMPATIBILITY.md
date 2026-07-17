# RootHide Edition compatibility

## Fully validated environment

- **Device:** iPhone 14 Pro Max
- **iOS:** 16.4.1
- **Jailbreak:** Dopamine 2 RootHide 2.4.9.25
- **WhatsApp:** 26.26.73
- **Global Jetsam multiplier:** 3×
- **RootHide PatchLoader:** 0.0.8 or newer
- **Target:** `net.whatsapp.WhatsApp.ServiceExtension`

Final field validation recorded 1,003 successful rewrites from 1,003 attempts, zero rewrite failures, zero compatibility warnings, normal first-message and burst delivery, no observed delay or single-tick episode attributable to Jetsam and approximately 0.0% idle diagnostics-bridge CPU.

## Additional confirmed runtime — RootHide Bootstrap

WAJetsamFix 0.7.1 runtime compatibility was independently confirmed with:

- **Device:** iPhone 14 Pro Max;
- **iOS:** 16.6.1;
- **Environment:** RootHide Bootstrap;
- **WhatsApp:** Fouad-modified TrollStore IPA with `ServiceExtension` injection;
- **Installation:** original package processed by RootHide Patcher, installed through Sileo and followed by **Reboot Userspace** from RootHide Bootstrap.

The returned status confirmed:

- `PatchLoader: hook-installed`;
- `Source hook: installed`;
- `Protection: confirmed`;
- 7 successful rewrites from 7 attempts;
- zero rewrite failures;
- zero compatibility warnings.

This evidence confirms that RootHide Bootstrap loaded the WAJetsamFix PatchLoader path into `runningboardd`, matched the expected WhatsApp `ServiceExtension` target and applied the exact 24 MiB -> 40 MiB rewrite. It is recorded as confirmed runtime compatibility rather than a second fully validated environment because the broader notification behavior of that modified WhatsApp IPA was not validated to the same depth as the primary Dopamine 2 RootHide baseline.

## Technical build range

The package is built for arm64 and arm64e with a minimum deployment target of iOS 15.0. The reachable RootHide range is broader than the fully validated and additionally confirmed environments and must not be presented as universal field validation.

## Unsupported or unvalidated environments

- conventional Dopamine without RootHide;
- rootful jailbreaks;
- systems lacking RootHide PatchLoader or ElleKit;
- modified WhatsApp packages with a different target path or identity;
- future WhatsApp versions not yet reviewed.