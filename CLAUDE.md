# NHNCD Website — Agent Instructions

This is the corporate website for NHNCD AI Limited, deployed via GitHub Pages at [https://nhncd.ai](https://nhncd.ai).

## Architecture

Static HTML — three pages (`index.html`, `energy/index.html`, `privacy/index.html`) plus a branded `404.html`, with `sitemap.xml` and `robots.txt` at root and the Open Graph image in `assets/`. CSS and SVGs are inlined per page — duplicated CSS between pages is deliberate (no shared stylesheet, no framework, no build step). Fonts: Space Grotesk, Inter, and IBM Plex Mono via a single Google Fonts link per page. Internal links are root-relative (`/energy/`, `/privacy/`, `/favicon_32.png`, `/assets/og-image.png`) so they resolve from subfolders.

## Brand rules

- **Wordmark is a bespoke vector, not a font.** Never replace the SVG paths with text.
- **The D letter uses `fill-rule="evenodd"`** to create the transparent inner cutout. The current pages rely on evenodd alone (the retired landing page additionally used a background rect); keep the cutout transparent — never flatten the D into a single filled shape, never change the fill-rule.
- **Secondary mark (aperture-dot)** is always placed above the wordmark, never beside it — except as a standalone decorative element (hero/band corners), where it appears without the wordmark.
- **Prohibited visuals:** neural networks, circuits, gradients, shadows, border-radius above 2px, brain imagery, tech blue/purple.
- **Colour palette is locked.** See README.md for hex values. The sub-brand accents — energy green (`#2F6B52` light / `#489B76` ink — lightened from #3E8E6B for WCAG-AA contrast) for NHNCD.energy and petrol (`#2E5F73` light / `#5C9BB3` ink) for NHNCD.vision — are deliberate July 2026 amendments. Do not introduce further colours. Gold is hairline-only, never text.

## Favicons

Two PNG favicon sets at 16, 32, 48, 180, and 512px are in the repo root: `favicon_*.png` (oxblood dot — used by `/`, `/privacy/`, `404.html`) and `favicon_energy_*.png` (energy-green dot `#489B76` — used by `/energy/` only). Source SVGs are in the brand identity folder in the main NHNCD drive (not this repo).

## Deployment

Push to `main` triggers a GitHub Pages build. The CNAME file must stay — it maps the custom domain `nhncd.ai`.

## Working on the site

The full v1 website is live (it replaced the landing page in July 2026). When changing it:
- Keep it static (no SSR needed for a corporate site)
- Maintain the colour system and brand constraints above
- Preserve and extend the per-page head blocks (canonical, Open Graph, twitter:card, theme-color, favicons)
- Copy is locked to the v1 copy draft (v1.3) in the NHNCD OS repo — do not rewrite copy during design changes
- Test that the CNAME and DNS configuration still work after any structural changes
