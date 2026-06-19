> DiyyMotion © 2026 @diyy4a__. See `OWNERSHIP.md` for provenance and usage restrictions.

# DiyyMotion v1.5.6

DiyyMotion is a Chromium-compatible TikTok creator extension with local video processing and no activation system.

## Main workflow

- A video selected in TikTok Studio is intercepted before upload.
- Fusion Maximum runs the enabled local processing components in sequence.
- The processed file is returned to the official TikTok Studio uploader.
- TikTok still performs its own server-side transcoding after upload.

## Fusion Maximum

All main processing components are enabled by default:

- Temporal Method with 2× input timestamp scaling.
- Fast lossless MP4 stream copy on compatible files, with an ultrafast H.264 fallback only when remuxing is not possible.
- AAC audio normalization at 192 kbps and 48 kHz.
- MP4 Fast Start and Clean Matrix B metadata cleanup.
- Scoped quality request flags during upload and publish requests.
- Legacy 1080/60 compatibility handling.

Temporal timestamp scaling is experimental and can change video duration and effective frame pacing.

## Live console

The live console is available in:

- The extension dashboard and popup.
- The TikTok Studio processing panel.
- Manual processing and automatic upload workflows.

The console records initialization, preflight checks, FFmpeg progress, metadata processing, upload handoff, warnings, and errors. Logs are stored locally and can be cleared from the interface.

## Creator tools

- TikTok Studio file interceptor and processing status panel.
- Publish-time caption and signature support.
- Manual local video processor.
- Video and profile statistics.
- Source video download with a fallback for Chromium forks without `chrome.downloads`.
- Repost management and TTWID repair tool.
- Diagnostic Center and GitHub Releases update checker.

## v1.5.6 changes

- Added Fast Fusion for MP4 uploads on Android and Mises.
- Temporal 2× timestamp scaling now uses lossless stream copy instead of decoding and re-encoding every frame when the source is already MP4-compatible.
- Preserves the original video and audio streams, so the fast path does not introduce another generation of compression.
- Keeps Fast Start, Clean Matrix B, upload quality flags, and Legacy 1080/60 handling.
- Falls back automatically to an ultrafast 1080p H.264 compatibility encode only if stream copy fails.
- Replaced the expensive Lanczos resize in the fallback with a faster bilinear resize.
- Added console messages that clearly identify Fast Fusion or compatibility fallback mode.

## v1.5.5 changes

- Fixed the hidden FFmpeg host handshake on Mises and Chromium forks.
- Replaced the invalid `new URL(chrome-extension://...).origin` target, which serializes as `null`, with a transferable `MessageChannel` handshake using `"*"`.
- Kept the bridge restricted to the exact iframe window while the host validates `event.source === window.parent`.
- Preserved the extension-origin FFmpeg engine, Android direct mode, Worker fallback, and original-file restoration.
- This fix runs before FFmpeg loading, so the previous `FFmpeg host did not respond` timeout no longer blocks the processing pipeline.

## v1.5.4 changes

- Removed dynamic `import()` calls from the TikTok Studio content script because Mises could not fetch extension ES modules from the page context.
- Added preloaded classic content-script bundles for the FFmpeg client and MP4 processor.
- Loaded the hidden FFmpeg host as a classic extension script to reduce module-loader compatibility failures on Android Chromium forks.
- Kept the extension-origin FFmpeg host, Android direct-engine mode, Worker fallback, transferable buffers, and original-file restoration.
- Added explicit errors when a processor bundle is missing after an extension update, making stale-tab problems easier to identify.

## v1.5.3 changes

- Added an Android and Mises compatibility engine that runs the bundled FFmpeg core inside the extension-origin host page without creating a nested Web Worker.
- Added automatic fallback from the normal extension Web Worker to compatibility mode when worker startup fails with an empty or unknown browser error.
- Preserved transferable file buffers between TikTok Studio and the extension host page.
- Added visible startup logs for worker selection, compatibility fallback, and WebAssembly readiness.
- Added a 90-second FFmpeg startup timeout instead of leaving failed sessions stuck indefinitely.
- Kept original-file restoration when both processing engines fail.

## v1.5.2 changes

- Fixed the FFmpeg core crash caused by loading an ES-module build through classic `importScripts()`.
- Converted the bundled FFmpeg core wrapper to a classic-worker-compatible script for Mises and Chromium forks.
- Added startup-stage logs for the core script and WebAssembly initialization.
- Added detailed worker crash locations and unhandled-rejection reporting to the live console.
- Kept original-file fallback when local processing fails.

## v1.5.1 changes

- Fixed FFmpeg startup on TikTok Studio and Mises Browser.
- Moved the FFmpeg Web Worker into a hidden extension-origin host page.
- Kept large video buffers transferable through a `MessageChannel` instead of copying them through extension storage or JSON messaging.
- Added explicit bridge timeout, crash, and unreadable-message handling.
- Preserved automatic fallback to the original file when local processing genuinely fails.

## v1.5.0 changes

- Added Fusion Maximum as the default automatic upload workflow.
- Enabled Temporal Method, HQ fallback, Clean Matrix B, AAC 48 kHz, quality metadata flags, and Legacy 1080/60 by default.
- Added a live system console to the dashboard, popup, and TikTok Studio panel.
- Added FFmpeg progress, processing-stage, request-patch, handoff, warning, and error logs.
- Added scoped quality metadata patching instead of permanently replacing page functions.
- Kept the Mises-compatible download fallback, multilingual interface, diagnostics, build metadata, and update checker.

## Installation

1. Extract the ZIP.
2. Open the browser extensions page.
3. Enable Developer mode.
4. Choose **Load unpacked**.
5. Select the extracted DiyyMotion folder.
6. Reopen TikTok Studio.

Fast Fusion avoids full video re-encoding for compatible MP4 files. The H.264 fallback can still use considerable memory and CPU on Android.

## Build and provenance

This package contains code ownership records, provenance metadata, a local build manifest, and SHA-256 file hashes. Development and protected builds remain unsigned unless they are signed with the official DiyyMotion release key.
