# Integrations

Every third-party system this build touches: what it's for, what it needs from us, and current status. Update the Status column as things move — this is the live tracker, not the roadmap doc.

| Integration | Purpose | Level | What it needs from us | Status |
|---|---|---|---|---|
| **Shopify** | Storefront, catalog, checkout | L1 | Store URL + Admin API token or theme access | Not connected |
| **Theme** (RTL-ready, e.g. an Online Store 2.0 theme) | Storefront presentation | L1/L2 | Brand kit (name, logo, colors) | Blocked on brand kit |
| **Matrixify** | Bulk product upload, variants, metafields | L2 | Shopify app install; master catalog in Google Sheets (Amal's) | Not started |
| **Payment gateway** — MyFatoorah / Tap Payments / PayTabs / Telr (pick one based on launch country) | Checkout payment, local rails (KNET, mada, etc.) | L2 | Country decision, merchant KYC approval (slow — start early), API credentials post-approval | Not started |
| **WhatsApp Business API** (via Meta) + BSP (**Zoko** or **WATI**) | Automated templated messages, checkout links in-chat | L2/L3 | Meta Business Manager, WhatsApp Business API approval (slow — start early), BSP account | Not started |
| **Klaviyo** | Email CRM: capture, segment, trigger/send, report | L1/L2 | Account + API key | Not started |
| **Shopify Flow** | Wiring simple triggers (e.g. Klaviyo → WhatsApp) | L1 | Native to Shopify, no separate account | N/A until store exists |
| **Courier** — Aramex / iMile / local GCC courier | Labels, tracking, delivery status sync | L1/L2 | Courier account, API credentials | Not started |
| **Zoho CRM** or **HubSpot** | Support/sub-admin CRM | L1 | Account | Not decided |
| **Prisync** (or similar) | Competitive price/stock monitoring + alerts | L2 | Account; do not scrape outside sanctioned tools (ToS/legal risk) | Not started |
| **Buffer / Later** | Social media scheduling, AI drafts + human approval to publish | L2 | Account, social handles secured | Not started |
| **Smile.io** or **Loyalty Lion** | Loyalty points | L1 | Shopify app install | Deferred to Phase 5 |
| **Magenative** or **Shopney** | Wraps existing storefront into a mobile app | L2 | Account, once storefront is stable | Deferred |
| **Google Maps API** | Delivery tracking (future in-house delivery app) | L3 (deferred) | Google Cloud project + API key | Deferred — not a launch requirement |
| **Looker Studio** | Combines Shopify + Klaviyo data for loss-of-sale/BI reporting | L1/L2 | Account, data source connections | Deferred to Phase 6 |

## How credentials are handled

- **Never commit real API keys, tokens, or secrets to this repo.**
- `.env.example` in the repo root lists every environment variable a custom app/integration needs, with no real values.
- Real values live in Shopify's app/env config (for Shopify-hosted code) or in whatever secrets manager the hosting platform provides for any standalone custom app (Phase 4/5 L3 pieces).
- Rotate keys as part of the Phase 7 security pass before launch.

## Decisions still open (blocks locking these in)

1. Launch country(ies) → payment gateway + courier
2. Klaviyo + Zoko/WATI budget tolerance (both usage-based)
3. Brand name/colors → theme selection
