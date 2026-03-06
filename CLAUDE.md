# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Photography business website for **Ragu Lens & Frames** (Raguraman Prabakaran), based in Voorhees, New Jersey. Contact: ragulensandframes@gmail.com.

Two standalone single-file HTML websites — no build system, no dependencies, no frameworks.

## Files

- `pastel-version.html` — Soft pastel theme (cream, dusty rose, sage)
- `dark-version.html` — Dark elegant theme (near-black, warm gold)
- `jpgs/` — All client photos used in the gallery

## Opening in Browser

```bash
start "C:\SRE\claude\pastel-version.html"
start "C:\SRE\claude\dark-version.html"
```

## Architecture

Both HTML files are fully self-contained (HTML + CSS + JS in one file). They share identical structure and content — only the visual theme differs.

**Section order:** Nav → Hero → Services → Gallery → About → Contact → Footer

**Gallery system:** Filter buttons with `data-filter` attributes drive JS-powered category filtering. Each `.gallery-item` has a `data-category` attribute (`family`, `baby`, `events`, `nature`). Hidden items use `.hidden { display: none }`.

**Contact form:** Uses [formsubmit.co](https://formsubmit.co) — no backend needed. Activates after first submission via email confirmation to ragulensandframes@gmail.com.

## Theme Differences

| | Pastel | Dark |
|---|---|---|
| Background | `#FDF6F0` (cream) | `#0F0F0F` |
| Accent | `#D4837A` (dusty rose) | `#C9A96E` (gold) |
| Buttons | Rounded pill (`border-radius: 50px`) | Sharp rectangular, uppercase |
| Gallery images | Natural color | `filter: brightness(0.75) grayscale(15%)` |

## Responsive Breakpoints

- `768px` — hamburger menu, services/about/contact stack to 1 col, gallery → 2 col
- `480px` — reduced section padding, gallery items shrink to `180px` height

## Photo Paths

All gallery images use relative paths: `jpgs/filename.jpg`. Filenames with spaces must be URL-encoded (e.g., `Deepavali%202025-14.jpg`, `142A7946-4%20-%20Copy.jpg`).

## Git

```bash
git add -A
git commit -m "message"
git push origin main
```

Remote: `https://github.com/RaguSRE1979/Ragu-lens-and-frames.git`
