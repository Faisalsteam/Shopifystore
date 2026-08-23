# Setup Checklist

Live blocker list, by owner. Check items off in PRs/issues as they close — this file is the source of truth, not the original PDF.

## Amal — blocks Phase 1–2 (store build can't start without these)

- [ ] Brand name
- [ ] Logo
- [ ] Color palette
- [ ] Domain purchased
- [x] ~~Theme selected~~ — Shopify Dawn v16.0.0 vendored at the repo root (see `THEME.md`), RTL-wired at the layout level; still unbranded (see the *Theme* row in `docs/integrations.md`)

## Faisal — feeds Phase 0 (merchant/courier setup) and Phase 3 (localization)

- [x] ~~Which GCC country(ies) launch first~~ — confirmed: **all GCC markets**. Still open: which gateway(s)/courier(s) actually cover all six at acceptable cost, see `docs/integrations.md`
- [ ] Payment gateway shortlist confirmed (MyFatoorah / Tap / PayTabs / Telr) — comparison ready in `docs/payment-gateway-comparison.md`, decision + direct rate quotes still needed
- [ ] Shipping/courier shortlist confirmed (Aramex / iMile / local courier) — same, full-GCC coverage
- [ ] Taxes
- [ ] Packaging supplier + costing
- [ ] Initial + monthly budget envelope
- [ ] Startup budget, run-rate, margin targets by product line

## Accounts to open (Phase 0, start immediately — long lead times)

- [ ] Shopify store (plan tier decided for staff permission granularity)
- [ ] GitHub org access confirmed (this repo)
- [ ] Meta Business Manager
- [ ] **WhatsApp Business API approval — start now, real lead time**
- [ ] **Payment gateway merchant account (KYC) — start now, real lead time**
- [ ] Google Cloud project (Maps API)
- [ ] Klaviyo account
- [ ] Zoko or WATI account (WhatsApp BSP)

## Content that blocks payment gateway approval

- [x] ~~Terms & Conditions~~ — draft ready, bilingual: `content/legal/{ar,en}/terms-and-conditions.md`
- [x] ~~Privacy Policy~~ — draft ready, bilingual: `content/legal/{ar,en}/privacy-policy.md`
- [x] ~~Refund / Shipping Policy~~ — draft ready, bilingual: `content/legal/{ar,en}/refund-shipping-policy.md`
- [ ] **All three need a licensed Kuwait/GCC lawyer's review before publishing** — see `content/legal/README.md` for exactly what's unverified (they're grounded in Kuwait Law No. 39/2014, which is solid; a couple of newer regulatory claims found in research were deliberately left out as unconfirmed — see that README)
- [ ] FAQ
- [ ] Trade license / commercial registration (varies by launch country)

All bilingual (AR/EN), written Arabic-first.

## What Claude (developer) needs handed over, once the above unblock

- [x] ~~Shopify store domain + Theme Access password~~ — received (`9gucqc-qy.myshopify.com`). Not usable from this development session (network policy blocks direct Shopify API access — see `docs/deployment.md`); deployment instead goes through Shopify's GitHub integration.
- [x] ~~Connect the store to this GitHub repo~~ — done. `9gucqc-qy.myshopify.com` is connected to this repo on this branch via Shopify's GitHub integration; preview confirmed working (2026-08-22). The theme had to be moved to the repo root for the connection to find it — Shopify's connector has no subfolder option (see `docs/deployment.md`). Future pushes to the connected branch update it automatically.
- [ ] **Next up:** brand kit (name, logo, colors) from Amal — this is the next real blocker; everything else (theme, RTL wiring, store connection) is in place and waiting on it
- [ ] Klaviyo API key
- [ ] Payment gateway API credentials (after merchant approval)
- [ ] WhatsApp BSP (Zoko/WATI) API credentials
- [ ] Google Maps API key
- [x] ~~Master product catalog~~ — 2,855-row supplier list received and parsed into a Matrixify-ready draft workbook (English fields, Arabic title draft, review-flags sheet); delivered directly, not committed to this repo per the Google Sheets convention below — see `docs/catalog-import.md` for the methodology. Still needed: prices, inventory counts, and product photos (not something that can be generated — see that doc)

None of these should ever be committed to this repo — see `.env.example` and `docs/integrations.md` for how secrets are handled.

## Agent-ready work (not blocked — happening now)

Five AI agents (`docs/agents/`) are producing drafts, specs, and templates that don't require any of the above — see each charter for exactly what's ready and what it unlocks once its blockers above clear:

- Designer → `docs/design/` (theme + store connection cleared — only final color/logo values still need brand kit)
- Chatbot / Call Center → `docs/support/` (needs: WhatsApp Business API + BSP)
- Dispatcher → `docs/dispatch/` (needs: launch country, courier account)
- Marketing Agency → `docs/marketing/` (needs: Klaviyo, WhatsApp BSP, social/Prisync accounts)
- SEO Content Writer (AR/EN) → `docs/seo/` (master catalog cleared — now drafting real per-brand-line content)
