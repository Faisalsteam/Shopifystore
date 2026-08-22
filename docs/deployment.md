# Deployment

How `theme/` gets from this repository onto the actual Shopify store.

## Why GitHub → Shopify, not Shopify CLI push

Claude's development environment runs in a network-restricted session and cannot reach `*.myshopify.com` directly — Shopify CLI / Admin API calls from that environment are blocked at the network policy level. Rather than working around that, we use Shopify's own **GitHub integration**, which works in the opposite direction: the Shopify store pulls from GitHub, GitHub isn't pulled from by Shopify's servers reaching out to us. This needs no API token on Claude's side at all, and it fits the existing review workflow (`CONTRIBUTING.md`) better than a one-off CLI push would.

If a custom (L3) app ever needs to call the Shopify Admin API directly (e.g. a webhook relay — see `docs/architecture.md`), that code runs on its own hosting, not from this development session, so it isn't affected by this restriction.

## One-time setup (Amal or Faisal, in the Shopify admin)

1. **Online Store → Themes → Add theme → Connect from GitHub**
2. Authorize Shopify's GitHub connection if prompted, and select the **`Faisalsteam/Shopifystore`** repository
3. Pick the branch to connect (see *Branch mapping* below)
4. When asked for a theme directory/subfolder, enter **`theme`** — the theme files live there, not the repo root
5. Shopify creates a new **unpublished** theme tied to that branch. Every push to that branch updates it automatically. Nothing goes live until someone publishes it from the admin.

## Branch mapping

| Branch | Connected theme | Purpose |
|---|---|---|
| `claude/shopify-integration-setup-6psb0x` (current work branch) | Preview theme | What exists right now, for early look/feedback before a formal staging branch exists |
| `main` (after this work is reviewed and merged) | Staging → Live | Per `CONTRIBUTING.md`: Amal tests the connected theme, approves, then it's published as the live theme |

As the project matures past this initial setup, we may split `main` into a dedicated `staging` branch (its own connected preview theme) and keep `main` reserved for what's actually published — worth revisiting once there's a real cadence of changes to review.

## What this means day to day

- Claude pushes theme changes to the connected branch, same as any other commit in this repo.
- Amal previews the connected (unpublished) theme in the Shopify admin — no separate deploy step.
- Amal approves → the branch merges per `CONTRIBUTING.md` → whoever manages the storefront publishes the corresponding theme from the Shopify admin.
- No Shopify credentials ever need to be shared with or stored by Claude for this flow.

## The Theme Access token

A Theme Access app password was generated earlier for CLI-based access. It isn't usable from this development session (see *Why GitHub → Shopify* above), but it isn't wasted — it's what you'd use to run `shopify theme dev` / `shopify theme push` from any machine with normal internet access (e.g. a contractor's laptop, a CI runner outside this session). Revoke it any time from **Settings → Apps → Theme Access** in the Shopify admin if it's not going to be used that way.
