# Theme

The Shopify theme lives at the **repository root** (`layout/`, `templates/`, `sections/`, `snippets/`, `assets/`, `config/`, `locales/`) — that's a Shopify requirement for the GitHub integration described in `docs/deployment.md`, not a stylistic choice; Shopify's "Connect from GitHub" only looks at the root of the branch, there's no subfolder option.

Base: [Shopify Dawn](https://github.com/Shopify/dawn) `v16.0.0`, vendored directly (not a git submodule, so it's self-contained and diffable in this repo). Dawn is Shopify's free, actively-maintained reference theme — Online Store 2.0, no build step, good performance defaults. License: `vendor/DAWN_LICENSE.md` (permits modification for a theme that runs on Shopify).

## Status

This is an unbranded starting point, not the finished storefront. What's done vs. still open:

**Done**
- Dawn v16.0.0 vendored in full (`layout/`, `templates/`, `sections/`, `snippets/`, `assets/`, `config/`, `locales/`)
- `layout/theme.liquid` sets `dir="rtl"`/`dir="ltr"` on `<html>` automatically based on the active storefront language (`request.locale.iso_code`), so the layout flips the moment Arabic is added as a shop language — no theme-setting toggle needed
- Connected to the live store (`9gucqc-qy.myshopify.com`) via Shopify's GitHub integration — see `docs/deployment.md`
- WhatsApp click-to-chat floating button (`sections/whatsapp-button.liquid`) — a plain `wa.me` link, no WhatsApp Business API/BSP account needed; number, message, colors, and on/off all editable from the theme customizer under Theme settings. The Business API + automated flows (Zoko/WATI) are a separate, later Phase 4 build — this just gets a real "message us" entry point live now.
- Klaviyo onsite tracking hook — a "Klaviyo Public API Key" setting under Theme settings → Integrations; once filled in, Klaviyo's tracking script and dashboard-built forms/popups work with no further code changes. Order/customer sync is separate (the Klaviyo Shopify app, no code either) — see `docs/marketing/klaviyo-flows.md`.

**Still open — see `docs/roadmap.md` (Phase 2) and `docs/setup-checklist.md`**
- Brand kit not applied yet: no logo, no color palette, no fonts — currently running Dawn's stock look
- No Arabic locale file (`locales/ar.json`) — Dawn ships English and other locales but not Arabic by default; content needs to be written Arabic-first per the roadmap, not machine-translated
- CSS/section-by-section RTL audit: first pass done (see below), full visual QA still pending real content

**RTL audit — first pass (`assets/rtl-overrides.css`)**

Dawn's CSS uses physical properties (`left`/`right`, `translateX`, `float`, `text-align: left`) throughout, which don't auto-flip just because `dir="rtl"` is set. Fixed with high confidence — components that were hardcoded to one physical screen edge regardless of reading direction, which is genuinely broken (not just imperfect) in RTL:
- **Cart drawer** — was hardcoded to always open from the right; now mirrors to open from the left in RTL, including the close button position and a couple of small text-align/float details inside it
- **Mobile menu drawer** (and its submenu panel) — same issue, same fix

Deliberately **not** attempted in this pass: Dawn has ~50 CSS files with some left/right usage, most of it non-directional (corner radii, one-off spacing) or low-risk enough that guessing at a fix without a live visual check risks introducing a new bug rather than fixing one. A full pixel-by-pixel pass needs real content and a live preview — worth doing once the brand kit lands and there's something real to look at, not against Dawn's placeholder content.

## How this gets to the store

Deployment is **GitHub → Shopify**, not a CLI push from Claude's development session (which can't reach `*.myshopify.com` — see `docs/deployment.md` for why). Push changes to the connected branch in this repo and the corresponding theme in the Shopify admin updates automatically; nothing goes live until it's published from there.

If you're working on this theme from a machine with normal internet access (not this session), the standard [Shopify CLI](https://shopify.dev/docs/api/shopify-cli) flow still works for local preview:

```
shopify theme dev --store <your-store>.myshopify.com
```

Never push straight to the live/published theme — follow the branch → staging theme → Amal approves → publish flow in `CONTRIBUTING.md`.

## Directory structure (Online Store 2.0)

- `layout/` — theme.liquid, checkout customizations
- `templates/` — JSON templates per page type
- `sections/` — reusable page sections
- `snippets/` — reusable Liquid partials
- `assets/` — CSS, JS, images, fonts
- `config/` — settings_schema.json, settings_data.json
- `locales/` — translation files (bilingual AR/EN target, Arabic-first per `docs/roadmap.md`)
- `vendor/` — upstream Dawn license and release notes, kept for attribution

Everything else at the repo root (`docs/`, `README.md`, `.github/`, etc.) is project documentation and tooling — Shopify's theme connector only reads the folders listed above and ignores the rest.
