# Repository Guidelines

This repository hosts the static marketing site for Sanjay Devnani, delivered via GitHub Pages. Treat every change as production-ready: there is no build step, so edited files publish exactly as committed.

## Project Structure & Module Organization
- `index.html` is the primary landing page; keep hero content and navigation here.
- `booking.html` and `eb1a.html` are standalone campaign pages that share styling patterns with `index.html`.
- `CNAME` pins deployment to `sanjaydevnani.com`; do not modify unless the custom domain changes.
- `sync.sh` batches add/commit/push for quick updates—adjust the commit message before running it.

## Local Development & Preview
- Edit pages directly in the repository root. Keep shared snippets (meta tags, header/footer) in sync across all HTML files.
- Preview changes locally with `python3 -m http.server 8000` and open `http://localhost:8000/index.html` in a browser. For quick spot checks, `open index.html` works on macOS.
- After each edit, hard-refresh the browser to flush cached Tailwind CDN assets.

## Coding Style & Naming Conventions
- Use 4-space indentation and double-quoted HTML attributes, matching the existing pages.
- Favor semantic elements (`<section>`, `<article>`, `<nav>`) before `<div>` wrappers.
- Tailwind utility classes are loaded from the CDN; prefer class-based styling and keep inline `<style>` blocks short, commented, and reused across pages.
- Keep metadata accurate—mirror SEO, Open Graph, and JSON-LD blocks across pages and update only changed fields.

## Testing & QA
- Manually validate visual changes across desktop and mobile breakpoints; browser dev-tools responsive mode is sufficient.
- Run `npx htmlhint index.html booking.html eb1a.html` when Node.js is available to catch malformed markup.
- Confirm external links (Calendly, Google Analytics, OG images) resolve and remain HTTPS.

## Commit & Pull Request Guidelines
- Follow the existing history: concise, present-tense subject lines (`Add calendar icon link`). Reference the page touched when helpful.
- Group related HTML edits into a single commit; include before/after screenshots in PR descriptions for layout updates.
- Link to tracked issues or describe the motivation clearly. Note any manual QA steps taken (devices, validators) so reviewers can reproduce them.

## Deployment & Maintenance
- Deploy by pushing to `main`; GitHub Pages publishes automatically. Use `./sync.sh` only after staging your changes and tailoring the commit message.
- After merge, visit the live site to confirm the CDN caches picked up the update within a few minutes.
