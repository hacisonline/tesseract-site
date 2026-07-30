# CLAUDE.md — Tesseract Marketing Site

You are working on the **public marketing site for Tesseract** (the company), live at **https://thinktesseract.com** (GitHub Pages custom domain on repo `hacisonline/tesseract-site`; the old hacisonline.github.io/tesseract-site URL 301-redirects here).

This folder is the **authoritative latest** version of the site. The `biz/tesseract-site/` folder elsewhere on the user's machine is older — ignore it. This folder is the one that gets pushed to GitHub Pages.

---

## Start here — current initiative (2026-07-29, site v3 built)

**Read `claude-workspace/STATUS.md` before doing website work.** The 2026-07-29 refresh rebuilt all four pages on one design system; it sits in the working tree awaiting owner review and push. Positioning remains **Real Estate Intelligence**; Fleet is excluded.

- Repo-scoped context lives in `claude-workspace/` — `STATUS.md` (read first), `DECISIONS.md`, `SESSION-LOG.md`.
- The **Home Architecture Explorer** in `home-architecture-explorer/` IS the hero of `home.html` (iframe embed; the folder must be committed for the page to work when deployed). Never modify the explorer casually; it is a finished, verified component.
- **Tesseract Brain** has its own page (`brain.html`): the building's own server plus the AI reception, per the 2026-07-22 Brain ADR. Never invent hardware specifications, prices, or dates for it.
- The Presidential appears as "The Presidential by Webtech Realty", Home's first white-label deployment: proof, not a product.
- Keep website work inside this repo only. Do not edit the Twin, Home, Presidential, Fleet or brand repos from a website session (rendering the Twin file read-only for screenshots is fine).

---

## What this is

A static, four-page marketing site for Tesseract (Real Estate Intelligence). Self-contained HTML — no build step, no framework, no bundler. Everything inline (CSS + JS). Deploys via GitHub Pages on push.

| File | Page |
|---|---|
| `index.html` | Landing — canonical cube-reveal intro, ecosystem flywheel, Twin V7.0 section, Home section with Brain nested, Presidential proof, foundation, CTA |
| `twin.html` | Tesseract Twin product page (V7.0, fresh live screenshots) |
| `home.html` | Tesseract Home product page — the Architecture Explorer is the hero (iframe) |
| `brain.html` | Tesseract Brain page — upcoming hardware within Home; architecture only, no specs |
| `home-architecture-explorer/index.html` | Canonical Home live-pipeline component; the home.html hero. Must be committed with the site |
| `index-cube-reveal.html` | Experimental hero variant — leave alone unless asked |
| `assets/` | Logo PNGs, `tesseract-mark.svg` (favicon), Twin V7.0 WebP screenshots |

---

## ⚠️ Brand canon — do NOT change without explicit approval

This site is the **source of truth** for the Tesseract brand. The resident app (`../tesseract-home-v0/`) literally pulls its logo and animation paths from here. If you change anything visual here, the resident app may need a matching update.

- **Colors:** all via CSS variables in `:root` (top of each file's `<style>` block). Never hardcode hex.
- **Typography:** Inter (sans, weights 300–900) + JetBrains Mono (mono, 400–600). No other fonts.
- **Brand mark:** outer blue isometric cube + inner green cube. The exact SVG paths in `index.html` (search `polygon points="160 28 ...`) are the canonical brand mark.
- **Voice:** confident, technical, builder's perspective. Read "Brand Voice" section in `references/design_system.md` if it exists, otherwise see the Sanity skill or `/codex/CLAUDE.md`.

---

## Deploy flow (main-based since 2026-07-29)

**`main` is both the working branch and the deploy branch.** GitHub Pages builds from `main`; a push goes live in ~60 seconds.

1. Edit files in this folder (on `main`)
2. From here:
   ```bash
   git add -A && git commit -m "Update X" && git push
   ```
3. Live in ~60 seconds at https://thinktesseract.com; hard-refresh to see it.
4. The `CNAME` file in the repo root holds the custom domain. Never delete it; deleting it detaches thinktesseract.com.

Push only finalised, locally reviewed changes: there is no staging step between `main` and the live site. The old `codex/website-redesign` working branch was merged into `main` on 2026-07-29 and is retired; do not resurrect it.

**Remote:** `github.com/hacisonline/tesseract-site` (public — required for GitHub Pages).

---

## Cross-page consistency rule

Nav and footer markup is duplicated across `index.html`, `twin.html`, `home.html`, and `brain.html`. **If you edit nav or footer in one file, update all four.** The shared `:root` token block is likewise duplicated per file; keep the values identical everywhere.

---

## What NOT to do here

- Don't add a build step (Vite, Webpack, etc.). The whole point of inline HTML is "edit, push, live."
- Don't add tracking pixels or analytics without asking.
- Don't change the cube SVG paths — they're load-bearing for brand consistency with the resident app.
- Don't push half-finished work: `main` deploys straight to the live site. Agents leave changes in the working tree for the owner to review and push.

---

## When to use the skills

- **`anthropic-skills:tesseract-website`** — full design system, color tokens, component patterns, deploy details
- **`anthropic-skills:tesseract-business`** — for copy/positioning decisions

If the user asks for a content change with strategic implications ("change the tagline," "rewrite the foundation section"), invoke the business skill first to stay aligned with positioning.
