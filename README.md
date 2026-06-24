# nhncd.ai

Corporate website for **NHNCD AI Limited** — strategic advisory and integration partner for AI adoption. Based at the AI Campus, DIFC, Dubai.

Live at **[https://nhncd.ai](https://nhncd.ai)**

## Status

Currently a "coming soon" landing page. Full website build planned for Q3 2026.

## Local development

```bash
python -m http.server 3000
```

Open [http://localhost:3000](http://localhost:3000).

No build step — the site is static HTML with inlined SVGs and CSS.

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
| Gold (detail only) | `#B8862F` |
| Wordmark | Bespoke vector — no font. Inlined as SVG. |
| Secondary mark | Filled aperture-dot (square with bottom-right corner cut) |
| Body font | [Inter](https://fonts.google.com/specimen/Inter) (300, 400, 500) via Google Fonts |

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
