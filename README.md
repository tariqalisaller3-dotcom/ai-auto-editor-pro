# AI Auto Editor Pro

A free-first, browser-based video editing starter project built with React, Vite and FFmpeg.wasm. It does not require installing a desktop video editor.

## Current working features
- Select a local video in the browser.
- Process one video at a time using FFmpeg.wasm.
- Remove the original audio track.
- Optionally add a user-supplied music file (use only music you have rights to use).
- Export MP4 with optional 9:16 1080x1920 framing.
- Basic sharpening, contrast and saturation enhancement.
- Preview the edited video and download it.

## Important limitations (read before publishing)
- **TikTok URL import is a UI placeholder, not a downloader.** TikTok may block browser-side retrieval through authentication, anti-bot controls and CORS. Use a video file you are authorized to download/upload. Do not bypass access controls or download content without permission.
- **This starter does not yet implement AI speech transcription, animated captions, automatic highlight clipping, face tracking, automatic sound-effect placement, or a copyright-detection database.** The interface marks captions as a next-build feature. These require additional models/services and careful testing.
- Removing audio and adding a different track does not make the underlying video copyright-free. Use original/licensed footage and music. No automated checker can guarantee that a video is copyright-safe.
- Enhancement here is conventional FFmpeg filtering, not generative AI super-resolution. True AI upscaling requires downloading model weights in the browser or using a remote inference service; model downloads can be large and hardware-dependent.
- FFmpeg.wasm is memory-intensive. Large or long videos may fail in a browser tab. Start with a short MP4 (e.g. under 300 MB).
- The FFmpeg core is loaded from unpkg on first edit, so internet is required for that initial download. The app itself runs in the browser after it is served.

## Run locally
Install Node.js (LTS) once, then:

```bash
npm install
npm run dev
```

Open the local URL printed by Vite.

## Build

```bash
npm run build
```

The production site is generated in `dist/`.

## Deploy to GitHub Pages
1. Push this repository to GitHub.
2. In the repository, open **Settings → Pages**.
3. Choose **GitHub Actions** as the build source.
4. Add a workflow that runs `npm ci`, `npm run build`, and publishes `dist/` with the official GitHub Pages actions. (A workflow can be added in the next setup step.)

## License
MIT. See `LICENSE`.

The included `.github/workflows/deploy.yml` automatically builds and deploys on pushes to `main`. In **Settings → Pages**, select **GitHub Actions** as the source.
