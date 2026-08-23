# Courier Selection Matrix & Exception Playbook

## Courier selection matrix

Placeholder structure — fill in once the launch country(ies) and courier shortlist are confirmed (`docs/setup-checklist.md`, owner: Faisal).

| Zone/Country | Primary courier | Backup courier | Target SLA | Cost tier | Notes |
|---|---|---|---|---|---|
| {{country_1}} | {{TBD}} | {{TBD}} | {{TBD}} | {{TBD}} | |
| {{country_2}} | {{TBD}} | {{TBD}} | {{TBD}} | {{TBD}} | |

Candidates per the roadmap: **Aramex, iMile, or a local GCC courier**. Selection criteria once the shortlist is real:
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

| Courier status | Shopify order status | Customer notification |
|---|---|---|
| Label created | Fulfilled | Tracking link sent |
| Out for delivery | Fulfilled (in transit) | "Out for delivery today" |
| Delivered | Delivered | Rating-request flow triggers (`docs/marketing/klaviyo-flows.md`) |
| Failed attempt | Fulfilled (exception) | Failed-attempt message above |
| Returned to sender | Cancelled/refund pending | Return-to-sender message above |

This mapping becomes real webhook/Shopify Flow code (living in `apps/` once it exists — `docs/architecture.md`) once a courier account and API credentials exist.
