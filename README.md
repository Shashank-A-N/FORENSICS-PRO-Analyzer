# FORENSICS-PRO-Analyzer (v3)

Forensics Pro Analyzer is a single-file, in-browser React application that performs a comprehensive set of forensic analyses on images. Everything runs client-side — there is no server processing — so image files remain on your machine and analyses are fast and private.

This repository contains the standalone `index.html` application that you can open locally or host on GitHub Pages.

---

## Features

- Pixel Loupe (Magnifier)
  - 10× loupe that follows the mouse on the "Original" view and reports exact RGB/Hex values for the pixel under the cursor.
- Color Histogram
  - R, G, B and Luminance histograms rendered on a canvas for distribution analysis.
- JPEG Ghost (Quantization Table / DCT)
  - Visualizes the 64 DCT coefficients (8×8) — a forensic test for double-compression or non-standard saves.
- Error Level Analysis (ELA)
  - Interactive ELA highlighting areas with different compression artifacts to detect edits.
- Improved Clone / Copy-Move Detection
  - Sensitive algorithm using small overlapping blocks to find subtle duplicated regions.
- LSB (Steganography) Visualization
  - Shows least-significant-bit planes for each channel to help spot hidden data.
- Noise Analysis
  - Emphasizes high-frequency noise differences across regions.
- Robust Metadata & EXIF Parsing
  - Multi-tier parsing strategy (exifr → exif-js → piexifjs fallback) to extract as much metadata as possible.
- String & Hex Dump
  - Scans file bytes for embedded strings and displays a hex dump of file headers.
- JSON Report Generation
  - Export a complete JSON report of all findings for archiving or further analysis.

---

## Quick Start — Run Locally

No build tools or server are required.

1. Download or copy `index.html` from this repository.
2. Save it to your computer.
3. Double-click `index.html` (or open it with your browser: Chrome, Firefox, Safari).
4. Drag & drop an image onto the upload area or use the file picker.
5. Analysis is automatic — switch between tabs (Metadata, ELA, JPEG Ghost, Histogram, etc.) to review results.
6. Use the export button to download a JSON report of the current analysis.

Notes:
- For best results use recent Chrome or Firefox.
- Large images may take longer to analyze and use more memory.

---

## Tabs / UI Overview

- Original
  - Main image viewer with pixel loupe and zoom controls.
- Metadata
  - Full EXIF and metadata listing with fallbacks and parsed fields.
- Histogram
  - Color and luminance histograms with channel overlays.
- JPEG Ghost
  - Quantization / DCT visualization useful for spotting double compression artifacts.
- ELA (Error Level Analysis)
  - Adjustable levels to emphasize recompressed regions.
- Clone Detection
  - Visual heatmap of likely copy-move regions.
- LSB
  - Visualizes LSB planes across channels.
- Noise
  - High-pass/noise emphasis visualization.
- Hex / Strings
  - Raw file header hex dump and printable string extraction.
- Report / Export
  - Download JSON report containing metadata + results of each analysis.

---

## Hosting on GitHub Pages

To publish this single-file app on GitHub Pages:

1. Create a new public repository (for example: `forensics-analyzer`).
2. Upload `index.html` to the repository root (Add file → Upload files).
3. Commit the change (e.g., "Initial commit with app").
4. Go to the repository Settings → Pages.
5. Under "Build and deployment" choose "Deploy from a branch".
6. Select the branch (usually `main`) and folder `/ (root)` then Save.
7. Wait a minute or two for GitHub to deploy. The Pages URL will appear in Settings → Pages.

Example live URL format:
https://<your-github-username>.github.io/<repo-name>/
(e.g. https://shashank-a-n.github.io/FORENSICS-PRO-Analyzer/)

---

## Privacy & Security

- All image processing is performed in the browser; nothing is uploaded to any server.
- JSON reports are generated locally and downloaded to your machine.
- Do not open untrusted or malicious files in your browser if you are concerned about security — the app reads file bytes into browser memory.

---

## Troubleshooting

- If the app appears blank after opening `index.html`, try:
  - Using a modern browser (Chrome/Firefox).
  - Opening the developer console (F12) to check for errors.
- If analysis is slow:
  - Try resizing the image or using a lower-resolution copy.
  - Close other tabs or applications that use lots of memory.

---

## Development & Contribution

This is intended as a single-file application. If you'd like to contribute:
- Open an issue describing the feature or bug.
- Fork the repo, make changes, and send a pull request.
- For significant changes (adding build tooling, splitting into modules, adding tests), please open an issue first to discuss design.

If you want me to add a template CONTRIBUTING.md, development build scripts, or split the single file into a multi-file project, tell me and I can draft those next.

---

## Dependencies / Credits

- Uses client-side libraries (exifr, exif-js, piexifjs, etc.) for robust metadata parsing and analysis utilities. See source code comments for full attributions.
- Algorithms and ideas adapted from common forensic analysis techniques (ELA, histogram inspection, DCT/quantization tests, LSB visualization).

---

## License

No license file is included by default in this repository. If you want this project to be permissively licensed, consider adding an MIT license. If you tell me which license you prefer I can add a LICENSE file and update README accordingly.

---

## Changelog

v3 — Consolidated UI; improved clone detection sensitivity; more robust metadata fallbacks; JSON report export; improved JPEG Ghost rendering.

---

If you want this README committed to the repository as README.md I can create the commit for you (or provide the exact patch to paste). I prepared the expanded README above to replace the single-line file that was previously present; next I can either push it to your repo or help create a CONTRIBUTING guide, example images, or a GitHub Actions workflow to auto-deploy to Pages — tell me which you'd like and I'll proceed.
