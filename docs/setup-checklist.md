# Setup Checklist

Live blocker list, by owner. Check items off in PRs/issues as they close — this file is the source of truth, not the original PDF.

## Amal — blocks Phase 1–2 (store build can't start without these)

- [ ] Brand name
- [ ] Logo
- [ ] Color palette
- [ ] Domain purchased
- [x] ~~Theme selected~~ — Shopify Dawn v16.0.0 vendored in `theme/`, RTL-wired at the layout level; still unbranded (see the *Theme* row in `docs/integrations.md`)

## Faisal — feeds Phase 0 (merchant/courier setup) and Phase 3 (localization)

- [x] ~~Which GCC country(ies) launch first~~ — confirmed: **all GCC markets**. Still open: which gateway(s)/courier(s) actually cover all six at acceptable cost, see `docs/integrations.md`
- [ ] Payment gateway shortlist confirmed (MyFatoorah / Tap / PayTabs / Telr) — evaluate against full-GCC coverage, not single-country
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

- [ ] Terms & Conditions
- [ ] Privacy Policy
- [ ] Refund / Shipping Policy
- [ ] FAQ
- [ ] Trade license / commercial registration (varies by launch country)

All bilingual (AR/EN), written Arabic-first.

## What Claude (developer) needs handed over, once the above unblock

- [x] ~~Shopify store domain + Theme Access password~~ — received (`9gucqc-qy.myshopify.com`). Not usable from this development session (network policy blocks direct Shopify API access — see `docs/deployment.md`); deployment instead goes through Shopify's GitHub integration.
- [ ] **Next up:** connect the store to this GitHub repo (**Online Store → Themes → Add theme → Connect from GitHub**, repo `Faisalsteam/Shopifystore`, folder `theme`) — exact steps and branch mapping in `docs/deployment.md`
- [ ] Klaviyo API key
- [ ] Payment gateway API credentials (after merchant approval)
- [ ] WhatsApp BSP (Zoko/WATI) API credentials
- [ ] Google Maps API key
- [ ] Master product catalog (Google Sheet, per the Phase 2 section of `docs/roadmap.md`)

None of these should ever be committed to this repo — see `.env.example` and `docs/integrations.md` for how secrets are handled.

## Agent-ready work (not blocked — happening now)

Five AI agents (`docs/agents/`) are producing drafts, specs, and templates that don't require any of the above — see each charter for exactly what's ready and what it unlocks once its blockers above clear:

- Designer → `docs/design/` (needs: brand kit)
- Chatbot / Call Center → `docs/support/` (needs: WhatsApp Business API + BSP)
- Dispatcher → `docs/dispatch/` (needs: launch country, courier account)
- Marketing Agency → `docs/marketing/` (needs: Klaviyo, WhatsApp BSP, social/Prisync accounts)
- SEO Content Writer (AR/EN) → `docs/seo/` (needs: master product catalog)
