# 🦷 dental-glow-by-claude

A modern Persian (RTL) dental clinic landing page built with pure HTML, CSS, and JavaScript — no frameworks.

> Designed and coded entirely by [Claude](https://claude.ai) (Anthropic).

---

## ✨ Features

- **Interactive X-Ray Reveal** — hover over the hero image to reveal a soft, foggy spotlight that uncovers the dental X-ray/implant layer beneath the smile photo. Custom glowing cyan cursor included.
- **Full-bleed Hero** — the two images stack and cover the full viewport width, fading smoothly into the page below.
- **Persian RTL Layout** — fully right-to-left with Vazirmatn font.
- **Scroll Animations** — every section fades up via IntersectionObserver.
- **Count-Up Numbers** — stats animate in Persian numerals on scroll.
- **Responsive** — mobile-friendly layout.

## 🖼️ Preview

| Normal | X-Ray Reveal |
|--------|-------------|
| Smile photo fills the hero | Soft glowing circle follows your cursor revealing the implant X-ray |

## 🗂️ Structure

```
dental-glow-by-claude/
├── index.html     # entire site — single file
├── after.png      # hero base image (smile)
├── before.png     # hero reveal image (X-ray / implant)
└── README.md
```

## 🚀 Usage

Just open `index.html` in a browser — no build step, no dependencies, no server needed.

```bash
git clone https://github.com/msadeghkarimi/dental-glow-by-claude.git
cd dental-glow-by-claude
# open index.html in your browser
```

## 🛠️ Tech Stack

| | |
|---|---|
| Markup | HTML5 |
| Styling | CSS3 (custom properties, grid, mask-image, backdrop-filter) |
| Interactivity | Vanilla JavaScript (IntersectionObserver, mask reveal, count-up) |
| Font | [Vazirmatn](https://fonts.google.com/specimen/Vazirmatn) — Google Fonts |

## 🎨 Color Palette

| Role | Hex |
|------|-----|
| Primary | `#0891b2` |
| Deep | `#0c4a6e` |
| Accent | `#06b6d4` |
| Background | `#f0f9ff` |

## 🤖 Built with Claude

This project was fully designed and implemented by **Claude Sonnet** (Anthropic) based on a brief and two images. No external UI libraries were used.

---

© 2024 dental-glow-by-claude — MIT License
