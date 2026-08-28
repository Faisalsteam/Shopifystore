# SEO Content Batch v1 — Index

First real pass for the SEO Content Writer agent (`docs/agents/seo-content.md`), now that the master catalog block is cleared (`docs/catalog-import.md` — 2,855-item supplier list parsed into a Matrixify-ready draft). Staged here in the scratchpad for review before this session commits it to `docs/seo/` and adds `docs/seo/category-pages.md`, per the agent's "no live account, drafted for Amal to paste in or approve" scope.

**Correction (2026-08-28):** the concentration, gender, and top-brand counts in this batch were first computed with a parser that undercounted gender labeling badly (missed single-letter `-M`/`-W`/`-U` suffixes) and had a few brand-list errors. All numbers below and throughout `docs/seo/` are now the corrected ones — see the correction note at the top of `keyword-strategy.md` for the full explanation. The gender-labeling finding in particular flips from "59% unlabeled, the biggest gap" to "87.1% labeled, a minor 12.9% gap" — good news, not a blocker.

## What's in this batch

| File | Replaces / adds | Status |
|---|---|---|
| `keyword-strategy.md` | Upgrades `docs/seo/keyword-strategy.md` | Real: concentration split, top-brand frequency, gender-labeling coverage. Same sections as before (Arabic-specific notes, "where this plugs in"), content upgraded in place — not redesigned. |
| `content-templates.md` | Upgrades `docs/seo/content-templates.md` | Templates unchanged (still good). The abstract AR/EN example skeleton is replaced with 3 real worked examples (Chanel Coco EDP, Dior Sauvage EDT, Ajmal Wisal EDP/no gender label) built only from the five parsed factual fields — brand, product line, concentration, size, gender. |
| `category-pages.md` | New — no prior version in `docs/seo/` | Real. The actual list of category/collection pages the catalog can support: 5 concentration pages, 3 gender pages (labeled subset only), 20 brand pages, plus what's deliberately excluded (gift sets) and not yet buildable (scent-family collections). Meant to go straight to whoever builds the Shopify collections. |
| `README.md` | This file | — |

## What's real vs. still placeholder/templated

**Real, grounded in the actual catalog this batch:**
- Concentration split (EDP 58.4% / EDT 21.1% / Parfum-Extrait 6.2% / EDC / EDF / Oil-Attar / 13.0% not parseable) and the category structure built from it
- Gender-label coverage (Women 973 / Men 782 / Unisex 732 / Kids 1 / 367 unlabeled — 87.1% labeled overall) and the resulting page scope
- Top-brand frequency list (20 brands) and per-brand page list
- 3 fully worked product-description examples on real SKUs/barcodes, AR + EN

**Still placeholder or explicitly flagged, not papered over:**
- Brand voice/tone — still generic, blocked on the Designer agent's brief (`docs/design/brief-template.md`) per the agent's charter; unchanged this batch.
- Scent family / key notes — not in the supplier parse at all (`docs/catalog-import.md`). Every template bullet that would need this is either omitted or marked `[needs input from category team — not in supplier data]`, never invented. This applies to all three worked examples and will apply to every future SKU description until real scent data exists.
- "Ideal occasion" bullets — same treatment as scent notes; not a parsed field, not guessed.
- Arabic brand-name transliterations in `category-pages.md` are standard/common renderings, not yet checked against the catalog's own Arabic-draft dictionary — needs reconciliation before publishing.
- Gender for the Ajmal Wisal example (and 366 other catalog rows) is stated as unlabeled rather than assumed — see the corrected gender numbers below.

## Remaining open items (corrected — much smaller than first reported)

367 items (12.9%) have no gender token in the source item name, and separately, 372 items (13.0%) have no concentration keyword in the name either. Both are real, modest gaps — not the "~59% unlabeled, biggest gap in the structure" first reported (that was a parser bug; see the correction note above). "Men's/Women's/Unisex" and concentration category pages can now be built against 87%+ of the catalog directly. The remaining unlabeled items are flagged for Amal/the catalog team as a manual-pass item, not something this agent should guess at from brand or product-line name. See `keyword-strategy.md` and `category-pages.md` §2/§4 for the full writeup.

## What the next batch should cover

1. **Once the 367 gender-unlabeled and 372 concentration-unparsed items get a manual pass** (by Amal/catalog team, or a second supplier data source): close the remaining gap so category pages cover 100% of the catalog, not just 87–99%.
2. **Full worked-example pass**: extend the 3-example pattern in `content-templates.md` across a real batch of SKUs — ideally matching the Matrixify import batches described in `docs/roadmap.md` Phase 2 ("publish in batches by product line"), so SEO content lands in the same batches Amal is already reviewing for the catalog import.
3. **Brand-name transliteration reconciliation**: check the Arabic brand names used in `category-pages.md` against the catalog's own Arabic-draft dictionary (`docs/catalog-import.md`) so naming is consistent between product pages and category pages, not reinvented per doc.
4. **Brand voice pass**: once the Designer agent's brief lands, revisit tone across all of `docs/seo/` — this batch is still placeholder tone by design.
5. **Scent-family data**: if/when the catalog gets real scent-note/family data (from the supplier or a manual pass), only then build the scent-family collections flagged as not-yet-buildable in `category-pages.md` §4, and fill in the `[needs input from category team]` bullets in every product description — including the 3 examples in this batch.

## Source data this batch is grounded in

Real 2,855-item supplier catalog stats, using the same parser that builds the actual product data (`docs/catalog-import.md`):
- Concentration: EDP 1,666 (58.4%), EDT 603 (21.1%), not parseable 372 (13.0%), Parfum/Extrait 177 (6.2%), EDC 24 (0.8%), EDF 5 (0.2%), Oil/Attar 8 (0.3%)
- Gender: Women 973 (34.1%), Men 782 (27.4%), Unisex 732 (25.6%), unlabeled 367 (12.9%), Kids 1 (0.0%)
- Top brands by catalog frequency: see `keyword-strategy.md` and `category-pages.md` for the full list (Chanel down to Memo)
- 8 real example SKUs (barcode + catalog name) supplied for grounding; 3 used as full worked examples in `content-templates.md`
