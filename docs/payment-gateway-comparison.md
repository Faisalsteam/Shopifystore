# Payment Gateway Comparison — All GCC Markets

Researched 2026-08-22 to support the decision in `docs/setup-checklist.md`. **Treat every fee figure here as indicative, not final** — a lot of the sources for GCC payment-gateway pricing are SEO-content blogs of inconsistent quality, not the providers' own pricing pages. Confirm actual rates directly with each provider's sales team before signing anything; rates are usually negotiable by volume anyway.

## Coverage at a glance

| | MyFatoorah | Tap Payments | PayTabs | Telr |
|---|---|---|---|---|
| **Origin / HQ** | Kuwait | Kuwait/Bahrain | Riyadh, Saudi Arabia | Dubai, UAE |
| **GCC countries** | Kuwait, Saudi Arabia, UAE, Bahrain, Qatar, Oman | Kuwait, Saudi Arabia, UAE, Bahrain, Oman, Qatar | UAE, Saudi Arabia, Kuwait, Bahrain, Oman, Qatar | Strongest in UAE/Bahrain; broader GCC support exists but is less consistently documented |
| **Also covers** | Egypt, Jordan | — | Jordan, Egypt, Palestine | 120+ currencies globally |
| **Local rails** | mada, KNET, Benefit, OmanNet, STC Pay, Meeza | mada, KNET, Benefit, QPAY | mada, KNET, SADAD, STC Pay | mada, KNET, STC Pay, Tabby, Tamara |
| **Licensing** | Licensed in every GCC market; regulated by SAMA (Saudi Central Bank) for KSA | Licensed regionally | Licensed | Licensed |
| **Shopify app** | Yes | Yes (native checkout + separate "Checkout Page" app for KNET/Benefit/BNPL) | Yes | Yes, described as straightforward to install |
| **Reported fees** | Not confidently found — get a direct quote | ~2.75% standard cards, ~3.25% international + FX, no monthly fee | ~2.85% + AED 1/transaction, no setup fee | From ~AED 349/month + ~2.49% + AED 1/transaction |
| **Reported onboarding** | Not confidently found | Not confidently found | 3–14 days depending on source (inconsistent) | 3–5 days |
| **Best fit per sources** | Broadest single-provider GCC coverage, Kuwait-native | Competitive fees, strong KNET/mada support | Widest total country count (9, incl. non-GCC) | Best documented for UAE-first, smaller monthly volume |

## Reading this table honestly

- **All four are real, licensed options with GCC-wide Shopify apps** — there's no clearly "wrong" choice here; this is a negotiation and requirements question, not a technical one.
- Given the confirmed launch scope is **all GCC markets** (not one country), coverage breadth and local-rail support (mada for Saudi, KNET for Kuwait, Benefit for Bahrain) matter more than headline fee percentage — a slightly higher rate on a gateway with clean local-rail support across all six countries likely beats a cheaper one that needs a second gateway bolted on for a market it doesn't cover well.
- **Merchant KYC approval time is the real bottleneck** (per `docs/roadmap.md`), not the integration itself — the onboarding-time figures above are the most valuable numbers in this table and the least confidently sourced, so verify them directly.
- None of the fee figures should be used for P&L modeling without a direct quote — see `docs/setup-checklist.md`, this decision belongs to Faisal.

## Suggested next step

Request a written rate card + KYC document checklist from all four in parallel (they're free to ask, no commitment) — that turns four rows of secondhand blog data into four real, comparable quotes. Worth starting now given the KYC lead time the roadmap already flags.

## Sources consulted

- [MyFatoorah](https://www.myfatoorah.com/en/home/), [MyFatoorah FAQs](https://www.myfatoorah.com/en/faqs/)
- [Tap Payments Kuwait](https://www.tap.company/en-kw), [Tap on Shopify App Store](https://apps.shopify.com/tap)
- [PayTabs Shopify plugin support](https://support.paytabs.com/en/support/solutions/articles/60000760093-1-5-shopify-plugin-supported-payment-methods)
- Telr, Tap, PayTabs fee/coverage figures cross-referenced against multiple third-party GCC payment-gateway comparison blogs (2026) — treated as indicative only per the caveat above
