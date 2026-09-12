# Handoff: Zetco landing page (mockup 2A) — Astro implementation

## Overview
Marketing landing page for **Zetco**, a Cali (Colombia) family-owned project-management firm founded in 1996 on 60+ years of experience in public works. It facilitates infrastructure projects between public and private sectors. Audience: public agencies, private developers, utilities, engineering/construction firms, investors, prospective hires. Primary CTA: **Contact us**. Tone: visionary, plain.

## About the design files
`Zetco Landing Mockups.dc.html` is a **design reference built in HTML** — not production code. It contains several alternatives; **implement only the artboard with `id="2a"`** (top of the file, labelled "2A · RED FIELD + LEDGER"). Recreate it as an **Astro** site (static output). No UI framework is required; a few lines of vanilla JS handle the theme toggle. Use Astro components for repeated blocks (nav, service row, stat) and scoped `<style>` or a global CSS file with the tokens below.

## Fidelity
**High-fidelity.** Match colors, type, spacing and copy exactly at the 1280px design width, then make it responsive (breakpoints below are recommendations; the mock is desktop only).

## Page structure (top → bottom), all at 1280px design width, 72px side gutters

### 1. Hero (red field) — `background:#D8262C; color:#fff; overflow:hidden`
- **Nav**: flex, `align-items:center; gap:36px; padding:22px 72px`.
  - Logo: `assets/zetco-logo.png` inside a white plate (`background:#fff; padding:6px 10px; border-radius:2px`), image height 36px, `margin-right:auto`.
  - Links (Services, Projects, Firm, Careers): Source Serif 4 15px, white, no underline.
  - Theme toggle: pill button, `border:1px solid rgba(255,255,255,.6); border-radius:999px; padding:6px 10px; font-size:13px`, contains a 26×14 track (`rgba(255,255,255,.35)`) with a 10px white knob (`left:2px` light / `14px` dark, `transition:left .2s`) and label "Light"/"Dark".
  - CTA "Contact us": `background:#0B0B0B; color:#fff; Archivo 700 14px; padding:10px 18px; border-radius:2px`.
- **Decorative mark**: the logo's chevron shapes as SVG, white at `opacity:.18`, `position:absolute; right:-60px; top:40px; width:640px`, `aria-hidden`. SVG (viewBox 0 0 400 300): polygons `0,0 160,0 80,120` · `200,0 290,0 90,300 0,300` · `310,0 400,0 200,300 110,300` · `320,180 400,300 240,300`.
- **Hero copy**: `padding:110px 72px 120px`.
  - H1: Archivo 800, 92px, line-height .98, letter-spacing -.03em, uppercase, max-width 11ch — "We build the bridge before the bridge."
  - Lead: Source Serif 4 20px/1.6, max-width 52ch, margin-top 40px — "Infrastructure stalls between the public entity that needs it and the private firm that can build it. Zetco is the team in the middle — planning, permitting, managing and delivering."
  - Buttons (flex, gap 16px, margin-top 40px): "Contact us" (black button as above, 15px, padding 14px 24px) and "Our approach" (white text 15px, `border-bottom:1px solid rgba(255,255,255,.6)`, padding 14px 6px).

### 2. Stat band — paper ground, 4 columns
- Grid `repeat(4,1fr)`, `padding:0 72px`, `border-bottom:1px solid <rule>`; each cell `padding:40px 24px` (first has no left padding, last no right), cells separated by `border-right:1px solid <rule>`.
- Number: Archivo 800 56px, letter-spacing -.03em, line-height 1. First number ("60+") is red `#D8262C`; others ink.
- Label: Source Serif 15px→14px, color `<muted>`, margin-top 10px.
- Content: 60+ / Years' experience · 140 / Projects facilitated · 38 / Public entities served · 1996 / Founded in Cali. **(Numbers are placeholders — confirm with client.)**

### 3. Services ledger — `padding:84px 72px 0`
- Kicker "Services": Archivo 13px, letter-spacing .12em, uppercase, red, margin-bottom 8px.
- Three rows, each grid `120px 1fr`, gap 32px, `padding:36px 0`, `border-bottom:1px solid <rule>`.
  - Numeral (01/02/03): Archivo 800 40px, red, letter-spacing -.03em.
  - Inner grid 2 cols, gap 48px: H2 Archivo 700 34px/1.1, letter-spacing -.02em; body Source Serif 16px/1.7 color `<sub>`.
- Copy:
  1. **Project & program management** — "Schedule, cost, contracts and quality under one accountable team — from scope to close-out. One plan, one truth, reported the way the owner needs to read it."
  2. **Feasibility & planning** — "Technical, financial and institutional feasibility, structured so a public entity and a private partner can each commit to the same document."
  3. **Public–private facilitation** — "Thirty years of trust on both sides of the table, put to work aligning institutions, contractors and lenders around one schedule."

