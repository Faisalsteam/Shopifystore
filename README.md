# GCC Perfumes & Cosmetics — Shopify Store

A Shopify build for a perfumes & cosmetics launch across the GCC (Arabic-first, English secondary).

## Roles

| Who | Role | Does | Doesn't |
|---|---|---|---|
| **Amal** | Product owner / moderator | Defines requirements, tests every build on staging, approves before it goes live, runs day-to-day store content | Write code |
| **Claude** | Developer | Builds/edits theme, custom apps, and automations; pushes to GitHub; documents everything | Make business or budget calls |
| **Faisal** | Financial owner | Budget, supplier payments, margins, P&L, ROI, settlement reconciliation | Touch code or moderation |

## How a build task flows

1. Requirement described in plain language
2. Claude builds it on a dev/staging branch
3. Amal tests on the staging store
4. Amal approves
5. Merge to `main`, deploy live

Every change is documented so nothing is locked to one person.

## Where things are

- [`docs/roadmap.md`](docs/roadmap.md) — full phased build plan, timeline, and complexity levels
- [`docs/setup-checklist.md`](docs/setup-checklist.md) — accounts, approvals, and decisions needed, by owner
- [`docs/integrations.md`](docs/integrations.md) — every third-party integration, what it needs, and its status
- [`docs/architecture.md`](docs/architecture.md) — planned repo structure and tech stack
- [`theme/`](theme/) — the Shopify theme (Online Store 2.0), scaffolded and waiting on brand assets
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — branching, workflow, and commit conventions

## Status

**Phase 0 — Setup & Foundation.** Repo scaffolding is in place. Blocked on brand kit (name, logo, colors) and Shopify store access before real theme work can start. See `docs/setup-checklist.md` for the live blocker list.
