> DiyyMotion © 2026 @diyy4a__. See `OWNERSHIP.md` for provenance and usage restrictions.

# DiyyMotion v1.5.0

DiyyMotion is a Chromium-compatible TikTok creator extension with local video processing and no activation system.

## Main workflow

- A video selected in TikTok Studio is intercepted before upload.
- Fusion Maximum runs the enabled local processing components in sequence.
- The processed file is returned to the official TikTok Studio uploader.
- TikTok still performs its own server-side transcoding after upload.

## Fusion Maximum

All main processing components are enabled by default:

- Temporal Method with 2× input timestamp scaling.
- Local H.264 HQ encoding with CRF 18 and `yuv420p` output.
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

Local HQ encoding can use considerable memory and CPU on Android. Large videos may fail on devices with limited RAM.

## Build and provenance

This package contains code ownership records, provenance metadata, a local build manifest, and SHA-256 file hashes. Development and protected builds remain unsigned unless they are signed with the official DiyyMotion release key.
