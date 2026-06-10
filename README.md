# VitalWealth Consultancy

A static single-page website for an exercise and financial consultancy business.

## Live Site

[https://mrsbenedict-design.github.io/DDB/](https://mrsbenedict-design.github.io/DDB/)

## Tech Stack

- Plain HTML, CSS, and vanilla JavaScript — no build tools, frameworks, or package managers.

## Project Structure

```
index.html   — All page structure and content
style.css    — All styling (CSS custom properties for the design system)
script.js    — Sticky navbar, hamburger menu, contact form, scroll-reveal animations
```

## Sections

| Section | Description |
|---|---|
| `#home` | Hero with stats and floating cards |
| `#services` | 6 service cards (fitness + finance offerings) |
| `#about` | Philosophy, stats, and team background |
| `#testimonials` | 3 client testimonials |
| `#contact` | Contact details and booking form |

## Design Tokens

Colors and surfaces are defined as CSS custom properties in `:root` inside `style.css`:

| Variable | Value | Use |
|---|---|---|
| `--primary` | `#6c63ff` | Buttons, highlights |
| `--accent` | `#00c896` | Badges, success states |
| `--dark` / `--dark2` / `--dark3` | — | Background layers |
| `--card-bg` / `--card-border` | — | Glassmorphism card surfaces |

## Running Locally

No installation needed. Open `index.html` directly in a browser:

```powershell
Start-Process "index.html"
```

## Responsive Breakpoints

- `≤ 900px` — hero visual hidden; about/contact stack to single column
- `≤ 640px` — nav links hidden, hamburger menu shown; form collapses to single column
