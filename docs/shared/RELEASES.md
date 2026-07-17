# Release policy

GitHub Releases are displayed in descending order, with the newest release at the top.

## Current state

Only the RootHide Edition has a public stable package. Its current stable Release retains the downloadable `.deb`; older RootHide Releases remain notes-only.

The Dopamine Edition may be described in public-safe documentation and development updates without creating a GitHub Release, tag, pre-release or binary asset. A documented private milestone is not a public package.

## Release authorization is separate from technical readiness

Passing technical, functional or RC gates does not automatically authorize publication.

A public RC or stable Release requires a separate maintainer decision based on:

- technical quality and safety;
- complete installation, recovery and removal documentation;
- expected support burden;
- available personal and family time;
- infrastructure and testing costs;
- long-term project sustainability.

A technically complete private build may remain private, be postponed or never be published.

See the [project sustainability policy](SUSTAINABILITY.md).

## Development communication without a binary

Public documentation may describe:

- the existence and intended environment of an edition;
- technical or functional milestones already validated privately;
- conservative architecture inherited from a stable edition;
- remaining stabilization, lifecycle and product gates;
- planned features clearly labeled as under evaluation;
- project sustainability and absence of release promises.

It must not expose private source, raw logs, internal paths, field reports, tester identity, private build artifacts or unapproved binaries.

A roadmap or changelog entry does not create a support commitment, public compatibility claim or release date.

## Multi-edition asset policy

If the Dopamine Edition later becomes public and stable, retain **one current stable downloadable package per supported edition**:

- current RootHide Edition stable `.deb`;
- current Dopamine Edition stable `.deb`.

When a newer stable version of an edition is published, remove the obsolete asset from that edition's previous Release while preserving its tag and curated release notes. Do not remove the other edition's current stable asset.

Historical Alphas and superseded RCs remain notes-only unless the maintainer intentionally authorizes a controlled public test artifact.

## Edition-qualified releases

Future Dopamine tags and titles must identify the edition so they cannot be confused with the existing RootHide history.

Recommended pattern:

```text
Tag: dopamine-vX.Y.Z-rcN or dopamine-vX.Y.Z
Title: WAJetsamFix — Dopamine Edition X.Y.Z RCN or X.Y.Z
```

Existing RootHide tags and titles remain unchanged.

GitHub exposes only one repository-wide `Latest` designation. Once two editions are public, each edition's documentation must link to its own current release/tag rather than relying on `/releases/latest` as a universal download selector.

## Release notes

- Release notes repeat the relevant edition changelog because many users read the Release page without opening repository documentation.
- RCs are marked as pre-releases and are not marked as the global latest stable release.
- Every release identifies package ID, edition, validated environment, filename and SHA-256.
- Dopamine release notes must include any required Choicy plugin isolation.
- Public release notes must not expose source code, private implementation details, credentials, internal paths, raw field reports or development records.
- The public sponsor call-to-action may appear after the latest release changelog so it is visible before the Assets section.
- Sponsorship language must describe sustainability without promising access, support, features or release dates.

No Dopamine RC or stable release is currently authorized.