# Frequently asked questions

## Does WAJetsamFix change Jetsam globally?

No. The supported architecture is intentionally limited to the exact WhatsApp notification `ServiceExtension` and an exact supported 24 MiB candidate. Unrelated processes and values pass through unchanged.

## Are the two editions interchangeable?

No. RootHide Edition and Dopamine Edition are separate packages for different jailbreak integration paths. Do not install the RootHide package on conventional Dopamine.

RootHide Bootstrap uses the RootHide Edition package after the documented RootHide processing and installation path; it is not a third WAJetsamFix package edition.

## Is the Dopamine Edition available?

No public Dopamine Edition package or RC is currently available. Its source-side hook, exact rewrite and notification behavior have reached successful private validation, but stabilization, memory-policy, lifecycle, recovery and product gates remain.

## Is the Dopamine Edition based on the stable RootHide implementation?

Yes. It inherits the exact-target, exact-candidate, candidate-first, local-copy and fail-open architecture proven by RootHide Edition 0.7.1. The jailbreak-specific loading path is adapted from RootHide PatchLoader to regular ElleKit integration.

## Does successful private validation guarantee a public release?

No.

Technical readiness and public publication are separate decisions. A private Alpha, completed milestone or future RC may remain private after successful testing.

Publication depends on technical safety, expected support burden, available personal and family time, infrastructure costs and whether continued public development is sustainable.

## What memory profiles are being tested?

A private RootHide 0.8 Alpha is testing three finite profiles:

- Recommended — 48 MiB;
- Expanded — 72 MiB;
- Extreme — 96 MiB.

These values are not a released feature or release promise. The smallest stable profile should always be preferred. Larger limits do not improve performance by themselves and do not reserve that memory permanently.

## How does private Alpha calibration work?

The private RootHide Alpha uses 96 MiB as its safe initial and calibration ceiling. A bounded observer measures only the exact rewritten `ServiceExtension` PID outside `runningboardd`. One distinct valid instance provides a preliminary result; three validate the smallest supported recommendation.

Calibration never changes the profile automatically. Applying a validated recommendation requires explicit user confirmation and Userspace Reboot. No continuous unrestricted self-tuning design is used.

This design has not been ported to the Dopamine Edition and is not a public feature or compatibility claim.

## Why is only the current stable package downloadable?

Older Releases are kept as changelog history, not as recommended installation sources. This reduces accidental installation of obsolete builds while preserving the project's evolution.

If both editions later become public and stable, the distribution plan is to retain one current stable asset per supported edition.

## Does a successful installation prove compatibility?

No. Installation, build range, technical hook reach and full field validation are different claims. Consult the compatibility document for the edition being used.

## Will every WhatsApp update be supported automatically?

No. Changes to the extension path, identity, request structure, original memory policy or workload may require reviewed compatibility work. Unknown conditions pass through unchanged.

Future compatibility work is not guaranteed and depends on technical need, maintainer availability and project sustainability.

## Why does the project ask for sponsorship?

WAJetsamFix requires reverse engineering, private device testing, build infrastructure, package auditing, diagnostics, documentation and compatibility review across different jailbreak environments.

That work consumes personal time and creates infrastructure, device-testing and electricity costs. Voluntary sponsorship helps make continued public development more viable.

## Does sponsorship purchase support, private access or a release?

No. Sponsorship does not purchase guaranteed support, access to private builds, a feature, compatibility with an individual setup, influence over safety decisions or a release date.

There is no sponsor threshold, countdown or pay-to-release promise.

See the [project sustainability policy](SUSTAINABILITY.md).
