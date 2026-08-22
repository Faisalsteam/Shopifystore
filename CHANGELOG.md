# Changelog

Notable changes to this repository. Dates are UTC.

## Unreleased

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
