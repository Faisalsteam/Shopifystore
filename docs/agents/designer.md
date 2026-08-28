# Agent: Designer

## Mission

Own the storefront's visual and UX execution — layout, design system, section behavior — so that the moment a brand kit and RTL theme are selected, the actual build is fast because the specs already exist.

## Responsibilities

- Wireframes/section specs for the core templates: homepage, product (PDP), collection, cart drawer, checkout-adjacent pages.
- A design system checklist: type scale, spacing, color-role naming (not values — those come from the brand kit), button/form states, empty/loading/error states.
- RTL layout notes for every component (mirroring, icon direction, number/price formatting) — RTL is a stated requirement, not an afterthought (`docs/roadmap.md`).
- Asset conventions: image sizing (2000px+ per the roadmap's product data spec), naming (`sku-1.jpg`), alt-text pattern for SEO/accessibility.
- A design brief template Amal fills in once, to hand over brand name, logo, palette, and tone in one pass.

## Out of scope

- Choosing the brand name, logo, or color palette — that's Amal's call, not the agent's.
- Committing final brand colors/logo into the live theme before the brand kit exists — layout and RTL fixes can land now, but visual polish (color tokens, logo placement) waits.
- Product photography direction beyond the asset-convention spec above.

## Current-phase deliverables

| File | Purpose |
|---|---|
| [`docs/design/brief-template.md`](../design/brief-template.md) | One form Amal fills to hand over the brand kit |
| [`docs/design/wireframes.md`](../design/wireframes.md) | Section-by-section layout specs, brand-agnostic, RTL-annotated |

**Update:** the base theme is no longer just planned — it's real. Shopify's Dawn `v16.0.0` is vendored at the repo root (see `THEME.md`), `dir="rtl"`/`dir="ltr"` is wired at the layout level, and the store (`9gucqc-qy.myshopify.com`) is connected via Shopify's GitHub integration and confirmed working (see `docs/deployment.md`). Two of this charter's three blockers are cleared — layout/RTL/structural work no longer needs to wait on the brand kit; only final color tokens and logo placement do.

## Blocked on → unlocks at

| Blocked on | Unlocks |
|---|---|
| Brand kit (name, logo, palette) — `docs/setup-checklist.md` (Amal) | Design tokens get real values; final visual polish |
| ~~RTL-ready base theme selected~~ | **Cleared** — Dawn v16.0.0 vendored, RTL wired at layout level |
| ~~Shopify store access~~ | **Cleared** — store connected via GitHub integration, preview confirmed working |

## Cadence

Weekly review of the wireframe/brief backlog. With the theme and store connection now real, structural/RTL work on actual `sections/`/`snippets/` (not just specs) can proceed now — the brand kit is the only remaining blocker, and only for final color/logo values.
