# Fulfillment SOP

The path every order takes from payment confirmed to rated, and who/what owns each step. Matches the customer journey in the main `README.md`: `Browse → Cart → Checkout → Payment confirmed → Fulfillment → Delivery → Rating → Retention`.

## 1. Payment confirmed

- Trigger: payment gateway webhook marks order as paid (native, no custom code — `docs/roadmap.md` Phase 3).
- System action: Shopify order status → "Payment confirmed"; Klaviyo/WhatsApp order-confirmation message sent (see `docs/marketing/klaviyo-flows.md`).

## 2. Pick & pack

- Owner: warehouse/ops (outside this repo's scope — physical operation).
- Target: same-day pack for orders placed before a cutoff time (cutoff TBD once launch country/team is set).
- Packaging: per the supplier/costing decision in `docs/setup-checklist.md`.

## 3. Handed to courier

- Courier chosen per `courier-matrix.md`.
- Shopify order status → "Fulfilled"; tracking number attached.
- Customer notified with tracking link (WhatsApp + email, per `docs/marketing/klaviyo-flows.md`).

## 4. In transit

- Courier status updates sync to Shopify order status (native app integration or webhook, depending on courier — see `docs/integrations.md`).
- Customer gets proactive updates only on status *changes* (out for delivery, delayed) — not a notification per tracking ping, to avoid spam.

## 5. Delivered

- Shopify order status → "Delivered".
- Triggers the delivery-rating Klaviyo flow (see `docs/marketing/klaviyo-flows.md`) after a short delay (e.g. same day evening or next day — exact timing decided once real delivery patterns are observed).

## 6. Exceptions

See `courier-matrix.md` for the full exception playbook (failed delivery, address issue, damaged item, return-to-sender). Every exception gets a customer-facing WhatsApp message (drafted from `docs/support/whatsapp-flows.md` patterns) — customers should never have to ask what happened.

## 7. Post-delivery

- Rating/review request (Klaviyo flow, not a custom widget — per roadmap).
- Loyalty points credited, once a loyalty app (Smile.io/Loyalty Lion) is live — Phase 5, deferred.

---

**Status:** this SOP is fully specced but not yet wired to anything live — no courier account, no Shopify store access yet. It's ready to implement the day both exist (`docs/agents/dispatcher.md`).
