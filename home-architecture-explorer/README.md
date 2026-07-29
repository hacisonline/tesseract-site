# Home Architecture Explorer

An interactive, self-contained explainer of how **Tesseract Home** works, built as the signature "how it works" component for the Home product page on the marketing site.

- **File:** `index.html`. Open it directly; no build step, no dependencies except one Google Fonts link with system fallbacks.
- **Status (2026-07-11):** built and browser-verified on desktop and mobile. The failed redesign was reverted; this remains a standalone component and is intended to become the future Tesseract Home page hero.
- **Deploys** as `/home-architecture-explorer/` on GitHub Pages once the repo is pushed.

## What it shows (self-contained: you do not need any app repo to work on this)

Tesseract Home is **edge AI infrastructure for a building**: a digital twin and a language model that run on **Tesseract Brain**, the device in the building's own control room, so the building's data never has to leave. The diagram is a live map of that:

- **Surfaces and sensors** (resident app, staff desks, management portal, sensors) **ingest** into **one digital twin**, the single living model of the building.
- A **question** travels **You, then the identity gate, then the twin, then grounding, then Tesseract Brain, then the answer back to you.** The identity gate binds every request to the asker's own units, deny by default. Grounding is retrieval-first (an honest miss below the evidence threshold). Brain runs the local language model over the grounded records.
- **Audit** (an actor on every write) and **capture** (each Reception exchange) are written back.
- **Egress** is only ever three things: a payment token, a visitor pass, an encrypted backup. Nothing else leaves.
- An **inference-mode** toggle (Retrieval / Local / Cloud) shows local as the zero-egress default and cloud as an explicit, logged, optional choice.

This is faithful to the product's documented architecture. The authoritative product spec lives in the Tesseract Home and The Presidential app repos, but **you do not need them to work on this component, and must not wire this to them.**

## Design and interaction

- **Responsive dual layout, chosen at load:** portrait (vertical) below 960px, wide (left-to-right) at 960px and up. Each layout is a single SVG that scales as one unit (mobile-first; no runtime re-layout, no horizontal scroll). If you resize across the breakpoint, reload to switch layout.
- **Tesseract Brain** is represented by a live, rotating tesseract (the official cube-within-cube: blue outer, green inner) with reactive states: an idle breathe, a faster "thinking" spin, and a green charge-and-release as the answer forms.
- **Live data flow:** continuous colour-coded packets on every channel (query, ingest, grounded context, answer, audit, egress), with a legend.
- **Interactions:** tap any node for its role; "Trace a question" runs the six-step pipeline with a travelling data point; the inference-mode toggle changes the Brain label and the egress.
- **Brand:** Tesseract tokens inline (navy, blue, green; Inter + JetBrains Mono) and the official mark. This is Tesseract's own view of the platform; the live building app wears each client's brand (at The Presidential, Webtech Realty's crown-gold).

## How it is built (for editing)

- Layout is **data-driven**: `META` (node labels), `PORTRAIT` and `WIDEL` (per-layout node positions as `[cx,cy,w,h]`, tier bands, egress, answer path), and `CH` (the flow channels). Channel paths are computed by a generic router from the node boxes, so both layouts work from the same channel list.
- To move or add a node, edit its entry in **both** layout maps; keep boxes from overlapping and keep labels within box width. The build was validated with a per-layout node-bounds and overlap check.
- Keep it self-contained and dependency-free. Do not add a build step and do not import from any app repo.

## Isolation

This is a self-contained marketing asset and does not depend on the Home, Brain or Presidential app repositories. Do not couple it to any product repo.

## Provenance

Built 2026-07-06 (Cowork), iterated to final and Chrome-verified. Full history in `../claude-workspace/SESSION-LOG.md`.
