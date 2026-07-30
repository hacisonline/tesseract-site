# STATUS — Tesseract marketing site

**Last updated:** 2026-07-29

## Current state

**Site v3.1 (2026-07-29, including same-day owner review corrections) is built and QA-verified in the working tree, awaiting owner push.** Corrections applied after review: Brain nested under Home everywhere (no top-nav peer link), hero panels equalized, and the homepage restructured into a chaptered narrative (thesis band with the split-coloured live map and numbered world cards, then chapters 01 Twin / 02 Home / 03 Foundation). The four root pages share one design system (the canonical index tokens: deep navy, blue and green, Inter + JetBrains Mono, pill buttons, rounded panels):

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
- Domain: **ROLLED BACK 2026-07-29 same day** to the original arrangement: site canonical at hacisonline.github.io/tesseract-site, thinktesseract.com keeps its registrar 302 forwarding, NO CNAME file. Reason: the committed CNAME plus the still-active registrar forwarding created a redirect loop ("cannot follow more than 20 redirects") and took the site down. When the owner is ready to host on the domain properly: FIRST delete the registrar forwarding and add the four GitHub Pages A records, THEN commit the CNAME and set the custom domain. Never both forwarding and CNAME at once.

## To publish (owner)

**Workflow since 2026-07-29: work happens directly on `main`, which is the GitHub Pages deploy branch.** After reviewing locally (open `index.html`):

```bash
git add -A && git commit -m "update" && git push
```

Live in ~60 seconds; hard-refresh. The `codex/website-redesign` branch was merged into `main` on 2026-07-29 and is retired. The explorer folder (`home-architecture-explorer/`) must stay tracked: the Home hero iframes it. Optional cleanup: `git rm assets/twin_screenshot.png`; `draft-v2/` can stay as untracked history or be archived.

## Isolation

Work happened only inside this website repository. Twin was read (rendered headless for screenshots), never edited. Home, Brain, Presidential, Fleet repos untouched.
