# Changelog

Notable changes to this repository. Dates are UTC.

## Unreleased

### Added — 2026-08-22 (parallel workstreams)
- `docs/payment-gateway-comparison.md` — MyFatoorah / Tap Payments / PayTabs / Telr compared across all six GCC countries (coverage, local rails, reported fees, onboarding), with sourcing caveats and a recommendation to request direct rate quotes given the low reliability of third-party GCC payment-gateway pricing blogs.
- `content/legal/` — bilingual (Arabic-first, English-adapted) draft Terms & Conditions, Privacy Policy, and Refund & Shipping Policy, grounded in Kuwait's Consumer Protection Law No. 39/2014. Explicitly flagged as drafts pending review by a licensed Kuwait/GCC lawyer; a newer "Decree 10/2026" claim found during research was deliberately excluded as unconfirmed (single, non-authoritative source) — see `content/legal/README.md`.
- `docs/catalog-import.md` — methodology for turning the raw 2,855-item supplier price list into a Matrixify-ready product catalog: deterministic parsing (brand/size/concentration/gender) plus a best-effort Arabic title draft, with every low-confidence row flagged for review rather than guessed silently. The generated workbook (English import sheet, Arabic draft sheet, review-flags sheet) was delivered directly — per the roadmap, the master catalog lives in Amal's Google Sheet, not this repo.
- Updated `docs/setup-checklist.md`, `docs/integrations.md`, and root `README.md` to reflect all three as delivered-but-needing-human-review, not finished.

### Fixed — 2026-08-22 (correction)
- Moved the theme from a `theme/` subfolder to the **repo root** (`layout/`, `templates/`, `sections/`, `snippets/`, `assets/`, `config/`, `locales/`, `vendor/`, plus `THEME.md` replacing `theme/README.md`). Shopify's "Connect from GitHub" dialog has no subfolder option — it only reads the theme from the root of the selected branch, which is why the first connection attempt showed no theme at all. Updated all docs (`docs/deployment.md`, `docs/architecture.md`, `docs/setup-checklist.md`, `docs/integrations.md`, root `README.md`) and the Theme Check CI workflow to match.

### Confirmed — 2026-08-22 (later still)
- Store `9gucqc-qy.myshopify.com` connected to `theme/` via Shopify's GitHub integration — preview theme opens correctly. Deployment pipeline (repo → store) is now live end to end.

### Added — 2026-08-22 (later)
- `docs/deployment.md` — documents that Claude's development session cannot reach `*.myshopify.com` (network policy), so `theme/` deploys via Shopify's native GitHub integration (store pulls from this repo) instead of a Shopify CLI push. Includes setup steps and branch mapping.
- Received the store domain (`9gucqc-qy.myshopify.com`) and a Theme Access password; recorded in `docs/setup-checklist.md` and `docs/integrations.md`. The password isn't used by this deployment method — kept for any future local/CLI use, revocable from the store admin at any time.
- Updated `theme/README.md`, `CONTRIBUTING.md`, and root `README.md` to point at the GitHub-integration deployment flow.

### Added — 2026-08-22
- Vendored [Shopify Dawn](https://github.com/Shopify/dawn) `v16.0.0` into `theme/` as the real base theme (replaces the empty directory scaffold). License and release notes kept in `theme/vendor/`.
- Wired `layout/theme.liquid` to set `dir="rtl"`/`dir="ltr"` automatically based on the active storefront language, so the layout is RTL-ready at the document level as soon as Arabic is added as a shop language.
- Confirmed launch scope: **all GCC markets** (not a single country) — updated `docs/roadmap.md`, `docs/integrations.md`, and `docs/setup-checklist.md` to reflect that the payment gateway and courier choice now need full-GCC coverage, not single-country.

### Added — 2026-08-22 (earlier)
- Initial repository foundation: README, `CONTRIBUTING.md`, `LICENSE`.
- `docs/roadmap.md` — full phased build plan transcribed from the roadmap document (phases, timeline, complexity levels, open decisions).
- `docs/setup-checklist.md` — live, owner-tagged blocker checklist.
- `docs/integrations.md` — third-party integration tracker (purpose, requirements, status).
- `docs/architecture.md` — planned tech stack and repo layout.
- `theme/` — Shopify Online Store 2.0 directory scaffold, awaiting brand kit and store access.
- `.env.example` — documents required integration credentials without real values.
- `.github/` — pull request template, build-task issue template, Theme Check CI workflow.

### Added — 2026-08-22 (2)
- `docs/agents/` — charters for 5 AI agent roles (Designer, Chatbot/Call Center, Dispatcher, Marketing Agency, SEO Content Writer AR/EN): mission, scope, current-phase deliverables, blockers, and operating cadence.
- `docs/design/` — brand kit brief template and brand-agnostic section wireframes (homepage, PDP, collection, cart drawer), RTL-annotated.
- `docs/support/` — bilingual (AR/EN) WhatsApp conversation flows, FAQ, and a bot-vs-human escalation matrix.
- `docs/dispatch/` — fulfillment SOP and courier selection/exception-handling matrix.
- `docs/marketing/` — content calendar template and Klaviyo lifecycle flow specs (welcome, abandoned cart, post-purchase, win-back, promo).
- `docs/seo/` — bilingual keyword strategy framework, content templates (meta tags, product descriptions), and sample blog posts in Arabic and English.
- `README.md`, `docs/architecture.md`, `docs/setup-checklist.md` updated to reference the new agent roles and their output locations.
