# Compatibility

## Fully validated environment

WAJetsamFix 0.7.1 was fully validated with:

- **Device:** iPhone 14 Pro Max
- **iOS:** 16.4.1
- **Jailbreak:** Dopamine 2 RootHide 2.4.9.25
- **WhatsApp:** 26.26.73
- **Global Jetsam multiplier:** 3×
- **RootHide PatchLoader:** 0.0.8 or newer
- **Target:** `net.whatsapp.WhatsApp.ServiceExtension`

The validated workload included first-message delivery, sequential notifications, bursts, mixed content, screen-locked delivery, target-process changes, Safe Mode recovery, uninstall/reinstall and `runningboardd` lifecycle changes.

Final field validation recorded:

- 1,003 successful rewrites from 1,003 attempts;
- zero rewrite failures;
- zero compatibility warnings;
- no observed notification loss attributable to the tweak;
- no observed delay or single-tick episode attributable to Jetsam;
- approximately 0.0% idle CPU for the diagnostics bridge.

## Build target versus validation

The package is built for **arm64 and arm64e** with a minimum deployment target of **iOS 15.0**. This is a technical build range, not a guarantee that every device, iOS version, WhatsApp build or RootHide configuration has been field-tested.

## Future WhatsApp versions

WhatsApp may change its extension structure, executable path, memory policy or notification architecture. A newer WhatsApp version should therefore be considered **not yet validated** until tested, even when the tweak installs and appears operational.

WAJetsamFix deliberately avoids broad or speculative matching. Unknown structures and values other than the exact supported 24 MB candidate are passed through unchanged.

## Unsupported environments

The package is not presented as validated for:

- rootful jailbreaks;
- non-RootHide environments;
- jailbreaks other than the documented Dopamine 2 RootHide architecture;
- modified WhatsApp packages with a different ServiceExtension path or identity;
- systems lacking RootHide PatchLoader or ElleKit.
