# Keyword Strategy Framework (Arabic / English)

Real structure, built from the actual 2,855-item supplier catalog (parsed per `docs/catalog-import.md`) instead of the illustrative placeholder this file used to carry. Arabic-first per the site's language priority — English keywords secondary, not a straight translation (search behavior differs).

**Source note:** all counts and brand rankings below come from *catalog frequency* — how many rows in the supplier price list mention that concentration/brand — not from sales, search volume, or margin data. Treat this as "what the catalog can support a page about," not "what sells best." Real search-volume and sales-weighted keyword prioritization is future work once Shopify/GA access exists.

## Structure per category

For each product category/collection, capture:

| Field | Example (Eau de Parfum category — real, from catalog) |
|---|---|
| Primary keyword (AR) | عطور او دو بارفان |
| Primary keyword (EN) | eau de parfum |
| Secondary/long-tail (AR) | عطر او دو بارفان نسائي فخم |
| Secondary/long-tail (EN) | long-lasting eau de parfum for women |
| Search intent | Transactional (ready to buy) vs. informational (EDP vs. EDT difference) |
| Local modifiers | + country/city name where relevant (e.g. "عطور دبي", "perfume shop UAE") |

| Field | Example (brand page — Tom Ford, real, from catalog) |
|---|---|
| Primary keyword (AR) | عطور توم فورد |
| Primary keyword (EN) | Tom Ford perfume |
| Secondary/long-tail (AR) | عطر توم فورد بلاك أورشيد |
| Secondary/long-tail (EN) | Tom Ford Black Orchid EDP |
| Search intent | Mostly transactional — branded searches skew high purchase-intent |
| Local modifiers | "توم فورد الكويت", "Tom Ford perfume UAE" |

## Category structure: build around concentration, not a generic "fragrance" catch-all

The catalog is dominated by two concentrations — EDP and EDT together are 81% of all 2,855 items — so top-level category/keyword architecture should be built around concentration first, with brand and gender as secondary facets, not the other way around.

| Concentration | Count | Share | Keyword priority |
|---|---|---|---|
| Eau de Parfum (EDP) | 1,694 | 59% | **Primary** — biggest single category, should be the default/anchor collection |
| Eau de Toilette (EDT) | 625 | 22% | **Primary** — second anchor collection |
| Parfum / Extrait | 182 | 6% | Secondary — "extrait de parfum" / "او دو extrait" as a distinct, lower-volume but higher-intent (often higher price point) keyword set |
| Eau de Cologne (EDC) | 25 | <1% | Minor — fold into EDT-adjacent content, not a standalone push |
| Oil / Attar | 12 | <1% | Minor — niche/attar-specific searches ("عطر زيتي", "attar") worth a small dedicated set given how distinct the search intent is (alcohol-free, Gulf-specific demand), even though volume is tiny |
| Gift sets | 6 | <1% | **Not worth a dedicated keyword push yet** — too small a slice of the catalog to justify its own category/keyword set this round. Revisit if the catalog's gift-set count grows. |

This replaces the old placeholder's generic "perfume category" framing: don't build one big undifferentiated "fragrance" keyword set — build EDP and EDT as the two primary pillars, with Parfum/Extrait and Oil/Attar as smaller supporting sets.

## Brand-based keyword sets (top brands by catalog frequency)

**Catalog-frequency proxy, not sales data** — this ranks how often a brand name appears in the 2,855-row supplier list, which is a reasonable proxy for what the category pages will actually contain (inventory breadth), but it is *not* a signal of what sells best, what has the highest margin, or what shoppers search for most. Treat it as "these are the brands we can credibly build a full page for," not a sales ranking.

| Brand | Catalog count | Brand | Catalog count |
|---|---|---|---|
| Chanel | 99 | Xerjoff | 28 |
| Marco Valentino | 94 | Giorgio Armani | 26 |
| Dynamique | 63 | Byredo | 26 |
| Mancera | 53 | Gucci | 26 |
| Tom Ford | 50 | Hermès | 26 |
| YSL | 41 | Versace | 25 |
| Ajmal | 35 | Guerlain | 24 |
| Rasasi | 35 | Creed | 22 |
| Bvlgari | 33 | Givenchy | 20 |
| Guess | 33 | Amouage | 15 |
| Dior | 30 | Lattafa | 13 |
| | | Khadlaj | 8 |

