# CLAUDE.md — Tesseract Marketing Site

You are working on the **public marketing site for Tesseract** (the company), live at https://hacisonline.github.io/tesseract-site/.

This folder is the **authoritative latest** version of the site. The `biz/tesseract-site/` folder elsewhere on the user's machine is older — ignore it. This folder is the one that gets pushed to GitHub Pages.

---

## Start here — current initiative (2026-07-11)

**Read `claude-workspace/STATUS.md` before doing website work.** The approved positioning is **Real Estate Intelligence**, focused only on the current real-estate ecosystem: Tesseract Twin, Tesseract Brain and Tesseract Home. Fleet is deliberately excluded. The approved plan is `TESSERACT_SITE_RESTRUCTURE_BRIEF.md` (repo root).

- Repo-scoped context lives in `claude-workspace/` — `STATUS.md` (read first), `DECISIONS.md`, `SESSION-LOG.md`.
- The **Home Architecture Explorer** in `home-architecture-explorer/` is the canonical live pipeline explainer. It uses Tesseract Brain as the current public name for the on-site device.
- The Presidential is a small proof point: Home's first live deployment and case study, never a separate Tesseract product.
- Keep website work inside this repo only. Do not edit the Twin, Home, Presidential, Fleet or brand repos from a website session.

---

## What this is

A static marketing site for Tesseract (Real Estate Intelligence). Self-contained HTML — no build step, no framework, no bundler. Everything inline (CSS + JS). Deploys via GitHub Pages on push.

| File | Page |
|---|---|
| `index.html` | Landing — hero with cube reveal, explore cards, ecosystem flywheel, foundation, CTA |
| `twin.html` | Tesseract Twin product page |
| `home.html` | Tesseract Home product page |
| `brain.html` | Tesseract Brain product page |
| `home-architecture-explorer/index.html` | Interactive Home + Brain system architecture |
| `index-cube-reveal.html` | Experimental hero variant — leave alone unless asked |
| `assets/` | Logo PNGs, brand visuals, screenshots |

---

## ⚠️ Brand canon — do NOT change without explicit approval

This site is the **source of truth** for the Tesseract brand. The resident app (`../tesseract-home-v0/`) literally pulls its logo and animation paths from here. If you change anything visual here, the resident app may need a matching update.

- **Colors:** all via CSS variables in `:root` (top of each file's `<style>` block). Never hardcode hex.
- **Typography:** Inter (sans, weights 300–900) + JetBrains Mono (mono, 400–600). No other fonts.
- **Brand mark:** outer blue isometric cube + inner green cube. The exact SVG paths in `index.html` (search `polygon points="160 28 ...`) are the canonical brand mark.
- **Voice:** confident, technical, builder's perspective. Read "Brand Voice" section in `references/design_system.md` if it exists, otherwise see the Sanity skill or `/codex/CLAUDE.md`.

---

## Deploy flow

1. Edit files in this folder
2. From here:
   ```bash
   git add -A && git commit -m "Update X" && git push
   ```
3. Branch in use: `codex/website-redesign` (NOT `main`). Push merges via GitHub PR or merge to main when ready.
4. Live in ~30–60 seconds via GitHub Pages

**Remote:** `github.com/hacisonline/tesseract-site` (public — required for GitHub Pages).

---

## Cross-page consistency rule

Nav and footer markup is duplicated across `index.html`, `twin.html`, `brain.html`, and `home.html`. **If you edit nav or footer in one file, update all four.**

---

## What NOT to do here

- Don't add a build step (Vite, Webpack, etc.). The whole point of inline HTML is "edit, push, live."
- Don't add tracking pixels or analytics without asking.
- Don't change the cube SVG paths — they're load-bearing for brand consistency with the resident app.
- Don't push to `main` directly — use the `codex/website-redesign` branch.

---

## When to use the skills

- **`anthropic-skills:tesseract-website`** — full design system, color tokens, component patterns, deploy details
- **`anthropic-skills:tesseract-business`** — for copy/positioning decisions

If the user asks for a content change with strategic implications ("change the tagline," "rewrite the foundation section"), invoke the business skill first to stay aligned with positioning.
