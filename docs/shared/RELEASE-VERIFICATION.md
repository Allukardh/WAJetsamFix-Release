# Release verification

Download the package only from the official GitHub Release and verify its SHA-256 before installation.

For RootHide 0.8.0:

`com.allukardh.wajetsamfix_0.8.0_iphoneos-arm64.deb`

Expected SHA-256:

`6bb869201df4ab00c5fc5465f29c56fcd312ff213ae559167a5b963a64ec65ce`

On macOS or Linux:

```sh
shasum -a 256 com.allukardh.wajetsamfix_0.8.0_iphoneos-arm64.deb
```

The output must match exactly. Do not install the package if the value differs.

The final v0.8.0 Release must contain exactly one asset: the RootHide `.deb`. Historical 0.8 prereleases are notes-only and contain no assets.
