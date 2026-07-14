# Changelog

## 0.7.1 — Stable

Candidate-first runtime correction and final stable release.

### Runtime

- non-24 MB requests pass through before PID-path inspection;
- only exact 24 MB candidates reach target validation;
- exact WhatsApp ServiceExtension target only;
- null, malformed and unknown requests pass through unchanged;
- no broad PID probing, cache or retained target state;
- exact 24 MB → 40 MB rewrite policy retained.

### Hardening retained from 0.7.0

- centralized protocol and version constants;
- authoritative PatchLoader and source-hook state;
- ABI-safe request handling;
- event-driven diagnostics;
- protected rotating log;
- non-resident `wajetsamfixctl status` command;
- no polling, timer, scan loop, repair loop or global Jetsam modification.

### Final field validation

- 1,003 successful rewrites from 1,003 attempts;
- zero failures;
- zero compatibility warnings;
- normal first-message, sequential and burst notification delivery;
- no observed delay or single-tick episode;
- approximately 0.0% diagnostics-bridge CPU.

## 0.7.0 — Superseded

Introduced the complete 0.7 hardening foundation. It was superseded by 0.7.1 after architectural review identified unnecessary synchronous PID-path inspection for non-24 MB requests. No deterministic failure was proven, but the extra resident work was outside the intentionally narrow scope of the tweak.

## Earlier versions

Versions 0.1.0 through 0.6.2 document the progression from experimental handling to the proven pure source-side PatchLoader architecture. Historical packages are not distributed from this repository; the latest stable package is the supported public download.
