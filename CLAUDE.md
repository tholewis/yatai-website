# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a zero-dependency static website about Japanese yatai (屋台), the food stalls. It covers how a stall is built and run, the history of stalls, and the food they cook. It is not a travel guide. The whole site is a single file, `index.html` (~600 lines of HTML, embedded CSS and inline SVG). There is no build step, no package manager and no JavaScript.

## Running the Site

Open `index.html` directly in a browser:

```bash
open index.html
```

## Content rules

- **Nothing made up.** The page has no visible citations, but every fact was checked against a source when it was written. New facts need a reliable source too, even though the citation isn't shown.
- **Traditions:** where a story is a tradition rather than a record, the text says so ("said to", "credited with", "tradition links").

## Architecture

**Sections** (anchor-linked via `scroll-behavior: smooth`): `#about`, `#stall`, `#history`, `#food` (subsections `#cat-teppan`, `#cat-sumi`, `#cat-nabe`, `#cat-amai`).

**Design direction: Techō, a cook's sketchbook.** Squared-paper background, washi-tape strips on cards, handwritten headings, marker highlights (`.hl`).

**CSS** is a single `<style>` block in `<head>`, in this order:
- **Base layout:** `.wrap` gutter, sticky header, nav, stall parts list, night timeline.
- **Illustration classes:** `.ill`, `.s`, `.s2` and the rest.
- **Design tokens and components:** starts at the `:root` block.
  - Colour tokens: `--paper`, `--grid`, `--ink`, `--ink-2`, `--marker`, `--pen`, `--tape`, `--card`.
  - Illustration tokens: `--ill-ink`, `--ill-spot`, `--ill-spot2`, `--ill-bg`.
  - Fonts, loaded from Google Fonts: Klee One (`--f-hand`, headings and Japanese) and Atkinson Hyperlegible (`--f-body`).
  - The page is deliberately light-only (`color-scheme: light`).

**Illustrations** are inline SVG line drawings (`<svg class="ill">`, `viewBox="0 0 120 120"`; the labelled stall drawing is `0 0 640 400`). Inside each SVG:
- `g.ln` holds the strokes, drawn in `currentColor` (from `--ill-ink`).
- Fill classes: `.s` / `.s2` spot colours, `.b` paper, `.k` ink, `.m` paper-coloured stroke, `.z` red zigzag.
- The numbered callouts on the stall drawing must match the numbered parts list below it.

**Responsive breakpoints:** `1024px` (two-column grids stack), `860px` and `420px` (the night timeline goes to 2 columns, then 1), `760px` (hero stacks), `640px` (mobile tweaks). The side gutter uses `max(16px, env(safe-area-inset-*))`. Nothing may scroll the page horizontally; the nav scrolls inside its own container.

## Accessibility

The site targets WCAG 2.1 AA. Maintain:
- Skip link (`.skip-link`) at the top of `<body>`
- `aria-hidden` on decorative SVG and kanji; `role="img"` and `aria-label` on informative drawings (the stall diagram)
- `lang="ja"` on Japanese text
- Visible focus: 3px `--pen` outline
- Semantic sectioning (`<main>`, `<section>`, `<nav>`, `<footer>`) and heading order h1 → h2 → h3 → h4
- `prefers-reduced-motion` disables animation and smooth scroll
