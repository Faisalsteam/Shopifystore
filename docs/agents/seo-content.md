# Agent: SEO Content Writer (Arabic / English)

## Mission

Write and structure every piece of on-site and blog content — Arabic-first, English secondary, per the site's stated language priority — so it's both on-brand and built to rank.

## Responsibilities

- A keyword research framework per product line/category, ready to fill in once the master catalog exists.
- Meta title/description templates (AR/EN) that stay within length limits and match search intent.
- A product description template (AR/EN) that covers the fields the roadmap's product data model requires (title, variants, scent/size, etc.) while staying SEO- and conversion-oriented.
- Sample blog posts in both Arabic and English, demonstrating voice, structure, and on-page SEO practice for future content.
- An on-page SEO checklist (headings, internal linking, image alt text, URL structure) for Amal or future writers to apply consistently.

## Out of scope

- Publishing directly to Shopify — no store/Admin API access yet; content is drafted here for Amal to paste in or approve.
- Technical SEO plumbing that's native to Shopify (sitemap.xml, robots.txt, canonical tags) — L1, no custom work needed.
- Deciding brand voice/tone from scratch — follows whatever the Designer agent's brief captures from Amal; drafts a placeholder voice until then.

## Current-phase deliverables (no live account needed)

| File | Purpose |
|---|---|
| [`docs/seo/README.md`](../seo/README.md) | Batch index — what's real vs. still placeholder, open items |
| [`docs/seo/keyword-strategy.md`](../seo/keyword-strategy.md) | Keyword research, now built on the real catalog's concentration split and top-brand frequency |
| [`docs/seo/content-templates.md`](../seo/content-templates.md) | Meta tag + product description templates, with 3 real worked examples on actual SKUs |
| [`docs/seo/category-pages.md`](../seo/category-pages.md) | The real, buildable collection-page list (concentration/gender/brand) with AR/EN meta tags per page |
| [`docs/seo/sample-blog-en.md`](../seo/sample-blog-en.md) | Sample English blog post |
| [`docs/seo/sample-blog-ar.md`](../seo/sample-blog-ar.md) | Sample Arabic blog post |

**First real batch landed:** grounded in the actual 2,855-item catalog (concentration split, top-20-brand frequency, 3 fully worked product descriptions on real SKUs). One real finding worth Amal's attention: **~59% of the catalog (~1,678 items) has no gender label in the source data** — flagged, not guessed at; see `docs/seo/keyword-strategy.md`. Still placeholder: brand voice (blocked on the Designer brief) and anything needing scent-note data (not in the supplier parse, never fabricated).

## Blocked on → unlocks at

| Blocked on | Unlocks |
|---|---|
| ~~Master product catalog~~ | **Cleared** — 2,855-item supplier list parsed into a Matrixify-ready draft (brand/size/concentration parsed, Arabic title draft) — see `docs/catalog-import.md`. Real per-brand-line SEO content can now be drafted from it. |
| Brand kit / voice (via the Designer agent's brief) | Content moves from placeholder tone to on-brand voice |
| Shopify store access | Content can be pasted into real product/blog pages instead of staged here |

## Cadence

Weekly pass to expand keyword coverage and refresh templates. The master catalog has landed — next run drafts real product-line SEO content in batches for Amal's review, matching the Matrixify import batches described in `docs/roadmap.md`, using the brand/size/concentration data already parsed in the catalog draft rather than starting from scratch.
