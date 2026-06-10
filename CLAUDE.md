# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

VitalWealth Consultancy — a static single-page website for an exercise and financial consultancy business. No build tools, frameworks, or package managers are used.

## Running the Site

Open `index.html` directly in a browser:

```powershell
Start-Process "index.html"
```

There is no build step, dev server, or compilation required.

## Architecture

Three files make up the entire site:

- **index.html** — All page structure and content. Sections in order: `#home` (hero), `#services`, `#about`, `#testimonials`, `#contact`, footer.
- **style.css** — All styling. Uses CSS custom properties defined in `:root` for the color palette (`--primary`, `--accent`, `--dark`, etc.). No preprocessor.
- **script.js** — Minimal vanilla JS: sticky navbar on scroll, hamburger menu toggle, contact form mock-submit with success message, and an `IntersectionObserver` scroll-reveal on cards.

## Design Tokens (CSS Variables)

Defined at the top of `style.css` under `:root`:

| Variable | Purpose |
|---|---|
| `--primary` | Purple `#6c63ff` — buttons, highlights |
| `--accent` | Teal `#00c896` — badges, success states |
| `--dark` / `--dark2` / `--dark3` | Background layers |
| `--card-bg` / `--card-border` | Glassmorphism card surfaces |

## Content Sections

Each section in `index.html` has a matching `id` used for smooth-scroll nav links:

- `#home` — Hero with stats and floating cards
- `#services` — 6 service cards (2 `.featured`, 4 standard)
- `#about` — Philosophy card + 4 stat numbers + text
- `#testimonials` — 3 testimonial cards (middle one has `.highlight` class)
- `#contact` — Contact details + booking form (`#contactForm`)

## Responsive Breakpoints

- `≤ 900px` — hero visual hidden, about/contact stack to single column
- `≤ 640px` — nav links hidden, hamburger shown; form rows collapse to single column
