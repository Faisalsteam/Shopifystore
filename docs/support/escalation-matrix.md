# Escalation Matrix — Bot vs. Human

Defines exactly when the WhatsApp bot answers automatically and when it hands off, so support never gets stuck in a loop or over-automates something sensitive.

| Intent | Bot handles automatically | Hands off to human when |
|---|---|---|
| Order status lookup | Yes, if order found | Order not found after one retry; customer disputes the status shown |
| Shipping/delivery time (general) | Yes | Customer reports a delivery that's overdue past the estimate |
| Returns/exchange — policy question | Yes | Customer wants to actually initiate a return/refund (payment action) |
| Product/scent/sizing guidance | Yes | Customer asks something the FAQ/catalog doesn't cover |
| Promo code validity | Yes | Code shows expired/invalid and customer pushes back |
| Complaint about product quality/damage | No — always hands off | Immediately, first message |
| Payment failure / double charge | No — always hands off | Immediately, first message |
| Anything mentioning a refund, chargeback, or legal language | No — always hands off | Immediately, first message |
| Wholesale/bulk/partnership inquiry | No — always hands off | Immediately, routes to Faisal/Amal per topic |
| Message in a language other than AR/EN, or unclear intent after 2 exchanges | No — hands off | After 2 failed clarification attempts |

## Handoff mechanics (once BSP is connected)

1. Bot sends the handoff phrase from `whatsapp-flows.md` §7.
2. Conversation is tagged/flagged in the BSP inbox (Zoko/WATI) for a human agent.
3. Human agent gets full conversation history — no re-asking the customer to repeat themselves.
4. Response SLA target: business hours same-day; define the exact number once support staffing is decided (owner: Amal).

## Working escalation today (Phase 0, no BSP yet)

There is no live bot — this matrix is the design spec. Until WhatsApp Business API + a BSP account exist (`docs/setup-checklist.md`), all customer contact is manual and this file just keeps the rules ready to implement on day one.
