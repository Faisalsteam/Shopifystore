# Architecture & Repo Structure

## Planned tech stack

- **Storefront**: Shopify Online Store 2.0 theme, RTL-ready (Arabic-first, English secondary)
- **Catalog management**: Matrixify app + a Google Sheet master catalog (owned by Amal, outside this repo)
- **Payments**: hosted checkout via a regional gateway (MyFatoorah / Tap / PayTabs / Telr) — no custom payment form, keeps card data out of PCI scope
- **CRM/marketing**: Klaviyo (native Shopify integration) + Shopify Flow for simple trigger wiring
- **WhatsApp**: WhatsApp Business API + a BSP app (Zoko or WATI); anything beyond Flow's simple rules is custom webhook code living in this repo
- **Delivery**: third-party courier integration at launch; a custom in-house delivery/tracking app is a later, separate build once volume justifies it
- **Reporting/BI**: Shopify analytics + Looker Studio; no custom BI dashboard pre-launch

## Repo layout

```
theme/                  Shopify theme (Online Store 2.0 structure)
  layout/
  templates/
  sections/
  snippets/
  assets/
  config/
  locales/
apps/                    Custom L3 apps/services (created as needed — e.g. WhatsApp
                         webhook relay, future delivery-tracking app). Each gets its
                         own README per docs/roadmap.md Phase 7-8.
docs/                    Roadmap, checklists, integration tracker, this file
.github/                 PR/issue templates, CI workflows
.env.example             Every env var a custom app needs, no real values
```

`apps/` doesn't exist yet — it's created the first time an L3 custom piece is built (see `docs/roadmap.md` for what's L3: WhatsApp checkout flow beyond simple Flow rules, custom delivery/tracking app, voice/photo search — all deferred or scoped as needed).

## Theme scaffold status

`theme/` currently holds the standard Online Store 2.0 directory structure with no theme installed yet. It's waiting on:
1. Brand kit (name, logo, colors) from Amal
2. An RTL-ready base theme selection
3. Shopify store access (to pull/push via Shopify CLI)

Once those land, the actual theme (either a purchased/RTL-ready theme or a fork of a base like Dawn) gets committed here and developed via `shopify theme dev` against a staging store, per the workflow in `CONTRIBUTING.md`.

## CI

`.github/workflows/theme-check.yml` runs [Shopify Theme Check](https://shopify.dev/docs/storefronts/themes/tools/theme-check) against `theme/` on every PR once real theme files exist. It's a no-op until then.
