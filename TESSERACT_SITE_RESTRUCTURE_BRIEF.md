# Tesseract Website — Approved Real-Estate Redesign Brief

**Owner:** Harshit Chhajed  
**Approved:** 11 July 2026  
**Scope:** `website-tesseract-site` only

## Direction

Keep **Real Estate Intelligence** as the parent positioning. The website focuses only on Tesseract's current real-estate ecosystem. Tesseract Fleet is deliberately excluded.

The public product architecture is:

```
TESSERACT — Real Estate Intelligence
│
├─ Tesseract Twin   — development-strategy digital twin
├─ Tesseract Brain  — on-site intelligence device for Home
└─ Tesseract Home   — building intelligence platform
      └─ The Presidential — first live deployment and case study
```

The Presidential is proof of Tesseract Home in a live building. It receives a small, restrained mention and must never be presented as a separate Tesseract product.

## Product truth

### Tesseract Twin

Twin connects feasibility, approvals, capital, execution risk and returns before capital is committed. It is the development-strategy product in the ecosystem. Avoid carrying forward version-specific metrics or claims unless the owner explicitly reconfirms them.

### Tesseract Brain

Brain is the current public name of the on-site device previously called Cortex. Brain runs Tesseract Home's digital twin and local intelligence inside the building. Brain and Cortex are not separate devices; public-facing website copy uses **Tesseract Brain**.

Do not invent hardware specifications, performance figures, model sizes or deployment quantities.

### Tesseract Home

Home is the building intelligence product. Its resident app, building-team desks, management portal and sensors operate through one living model of the building. Verified Home surfaces include visitor pre-authorisation, amenity booking, bills, helpdesk, parking and valet, and notices.

The live system architecture is the canonical explanation of Home's pipeline:

1. A person makes a request on an authorised surface.
2. The identity gate binds the request to the person and allowed units, deny by default.
3. The building's twin supplies relevant records.
4. Grounding retrieves evidence and returns an honest miss below threshold.
5. Tesseract Brain forms the answer locally over grounded context.
6. The answer returns to the person and the exchange is captured and auditable.

The displayed egress paths are a payment token, a visitor pass and an encrypted backup. Local is the zero-egress default; cloud inference is explicit and optional.

### The Presidential

The Presidential is Tesseract Home's first live deployment and case study. Keep the mention small. It is not a separate product and should not take over the Tesseract brand experience.

## Brand canon

- Master mark: exact outer blue isometric cube and inner green cube paths already in the site.
- Master palette: deep navy, Tesseract blue and Tesseract green.
- Twin accent: blue.
- Home accent: green.
- Brain uses the master blue/green relationship; do not create a third arbitrary product colour.
- Typography: Inter plus JetBrains Mono only.
- Voice: confident, technical, precise and grounded in implementation.
- Motion must explain state, sequence or system behavior. Avoid decorative motion without meaning.
- Avoid generic AI visuals, stock imagery, loud gradients, inflated claims and template-like feature grids.

## Experience architecture

### Homepage

1. Preserve the opening scroll-reveal of the canonical Tesseract mark.
2. Resolve into `TESSERACT`, `See what others can't` and `Real Estate Intelligence`.
3. Introduce Twin, Brain and Home as three distinct products in one real-estate ecosystem.
4. Feature the live Home system architecture as the signature interactive experience.
5. Mention The Presidential only as Home's first live deployment.
6. Keep `Built by builders, not consultants` as the foundation.
7. End with a direct conversation CTA.

### Product pages

- `twin.html`: development strategy, lifecycle and connected decision logic.
- `brain.html`: the on-site device, governed inference path and data boundary.
- `home.html`: resident and building-team experience, role-aware surfaces and privacy architecture.
- `home-architecture-explorer/`: the canonical interactive pipeline, optimized for desktop and mobile.

## Engineering constraints

- Static, self-contained HTML.
- No framework, bundler, analytics or new dependencies.
- Keep CSS and JavaScript inline.
- Keep colors tokenized in `:root`.
- Preserve the exact logo geometry.
- Maintain matching navigation and footer links across all four primary pages.
- Verify desktop and mobile before handoff.

## Isolation

All implementation and working-memory updates stay inside this website repository. Do not edit, import from or write into the Twin, Home, Brain, Presidential, Fleet, Brand or archive repositories. The owner performs commits and pushes.
