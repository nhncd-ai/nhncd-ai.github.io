# NHNCD Website — Agent Instructions

This is the corporate website for NHNCD AI Limited, deployed via GitHub Pages at [https://nhncd.ai](https://nhncd.ai).

## Architecture

Static HTML — single `index.html` with inlined CSS and SVGs. No framework, no build step, no dependencies beyond Google Fonts (Inter).

## Brand rules

- **Wordmark is a bespoke vector, not a font.** Never replace the SVG paths with text.
- **The D letter uses `fill-rule="evenodd"` with a background rect** to create the transparent inner cutout. Do not remove the rect or change the fill-rule.
- **Secondary mark (aperture-dot)** is always placed above the wordmark, never beside it.
- **Prohibited visuals:** neural networks, circuits, gradients, brain imagery, tech blue/purple.
- **Colour palette is locked.** See README.md for hex values. Do not introduce new colours.

## Favicons

PNG favicons at 16, 32, 48, 180, and 512px are in the repo root. Source SVGs are in the brand identity folder in the main NHNCD drive (not this repo).

## Deployment

Push to `main` triggers a GitHub Pages build. The CNAME file must stay — it maps the custom domain `nhncd.ai`.

## What's coming

The full website will replace this landing page. When building it:
- Keep it static if possible (no SSR needed for a corporate site)
- Maintain the same colour system and brand constraints
- Preserve the existing meta tags and Open Graph data
- Test that the CNAME and DNS configuration still work after any structural changes
