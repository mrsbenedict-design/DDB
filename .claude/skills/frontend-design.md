# Frontend Design Skill — VitalWealth Finance & Investment Site

## Purpose
Guidelines for designing, refining, or extending the VitalWealth Consultancy site to feel like a premium, trustworthy financial investment brand — not a generic wellness site.

---

## Design Philosophy

Finance clients buy **trust and authority** before they buy a service. Every design decision must reinforce:
- **Credibility** — clean hierarchy, no clutter, confident whitespace
- **Precision** — sharp typography, numbers that pop, data feels real
- **Premium** — deep navy backgrounds, gold accents, serif headings
- **Engagement** — micro-interactions, scroll reveals, floating data cards

---

## Color System

| Token | Value | Role |
|---|---|---|
| `--primary` | `#1d4ed8` | Royal blue — CTAs, links, icons |
| `--primary-dark` | `#1e3a8a` | Deep navy blue — hover states |
| `--primary-light` | `#3b82f6` | Sky blue — highlights, glows |
| `--accent` | `#f59e0b` | Gold — badges, stars, success, premium feel |
| `--accent-dark` | `#d97706` | Deep gold — hover on gold elements |
| `--dark` | `#020b18` | Near-black navy — page background |
| `--dark2` | `#071428` | Deep navy — footer, navbar |
| `--dark3` | `#0a1e3d` | Navy — section backgrounds |
| `--card-bg` | `rgba(29,78,216,0.05)` | Glassmorphism card fill |
| `--card-border` | `rgba(59,130,246,0.12)` | Subtle blue card border |

### Gradients
- **Primary gradient**: `linear-gradient(135deg, #1d4ed8, #3b82f6)` — buttons, stat numbers
- **Accent gradient**: `linear-gradient(135deg, #f59e0b, #fbbf24)` — gold highlights
- **Hero glow**: `radial-gradient(ellipse 80% 60% at 60% 40%, rgba(29,78,216,0.14), transparent 70%)`
- **Section tint**: `rgba(29,78,216,0.04)` — subtle section-level depth

---

## Typography

### Font Stack
```css
font-family: 'Playfair Display', Georgia, serif;  /* Headings: h1–h3 */
font-family: 'Inter', system-ui, sans-serif;       /* Body, labels, UI */
```

### Scale
| Element | Size | Weight | Font |
|---|---|---|---|
| H1 (hero) | `clamp(2.4rem, 5vw, 3.8rem)` | 700 | Playfair Display |
| H2 (section) | `clamp(2rem, 4vw, 2.8rem)` | 700 | Playfair Display |
| H3 (card) | `1.25rem` | 700 | Playfair Display |
| Body | `0.95–1.05rem` | 400 | Inter |
| Label/tag | `0.78–0.85rem` | 600 | Inter |
| Stat number | `1.8rem` | 800 | Inter |

### Why Playfair Display?
- Editorial serif trusted by banks, law firms, and investment brands
- Creates immediate authority contrast against the clean Inter body
- Works beautifully large, even in dark themes

---

## Component Patterns

### Cards (Glassmorphism)
```css
background: var(--card-bg);
border: 1px solid var(--card-border);
border-radius: 16px;
backdrop-filter: blur(16px);
transition: transform 0.3s, border-color 0.3s, box-shadow 0.3s;
```
On hover: `translateY(-6px)` + `box-shadow: 0 16px 48px rgba(29,78,216,0.15)`

### Featured Cards
```css
border-color: rgba(29,78,216,0.35);
background: linear-gradient(135deg, rgba(29,78,216,0.1), rgba(245,158,11,0.04));
```

### Buttons
- **Primary**: `linear-gradient(135deg, #1d4ed8, #3b82f6)` with white text
- **Hover**: `translateY(-2px)` + `box-shadow: 0 8px 24px rgba(29,78,216,0.4)`
- **Outline**: `border: 2px solid rgba(255,255,255,0.2)` → hover turns blue

### Section Tags / Badges
```css
background: linear-gradient(135deg, rgba(29,78,216,0.15), rgba(245,158,11,0.1));
border: 1px solid rgba(29,78,216,0.3);
color: var(--primary-light);
```

### Avatars
```css
background: linear-gradient(135deg, var(--primary), var(--primary-light));
```

---

## Engagement Patterns

1. **Floating data cards** in hero (portfolio value + fitness metric) — animate with `float` keyframe
2. **Scroll reveal** via IntersectionObserver — cards fade+slide in on entry
3. **Stat counters** — large gradient numbers that draw the eye
4. **Gold stars** on testimonials — trust signal, aligns with `--accent` gold
5. **Sticky navbar** — adds `background: rgba(2,11,24,0.95)` on scroll
6. **Gradient text** on key phrases in headings — primary-to-primary-light

---

## Finance-Specific UX Rules

- Lead with **outcomes** not process (e.g., "Grow your portfolio" not "We offer financial planning")
- Stats must feel **real and specific** (500+ clients, 12+ years, 98% success rate)
- Call to action is always **"Book a Session"** — low-friction, personal
- Contact form label: "Select Service" with finance options listed first
- Footer: include compliance/disclaimer area if needed
- Avoid playful language; prefer: *strategic, proven, disciplined, compounding, holistic*

---

## How to Apply This Skill

When asked to update or design any part of this site:
1. Reference the token names above — never hardcode hex values
2. Use Playfair Display for all headings, Inter for body
3. Gold (`--accent`) for stars, badges, and success states only — don't overuse
4. Blue glows/shadows reference `rgba(29,78,216,...)` not purple
5. Section alternation: plain dark → subtle blue tint → plain dark (never same bg twice in a row)
