# vendor/

Third-party JavaScript libraries the tool depends on, vendored locally so the
CSP can drop `cdn.jsdelivr.net` and the standalone-HTML build doesn't need a
network connection. Versions are pinned; SHA-256 manifest is in
[`MANIFEST.sha256`](./MANIFEST.sha256).

## What's here

| File | Source | Version | Purpose |
|---|---|---|---|
| `browser-image-compression.js` | [`browser-image-compression`](https://www.npmjs.com/package/browser-image-compression) | 2.0.2 | Canvas-based JPEG/PNG/WebP compression with Web Worker offload |
| `piexif.js` | [`piexifjs`](https://www.npmjs.com/package/piexifjs) | 1.0.6 | EXIF read/strip for JPEG (no native browser API exists) |
| `jszip.min.js` | [`jszip`](https://www.npmjs.com/package/jszip) | 3.10.1 | Batch zip for "Download all" |

All three are MIT-licensed.

## Updating

To bump a version:

1. Download the new file from `https://cdn.jsdelivr.net/npm/<pkg>@<version>/dist/<file>`
2. Run `sha256sum *.js > MANIFEST.sha256` from inside this directory
3. Update the version table above
4. Test the prototype end-to-end (drag in a JPEG with GPS data, confirm strip works, batch zip)

## Why vendor

The CSP for this site locks `script-src` to `'self'`. Without vendoring, the
prototype can't load these libs. Pinning + SHA hashes also means we can detect
supply-chain tampering: if jsdelivr ever served a modified version, our local
copy + manifest would catch the divergence.
