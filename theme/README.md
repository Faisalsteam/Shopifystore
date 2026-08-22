# Theme

Base: [Shopify Dawn](https://github.com/Shopify/dawn) `v16.0.0`, vendored directly (not a git submodule, so it's self-contained and diffable in this repo). Dawn is Shopify's free, actively-maintained reference theme — Online Store 2.0, no build step, good performance defaults. License: `vendor/DAWN_LICENSE.md` (permits modification for a theme that runs on Shopify).

## Status

This is an unbranded starting point, not the finished storefront. What's done vs. still open:

**Done**
- Dawn v16.0.0 vendored in full (`layout/`, `templates/`, `sections/`, `snippets/`, `assets/`, `config/`, `locales/`)
- `layout/theme.liquid` now sets `dir="rtl"`/`dir="ltr"` on `<html>` automatically based on the active storefront language (`request.locale.iso_code`), so the layout flips the moment Arabic is added as a shop language — no theme-setting toggle needed

**Still open — see `docs/roadmap.md` (Phase 2) and `docs/setup-checklist.md`**
- Brand kit not applied yet: no logo, no color palette, no fonts — currently running Dawn's stock look
- No Arabic locale file (`locales/ar.json`) — Dawn ships English and other locales but not Arabic by default; content needs to be written Arabic-first per the roadmap, not machine-translated
- CSS/section-by-section RTL audit not done — the `dir` attribute is wired at the document level, but every custom element (cart drawer, WhatsApp widget, reviews, checkout customizations) still needs to be visually checked in RTL as it's built or modified, per the roadmap's reality check
- Not yet connected to a live Shopify store — see the root `README.md` status section for what unblocks this

## Working on it locally

Requires the [Shopify CLI](https://shopify.dev/docs/api/shopify-cli) and a way to authenticate against the store (see root `README.md` for the current plan — a Theme Access app password, generated from the store's admin).

```
shopify theme dev --store <your-store>.myshopify.com
```

This serves the theme locally against live store data without touching the published theme. Push to a new unpublished theme on the store with:

```
shopify theme push --unpublished --store <your-store>.myshopify.com
```

Never push straight to the live/published theme — follow the branch → staging theme → Amal approves → publish flow in `../CONTRIBUTING.md`.

## Directory structure (Online Store 2.0)

- `layout/` — theme.liquid, checkout customizations
- `templates/` — JSON templates per page type
- `sections/` — reusable page sections
- `snippets/` — reusable Liquid partials
- `assets/` — CSS, JS, images, fonts
- `config/` — settings_schema.json, settings_data.json
- `locales/` — translation files (bilingual AR/EN target, Arabic-first per `../docs/roadmap.md`)
- `vendor/` — upstream Dawn license and release notes, kept for attribution
