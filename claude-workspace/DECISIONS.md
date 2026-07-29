# DECISIONS — Tesseract marketing site

Most recent first. One entry per material decision.

## 2026-07-29 — v3.2 owner critiques (thesis, touch, deploys)

- **The thesis section must add information, not restate the hero.** It is now the lifecycle spine under "Every building lives twice.": Twin's half, the handover, Home's half with Brain nested inside. Side-by-side product-card duos are banned on the homepage; the hero already introduces the products.
- **Touch is first-class.** Any hover-only affordance needs a scroll equivalent on touch screens; the pattern is the `.lit` middle-band illumination driven by IntersectionObserver under `(hover: none)`. Safe areas are handled with `viewport-fit=cover` + `env(safe-area-inset-*)`.
- **Deploys are main-based.** The owner pushes finalised changes from the terminal; `main` is the deploy branch and there is no staging step. Agents leave work uncommitted for owner review.

## 2026-07-29 — v3.1 owner review corrections

- **Brain is never a top-level peer.** It does not appear in the primary nav; it is reached through Home (Home chapter banner, Home page band, footer "Brain · inside Home", indented mobile-menu entry). Any future nav change must preserve this.
- **The intro's two product panels must be structurally identical** so they render at equal size; each carries one meta line (Twin: version + tests; Home: Brain inside).
- **The homepage is a chaptered narrative, not stacked sections.** Thesis band (split-coloured map + numbered world cards) then chapters 01 Twin, 02 Home, 03 Foundation with a shared chapter-header component. The old four-step sticky ecosystem scroller is retired.

## 2026-07-29 — site v3 direction (owner-answered in session)

- **Explorer placement: Home page hero ONLY.** The homepage links into it ("See the live architecture") but does not embed it. Confirms and finalises the 2026-07-11 direction.
- **Brain goes public by name, full story.** "Tesseract Brain" is the public name on the site. The page tells the expanded 2026-07-22 ADR story: the building's own server (hosts Home's app, records, and local model) plus the front-of-house AI reception. Hard rule kept: no specifications, no prices, no dates; the page carries an explicit honesty note.
- **The Presidential is credited.** Public credit reads "The Presidential by Webtech Realty", framed as Home's first white-label deployment, in active build. Still proof, not a product.
- **Domain stays a redirect.** thinktesseract.com continues 302-forwarding to hacisonline.github.io/tesseract-site. Canonical/OG URLs point at the GitHub Pages origin. No CNAME committed.
- **One design system across all four pages.** twin.html and home.html abandoned their legacy pre-redesign token set; every page now uses the canonical index tokens and shared nav/footer. The cube-reveal intro was preserved implementation-intact.
- **Fresh product truth over stale claims.** Twin imagery re-captured from the live V7.0 file (sample scenario, recalculated); the stale "266KB" size claim was dropped; the old smart-home feature claims (adaptive climate, elevator dispatch) were removed from Home in favour of the documented architecture story.

## 2026-07-11 — corrected after rollback

- **Rollback completed.** Commit `18bdf5f` was reverted by `705ceba`; no history was rewritten.
- **Keep Real Estate Intelligence and exclude Fleet.** The website stays focused on real estate.
- **Home owns the architecture hero.** The existing live, mobile-optimized architecture is the future Home page's primary experience.
- **Brain belongs within Home's ecosystem.** Brain is upcoming cutting-edge hardware and must receive a purposeful hardware narrative—not a generic grey peer card or floating-logo hero.
- **The Presidential stays small.** It is Home's first live deployment and case study, not a separate product.
- **Do not repeat the failed visual language.** Avoid generic product grids, accidental bloom spots, shallow logo treatments and unsupported marketing claims.

## 2026-07-06

- **The Presidential is proof, not a product.** It is the first live white-label deployment of Tesseract Home. Never present it as a Tesseract-branded product.
- **Home Architecture Explorer built as a Home-page component.** The responsive live pipeline in `home-architecture-explorer/` is a self-contained marketing asset and does not depend on product repositories.
- **Everything additive and untracked.** The brief, explorer and workspace context were placed in this repository without touching the live pages. The owner does all Git.
