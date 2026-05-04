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

Most online image compressors upload your files to a server. This one does not. There is no backend. After the page loads, no network requests are made. Open DevTools and watch the Network tab while you compress a file. Nothing fires.

## Three ways to run it

1. **Open the website:** [image.xjmani.com](https://image.xjmani.com) (coming soon)
2. **Download the standalone HTML:** clone this repo (or grab the zip) and open `index.html`. Libraries are vendored under `vendor/`, so no internet is required after that
3. **Self-host:** drop `index.html` and `vendor/` on any static host (NAS, intranet, SharePoint). Anyone who can reach the page can use it without bytes leaving the network

## Self-host

Drop `index.html` and `vendor/` on any static file host: NAS, SharePoint, internal wiki, or any HTTP server you control. The page runs entirely in the browser, so anyone who can reach the URL can compress images and strip EXIF without bytes leaving your network.

No build step. No server runtime.

## Privacy

- No uploads, ever
- No analytics, no telemetry
- No cookies, no tracking
- The only data stored on your device is your theme preference (`localStorage`)

## Development

This is a single-file prototype: open `index.html` in a browser. The production build will be extracted to a Vite-based standalone deployment.

## License

MIT, see [LICENSE](LICENSE).
