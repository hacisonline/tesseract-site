# STATUS — Tesseract marketing site

**Last updated:** 2026-07-30

## Current state

**Site v3.6 is LIVE at https://thinktesseract.com** (GitHub Pages custom domain since 2026-07-30; the old hacisonline.github.io/tesseract-site URL 301-redirects to the domain). All owner review rounds through v3.6 are pushed: Brain nested under Home everywhere (no top-nav peer link), hero panels equalized, the homepage restructured into a chaptered narrative with the lifecycle-spine thesis, the YOUR PROJECT hero HUD, sequential chapter-card spotlight, de-slop pass (no pulsing dots, no Build Log links), and the footer credit line. The four root pages share one design system (the canonical index tokens: deep navy, blue and green, Inter + JetBrains Mono, pill buttons, rounded panels):

- `index.html` — canonical cube-reveal scroll intro preserved exactly (green cube, blue draw-in, wordmark, "Real Estate Intelligence.", product panels). New sections after the ecosystem: Twin V7.0 with a fresh live-product screenshot, Home with four architecture principles and Brain nested inside, The Presidential by Webtech Realty proof strip, foundation, CTA. Brain added to nav ("soon" tag) and footer.
- `twin.html` — rebuilt on the shared system, reflecting the verified V7.0 state: fresh screenshots (overview + analytics, rendered from the real V7.0 file with the sample scenario), 6-stage lifecycle, capabilities incl. Monte Carlo (1,000 scenarios), Decision Flow and the tax layer, workbench strip (compare / offline / PDF), data strip (9 / 405 / 500+ / 574), sources.
- `home.html` — the Home Architecture Explorer IS the hero (per the 2026-07-29 owner decision: Home page hero only). Embedded as a same-origin iframe with auto-height, breakpoint-aware reload, and an embed-only style injected from the parent that hides the explorer's own brand row (the explorer file itself is untouched). Below: surfaces, privacy boundary with the egress trio, Brain band, Presidential proof.
- `brain.html` — NEW page. Full public Brain story per the 2026-07-22 ADR, as approved 2026-07-29: the building's own server (app + records + local model) plus the front-of-house AI reception. System-role visual, stack cards, reception narrative, physical-boundary strip, and an explicit honesty note. No invented specs, prices, or dates.

New assets: `assets/twin_v7_model.webp`, `assets/twin_v7_overview.webp`, `assets/twin_v7_analytics.webp` (all captured read-only from `tesseract_V7_0.html` with the sample scenario recalculated; ~365 KB total vs the old 1.6 MB PNG), `assets/tesseract-mark.svg` (official geometry, used as favicon). The old `assets/twin_screenshot.png` is no longer referenced and can be deleted by the owner.

## QA (2026-07-29)

Playwright, Chromium, real fonts: all 4 pages at 1440px and 390px, zero console errors, zero horizontal overflow, no broken links or images, reduced-motion honoured, explorer verified wide (desktop) and portrait (mobile) inside the iframe with auto-height working. Mobile was treated as the primary surface per owner instruction.

## Decisions in force

- Real Estate Intelligence positioning. Fleet excluded.
- Explorer = Home page hero only (homepage links to it, does not embed it).
- Brain named publicly, full ADR-001 story, zero specifications.
- The Presidential credited as "The Presidential by Webtech Realty".
- Domain: **LIVE at thinktesseract.com since 2026-07-30**, done in the correct order this time: registrar forwarding deleted and the four GitHub Pages apex A records added at GoDaddy (plus `www` CNAME → hacisonline.github.io) FIRST, then the `CNAME` file pushed to `main` (commit `cc3a4f5`). Certificate issued; canonical + og URLs on all four pages point at https://thinktesseract.com. Standing rule from the 2026-07-29 outage: never registrar forwarding and a CNAME file at the same time — that combination is a redirect loop. The `CNAME` file must stay in the repo root.

## To publish (owner)

**Workflow since 2026-07-29: work happens directly on `main`, which is the GitHub Pages deploy branch.** After reviewing locally (open `index.html`):

```bash
git add -A && git commit -m "update" && git push
```

Live in ~60 seconds; hard-refresh. The `codex/website-redesign` branch was merged into `main` on 2026-07-29 and is retired. The explorer folder (`home-architecture-explorer/`) must stay tracked: the Home hero iframes it. The root `CNAME` file must stay tracked too: it binds the thinktesseract.com custom domain. Optional cleanup: `git rm assets/twin_screenshot.png`; `draft-v2/` can stay as untracked history or be archived.

## Isolation

Work happened only inside this website repository. Twin was read (rendered headless for screenshots), never edited. Home, Brain, Presidential, Fleet repos untouched.
