# nhncd.ai

Corporate website for **NHNCD AI Limited** — strategic advisory and integration partner for AI adoption. Based at the AI Campus, DIFC, Dubai.

Live at **[https://nhncd.ai](https://nhncd.ai)**

## Status

Live — full v1 website:

| Path | Page |
|---|---|
| `/` | nhncd.ai — main site (light Letterhead system) |
| `/energy/` | NHNCD.energy — Project Intelligence (dark Ink system) |
| `/privacy/` | Privacy notice |
| `404.html` | Branded not-found page |

Plus `sitemap.xml`, `robots.txt`, and `assets/og-image.png` (1200×630 Open Graph image). Copy source of truth: website v1 copy draft (v1.3) in the NHNCD OS repo (`handoffs/`).

## Local development

```bash
python -m http.server 3000
```

Open [http://localhost:3000](http://localhost:3000).

No build step — the site is static HTML with inlined SVGs and CSS. Each page is fully self-contained (CSS is duplicated per page deliberately; there is no shared stylesheet).

## Deployment

- **Hosting:** GitHub Pages (this repo is the org site: `nhncd-ai.github.io`)
- **Branch:** `main`, root directory
- **Custom domain:** `nhncd.ai` (configured via CNAME file + GoDaddy DNS)
- **HTTPS:** Enforced, certificate auto-provisioned by GitHub

Pushes to `main` trigger an automatic Pages build. No CI/CD workflow needed.

## Brand reference

| Element | Value |
|---|---|
| Ink (dark background) | `#14181A` |
| Off-white (text/fills) | `#F4F2EC` |
| Oxblood (primary accent) | `#7E2632` |
| Oxblood Bright (dark bg accent) | `#CC5F73` |
| Gold (hairline detail only, never text) | `#B8862F` |
| Energy Green (NHNCD.energy accent) | `#2F6B52` on light grounds / `#489B76` on ink (AA-adjusted) |
| Vision Petrol (NHNCD.vision accent) | `#2E5F73` on light grounds / `#5C9BB3` on ink |
| Wordmark | Bespoke vector — no font. Inlined as SVG. |
| Secondary mark | Filled aperture-dot (square with bottom-right corner cut) |
| Fonts | [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk) (400/500/700), [Inter](https://fonts.google.com/specimen/Inter) (400/500/600), [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono) (400/500) via Google Fonts |

The two sub-brand accent rows are deliberate July 2026 palette amendments: green marks everything NHNCD.energy, petrol marks NHNCD.vision. No other colours may be introduced.

Full brand framework: see `NHNCD_Brand_Framework.md` in the brand identity folder (not in this repo).

## DNS records (GoDaddy)

| Type | Name | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | nhncd-ai.github.io |

MX and TXT records for Microsoft 365 email are managed separately — do not modify.

## Enterprise note

The `nhncd-ai` GitHub org is part of a GitHub Enterprise trial (NHNCD AI Limited). If Pages builds fail, check Enterprise Settings > Policies > Actions > Runner groups — the Default runner group must have "Allow public repositories" enabled.
