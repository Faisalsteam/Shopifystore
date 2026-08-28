# Courier Selection Matrix & Exception Playbook

## Courier selection matrix

**Confirmed (2026-08-28):** fulfillment is via **local drivers**, not a third-party courier account (Aramex/iMile shortlist below is dropped — not the chosen model). Rates confirmed by Faisal: see `docs/shipping-setup.md` for the exact Shopify Admin setup steps.

| Zone | Fulfillment | Rate | Target SLA | Notes |
|---|---|---|---|---|
| Kuwait | Local drivers | 1.5 KWD | TBD — set once real delivery patterns are observed | Primary market |
| Rest of GCC (Saudi, UAE, Qatar, Bahrain, Oman) | Local drivers | 5.5 KWD | TBD | Single combined zone for now — split per-country later if SLA/reliability differs enough to justify it |

Because this is local drivers rather than a courier API/app, there's no automatic tracking-number sync (no Aramex/iMile-style webhook) — order-to-driver assignment and delivery-status updates are a manual/operational process until a local-delivery management tool is added, if ever needed. See `docs/shipping-setup.md` for what that means day-to-day.

~~Candidates per the roadmap: Aramex, iMile, or a local GCC courier~~ — resolved: local drivers chosen. Selection criteria below kept for reference in case a third-party courier gets added later (e.g. for zones local drivers can't reach):
- Coverage of the launch country/zone
- Cost per shipment at expected order volume
- Native Shopify app / API quality (affects how much custom integration work is needed — see `docs/integrations.md`)
- COD (cash on delivery) support, if needed for the launch market
- Average delivery SLA and track record for the product category (fragile/cosmetics)

## Exception playbook

| Exception | Immediate system action | Customer message | Resolution owner |
|---|---|---|---|
| Failed delivery attempt | Order flagged, courier's next-attempt date pulled in | "We attempted delivery — here's the next attempt date, or reply to reschedule" | Dispatcher agent drafts message; human confirms reschedule if needed |
| Incomplete/wrong address | Order paused, customer prompted for correction | "We need to confirm your delivery address — please reply with the full address" | Customer support (bot intent → human if unresolved after 1 retry) |
| Damaged item reported | Always hands off — see `docs/support/escalation-matrix.md` | Empathetic acknowledgment + hands to human | Human agent, replacement/refund decision |
| Delayed beyond SLA | Proactive customer update before they ask | "Your order is running behind schedule — new estimate: {{date}}" | Dispatcher agent triggers proactive check per courier status |
| Return-to-sender | Order flagged for restock or reship decision | "Your order is being returned to us — we'll reach out to arrange redelivery or refund" | Human agent |

## Status-sync mapping (spec, not yet wired)

**Note:** this table assumes an automated courier status feed. With local drivers (confirmed model above), these transitions are triggered manually by whoever manages dispatch (Amal/ops), not by a webhook — the target Shopify order status and customer message per step are still the right spec to follow by hand.

| Courier status | Shopify order status | Customer notification |
|---|---|---|
| Label created | Fulfilled | Tracking link sent |
| Out for delivery | Fulfilled (in transit) | "Out for delivery today" |
| Delivered | Delivered | Rating-request flow triggers (`docs/marketing/klaviyo-flows.md`) |
| Failed attempt | Fulfilled (exception) | Failed-attempt message above |
| Returned to sender | Cancelled/refund pending | Return-to-sender message above |

This mapping becomes real webhook/Shopify Flow code (living in `apps/` once it exists — `docs/architecture.md`) once a courier account and API credentials exist.
