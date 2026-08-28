# Shipping Rates Setup — Kuwait + GCC (Local Drivers)

Real rates confirmed by Faisal (2026-08-28): **1.5 KWD within Kuwait, 5.5 KWD for the rest of the GCC**, fulfilled by local drivers (not a third-party courier like Aramex/iMile). This replaces the placeholder shortlist in `docs/dispatch/courier-matrix.md`.

## Why this is a manual Shopify Admin step, not something pushed from this repo

Shipping rates and zones are store configuration, not theme code — they live in **Shopify Admin → Settings → Shipping and delivery**, not in this GitHub repo. There's no file here that controls them, and this development session has no Shopify Admin/API access (same network restriction as `docs/deployment.md` and `docs/payments-setup.md` — the store connects to this repo one-way, for theme code only). This doc is the exact click-by-click steps so Amal or Faisal can set it up directly; it takes a few minutes.

## Steps (Shopify Admin)

1. **Settings → Shipping and delivery → Shipping**.
2. Under **General shipping rates**, click **Manage rates** (or **Create shipping zone** if none exist yet — Shopify's default "Rest of World" / "Domestic" zones won't have the right split, replace them).
3. **Create shipping zone 1 — Kuwait:**
   - Zone name: `Kuwait`
   - Countries: Kuwait only
   - Add rate → **Price-based rate** (flat) or **Weight-based** — recommend flat first (fixed price):
     - Rate name (customer-facing): `Local Delivery` / English, `توصيل محلي` Arabic (Shopify's rate names support a translated variant via Translate & Adapt, or Amal can just use one bilingual name like `Local Delivery / توصيل محلي`)
     - Price: **1.500 KWD**
4. **Create shipping zone 2 — Rest of GCC:**
   - Zone name: `GCC` (or split into separate zones per country if delivery reliability differs — start with one combined zone unless there's a reason not to)
   - Countries: Saudi Arabia, UAE, Qatar, Bahrain, Oman (the other five GCC countries — Kuwait is its own zone above, don't double-include it)
   - Add rate → flat price-based rate:
     - Rate name: `GCC Delivery` / `توصيل دول الخليج`
     - Price: **5.500 KWD**
5. **Currency check:** confirm the store's currency is set to KWD (Settings → General → Store currency) before entering these — if the store currency is different, Shopify will treat "1.5" as that currency, not KWD, and the rate will be wrong. If KWD isn't a supported presentment currency for the plan, flag that back — it changes how these two numbers get entered.
6. Save each zone.
7. **Test:** go through a real or test checkout (see `docs/testing-checkout.md` — same live-account money-safety note applies) with a Kuwait address and a non-Kuwait GCC address, confirm the correct rate shows at checkout for each.

## What's still open (needs Faisal/Amal, not code)

- **Free-shipping threshold** — common in the region (e.g. free above X KWD) — not set here since no threshold amount was given; add a second rate tier per zone if wanted (Shopify supports multiple rates per zone, e.g. "under 20 KWD: 1.5 KWD" / "20 KWD+: free").
- **Delivery time estimate shown at checkout** (e.g. "1–2 business days") — cosmetic but affects conversion; not specified yet.
- **Per-driver dispatch/routing** — since fulfillment is local drivers rather than a courier API/app, there's no automatic tracking-number sync like `docs/dispatch/courier-matrix.md`'s courier-API rows describe. Orders will need a manual "assign to driver" step (a person, or a simple spreadsheet/WhatsApp coordination) until/unless a local-delivery management tool gets added later — this is an operational process decision, not a code gap.
- **COD (cash on delivery)** — common for GCC local-driver delivery; if wanted, enable under Settings → Payments → Manual payment methods → Cash on Delivery, separate from the MyFatoorah gateway setup in `docs/payments-setup.md`.

## Cross-references updated alongside this doc

- `docs/dispatch/courier-matrix.md` — placeholder Aramex/iMile shortlist replaced with the real local-driver model and these two zones/rates.
- `docs/setup-checklist.md` — shipping/courier line marked resolved with the real decision.
