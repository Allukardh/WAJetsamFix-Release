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

## Technical build range

The package is built for arm64 and arm64e with a minimum deployment target of iOS 15.0. The Dopamine 2 reachable range is broader than the single fully validated environment and must not be presented as universal field validation.

## Unsupported or unvalidated environments

- conventional Dopamine without RootHide;
- rootful jailbreaks;
- systems lacking RootHide PatchLoader or ElleKit;
- modified WhatsApp packages with a different target path or identity;
- future WhatsApp versions not yet reviewed.
