# SnipLocal

Remove image backgrounds locally in your browser. No upload. No server. No account.

Powered by [RMBG-1.4](https://huggingface.co/briaai/RMBG-1.4) via [Transformers.js](https://github.com/huggingface/transformers.js) — the model runs entirely in WebAssembly on your device.

## Features

- **Background removal** — drop any JPG, PNG, or WebP and get a clean PNG
- **Background fill** — transparent, white, black, cream, beige, or any custom colour
- **Soften edges** — feathers the mask for cleaner hair and fine detail
- **Passport mode** — center-crops to country-specific dimensions at 300 DPI
- **4-up print sheet** — 4 passport photos laid out on A4, ready to print
- **Privacy-first** — images never leave your device

## Usage

Open `index.html` directly in Chrome or Edge. No build step, no install, no server.

First load downloads ~176 MB of model weights from Hugging Face — cached by the browser after that, works offline.

## Passport sizes

| Country | Size | Pixels (300 DPI) |
|---|---|---|
| US | 2×2 in | 600×600 |
| UK / EU | 35×45 mm | 413×531 |
| India | 35×45 mm | 413×531 |
| Canada | 50×70 mm | 591×827 |
| China | 33×48 mm | 390×567 |
| Australia | 35×45 mm | 413×531 |

## Part of the NakliTechie series

Single-file browser tools that do useful things locally.

## License

MIT
