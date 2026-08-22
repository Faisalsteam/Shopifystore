# Klaviyo Flow Specs

Specs for the lifecycle flows named in `docs/roadmap.md` Phase 4. These are ready to build as real Klaviyo flows the moment the Klaviyo account exists — right now they're specs for Amal to review.

## 1. Welcome series

- **Trigger:** newsletter/WhatsApp signup (homepage or checkout opt-in).
- **Email 1** (immediate): welcome + brand intro + first-order incentive if approved.
- **Email 2** (+2 days): best sellers / how to choose a scent (ties to `docs/support/whatsapp-flows.md` §4 logic, same guidance both places).
- **Email 3** (+5 days): social proof / trust content (once reviews exist).
- Fan-out: WhatsApp welcome message via Shopify Flow once Zoko/WATI is connected.

## 2. Abandoned cart

- **Trigger:** cart created, checkout not completed within 1 hour.
- **Email 1** (+1 hr): reminder, shows cart contents.
- **Email 2** (+24 hr): reminder + urgency (stock/limited-time) if genuinely true — no fake urgency.
- **Email 3** (+72 hr): final nudge, incentive only if approved by Amal/Faisal (margin impact).
- Fan-out: WhatsApp cart-reminder message, same timing logic, via Flow/webhook.

## 3. Post-purchase

- **Trigger:** order confirmed (payment webhook, per `docs/dispatch/fulfillment-sop.md`).
- **Email 1** (immediate): order confirmation + what happens next.
- **Email 2** (on "Delivered" status): delivery-rating request (this is the "Rating" step of the customer journey — a Klaviyo flow, not a custom widget, per roadmap).
- **Email 3** (+14 days): usage tips / replenishment nudge if the product category supports it (e.g. perfume longevity tips).

## 4. Win-back

- **Trigger:** no purchase in {{X days — to be set once real purchase-frequency data exists}}.
- **Email 1:** "we miss you" + best sellers since their last visit.
- **Email 2** (+7 days): incentive, if approved — margin-sensitive, needs Faisal's sign-off on discount depth.

## 5. Promo / trend alert

- **Trigger:** manual campaign send (ties to `docs/marketing/content-calendar.md`) or a competitive-price alert from Prisync once connected.
- Not automated end-to-end — Amal reviews and triggers each send, per the confirmed operations model (AI drafts, doesn't auto-send).

## Segmentation reference (for when Klaviyo is connected)

- Recent buyers (last 30/60/90 days)
- High spenders (top X% by lifetime value)
- Lapsed customers (feeds win-back flow above)
- Category/scent-family affinity (feeds targeted promo content)

---

**Status:** all five flows are specs only — no Klaviyo account exists yet (`docs/setup-checklist.md`). Building them for real is a Klaviyo-editor task once the account and API key land; this file is what gets translated into that editor.
