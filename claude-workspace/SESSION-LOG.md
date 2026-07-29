# SESSION LOG — Tesseract marketing site

Most recent first.

## 2026-07-29 (Cowork, Claude) — v3.1: owner review corrections

- Owner reviewed v3 and flagged three things: Brain must read as part of Tesseract Home (not a nav peer), the hero product panels were unequal in size, and the homepage middle felt like content added to the old page rather than one designed story.
- Hierarchy fixed everywhere: Brain removed from the top nav on all four pages (discovery now flows through Home: the homepage Home chapter's Brain banner, the Home page's Brain band, the footer "Brain · inside Home", and an indented "↳ Brain · inside Home" entry in the mobile menu). brain.html's nav highlights Home as the active section. CTA copy reframed to two products with Brain inside Home.
- Hero panels equalized: both panels now share the identical structure; Twin gained a "Now at V7.0 · 574 automated tests" meta line mirroring Home's "Inside: Tesseract Brain" line.
- Homepage restructured into one chaptered narrative: the old sticky four-step ecosystem section was replaced by a compact thesis band (the live map, now permanently split blue/green to show the two worlds, beside two world cards numbered 01/02 that link into the chapters). Consistent chapter headers (outlined 01/02/03 numerals) now front the Twin, Home, and Foundation sections; the Home chapter carries principles, the full-width Brain banner, and the Presidential proof. Dead step-observer JS removed.
- Full re-verification: zero console errors, zero overflow at 1440/390 on all pages, and interaction tests all passing: mobile menu open/navigate, explorer Trace-a-question and cloud toggle inside the iframe, breakpoint-triggered portrait reload with auto-height, and the index anchor into home.html#architecture.
- No repository outside `website-tesseract-site` touched.

## 2026-07-29 (Cowork, Claude) — site v3 built: four pages, one system

- Owner requested a world-class refresh: explorer as the Home page centrepiece, latest Twin, the Brain hardware story, canonical design and intro animation, no fabricated claims. Four decisions taken via in-session questions (see DECISIONS 2026-07-29).
- Rebuilt `index.html` around the preserved cube-reveal intro; added Twin V7.0 and Home sections, Brain nesting, and the Presidential (by Webtech Realty) proof strip. Fixed the footer's stale "Local draft, not published" line.
- Rebuilt `twin.html` and `home.html` from scratch on the canonical design system; wrote the new `brain.html` (full ADR-001 public story, honesty note, no specs).
- Made the Home Architecture Explorer the home.html hero via a same-origin iframe: parent-side auto-height, breakpoint-aware reload, and an injected embed style that hides only the explorer's own brand row. The explorer file was not modified.
- Captured fresh Twin V7.0 screenshots read-only in headless Chromium (sample scenario, recalculate() run, Chart.js served locally); shipped as three optimized WebPs replacing the 1.6 MB PNG. Added `assets/tesseract-mark.svg` (official geometry) as the favicon.
- QA with Playwright at 1440px and 390px on all four pages: zero console errors, zero horizontal overflow, links and images verified, reduced-motion checked, explorer verified in both wide and portrait layouts. Mobile treated as the primary surface per owner instruction mid-session.
- Fixed during QA: a 4px mobile overflow from the flow-card entrance transform; screenshot annotation pins repositioned to straddle panel edges instead of covering product data.
- Docs updated (STATUS, DECISIONS, this log, CLAUDE.md, brief). No git performed; owner reviews and pushes. No repository outside `website-tesseract-site` was modified (Twin read-only for rendering).

## 2026-07-11 (Codex) — isolated draft v2 created

- Created an untracked replacement prototype in `draft-v2/`; restored public pages were not edited.
- Rebuilt the homepage hierarchy around Twin and Home, with Brain nested inside Home.
- Made the existing live Home Architecture Explorer the Home page hero.
- Reframed Brain as upcoming on-site hardware with a system-role visual and no invented industrial design, specifications or claims.
- Kept The Presidential to a restrained first-live-deployment proof.
- Verified the three pages visually at desktop and mobile widths, checked responsive overflow and reviewed the core navigation paths.
- Stopped the temporary local preview server after QA. No commit, push or deployment was performed.
- No repository outside `website-tesseract-site` was touched.

## 2026-07-11 (Codex) — failed redesign rolled back

- The attempted redesign incorrectly flattened Twin, Brain and Home into peer cards, treated Brain with a generic grey hierarchy, relegated the live Home architecture to a secondary feature and produced an inadequate Brain hero.
- The owner rejected the result and clarified that the live architecture must be the Home page hero, while Brain is cutting-edge upcoming hardware within the Home ecosystem.
- Created and pushed revert commit `705ceba`, reversing published commit `18bdf5f` without rewriting history.
- Restored the pre-existing website context and Home Architecture Explorer as untracked local working materials. The invented `brain.html` was not restored.
- No replacement redesign attempted in the rollback turn.
- No repository outside `website-tesseract-site` was touched.

## 2026-07-06 (Cowork) — restructure brief + Home Architecture Explorer

- Audited the public sites and identified stale positioning and missing proof.
- Built the Home Architecture Explorer as a responsive, interactive explanation of Home's live pipeline.
- Verified the explorer on desktop and mobile.
- Placed the explorer and repo-scoped context into the website repository as untracked working materials. No live-page changes and no other repository touched.
