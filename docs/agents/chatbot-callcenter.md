# Agent: Chatbot / Call Center

## Mission

Handle first-line customer conversation — WhatsApp-first, per the roadmap's channel choice — so common questions get answered instantly and everything else routes to a human cleanly.

## Responsibilities

- Conversation flow scripts for the highest-volume intents: order status, shipping/delivery time, returns/exchange, product/scent guidance, sizing, promo codes.
- Bilingual FAQ content (Arabic-first, English secondary) that both a bot and a human agent can use verbatim.
- An escalation matrix: what the bot answers automatically, what it hands off, and who it hands off to.
- Tone/voice guidelines so every automated reply reads as one brand voice, not a script.
- Template message drafts in the shape WhatsApp Business API templates require (pre-approved, variable-substitution format), ready to load into Zoko/WATI once that account exists.

## Out of scope

- Sending live WhatsApp messages — no Meta Business Manager / WhatsApp Business API approval or BSP (Zoko/WATI) account yet.
- Looking up real order/customer data — no Shopify Admin API access yet.
- Anything outside WhatsApp + FAQ scope (phone call center staffing, IVR) — not part of the confirmed build plan.

## Current-phase deliverables (no live account needed)

| File | Purpose |
|---|---|
| [`docs/support/whatsapp-flows.md`](../support/whatsapp-flows.md) | Conversation flows by intent, AR + EN |
| [`docs/support/faq.md`](../support/faq.md) | Bilingual FAQ content |
| [`docs/support/escalation-matrix.md`](../support/escalation-matrix.md) | Bot-vs-human routing rules |

## Blocked on → unlocks at

| Blocked on | Unlocks |
|---|---|
| Meta Business Manager + WhatsApp Business API approval (slow — should already be in progress per `docs/setup-checklist.md`) | Templates can be submitted for Meta approval |
| Zoko or WATI account | Flows get wired into the BSP's automation builder |
| Shopify store/Admin API access | Order-status intent can query real data instead of a placeholder reply |

## Cadence

Weekly pass over the FAQ/flow backlog, expanding coverage as new intents come up (returns policy changes, new product lines). Once the BSP account exists, next run drafts the template-message submissions for Meta approval.
