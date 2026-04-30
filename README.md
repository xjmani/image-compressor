# image-compressor

A privacy-first image compressor and EXIF stripper. Runs entirely in your browser. Nothing is uploaded.

Part of the [xjmani](https://xjmani.com) tools collection.

## What it does

- Compresses JPEG, PNG, and WebP files using the Canvas API in your browser
- Strips all EXIF metadata by default (GPS coordinates, camera serial numbers, timestamps)
- Batches up to 50 files at once
- Lets you tune quality, max dimension, and output format
- Downloads single files or a `.zip` of the whole batch

## Why use it

Most online image compressors upload your files to a server. This one does not. There is no backend. The page makes zero network requests after it loads — there is a counter in the header showing exactly that, which you can verify in your browser's devtools.

## Three ways to run it

1. **Open the website:** [image.xjmani.com](https://image.xjmani.com) (coming soon)
2. **Download the standalone HTML:** one self-contained file you can run from disk, fully offline
3. **Use the CLI:** `npx xjmani-image-compressor ./photos` (coming soon)

## Privacy

- No uploads, ever
- No analytics, no telemetry
- No cookies, no tracking
- The only data stored on your device is your theme preference (`localStorage`)

## Development

This is a single-file prototype: open `index.html` in a browser. The production build will be extracted to a Vite-based standalone deployment.

## License

MIT — see [LICENSE](LICENSE).