### 4. Active project — `padding:84px 72px 0`, grid 2 cols, gap 2px
- Left: photo, aspect 16/10, `filter:grayscale(1) contrast(1.2)`, dark fallback bg `#2d2b2b`. (Client to supply a Cali–Jamundí works photograph.)
- Right: red panel `#D8262C`, white text, `padding:40px`, flex column, space-between. Kicker "Active project" (Archivo 13px .12em uppercase). H3 Archivo 800 40px/1 -.03em — "Vía Cali–Jamundí corridor widening". Body 16px/1.6 max-width 40ch — "Program management for a 14 km urban corridor: three municipalities, two concessionaires, one schedule held." Link "All projects": Archivo 700 14px uppercase .08em, white, `border-bottom:2px solid #fff; padding-bottom:4px`.

### 5. Clients & partners — `padding:84px 72px 0`, grid `1fr 2fr`, gap 72px, centered
- Kicker "Clients & partners" (red, Archivo 13px uppercase). Right: 5 logo slots, grid 5 cols gap 20px, 44px tall, `<tile>` background. Replace with real client logos (grayscale).

### 6. Close — red band `#D8262C`, `margin-top:84px; padding:72px`, grid `2fr 1fr`, gap 72px, align end
- H3 Archivo 800 64px/.98 -.04em white — "Have a project that needs to move?"
- Right column (flex column, gap 12px): black "Contact us" button (Archivo 700 15px, padding 14px 24px, centered) and "contacto@zetco.com.co · Cali, Colombia" (15px white).

### 7. Footer — `padding:24px 72px 36px`, 13px, `<muted>`, flex space-between: "© Zetco S.A.S." / "Since 1996".

## Interactions & behavior
- **Theme toggle** (nav): toggles a `data-theme="dark"` attribute on `<html>`; persist in `localStorage("zetco-theme")`; respect `prefers-color-scheme` on first visit. Red hero, red project panel and red close are **identical in both modes**; only paper/ink/muted/rule/tile swap (see tokens). Knob slides `left .2s`.
- Links: hover color `#A81C21` for red text links; black buttons hover `#2d2b2b`; red buttons hover `#B81F24`. Focus: `outline:2px solid #D8262C; outline-offset:2px`.
- "Contact us" → `/contact` (or `mailto:contacto@zetco.com.co` until a form exists). Nav anchors scroll to sections (`#services`, `#projects`, `#firm`, `#careers`).
- Responsive suggestions: ≤1024px hero H1 clamp(56px,8vw,92px), stat band 2×2, service inner grid 1 col, project grid 1 col (photo above panel); ≤640px nav links collapse to a menu, close grid 1 col.
- Reduced motion: disable knob transition.

## Design tokens
Light (paper): `--bg #F3F2F2` · `--ink #0B0B0B` · `--sub #3a3737` · `--muted #4a4747` · `--rule #0B0B0B` · `--tile #e4e2e1`
Dark: `--bg #0F0E0E` · `--ink #F3F2F2` · `--sub #CFCBCB` · `--muted #9B9797` · `--rule #4a4646` · `--tile #262424`
Brand (both modes): `--red #D8262C` · `--red-hover #B81F24` · `--black #0B0B0B` · white `#fff`
Fonts (Google Fonts): **Archivo** 700/800 for display, kickers, buttons; **Source Serif 4** 400/600 for body and nav links. Self-host via `@fontsource/archivo` and `@fontsource/source-serif-4` if preferred.
Radii: buttons/plates 2px; pill 999px. Shadows: none on the page.
Spacing: gutters 72px; section padding 84px; hero 110/120px; stat cells 40px; service rows 36px.

## Assets
- `assets/zetco-logo.png` (1097×975, white background, red chevron mark + black wordmark). Ask client for an SVG/transparent version; until then the white plate around the logo is intentional.
- Chevron background: inline SVG polygons above (derived from the logo mark).
- Photos: placeholders in the mock; client to supply.

## Suggested Astro layout
```
src/
  layouts/Base.astro        (fonts, tokens, theme script, meta)
  components/Nav.astro, ThemeToggle.astro, Stat.astro, ServiceRow.astro, ProjectPanel.astro, Partners.astro, Close.astro, Footer.astro
  pages/index.astro
  styles/tokens.css
public/zetco-logo.png
```

## Files in this bundle
- `Zetco Landing Mockups.dc.html` — design reference; implement artboard `#2a` only.
- `image-slot.js`, `support.js` — runtime the mock uses to render; ignore for implementation.
- `assets/zetco-logo.png` — logo.
