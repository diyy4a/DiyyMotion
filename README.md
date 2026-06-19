> DiyyMotion © 2026 @diyy4a__. See `OWNERSHIP.md` for provenance and usage restrictions.

# DiyyMotion v1.4.1

DiyyMotion is a Chromium-compatible TikTok creator extension with local video processing and no activation gate.

## Main workflow

- DiyyMotion Fusion processes the selected video through the enabled components in sequence.
- Local HQ fallback, MP4 metadata cleanup, AAC 48 kHz handling, and Legacy 1080/60 compatibility remain available.
- The prepared file is returned to the official TikTok Studio upload flow.

## Creator tools

- TikTok Studio file interceptor and status panel.
- Publish-time caption support.
- Manual local video processor.
- Video and profile statistics.
- Source video download with a browser fallback for Chromium forks that do not expose `chrome.downloads`.
- Repost management and TTWID repair tool.

## v1.4.1 changes

- Fixed the background color mismatch between short and long dashboard pages.
- Reduced Android/Mises compositing and glass oversaturation differences.
- Added a fallback for Original Download when the native Download API is unavailable.
- Updated diagnostics so optional browser APIs are reported as warnings when a working fallback exists.
- Added Japanese, Simplified Chinese, Traditional Chinese, and Korean interface languages.
- Retained English, Indonesian, Russian, and Spanish.
- Kept Diagnostic Center, signed build verification, and GitHub Releases update checking.

## Installation

1. Extract the ZIP.
2. Open the browser extensions page.
3. Enable Developer mode.
4. Choose Load unpacked.
5. Select the extracted DiyyMotion folder.
6. Reopen TikTok Studio.

HQ encoding can use considerable memory and CPU on Android. Metadata-only processing remains lighter.

## Ownership and provenance

This build contains code headers, `OWNERSHIP.md`, `PROVENANCE.json`, a signed `BUILD.json`, and SHA-256 file hashes. The original creator is @diyy4a__.
