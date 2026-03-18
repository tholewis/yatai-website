# 屋台 Yatai — The Soul of Japanese Street Food

A single-page website celebrating the culture, history, and flavours of Japanese yatai (屋台) — the iconic street food stalls that have been a cornerstone of Japanese life since the Edo period.

## Live Demo

Open `index.html` in any modern browser — no build step required.

## Features

- **Hero section** with animated hanging lanterns and a full-bleed atmospheric background
- **Introduction** — what yatai are and why they matter
- **History timeline** — four centuries of street food culture, from Edo push-carts to Fukuoka's licensed stalls
- **Food guide** — cards for Tonkotsu Ramen, Takoyaki, Yakitori, Gyoza, Oden, and Taiyaki with regional origins and flavour notes
- **The Yatai Experience** — the customs, etiquette, and atmosphere of eating at a stall
- **Regions** — Fukuoka, Tokyo, Osaka, and Kyoto yatai scenes
- **Festivals calendar** — Hakata Dontaku, Tenjin Matsuri, Obon, and Gion Matsuri
- **Responsive design** — works on desktop and mobile
- **Zero dependencies** — pure HTML and CSS, no frameworks or build tools

## Tech Stack

| Layer | Details |
|-------|---------|
| Markup | Semantic HTML5 |
| Styles | Vanilla CSS (custom properties, grid, flexbox, animations) |
| Fonts | Google Fonts — Noto Serif JP, Noto Sans JP, Playfair Display |
| Images | Inline SVG illustrations |

## Browser Support

Tested in Chrome, Firefox, Safari (including iOS), and Edge.
Vendor prefixes (`-webkit-backdrop-filter`, `-webkit-user-select`) are included for full Safari compatibility.

## Project Structure

```
yatai-website/
└── index.html   # Entire site — styles, markup, and SVG assets in one file
```

## Getting Started

```bash
git clone https://github.com/tholewis/yatai-website.git
cd yatai-website
open index.html   # macOS
# or: xdg-open index.html (Linux) / start index.html (Windows)
```

## Design Decisions

- **Single-file architecture** — keeps the project portable and easy to share without a server or bundler.
- **CSS custom properties** — a consistent colour palette (`--red`, `--gold`, `--ink`, `--cream`) used throughout.
- **Japanese typography** — Noto Serif JP for display text and kanji watermarks; Playfair Display for English headings to evoke a editorial quality.
- **Accessibility** — semantic elements (`<section>`, `<nav>`, `<footer>`), sufficient colour contrast on body text, and `pointer-events: none` on decorative elements.

## License

MIT — free to use, adapt, and share.
