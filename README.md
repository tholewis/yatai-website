# 屋台 Yatai: Japan's food stalls

A single-page website about Japanese yatai (屋台), the food stalls: how a stall is built and run, where stalls came from, and the food they cook.

## Live Demo

Open `index.html` in any modern browser, with no build step. Or go to https://tholewis.github.io/yatai-website/ to view the site on GitHub Pages.

## Features

- **What a yatai is:** the word's two meanings, from the dictionary.
- **How a stall works:** a labelled drawing of a stall, one night from set-up to clear-up, Fukuoka's operating rules, the counter etiquette, and how festival stalls differ.
- **History:** from Edo's night soba sellers to Fukuoka's 2013 ordinance and new operators chosen since 2016.
- **Food:** 18 dishes in four groups (griddle, grill and fryer, pot, sweet), each with an original drawing.
- **Responsive:** works from phone width up, with no horizontal scrolling.
- **Zero dependencies:** HTML and CSS only, no JavaScript, frameworks or build tools.

## Tech Stack

| Layer | Details |
|-------|---------|
| Markup | Semantic HTML5 |
| Styles | Vanilla CSS (custom properties, grid, flexbox) |
| Fonts | Google Fonts: Klee One, Atkinson Hyperlegible |
| Images | Original inline SVG line drawings |

## Project Structure

```
yatai-website/
└── index.html   # The site: styles, markup and SVG drawings in one file
```

## Getting Started

```bash
git clone https://github.com/tholewis/yatai-website.git
cd yatai-website
open index.html   # macOS
# or: xdg-open index.html (Linux) / start index.html (Windows)
```

## Design Decisions

- **Sketchbook look (Techō):** squared paper, washi tape, handwritten headings and marker colour suit a site built around drawings.
- **Single-file architecture:** keeps the project portable and easy to share without a server or bundler.
- **Checked content:** every fact was checked against a source when written. Traditions are labelled as traditions.
- **Accessibility:** skip link, semantic sections, `lang="ja"` on Japanese text, visible focus outlines and reduced-motion support.

## License

MIT: free to use, adapt and share.
