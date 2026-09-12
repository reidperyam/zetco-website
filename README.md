# Zetco Website

Marketing landing page for Zetco S.A.S. (Cali, Colombia) — a static [Astro](https://astro.build) site deployed on Vercel.

Implements artboard **2A · Red field + ledger** from `design_handoff_zetco_landing/`.

## Develop

```sh
npm install
npm run dev      # http://localhost:4321
npm run build    # static output in dist/
npm run preview
npx astro check  # type/template check
```

## Structure

```
src/
  layouts/Base.astro        fonts (self-hosted via @fontsource), tokens, pre-paint theme script, meta
  components/               Nav, ThemeToggle, Hero, Stat, StatBand, ServiceRow, Services,
                            ProjectPanel, Partners, Close, Footer
  pages/index.astro
  styles/tokens.css         light/dark design tokens, shared primitives
public/zetco-logo.png
```

Theme toggle persists to `localStorage("zetco-theme")` and respects `prefers-color-scheme` on first visit.

## Open items (from the handoff)

- Stat numbers (60+ / 140 / 38 / 1996) are placeholders — confirm with client.
- Client to supply a Cali–Jamundí works photograph (`ProjectPanel.astro` → `photo`).
- Client logos for the Clients & partners tiles.
- Logo as SVG / transparent PNG (white plate around it is intentional until then).
- "Contact us" currently links to `mailto:contacto@zetco.com.co`; swap for `/contact` when a form exists.
