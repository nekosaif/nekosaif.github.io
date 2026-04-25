# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a personal portfolio/CV website for Mollah Md Saif, deployed as a GitHub Pages static site at `www.nekosaif.com` (CNAME configured). There is no build system, package manager, or framework — everything is plain HTML, CSS, and vanilla JavaScript.

## Development

Since this is a static site with no build step, development is straightforward:
- Open HTML files directly in a browser, or use any static file server (e.g., `python3 -m http.server`)
- No compilation, bundling, or dependency installation needed

## Site Structure

| File/Path | Purpose |
|---|---|
| `index.html` | Main CV page — the primary page of the site |
| `cv.html` | Currently empty (1-line placeholder) |
| `projects.html` | Redirect to Heroku-hosted Flask chatbot demo |
| `appointment/general.html` | Redirect to Google Calendar (general meetings) |
| `appointment/thesis.html` | Redirect to Google Calendar (thesis meetings) |
| `resources/khr-routine.html` | Redirect to shared Google Calendar |
| `publications/posetrajnet.pdf` | ICRA 2025 paper PDF |
| `CV of Mollah Md Saif (AI).pdf` | AI Software Engineer CV |
| `CV of Mollah Md Saif (Robotics).pdf` | Robotics Engineer CV |
| `CV of Mollah Md Saif (Academic).pdf` | Academic CV |

## Key Architecture Notes

**`index.html` is self-contained** — all CSS is inline in a `<style>` block, and all JS is inline at the bottom of `<body>`. No external `.css` or `.js` files are linked (only CDN resources: Lucide icons).

**CV download modal**: The floating download button (`#downloadCvBtn`) opens a modal (`#cvModal`) that lets users pick from three PDF CV versions. Modal state is managed with `.show` CSS class toggling via vanilla JS.

**Redirect pages**: `projects.html`, `appointment/*.html`, and `resources/*.html` use `<meta http-equiv="refresh">` plus `window.location.href` for instant redirects to external URLs.

**External dependencies (CDN only)**:
- Lucide icons: `https://cdn.jsdelivr.net/npm/lucide@0.474.0/dist/umd/lucide.min.js`
- Icons initialized with `lucide.createIcons()` after DOM load

## Deployment

Push to the `main` branch — GitHub Pages deploys automatically. No CI/CD configuration exists in the repo.
