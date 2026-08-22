# Shopify Build Plan — Roadmap

Source: *GCC Perfumes & Cosmetics — Shopify Build Plan* (roadmap PDF, folded-in review included). Kept in-repo so it's version-controlled and not locked in a slide deck.

## Complexity levels used throughout

| Level | Meaning | Typical time | Examples |
|---|---|---|---|
| **L1** — Native / config | Built into Shopify or a paid app — just needs setup | Days | Staff permissions, collections, loyalty app, courier tracking sync |
| **L2** — App + integration work | A third-party app plus custom configuration or connecting glue | 1–3 weeks | Bulk upload via Matrixify, payment gateway, Klaviyo automation, CRM setup |
| **L3** — Custom build | No off-the-shelf tool does this exactly — real custom code, hosted and maintained | 3–6+ weeks | WhatsApp checkout flow, custom delivery/tracking app, voice & photo search |

## The full customer journey

`Browse → Cart → Checkout → Payment confirmed → Fulfillment → Delivery → Rating → Retention (CRM)`

Every phase below exists to make one of these eight steps work reliably.

## Phases

### Phase 0–1 · Weeks 1–3 · Setup & Foundation
- Accounts: Shopify, GitHub org, Meta Business Manager, GCC payment gateway merchant account, domain, Google Cloud project (Maps API)
- **Start WhatsApp Business API approval and payment gateway merchant approval immediately** — both have real lead times and are the most common real-world delay, not the coding
- Financial plan (Faisal): startup budget, monthly run-rate, margin targets by product line
- Brand name, color palette, logo finalized — **blocks the store build**
- Product data model defined; packaging/sticker supplier sourced with sample costing

### Phase 2 · Weeks 3–7 · Store Build & Bulk Upload
Product data fields: Title, SKU, barcode, product type/vendor/tags, variants (size/volume × scent), price/compare-at/cost, inventory qty/weight, images (2000px+, `sku-1.jpg` naming), SEO title/description.

