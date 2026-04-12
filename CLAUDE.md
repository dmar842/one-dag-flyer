# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Single-page marketing brochure for a **6,150 RSF sublease on the 26th floor of One Dag Hammarskjold Plaza** (Midtown East, NYC). Built for CBRE as a digital flyer — no build tools, no dependencies.

## Architecture

- `index.html` — redirect stub (`meta refresh` → `OneDag_Sublease_Brochure.html`)
- `OneDag_Sublease_Brochure.html` — the entire site: HTML + inline CSS + inline JS in a single ~1.7MB file. All images are base64-encoded inline. No external assets except Google Fonts (Bodoni Moda, Hanken Grotesk).

## Design System

CSS custom properties defined in `:root`:
- **Colors**: OKLCH palette — midnight navy base (hue 260), warm gold accent (hue 85). Warm white (`--warm`) body bg, cream sections. All neutrals tinted toward navy.
- **Fonts**: `--font-display` (Bodoni Moda, serif), `--font-body` (Hanken Grotesk, sans-serif)
- **Spacing**: 4pt scale via `--sp-4` through `--sp-96`

## Design Reference

Follow the aesthetic of `~/401-pas/index.html` (401 Park Avenue South flyer): warm white base, light-dominant sections, centered hero with decorative frame and badge, copper/gold accents restrained to labels and hover states, border-based card interactions. Dark sections only for hero, floor plan, building stats, gallery, and footer.

## Git Workflow

GitHub email privacy is enabled. Every commit needs: `GIT_COMMITTER_EMAIL="170487050+dmar842@users.noreply.github.com"`

## Working with the File

The file cannot be read in one pass (~488k tokens). Use `offset`/`limit` to read CSS (lines 1–650) or HTML (lines 650+). To modify images, extract base64 URIs via Python regex, rebuild HTML, and inject them back.

## Development

No build step. Open `OneDag_Sublease_Brochure.html` directly in a browser:

```bash
open OneDag_Sublease_Brochure.html
```

## Previewing

Playwright blocks `file://` — use `python3 -m http.server 8123` then navigate to `http://localhost:8123/OneDag_Sublease_Brochure.html`.
