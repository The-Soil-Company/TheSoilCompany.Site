# TheSoilCompany.Site

Institutional website of The Soil Company. A static landing page plus the
legal pages required to publish the **TSC Coleta** app on Google Play.

No framework, no build step: plain HTML and CSS served as-is.

## Pages

| File | Purpose |
|---|---|
| `index.html` | Landing page: what we do, how it works, platform features, the TSC Coleta app, FAQ and contact |
| `privacidade.html` | Privacy and personal data protection policy (LGPD), transcribed from the official PDF |
| `termos.html` | Terms of use of the TSC platform and the TSC Coleta app |
| `exclusao-de-conta.html` | How to request account deletion (required by Google Play for apps with login) |

All copy is in pt-BR, UTF-8, with proper accents.

## Structure

```
.
├── index.html
├── privacidade.html
├── termos.html
├── exclusao-de-conta.html
├── styles.css          # single stylesheet shared by every page
└── assets/
    ├── logo.png        # official brand mark, also used as favicon
    ├── app-icon.png    # TSC Coleta app icon
    └── seedling.jpg    # contact section background
```

## Running locally

Any static file server works. With Python:

```bash
python -m http.server 8765
```

Then open <http://localhost:8765>.

## Deploying

Upload the folder to any static host (GitHub Pages, Cloudflare Pages,
Netlify, Vercel, a bucket behind a CDN). There is nothing to compile.

The URLs below are the ones to register in the Google Play Console:

- Privacy policy: `/privacidade.html`
- Account deletion: `/exclusao-de-conta.html`

## Design notes

- Colors and fonts follow the TSC platform theme (`TheSoilCompanyFront`):
  primary `#f26522`, green `#6b8e4e`, background `#f5f5f2`, Inter for text
  and Newsreader for headings. Fonts are loaded from Google Fonts.
- Sections alternate between the page background and white.
- The hero illustration is inline SVG (field, management zones, sampling
  points) so it stays crisp without image assets.
- The platform features listed on the landing page are limited to what the
  **client** profile can see. Internal and partner-only modules (financial,
  user management, catalogs, sampling grid generation) are intentionally
  left out.

## Content rules

- The privacy policy mirrors the official document. Changes go to the
  document first, then here.
- The terms of use were drafted for the site and should be reviewed by the
  company before publishing.
- The Soil Company does not perform field sampling: clients and their teams
  collect using the app. Copy must not state otherwise.
