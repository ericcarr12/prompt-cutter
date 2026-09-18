# Prompt Cutter

**Cut AI prompt token usage without losing meaning.**

🔗 **Live site:** [https://www.promptcutter.com](https://www.promptcutter.com)

Prompt Cutter is a browser-based tool that compresses AI prompts to reduce token usage and stretch AI plan token limits further. It offers two compression modes:

- **Basic** — offline, rule-based compression. Runs entirely client-side; nothing you type ever leaves your device.
- **Turbo** — AI-powered compression via the Anthropic Claude API, using your own API key (BYOK — your key stays in your browser's local storage, never on our servers).

## Features

- Automatic task-tag detection (e.g. summarize, generate, translate), with a diff view showing exactly what was trimmed
- Voice input via the Web Speech API
- Share directly to Email, X, Facebook, LinkedIn, WhatsApp, or Reddit — or the device's native share sheet on mobile
- Fully responsive, mobile-first layout
- Built and audited to WCAG 2.1 AA: full keyboard operability, managed focus for all modal dialogs, and screen-reader-friendly labeling throughout

## Repository structure

```
.
├── README.md          ← you are here
├── index.html          ← minified production build (what's deployed to promptcutter.com)
├── index-edit.html     ← readable source — edit this, then rebuild index.html
└── images/             ← logo, icons, and share-platform assets referenced by index.html
```

## Legal & Proprietary Notice

Prompt Cutter, its logo, and its compression engine are the proprietary property of **Oxygen For Aliens LLC**. © 2026 Oxygen For Aliens LLC. All rights reserved.

This repository is made available for **viewing and reference purposes only**. Unless you have received prior written permission from Oxygen For Aliens LLC:

- You may **not** copy, reproduce, distribute, sublicense, or create derivative works from the code, algorithms, branding, or content in this repository, in whole or in part.
- You may **not** use this code, or any substantially similar reimplementation of its compression logic, in any commercial or publicly deployed product or service.
- You may **not** reverse-engineer, decompile, or deobfuscate any minified or obfuscated assets in this repository with the intent of extracting, copying, or re-implementing the underlying algorithms.

No license, express or implied, to any patent, trademark, copyright, or other intellectual property right is granted by the publication of this repository. See [`LICENSE`](./LICENSE) for the full terms.

For licensing inquiries, contact Oxygen For Aliens LLC directly.

> This notice is provided for informational purposes and does not constitute legal advice. Consult a qualified attorney regarding enforcement of intellectual property rights.
