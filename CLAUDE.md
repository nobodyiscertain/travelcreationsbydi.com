# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static website for Travel Creations by Di — a Texas Hill Country travel agency run by Diane Mack. Hosted on GitHub Pages at `nobodyiscertain.github.io/travelcreationsbydi.com`.

## Tech Stack

- Pure HTML + CSS, no build tools, no JavaScript frameworks
- Single shared `styles.css` linked from all pages
- Google Fonts: Pacifico (headings/script) + Poppins (body text)
- Forms submit via [FormSubmit.co](https://formsubmit.co) to `dmack@lamacchiajs.com`
- Mobile hamburger menu uses CSS-only checkbox hack (no JS)

## Development

No build step. Open any `.html` file directly in a browser, or use a local server:

```
python3 -m http.server 8000
```

## Design System

All pages follow the design established in `index.html`. CSS variables defined in `:root` of `styles.css`:

| Variable | Value | Usage |
|---|---|---|
| `--teal` | `#00b4d8` | Primary accent |
| `--teal-dark` | `#0096b7` | Headings, links |
| `--yellow` | `#f4a024` | CTAs, buttons |
| `--light-bg` | `#e8f8fc` | Card backgrounds |
| `--dark-text` | `#1a2b3c` | Body text |
| `--warm-white` | `#fefcf7` | Alternate section bg |

## Architecture

- **Shared nav/footer**: Every page duplicates the same `<nav>` and `<footer>` markup from `index.html`. When updating nav links or footer, update all HTML files.
- **Page hero**: Inner pages use `.page-hero` class (not `.hero` which is homepage-only full-viewport).
- **Active nav**: Add `.active` class to the current page's nav link.
- **styles.css organization**: Sections are grouped by page/component with comment headers. Page-specific styles (About, Disney, Cruising, Universal, Blog, Gallery, Contact, Thank You) follow shared/global styles. Responsive overrides are at the bottom in a single `@media (max-width: 768px)` block.

## Content Reference

- `BRIEF.md` — Full site spec with page requirements, content, and structure
- `screenshots/` — Full-page screenshots of the original site for content reference

## Key Details

- Contact info: 110 Hideaway Circle, Ingram TX 78025 / dmack@lamacchiajs.com / (469) 248-6318
- Social: [Facebook](https://www.facebook.com/yourtravelcreator) / [Instagram](https://www.instagram.com/yourtravelcreator/)
- Form hidden fields: `_subject` = "New Trip Request from Website", `_next` = full URL to `thank-you.html`
- Images: Unsplash URLs used directly (no local image assets)
