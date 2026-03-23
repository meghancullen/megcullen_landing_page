# megcullen_landing_page

BAIS:3300 / BAIS:3500 — Personal Landing Page for Meghan Cullen, University of Iowa.

## Project Overview

A professional static HTML landing page for Meghan Cullen, a Business Analytics & Marketing senior at the University of Iowa (graduating May 2026). Targets recruiters and hiring managers at global firms and marketing agencies. Built per `PRD.md` and `STANDARDS.md`.

## Architecture

- **Type**: Static HTML site — no backend, no database, no JavaScript logic
- **Framework**: Bootstrap 5.3 via CDN
- **Fonts**: Inter from Google Fonts
- **Icons**: Bootstrap Icons via CDN

## Folder Structure

```
/
├── index.html          # Main page (single file)
├── css/
│   └── stylesheet.css  # All custom styles — no inline styles anywhere
├── js/
│   └── scripts.js      # Empty placeholder per STANDARDS.md spec
├── images/
│   └── headshot_2025.jpeg
├── PRD.md
├── STANDARDS.md
└── resume.docx
```

## Sections

1. **Hero** — Name, tagline, circular headshot (220px)
2. **About** — Bio with real content from resume and PRD
3. **Skills** — Pill badges split into Technical Tools (green) and Analytic Methods (navy)
4. **Projects** — Three project cards in a two-column grid (desktop) / single column (mobile)
5. **Contact** — LinkedIn, GitHub, UIowa email as labeled icon badges

## Design

- Color palette: navy (`#1a2332`) / army green (`#2d5a1b`) / off-white (`#f8f9fa`)
- Max content width: 800px centered
- Sticky top navigation with anchor links
- Fully responsive down to 320px

## Development

Served with Python's built-in HTTP server on port 5000:

```
python3 -m http.server 5000
```

## Deployment

Configured as a static site deployment serving from the root directory.
