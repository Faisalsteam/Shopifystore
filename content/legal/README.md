# Legal Pages — Status

**DRAFT. Do not publish without a licensed Kuwaiti/GCC lawyer's review.** These are professionally-structured starting drafts, not legal advice, and not a substitute for counsel — see *Legal basis and open questions* below for exactly what still needs verification.

## What's here

Written Arabic-first and adapted to English, per `docs/roadmap.md` — the Arabic version is the source; English is the adaptation, not a machine translation.

| Policy | Arabic | English |
|---|---|---|
| Terms & Conditions | [`ar/terms-and-conditions.md`](ar/terms-and-conditions.md) | [`en/terms-and-conditions.md`](en/terms-and-conditions.md) |
| Privacy Policy | [`ar/privacy-policy.md`](ar/privacy-policy.md) | [`en/privacy-policy.md`](en/privacy-policy.md) |
| Refund & Shipping Policy | [`ar/refund-shipping-policy.md`](ar/refund-shipping-policy.md) | [`en/refund-shipping-policy.md`](en/refund-shipping-policy.md) |

## Legal basis and open questions

Grounded in **Kuwait Law No. 39 of 2014 on Consumer Protection** — well-corroborated (WIPO Lex, ILO NATLEX, FAOLEX, and Kuwaiti press): a 14-day return/exchange/refund right on defective goods, joint vendor/supplier liability, and the National Committee for Consumer Protection (NCCP) as the dispute body. That part of these drafts is solid.

What is **not** solid, and needs a lawyer or direct MOCI confirmation before publishing:

- Kuwait's specific **e-commerce/online-seller licensing** requirement (a valid commercial registration / online store license from the Ministry of Commerce and Industry) is directionally well-supported by multiple sources, but the exact current procedure should be confirmed against MOCI's own guidance, not a blog.
- One search result claimed a specific **"Kuwait Decree 10/2026"** with exact fine amounts (up to 10,000 KWD) and a 5-year data retention mandate. That claim traces back to a single vendor's marketing site selling "compliance automation" — not an official gazette, government portal, or a recognized law firm's briefing. **It is not cited in these drafts** because it couldn't be independently corroborated. If a real 2026 decree updates the e-commerce rules, get the actual text (or a reputable firm's summary — Al Tamimi, PwC Legal, etc.) before relying on it.
- These drafts also don't assume a single launch country — see `docs/setup-checklist.md`: launch scope is all GCC markets, so the final policies likely need a per-country appendix (or separate policy sets) once the payment-gateway/courier coverage decision narrows which countries are actually live at launch.
- Every `[Store Name]` / `[البراند]` placeholder needs the real brand name once Amal finalizes it (see `docs/setup-checklist.md`).

## Publishing

Shopify has dedicated fields for these under **Settings → Policies** (Refund policy, Privacy policy, Terms of service, Shipping policy) — paste the approved English there, and use Shopify's Translate & Adapt app (or Matrixify) to add the Arabic version once RTL/translation is wired up per `docs/roadmap.md` Phase 2. These also block payment gateway merchant approval (per the roadmap) — MOCI/gateway KYC will likely want to see them live.
