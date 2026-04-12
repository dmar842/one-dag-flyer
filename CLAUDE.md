# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Single-page marketing brochure for a **6,150 RSF sublease on the 26th floor of One Dag Hammarskjold Plaza** (Midtown East, NYC). Built for CBRE as a digital flyer — no build tools, no dependencies.

## Architecture

- `index.html` — redirect stub (`meta refresh` → `OneDag_Sublease_Brochure.html`)
- `OneDag_Sublease_Brochure.html` — the entire site: HTML + inline CSS + inline JS in a single ~1.7MB file. All images are base64-encoded inline. No external assets except Google Fonts (Cormorant Garamond, Outfit).

## Design System

CSS custom properties defined in `:root`:
- **Colors**: navy (`#0d1f4c`), gold (`#c9a84c`), CBRE green (`#006a4d`), warm grays
- **Fonts**: `--font-display` (Cormorant Garamond, serif), `--font-body` (Outfit, sans-serif)
- **Spacing scale**: `--space-xs` through `--space-5xl` (4px–128px)

## Development

No build step. Open `OneDag_Sublease_Brochure.html` directly in a browser:

```bash
open OneDag_Sublease_Brochure.html
```

The file is large (~1.7MB) due to inline base64 images. When editing, use offset/limit to read specific sections rather than loading the entire file.
