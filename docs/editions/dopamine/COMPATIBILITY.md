# Dopamine Edition compatibility

## Intended environment

- conventional rootless Dopamine 2;
- regular ElleKit tweak injection;
- arm64 and arm64e targets supported by the environment;
- WhatsApp notification `ServiceExtension` as the exact target;
- documented WhatsApp and relevant tweak versions for each validation cycle.

## Current private evidence

Private real-device testing has confirmed that the Dopamine Edition can:

- load its final dylib inside live `/usr/libexec/runningboardd`;
- install the real `memorystatus_control` hook;
- preserve a real call in exact pass-through mode;
- rewrite an exact supported 24 MiB target request;
- retain zero rewrite failures and zero compatibility warnings;
- restore normal notification delivery in a controlled high-ceiling test;
- collect useful physical-memory telemetry through a separate bounded on-demand tool.

The validated private environment used:

```text
Device: iPhone15,3 / iPhone 14 Pro Max
System: iOS 16.3.1 (20D67)
Jailbreak: conventional rootless Dopamine 2
WhatsApp: 26.26.73
Watusi: 1.3.18
WatusiTools: 2.8.3
```

The passing private configuration kept global Tweak Injection enabled and used Choicy to disable injection in:

- `ServiceExtension`;
- `NotificationExtension`;
- `ShareExtension`.

Text, consecutive messages, images, audio messages and stickers delivered with WhatsApp closed and the device locked. More than 2,800 exact rewrites were retained with zero failures and zero compatibility warnings.

## Memory-policy qualification

The unusually heavy restored-data profile exceeded 40 MiB during successful ServiceExtension work. A temporary 96 MiB private diagnostic ceiling restored delivery and allowed measurement, but it is not the final RC policy.

The planned RC profile values are:

```text
Recommended: 48 MiB
Expanded:    72 MiB
Extreme:     96 MiB
```

These profiles are not implemented in the current Alpha and are not a public compatibility claim. They will be ported to conventional Dopamine only after the profile architecture passes private RootHide validation.

An automatic recommendation mode is only under evaluation. It must not be described as compatible until peak collection, recommendation margins, persistence, Userspace Reboot and fallback behavior have been validated.

Total backup size alone does not define the required memory limit.

## Third-party package information

A future Preferences page may display locally detected versions of relevant WhatsApp tweaks as diagnostic context. Such display would be informational only and would not establish endorsement or compatibility.

No third-party package version may alter the protection policy automatically without an independently validated WAJetsamFix rule.

## Not yet approved

No conventional Dopamine combination is approved for public compatibility yet.

Still required:

- extended field stabilization;
- RootHide profile-layer validation;
- Dopamine RC profile port and revalidation;
- Safe Mode and recovery testing;
- direct upgrade, uninstall and clean reinstall;
- sustained RC use;
- final maintainer approval.

Technical reach and one successful private Alpha environment must not be presented as universal support, RC readiness or a public package.