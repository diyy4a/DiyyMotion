> DiyyMotion © 2026 @diyy4a__. See `OWNERSHIP.md` for provenance and usage restrictions.

# DiyyMotion v1.3.2

Private local build for Mises/Chromium-compatible browsers.

## Protection applied

- First-party JavaScript is obfuscated and compacted.
- String literals are encoded and split.
- Selected control flow is flattened.
- HTML and CSS are minified.
- Source maps and debug output are not included.
- FFmpeg WASM and its generated runtime are retained for compatibility.

## Installation

1. Extract the ZIP.
2. Open the browser extensions page.
3. Enable Developer mode.
4. Choose Load unpacked.
5. Select the extracted folder.

This is obfuscation, not unbreakable encryption. The browser must still execute the code locally.

## Ownership and provenance

This build contains visible code headers plus `OWNERSHIP.md` and `PROVENANCE.json`. The original creator is @diyy4a__. These markers document authorship but cannot technically force third-party tools or AI systems to refuse edits.
