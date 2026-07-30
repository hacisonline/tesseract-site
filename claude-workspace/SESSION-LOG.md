# SESSION LOG — Tesseract marketing site

Most recent first.

## 2026-07-30 (Cowork, Claude) — thinktesseract.com LIVE (custom domain, done right)

- Second attempt, correct order: owner deleted the GoDaddy forwarding remnants (the "Parked" A record), added the four GitHub Pages apex A records on `@`, and pointed the `www` CNAME at hacisonline.github.io, all guided live in the GoDaddy DNS dashboard. DNS verified propagated (all four IPs resolving) before touching GitHub.
- Owner then pushed the `CNAME` file from his terminal (commit `cc3a4f5`), which set the Pages custom domain. Certificate issued and https://thinktesseract.com confirmed serving the full v3.6 site from outside. Owner's local 405/awselb curl result diagnosed as his Mac's stale DNS cache (flush: `sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder`). Remaining owner tick-box: Enforce HTTPS in Settings → Pages.
- Canonical + og:url + og:image flipped from hacisonline.github.io/tesseract-site to https://thinktesseract.com on all four pages (12 URLs). CLAUDE.md, STATUS, DECISIONS updated to the domain-live state; the old github.io URL now 301-redirects to the domain.

## 2026-07-29 (Cowork, Claude) — domain move ROLLED BACK (redirect loop)

- The custom-domain push went out while the registrar's forwarding rule was still active: forwarding sent thinktesseract.com to github.io, the CNAME made github.io redirect back, and the site went down with a redirect loop. Rolled back same day: CNAME removed (owner runs `git rm CNAME`), canonical + og URLs restored to hacisonline.github.io/tesseract-site on all four pages, STATUS updated with the correct future order of operations (registrar DNS first, CNAME second). thinktesseract.com continues 302-forwarding as before.

## 2026-07-29 (Cowork, Claude) — v3.6: de-slop pass, build log delinked, footer credit

- Owner cull of AI-cliché elements: the pulsing green dot chips are gone sitewide. twin.html's chip now reads just "BETA" (no dot, no "sample scenario shown"); home.html's "LIVE · INTERACTIVE" and brain.html's "In development" chips lost their pulsing dots (text kept, pulse keyframes removed).
- Fixed mobile-only overlap: the annotation bars below product screenshots inherited the scroll-lift transform in their static mobile layout and started 14-18px shifted on first load; transform now cleared at ≤760px on index and twin. Verified no overlap at first paint.
- All Build Log links removed sitewide (footer links on four pages, hero and CTA buttons on twin.html, chapter button on index) with copy scrubbed where it referenced the log. REbuildlog itself still exists; the site just no longer links to it.
- Footer gained a single muted mono credit line on all four pages: "Lead developer · hacisonline".

## 2026-07-29 (Cowork, Claude) — thinktesseract.com custom domain prepared

- Owner decided to host at thinktesseract.com directly (supersedes the redirect decision). Added `CNAME` (thinktesseract.com), moved canonical + og:url + og:image on all four pages to https://thinktesseract.com, updated CLAUDE.md and STATUS. Owner actions: remove registrar domain forwarding, add the four GitHub Pages apex A records (+ optional www CNAME to hacisonline.github.io), set the custom domain in repo Settings → Pages, then Enforce HTTPS after the cert issues.

## 2026-07-29 (Cowork, Claude) — v3.5: YOUR PROJECT hero HUD, thesis scan-field, editorial alignment

- Hero state one now names its subject: a viewfinder HUD (four breathing corner brackets + a mono "YOUR PROJECT" tag) frames the lone green cube, and dissolves exactly as the blue cube draws in, so the intro reads as the brand's actual claim: the green cube is the owner's asset, the blue cube is Tesseract wrapping intelligence around it. Wired to the existing --seq-asset scroll variable; verified opacity hits 0 by 30% of the hero.
- The thesis section gained a quiet instrumentation field: a fine 34px blueprint grid (radially masked) with a slow 12s scan sweep drifting across. Transform-only animation; disabled under reduced motion.
- The thesis header block is now left-aligned (eyebrow tick restored, dek at 620px measure) matching the chapter heads, so every section header on the page follows one editorial system. Centered multi-line body copy eliminated.
- index.html previously had NO reduced-motion handling (an original-site gap); a proper block now disables the HUD pulse, scan sweep, and spine pulses for prefers-reduced-motion.

## 2026-07-29 (Cowork, Claude) — v3.4: chapter 01 scroll spotlight restored

- Owner noted the old public site lit each narrative card as you scrolled; the rebuild had only a whole-group fade on desktop. Chapter 01's flow cards (01 MODEL / 02 STRESS / 03 DECIDE) now spotlight sequentially on ALL devices: an IntersectionObserver with a one-card middle band (-41%) lights exactly the card being read (bright border, full opacity, glow) and hands off to the next. Flow cards removed from the touch-only observer so the two never fight. Verified: lit = [1,0,0] → [0,1,0] → [0,0,1] across the three scroll positions, zero errors, zero overflow.

## 2026-07-29 (Cowork, Claude) — v3.3: decision-execution spine, seamless Safari bars

- Spine relabelled per owner: the centre node is the DECISION layer (not "handover"), followed by an EXECUTION segment (blue-to-green gradient line), then Tesseract Home. Story now reads Twin tests → decision → execution → Home runs. Intro copy adjusted.
- Safari's solid navy bars behind the status bar and URL bar were caused by the fixed `theme-color` meta; removed on all four pages (plus `color-scheme: dark` hint) so Safari samples the real page edge and the top and bottom bars continue the page seamlessly.

## 2026-07-29 (Cowork, Claude) — v3.2: thesis rebuilt as the lifecycle, mobile polish, main-based deploys

- v3.1 went live: the owner merged `codex/website-redesign` into `main` and pushed; the workflow is now main-based (work on `main`, push, live in ~60s). Docs updated accordingly; the codex branch is retired.
- Thesis section rebuilt after owner critique that it repeated the hero. The two product cards and the reused ecosystem map are gone. In their place: "Every building lives twice." over a purpose-built lifecycle spine, Twin's half (Land / Regulation / Capital / Risk) running into a handover diamond, Home's half (Residents / Staff / Service / Privacy) running out of it, with Tesseract Brain nested inside Home's half. Nav label "Ecosystem" renamed "Thesis" on all pages (anchor id unchanged). ~13 KB of dead CSS from the old map era removed.
- Mobile polish pass: `viewport-fit=cover` plus safe-area insets on the nav, mobile menu, and footer (notch and home-indicator letterboxing); the nav is now transparent over the hero and gains its glass surface after 24px of scroll on every page; on touch screens, cards illuminate as they pass the viewport's middle band, giving phones the hover treatment desktop gets. Footer carries the brand mark.
- Verified in iPhone emulation (hover:none path active, middle-band lighting works, nav state toggles) and the full sweep stayed clean: zero console errors, zero overflow, both viewports, all four pages.

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
