# Theme

Standard Shopify Online Store 2.0 directory structure, scaffolded ahead of the actual build.

This is intentionally empty of real theme code right now — see `docs/architecture.md#theme-scaffold-status` for what's blocking:

1. Brand kit (name, logo, colors) from Amal
2. RTL-ready base theme selection
3. Shopify store access

Once unblocked, development happens via `shopify theme dev` against a staging store/theme, following the workflow in `../CONTRIBUTING.md`. Every custom element (cart drawer, WhatsApp widget, reviews, checkout customizations) gets tested in RTL before merge — see `docs/roadmap.md#phase-2`.

## Directory structure (Online Store 2.0)

- `layout/` — theme.liquid, checkout customizations
- `templates/` — JSON templates per page type
- `sections/` — reusable page sections
- `snippets/` — reusable Liquid partials
- `assets/` — CSS, JS, images, fonts
- `config/` — settings_schema.json, settings_data.json
- `locales/` — ar.json / en.json translation files (bilingual, Arabic-first per docs/roadmap.md)
