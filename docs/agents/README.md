# Agents

Five AI-managed roles that keep the build and the future store moving between check-ins with Amal and Faisal — extending the "AI-driven operations model" confirmed in `docs/roadmap.md`. They're documented here the same way the human roles are documented in the main [`README.md`](../../README.md#roles--working-model): what each owns, what it doesn't, and what it's blocked on right now.

| Agent | Owns | Full charter |
|---|---|---|
| **Designer** | Layout, UX, design system, section specs | [`designer.md`](designer.md) |
| **Chatbot / Call Center** | WhatsApp + FAQ customer support flows | [`chatbot-callcenter.md`](chatbot-callcenter.md) |
| **Dispatcher** | Fulfillment, courier selection, delivery exceptions | [`dispatcher.md`](dispatcher.md) |
| **Marketing Agency** | Campaigns, Klaviyo flows, social, competitive alerts | [`marketing.md`](marketing.md) |
| **SEO Content Writer (AR/EN)** | Product/blog copy, meta tags, keyword strategy | [`seo-content.md`](seo-content.md) |

## The one rule that doesn't change

**Nothing an agent produces goes live without Amal's approval.** This was already decided in the roadmap's AI-driven operations model and it applies to every agent above: they draft, Amal moderates and approves, then it publishes or sends. An agent finding no live Shopify/Klaviyo/WhatsApp/courier connection yet is not a bug — it's Phase 0, and is exactly why each charter below has a "blocked on" section instead of live integration code.

## How they operate day to day

- Each agent's real output is files in this repo (`docs/design/`, `docs/support/`, `docs/dispatch/`, `docs/marketing/`, `docs/seo/`) — templates, flows, briefs, drafts — reviewable in a PR like any other change, per [`CONTRIBUTING.md`](../../CONTRIBUTING.md).
- An agent that's blocked on an account/credential doesn't stall — it keeps preparing the thing that will be wired in the moment that account exists (see each charter's "Unlocks at" row), and flags what it needs in `docs/setup-checklist.md`.
- A scheduled session (see below) checks in on this backlog regularly so work continues even when nobody is actively driving Claude — same "developer" role from the main README, just running unattended, with the same requirement that nothing publishes without Amal.

## Autonomous scheduling

A weekly Routine ("Store Agents Weekly Sync") runs against this repo, works through whichever agent lanes aren't blocked, commits, and pushes to a review branch — it never pushes to `main` and never opens or merges a PR on its own. Ask to have it paused, retimed, or reviewed at any point; see the trigger by name if you want to inspect or change its schedule.

## Current phase snapshot

All five agents are in **Phase 0 mode**: producing specs, templates, and drafts that don't require a live account, ready to wire in the moment `docs/setup-checklist.md` items clear. See each charter for its specific blockers.
