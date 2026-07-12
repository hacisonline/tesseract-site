# STATUS — Tesseract marketing site

**Last updated:** 2026-07-11

## Current direction

The approved parent positioning is **Real Estate Intelligence**. The website focuses only on the current real-estate ecosystem:

- Tesseract Twin — development strategy.
- Tesseract Brain — the on-site device that runs Home's digital twin and local intelligence.
- Tesseract Home — the building intelligence platform.
- The Presidential — Home's first live deployment and case study, mentioned only as a small proof point.

Fleet is deliberately excluded from the website.

## Current implementation

- `index.html` — redesigned master experience with the canonical scroll-reveal mark, the three-product system, architecture feature, small Presidential proof and builder foundation.
- `twin.html` — refreshed product page with stale version-specific metrics removed.
- `brain.html` — new product page for the on-site device, the grounded request path and the data boundary.
- `home.html` — rebuilt around current verified surfaces, role-aware operations, Brain and privacy architecture.
- `home-architecture-explorer/` — linked as the canonical live pipeline; public naming changed from Cortex to Tesseract Brain.
- `TESSERACT_SITE_RESTRUCTURE_BRIEF.md` — replaced with the approved real-estate-only brief.

## Verification

Verified locally on 2026-07-11:

- Desktop viewport: 1440 × 900.
- Mobile viewport: 390 × 844.
- No horizontal overflow across the homepage, Twin, Brain, Home or the architecture explorer.
- Homepage opening and final three-product reveal visually inspected.
- Brain and Home product heroes visually inspected.
- Explorer wide and portrait layouts visually inspected.
- `Trace a question` interaction verified.
- Mobile menu verified.
- Browser console clean during the explorer test.
- Local link targets and `git diff --check` pass.

## Working state

- Branch: `codex/website-redesign`.
- The owner performs all commits and pushes.
- Do not commit or push from an AI session unless the owner explicitly asks.
- Pre-existing untracked website context remains inside this repository by design.

## Isolation

All work stays inside this repository. Do not edit or import from Twin, Home, Brain, Presidential, Fleet, Brand or archive repositories.
