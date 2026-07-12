# DECISIONS — Tesseract marketing site

Most recent first. One entry per material decision.

## 2026-07-11

- **Keep Real Estate Intelligence.** The owner approved the existing parent positioning; no broad digital-twin or mobility repositioning.
- **Exclude Fleet.** The public site focuses only on current real-estate products.
- **Three-product architecture.** Twin, Brain and Home are the Tesseract products shown on the website.
- **Brain replaces Cortex publicly.** Brain and Cortex are one device; Tesseract Brain is the current name. Public-facing explorer and website copy use Brain.
- **The Presidential stays small.** It is Home's first live deployment and case study, never a separate product.
- **Preserve the signature experiences.** Keep the canonical scroll-reveal logo opening and the live Home architecture pipeline, including its mobile-first layout.
- **Remove stale claims.** Version-specific Twin metrics and unsupported older Home promises were removed rather than carried into the redesign.
- **Website-only isolation.** Implementation and persistent memory updates occur only in `website-tesseract-site`; all other repositories remain untouched.

## 2026-07-06

- **Reposition to a digital-twin company.** Move the top-line story off "Real Estate Intelligence" to "a digital-twin company" with two worlds: Built Environment (Twin before the build, Home once lived in) and Mobility (Fleet). Real estate stays the hero; Fleet stays lightly featured (concept stage). Rationale and layout in `../TESSERACT_SITE_RESTRUCTURE_BRIEF.md`.
- **The Presidential is proof, not a product.** It is the first live white-label deployment of Tesseract Home (a Webtech Realty tower). On our sites it appears only as Home's first live deployment or case study, wearing the client's crown-gold brand with a discreet "Powered by Tesseract". Never present it as a Tesseract-branded product.
- **Home Architecture Explorer built as a Home-page component.** An interactive, self-contained explainer of Home's edge-AI architecture, in `home-architecture-explorer/`. Kept in its own folder, isolated: it borrows only the interaction pattern from tesseract-fleet's system map, contains no Fleet code, and does not depend on the Home or Presidential app repos. Responsive dual layout (portrait mobile, wide desktop). Uses the official cube-within-cube mark (blue outer, green inner). Not embedded in the live pages until integration is approved.
- **Everything additive and untracked.** The brief, the explorer and this workspace were added to the repo without touching the live pages, on the redesign branch, uncommitted. The owner does all git.
