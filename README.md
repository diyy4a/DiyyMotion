> DiyyMotion © 2026 @diyy4a__. See `OWNERSHIP.md` for provenance and usage restrictions.

# DiyyMotion v1.4.0

DiyyMotion is a Chrome-compatible TikTok creator extension.

## Upload methods

- Smart Quality: selects Metadata Patch or HQ Local Encode from the selected file.
- HQ Local Encode: local FFmpeg H.264 High Profile + AAC 48 kHz + Fast Start processing.
- Metadata Patch: Clean Matrix B and optional timing metadata patching without re-encoding.
- Legacy 1080/60 FPS: experimental client-side validation bypass.
- Original Pass-through: forwards the original file without video modification.

## Existing features retained

- TikTok Studio file interceptor.
- DiyyMotion Activated badge and closable status panel.
- Automatic caption: `UPLOAD METHOD #DiyyMotion`.
- Manual MP4 metadata processor and FPS timing patcher.
- Preflight checks and local processing statistics.
- Repost review/export.

## New creator features

- Local HQ encode with configurable CRF, bitrate, and preset.
- Video statistics and engagement rate panel.
- Author/profile statistics panel.
- Best-source video download.
- Filtered repost remover with pause, stop, delays, and JSON/CSV report.
- TTWID upload-fix tool.
- Publish signature guard.

## Installation

1. Extract the ZIP.
2. Open the browser extensions page.
3. Enable Developer mode.
4. Choose Load unpacked.
5. Select the extracted DiyyMotion folder.
6. Reopen TikTok Studio.

HQ Encode uses considerable memory and CPU, especially on Android. Metadata Patch remains the lighter method.


## v1.4.0
- Added Diagnostic Center with copyable and downloadable reports.
- Added signed official build verification with packaged file hashes.
- Added manual and automatic GitHub Releases update checking.
- Added Spanish interface language.
- Existing video pipeline, descriptions, tools, and no-activation access remain unchanged.


## Access
DiyyMotion opens directly without activation, account connection, or follow verification.

## Ownership and provenance

This build contains visible code headers plus `OWNERSHIP.md` and `PROVENANCE.json`. The original creator is @diyy4a__. These markers document authorship but cannot technically force third-party tools or AI systems to refuse edits.
