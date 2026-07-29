# CutLocal — Background Remover

Next project in the NakliTechie series. Single HTML file, zero dependencies, zero build step.

## What we're building

Drop an image → ML removes the background → download as transparent PNG. Nothing leaves the browser.

## Key decisions (already researched)

- **Model:** `briaai/RMBG-1.4` (~176 MB, ISNet architecture)
  - Loaded via Transformers.js `image-segmentation` pipeline
  - No WebGPU required — runs on WASM CPU
  - Sweet spot between RMBG-2.0 (~1 GB, too heavy) and older U2-Net models
  - Works best at 1024px input
  - Reference: Addy Osmani has an open-source demo using this exact model

- **Output:** Alpha mask applied to original image via Canvas → `canvas.toBlob('image/png')` → download
- **Pattern:** Same Web Worker + Transformers.js stack as BabelLocal and VoiceVault
- **Design:** NakliTechie design system (indigo `#667eea`, gray palette, card layout, status badge)
- **Name:** CutLocal
- **Repo:** Will go to https://github.com/NakliTechie/CutLocal

## Main technical challenge

Rendering the mask correctly:
1. Model returns a greyscale mask (or float32 probability map per pixel)
2. Draw original image on canvas
3. Use mask as alpha channel — pixels where mask ≈ 0 become transparent
4. Export as PNG (PNG supports transparency; JPEG does not)

## Files to ship

- `index.html` — entire app
- `README.md`
- `LICENSE` (MIT)
- `.gitignore` (same pattern: `*`, then `!index.html`, `!README.md`, `!LICENSE`, `!.gitignore`)

## Series context

See `ideas.md` (copied here) for full backlog. After CutLocal: ReadLocal (OCR) then SpeakLocal (TTS).
