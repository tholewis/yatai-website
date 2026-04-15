# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a zero-dependency static website about Japanese street food culture (屋台 yatai). The entire application lives in a single file: `index.html` (~1,500 lines of HTML + embedded CSS + inline SVG). There is no build step, no package manager, and no JavaScript.

## Running the Site

Open `index.html` directly in a browser:

```bash
open index.html
```

## Architecture

**Single-file layout** — all HTML, CSS, and SVG are embedded in `index.html`. Sections are anchor-linked via smooth scroll (`scroll-behavior: smooth`). Navigation anchors: `#intro`, `#history`, `#foods`, `#experience`, `#regions`, `#festivals`.

**CSS structure** (lines 7–863 of `index.html`):
- CSS custom properties define the full color palette at `:root`:
  - `--red` / `--dark-red` — brand accents
  - `--ink` — deep navy, primary text/backgrounds
  - `--gold` — nav and tag highlights
  - `--cream` / `--warm` / `--mid` / `--light` — background and surface tones
- Typography: Noto Serif JP (display/kanji), Noto Sans JP (body), Playfair Display (English headings) — loaded from Google Fonts
- Layout uses CSS Grid for content sections and Flexbox for nav/buttons
- Decorative kanji watermarks use absolute positioning with low opacity
- `backdrop-filter: blur(8px)` on the nav (with `-webkit-` prefix)

**Animations**: `lantern-sway` keyframe on hero lanterns; `@media (prefers-reduced-motion: reduce)` disables animations for accessibility.

**Responsive breakpoints**: `max-width: 1024px` and `max-width: 560px` — grids collapse to single columns.

## Accessibility

The site targets WCAG 2.1 AA. Maintain:
- Skip link (`.skip-link`) at the top of `<body>`
- `aria-label` / `aria-hidden` on decorative elements
- Focus styles: 3px `--gold` outline
- Semantic sectioning (`<main>`, `<section>`, `<nav>`, `<footer>`)
