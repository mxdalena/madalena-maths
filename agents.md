# Agent Guide

## Architecture

This is a zero-build static site. The entire site lives in a single file:

- `index.html` — all HTML, CSS, and JavaScript in one self-contained file
- `netlify.toml` — tells Netlify to publish the repo root (`.`) directly

There is no framework, no bundler, and no node dependencies required at runtime.

## Key decisions

- **Single-file design**: Keeps deployment trivial and avoids a build pipeline for a simple brochure site.
- **Inline CSS variables**: All colours are defined as CSS custom properties in `:root` for easy theming.
- **Google Fonts via CDN**: Lora (serif headings) and Plus Jakarta Sans (body). No self-hosted fonts.
- **Booking via Google Form**: The CTA buttons link to an external Google Form (`https://forms.gle/…`). There is no server-side form handling on this site.
- **Seasonal eyebrow text**: A small `<script>` block at the bottom of `index.html` swaps the hero badge text based on `new Date().getMonth()` to keep the copy contextually relevant throughout the year.

## Editing content

All copy, pricing, and links are in `index.html`. The Google Form URL appears in three places — search for `forms.gle` to find and update all occurrences together.
