# Setup Checklist

Live blocker list, by owner. Check items off in PRs/issues as they close — this file is the source of truth, not the original PDF.

## Amal — blocks Phase 1–2 (store build can't start without these)

- [ ] Brand name
- [ ] Logo
- [ ] Color palette
- [ ] Domain purchased
- [ ] Theme selected (must be RTL-ready — see `docs/integrations.md#theme`)

## Faisal — feeds Phase 0 (merchant/courier setup) and Phase 3 (localization)

- [ ] Which GCC country(ies) launch first (decides payment gateway + courier)
- [ ] Payment gateway shortlist confirmed (MyFatoorah / Tap / PayTabs / Telr)
- [ ] Shipping/courier shortlist confirmed (Aramex / iMile / local courier)
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

- [ ] Shopify store URL + Admin API access token or theme access (to push theme code)
- [ ] Klaviyo API key
- [ ] Payment gateway API credentials (after merchant approval)
- [ ] WhatsApp BSP (Zoko/WATI) API credentials
- [ ] Google Maps API key
- [ ] Master product catalog (Google Sheet, per `docs/roadmap.md#phase-2`)

None of these should ever be committed to this repo — see `.env.example` and `docs/integrations.md` for how secrets are handled.
