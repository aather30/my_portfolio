# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Single-page personal portfolio website for Ali Ather (aliather.dev). The entire site lives in one file — `index.html` — with no build step, no framework, and no dependencies beyond Google Fonts loaded via CDN.

## Development

Open `index.html` directly in a browser — no server required for most changes. For accurate Calendly widget or font loading, serve locally:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

There are no tests, linters, or build commands.

## Architecture: `index.html`

The file is structured in three blocks:

1. **`<head>`** — SEO meta tags, Open Graph, Twitter Card, JSON-LD structured data (`Person` schema), Google Fonts preconnect, and a large `<style>` block.

2. **`<style>` block** — All CSS is inline here. Organized with CSS custom properties (design tokens) at the top in `:root`, followed by resets, utilities, animations, and component styles. Sections are clearly commented (e.g., `DESIGN TOKENS`, `ANIMATIONS`, `BUTTONS`).

3. **`<body>`** — Sections in order: `#navbar` → `#hero` → `#stats` → `#about` → `#experience` → `#skills` → `#education` → `#certifications` → `#book-meeting` (Calendly embed) → `#references` (PDF recommendation letters) → `#contact` → `<footer>`. A `<script>` block at the end handles: typewriter animation, fade-up scroll observer, mobile nav toggle, skill bar fill animation, counter animation, and active nav link highlighting via `IntersectionObserver`.

## Assets

`my_documents/` contains PDF files (resumes, cover letters, reference letters) that are linked from the `#references` section and the resume download button.

## Design tokens

All colors, spacing, and typography values are CSS variables in `:root`. When changing the visual style, update the tokens rather than individual properties. Key tokens: `--bg`, `--surface`, `--card`, `--blue`, `--grad`, `--grad-text`, `--font`, `--mono`.