Each of these is a candidate for its own brand keyword set (branded primary keyword + top product-line long-tails) — see `category-pages.md` for the actual page list built from this ranking. Brands below Khadlaj-level frequency aren't worth a dedicated keyword set yet; fold them into concentration/gender category pages instead.

## Open item: gender labeling gap (flag for Amal / catalog team, not guessed)

Gender parsed from the raw item name splits as: Unisex 500, Men 365, Women 312 — but **~1,678 items (59% of the catalog) have no gender indicator in the name at all.** This is the single biggest gap in the current keyword/category structure:

- Men's and Women's category pages can only be built reliably from the ~1,177 labeled items right now — building "best men's cologne" style keyword sets against the full catalog would overstate what's actually taggable today.
- This is **not something to guess or infer from brand/product-line name** (e.g. assuming a Chanel line is "women's" because it's a common assumption) — that risks misgendering products and needs a real human/data-driven pass, not an SEO agent's best guess.
- Flagging this explicitly for Amal/the catalog team: the ~1,678 unlabeled items need a manual categorization pass (or a second data source — brand-line gender data from the supplier) before gender-specific keyword sets can cover the full catalog. Until then, gender category pages are scoped to the labeled subset only (see `category-pages.md`).

## Keyword categories to build out per product line

1. **Category/collection keywords** — now concentration-first: "eau de parfum" / "او دو بارفان", "eau de toilette" / "او دو تواليت", rather than a generic "men's cologne" / "عطور رجالية" starting point (those still apply, but as a secondary facet — see gender gap above).
2. **Attribute keywords** — concentration, size/volume, occasion, gift-worthy. Scent family is **not yet usable** as an attribute keyword axis — the catalog parse gives brand/concentration/size/gender only, no scent-note data (see `content-templates.md` for how this constraint plays out in actual descriptions).
3. **Comparison/consideration keywords** — "best X for Y", "افضل عطر ل...", including EDP-vs-EDT informational content (real search demand, and the catalog can actually support product recommendations on both sides).
4. **Brand/authenticity keywords** — "أصلي 100%", "authentic perfume UAE" (ties to the FAQ's authenticity answer). Now paired with the real top-brand list above.
5. **Local/GCC-specific keywords** — country and city modifiers per launch market.

## Arabic-specific notes

- Modern Standard Arabic (MSA) as the baseline, since dialect preference varies by GCC country — confirm with Amal once the launch country is fixed whether local dialect terms should be layered in for search (many GCC shoppers search in a mix of MSA and dialect).
- Check both diacritic-free and common misspelling variants — Arabic search behavior includes more spelling variation than English.
- Right-to-left doesn't affect keyword research itself, only how the content is laid out (`docs/design/wireframes.md`).
- Brand names in Arabic keyword sets should follow the same transliteration used in the catalog's Arabic draft (`docs/catalog-import.md`) rather than a separate ad hoc transliteration, so on-site content and category taxonomy stay consistent with the product data itself.

## Where this plugs in

- Feeds meta title/description templates in `content-templates.md`.
- Feeds the real category/collection page list in `category-pages.md` (new this batch).
- Feeds blog topic selection (`sample-blog-en.md` / `sample-blog-ar.md` show the target structure).
- Category groupings here should match the ones used in `docs/support/whatsapp-flows.md` §4 (scent guidance — fresh & light / warm & sweet / woody & bold). Note: that scent-family taxonomy is a *different axis* from the concentration/brand structure above, and scent family isn't in the parsed catalog data yet — so the WhatsApp flow's scent guidance and this file's category structure are complementary, not yet unified into one taxonomy. Revisit once scent-family data exists.

---

**Status:** first real pass, grounded in the actual 2,855-item catalog (concentration split, top-brand frequency, gender-labeling coverage). Still open: scent-family/note data (not in the supplier parse — see `docs/catalog-import.md`), search-volume/sales-weighted prioritization (needs Shopify/GA access), and the gender-labeling gap above. Next pass covers whatever the manual gender-categorization pass produces.
