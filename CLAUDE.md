# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static website for Travel Creations by Di — a Texas Hill Country travel agency run by Diane Mack. Hosted on GitHub Pages, served at `https://travelcreationsbydi.com` via custom domain (CNAME file in repo root, DNS at Bluehost). Pages with custom domain redirect from `nobodyiscertain.github.io/travelcreationsbydi.com`.

## Tech Stack

- Pure HTML + CSS, no build tools, no JavaScript frameworks
- Single shared `styles.css` linked from all pages
- Google Fonts: Playfair Display (headings) + Pinyon Script (script accents) + Montserrat (body text)
- Forms submit via [FormSubmit.co](https://formsubmit.co) to `diane@travelcreationsbydi.com`
- Mobile hamburger menu uses CSS-only checkbox hack (no JS)
- Fathom analytics (site code `SHUSGKUF`) loaded via `<script>` before `</head>` on every page

## Git Workflow

Committing directly to `main` is fine for this repo. GitHub Pages rebuilds in ~30s after push.

## Quality Gates — EVERY Push (Non-Negotiable)

Before pushing any HTML/CSS changes, ALWAYS verify:

1. **SEO meta tags** on every page touched: `<title>`, `<meta name="description">`, `<meta property="og:title">`, `og:description`, `og:image`, `og:url`, `og:type`, `<meta name="twitter:card">`, `<link rel="canonical">`. Match content changes to meta updates — don't leave stale descriptions.
2. **sitemap.xml** — update when pages are added/removed/renamed. File lives at repo root. Currently lists home, about, disney, sip-and-sail, hill-country, blog + posts, gallery, contact. Hidden pages (cruising, reviews, /preview/*) are intentionally excluded.
3. **JSON-LD structured data** — refresh on content changes that affect schema (TravelAgency, FAQPage, BlogPosting, LocalBusiness, Reviews).
4. **Canonical URLs** — present on every page, pointing to the production https://travelcreationsbydi.com/<path> form.
5. **Heading hierarchy** — h1 → h2 → h3 with no skipped levels.
6. **Semantic HTML** — `<main>`, `<nav>`, `<footer>`, descriptive `alt` text on images, descriptive link text.
7. **Mobile responsive** — grids must stack cleanly, no horizontal scroll, touch targets adequate. Avoid inline grid styles. Test at 1024px (tablet) and 768px (phone) breakpoints.
8. **`llms.txt`** — sync when services, offerings, properties, or featured collections change.
9. **Hidden pages** — pages we don't want public yet need `<meta name="robots" content="noindex,nofollow">` and exclusion from sitemap.xml AND no internal links from visible pages. Currently noindex'd: `cruising/`, `reviews/`, `preview/cards/`.

This Quality Gates list was established 2026-03-15 after a sweep found every page missing og:image, canonical URLs, structured data, and several grids broken on mobile.

## Development

No build step. Open any `.html` file directly in a browser, or use a local server:

```
python3 -m http.server 8000
```

## Design System

All pages follow the design established in `index.html`. CSS variables defined in `:root` of `styles.css`:

| Variable | Value | Usage |
|---|---|---|
| `--gold` | `#C5A059` | Primary accent (from logo) |
| `--gold-light` | `#D4B472` | Hover states, script text |
| `--gold-dark` | `#A88740` | Darker gold variant |
| `--charcoal` | `#4A5259` | Headings, nav text |
| `--charcoal-dark` | `#2C3338` | Footer bg, body text |
| `--cream` | `#FAF8F5` | Section backgrounds |
| `--ivory` | `#F0EBE3` | Card backgrounds |
| `--border` | `#E8E2D9` | Subtle borders |

## Architecture

- **Shared nav/footer**: Every page duplicates the same `<nav>` and `<footer>` markup from `index.html`. When updating nav links or footer, update all HTML files.
- **Page hero**: Inner pages use `.page-hero` class (not `.hero` which is homepage-only full-viewport).
- **Active nav**: Add `.active` class to the current page's nav link.
- **styles.css organization**: Sections are grouped by page/component with comment headers. Page-specific styles (About, Disney, Cruising, Universal, Blog, Gallery, Contact, Thank You) follow shared/global styles. Responsive overrides are at the bottom in tiered media query blocks: `@media (max-width: 1024px)` for tablet+nav (hamburger triggers here), `@media (max-width: 900px)` for pillar/offer mid-tablet, `@media (max-width: 768px)` for phone, `@media (max-width: 480px)` for small phones.
- **Hidden pages**: `cruising/` and `reviews/` are temporarily off the menu but kept in the repo for later relink — do not delete, do not link from visible pages. `preview/cards/` is a sandbox for design variants under review by Diane and Jamie.
- **Whitetail Court Hotel**: deal hadn't closed as of 2026-04-26; markup was physically removed from gallery and hill-country pages and from llms.txt. Restore from git history (commit `da8546a^`) when the deal closes.

## Content Reference

- `BRIEF.md` — Full site spec with page requirements, content, and structure
- `screenshots/` — Full-page screenshots of the original site for content reference

## Key Details

- Contact info: 110 Hideaway Circle, Ingram TX 78025 / diane@travelcreationsbydi.com / (469) 248-6318
- Social: [Facebook](https://www.facebook.com/yourtravelcreator) / [Instagram](https://www.instagram.com/yourtravelcreator/)
- Form hidden fields: `_subject` = "New Trip Request from Website", `_next` = full URL to `thank-you.html`
- Logo: `logo.png` in project root (extracted from official SVG, used in nav/hero/footer)
- Images: Unsplash URLs used directly (no local image assets except logo)
