# Contributing / Workflow

This repo follows the flow defined in the roadmap (`docs/roadmap.md`):

1. **Requirement** described in plain language (an issue, using `.github/ISSUE_TEMPLATE/build-task.md`)
2. **Claude builds it** on a dev/feature branch
3. **Amal tests** on the staging store
4. **Amal approves**
5. **Merge to `main`**, deploy live

Theme changes reach the store via Shopify's GitHub integration (the store pulls from this repo — see `docs/deployment.md` for setup and branch mapping), not a manual push.

## Branching

- `main` — live/production. Only merged into after Amal's approval.
- `claude/<short-description>` — active development branches.
- Never push directly to `main`.

## Commits

- Clear, descriptive messages — what changed and why, not just what file.
- Each custom (L3) piece gets its own README documenting what it does and how to maintain it (per Phase 7–8 in the roadmap) — the goal is that the business isn't dependent on one person.

## Before merging anything touching payments, customer data, or a custom (L3) build

- Code review required.
- Confirm it's been tested on staging by Amal.
- Confirm no secrets are committed (see `.env.example` / `docs/integrations.md`).

## RTL

The site is Arabic-first. Any change touching the storefront (theme, cart drawer, checkout customization, WhatsApp widget, reviews) must be tested in RTL before it's considered done — not assumed to work because the base theme supports RTL.