Bulk upload process: master catalog in Google Sheets (Amal's, not GitHub) → Matrixify app for variants/metafields/repeat updates (native CSV import only for simple catalogs) → export → import to staging/unpublished → Amal spot-checks on storefront preview → publish in batches by product line → same sheet reused for ongoing price/stock updates.

**RTL is a theme requirement, not a checkbox.** Site is Arabic-first — pick an RTL-ready theme from day one and test every custom element (cart drawer, WhatsApp widget, reviews, checkout) in RTL.

### Phase 3 · Weeks 4–6 (parallel) · Payments & GCC Localization
- Shopify Payments has limited/no GCC coverage — a regional gateway is the realistic path
- Options with native Shopify apps + local rails (KNET, mada, etc.): **MyFatoorah, Tap Payments, PayTabs, Telr**
- Choice depends on which GCC country(ies) launch first
- Integration itself is fast — **merchant KYC approval is the slow part**, apply in Phase 0
- Payment-confirmed → order-status-updated handled natively via gateway webhook, no custom code needed
- Card data stays out of PCI scope by using the gateway's hosted checkout, not a custom payment form

### Phase 4 · Weeks 6–9 · CRM & Marketing Automation
- Email/marketing CRM: **Klaviyo** (standard, deeply Shopify-integrated)
- WhatsApp: WhatsApp Business API (via Meta) + a BSP app (**Zoko** or **WATI**) for automated templated messages
- "WhatsApp checkout" realistically = a checkout link sent in-chat, not native in-app payment
- Klaviyo + WhatsApp on the same trigger: Shopify Flow for simple rules, custom webhook code for anything more
- Support/sub-admin CRM: **Zoho CRM** (affordable, GCC presence) or **HubSpot** (pricier at scale)
- Voice/photo search: genuinely L3 and low-value on a small launch catalog — **defer to post-launch**

#### What Klaviyo actually does
- **Capture** — every browse/cart/purchase event synced from Shopify automatically, profile builds itself
- **Segment** — recent buyers, trend-followers, high spenders, lapsed customers; updates live
- **Trigger & send** — abandoned cart, post-purchase, win-back, promo/trend alerts; can fan out to WhatsApp via Flow/webhook
- **Report** — revenue per email/flow, open/click rates, feeds Phase 6 loss-of-sale reporting

It automates the sending once a rule is approved — it doesn't replace Amal's judgment on what to send.

### AI-driven operations model (confirmed)
- **Category team**: only manual data feed — specs, factory photos, pricing input
- **Amal**: moderates — approves AI-drafted content, social posts, campaign sends *before* anything goes live
- **AI-managed**: product/marketing copy, social post creation + scheduling, competitive price/stock monitoring + alerts, CRM segmentation/triggers, marketing optimization (subject lines, send-time, targeting)
- Recommend Amal's approval sits **before** publish, not after, for at least the first few months, then loosen once trusted

### Additional scope (folded in from latest review)

| Item | What's realistic | Level |
|---|---|---|
| RTL (Arabic site) | Theme + every custom element tested RTL, not assumed | L2 |
| Content automation | AI drafts copy from product sheet; Amal reviews before publish | L2 |
| Social media (create + post) | AI generates, scheduler (Buffer/Later) publishes on approval — no full hands-off pre-launch | L2/L3 |
| Competitive analysis + alerts | Monitoring tool (e.g. Prisync); scraping outside these tools raises ToS/legal risk | L2 |
| CRM functionality | Segmentation, triggers, WhatsApp sync via Klaviyo + Flow | L1/L2 |
| Mobile app | Shopify-to-app converter (Magenative, Shopney) wraps existing storefront, not from-scratch | L2 |

### Phase 5 · Weeks 7–10 · Delivery & Fulfillment
- Launch on a third-party courier integration (Aramex, iMile, or local GCC courier) — labels, tracking, status sync
- Fully custom in-house delivery app (own drivers, live Maps tracking) is a real software build, **not launch-week** — sequence it later once volume justifies it
- Delivery rating via a post-delivery Klaviyo email flow at launch, not a custom widget
- Loyalty points via an existing app (Smile.io or Loyalty Lion), not built from scratch

### Phase 6 · Week 8+ (ongoing) · Reporting, Finance & BI
- Daily/monthly/yearly financial closing — Faisal's process, supported by Shopify + gateway settlement reports
- P&L/projections in a spreadsheet model fed by Shopify + gateway exports
- Loss-of-sale/diagnostic reporting: Shopify natively tracks abandoned checkouts + OOS views; fuller report combines with Klaviyo via Looker Studio
- No custom BI dashboard until volume makes spreadsheets a real bottleneck

### Phase 7–8 · Weeks 9–12 · Security, QA & Launch
- Every custom (L3) piece goes through code review before touching the live store, especially payments/customer data
- Documentation: every custom piece gets a README so the business isn't dependent on one person
- Security pass: staff permission audit, API key rotation, webhook signature verification, PCI scope check
- Soft launch first (friends/family or small ad budget) to catch real issues at low stakes
- Full launch once a soft-launch order cleanly completes the entire journey end to end

## Timeline summary

| Phase | Weeks | Depends on |
|---|---|---|
| 0. Accounts & access | 1 | — |
| 1. Foundation | 1–3 | — |
| 2. Store build & bulk upload | 3–7 | Brand kit, cost sheet |
| 3. Payments / localization | 4–6 (parallel) | Merchant approval |
| 4. CRM & marketing automation | 6–9 | Store build, WhatsApp approval |
| 5. Delivery & fulfillment | 7–10 | Store build |
| 6. Reporting & BI | 8+ (ongoing) | Payments & CRM data flowing |
| 7. Security & QA | 9–11 | All custom code complete |
| 8. Launch | ~12 | All above |
| 9. Post-launch | ongoing | Launch |

**~3 months to a real launch** is realistic if Phase 0 approvals start immediately and the brand/financial foundation closes fast.

## Website content, legal & brand (beyond theme/name/policies)

- **Legal & policy pages** (blocks payment gateway approval): Terms & Conditions, Privacy Policy, Refund/Shipping Policy, FAQ, trade license/commercial registration
- **Bilingual content (AR/EN)**, written Arabic-first and adapted to English — About Us, policies, FAQ, homepage copy, product usage/ingredients copy, brand tone-of-voice guide
- **Contact, trust & housekeeping**: contact page (support email, WhatsApp, response-time), social handles secured, business email (info@/support@) once domain is live, favicon + SEO metadata

## Open decisions (before work starts)

1. **Which GCC country(ies) launch first** — determines payment gateway and courier partner
2. **Klaviyo + Zoko/WATI vs. alternatives** — confirm budget tolerance, both usage-based
3. **Brand name and colors** — currently blocking the store build phase
4. **Initial + monthly budget envelope** — so tool choices are picked against real numbers

## Immediate action items

**Amal:** Theme, store name, domain, logo — blocks Phase 1–2.
**Faisal:** Payment companies (shortlist), shipping companies (shortlist), taxes, packaging — feeds Phase 0 merchant/courier setup and Phase 3 localization.

Starting bills already on the table: Domain ~$20/yr, Shopify ~$1 (trial/starter rate) — placeholder figures, confirm actual plan tier and renewal pricing before budgeting on these.
