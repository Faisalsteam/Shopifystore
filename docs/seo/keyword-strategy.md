# Keyword Strategy Framework (Arabic / English)

Real structure, built from the actual 2,855-item supplier catalog (parsed per `docs/catalog-import.md`) instead of the illustrative placeholder this file used to carry. Arabic-first per the site's language priority — English keywords secondary, not a straight translation (search behavior differs).

**Source note:** all counts and brand rankings below come from *catalog frequency* — how many rows in the supplier price list mention that concentration/brand — not from sales, search volume, or margin data. Treat this as "what the catalog can support a page about," not "what sells best." Real search-volume and sales-weighted keyword prioritization is future work once Shopify/GA access exists.

**Correction (2026-08-28):** the first pass of this file undercounted gender labeling significantly — it only matched full words (`MEN`/`WOMEN`/`UNISEX`), missing the single-letter suffixes (`-M`, `-W`, `-U`) this catalog actually uses most (e.g. `...-100ML-W`). The real parser used to build the actual product data (`docs/catalog-import.md`) catches both, and the true numbers are much better than first reported — corrected throughout this file and `category-pages.md`.

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

The catalog is dominated by two concentrations — EDP and EDT together are ~79.5% of all 2,855 items — so top-level category/keyword architecture should be built around concentration first, with brand and gender as secondary facets, not the other way around.

| Concentration | Count | Share | Keyword priority |
|---|---|---|---|
| Eau de Parfum (EDP) | 1,666 | 58.4% | **Primary** — biggest single category, should be the default/anchor collection |
| Eau de Toilette (EDT) | 603 | 21.1% | **Primary** — second anchor collection |
| **Not parseable from the item name** | **372** | **13.0%** | **Flag for the catalog team** — no concentration keyword in the raw name at all (not the same as the gender gap below). Can't build a reliable EDP/EDT keyword set for this slice yet; needs either a supplier data field or a manual pass. |
| Parfum / Extrait | 177 | 6.2% | Secondary — "extrait de parfum" / "او دو extrait" as a distinct, lower-volume but higher-intent (often higher price point) keyword set |
| Eau de Cologne (EDC) | 24 | 0.8% | Minor — fold into EDT-adjacent content, not a standalone push |
| Eau Fraiche (EDF) | 5 | 0.2% | Minor — small enough to fold into EDT-adjacent content too |
| Oil / Attar | 8 | 0.3% | Minor — niche/attar-specific searches ("عطر زيتي", "attar") worth a small dedicated set given how distinct the search intent is (alcohol-free, Gulf-specific demand), even though volume is tiny |

This replaces the old placeholder's generic "perfume category" framing: don't build one big undifferentiated "fragrance" keyword set — build EDP and EDT as the two primary pillars, with Parfum/Extrait and Oil/Attar as smaller supporting sets. (The first pass of this table also listed a "Gift sets" row — that was never actually a category the parser produces; dropped, since it wasn't real data.)

## Brand-based keyword sets (top brands by catalog frequency)

**Catalog-frequency proxy, not sales data** — this ranks how often a brand name appears in the 2,855-row supplier list, which is a reasonable proxy for what the category pages will actually contain (inventory breadth), but it is *not* a signal of what sells best, what has the highest margin, or what shoppers search for most. Treat it as "these are the brands we can credibly build a full page for," not a sales ranking.

| Brand | Catalog count | Brand | Catalog count |
|---|---|---|---|
| Chanel | 99 | Bvlgari | 33 |
| Marco Valentino | 93 | Guess | 33 |
| Dynamique | 63 | Xerjoff | 32 |
| Mancera | 53 | Dior | 30 |
| Tom Ford | 50 | French Avenue | 29 |
| YSL | 41 | Byredo | 26 |
| Ajmal | 35 | Dolce & Gabbana | 26 |
| Rasasi | 35 | Gucci | 26 |
| Allman | 34 | Hermès | 26 |
| | | Versace | 26 |
| | | Memo | 25 |

(Corrected list — the first pass missed Allman, French Avenue, Dolce & Gabbana, and Memo entirely, and wrongly included Giorgio Armani, Guerlain, Creed, Givenchy, Amouage, Lattafa, and Khadlaj, none of which actually make the top 20 by catalog count. Just below the cutoff, tied at 24: Guerlain and Zeon.)

Each of these is a candidate for its own brand keyword set (branded primary keyword + top product-line long-tails) — see `category-pages.md` for the actual page list built from this ranking. Brands below Memo-level frequency (25) aren't worth a dedicated keyword set yet; fold them into concentration/gender category pages instead.

## Gender labeling: corrected — coverage is good, not a major gap

The first pass of this file reported gender labeling as the single biggest gap in the catalog (claimed ~59% unlabeled). That was a parsing bug, not a real finding — see the correction note at the top of this file. The actual split, using the same parser that builds the real product data:

| Gender | Count | Share |
|---|---|---|
| Women | 973 | 34.1% |
| Men | 782 | 27.4% |
| Unisex | 732 | 25.6% |
| **Not labeled in the name** | **367** | **12.9%** |
| Kids | 1 | 0.0% |

**87.1% of the catalog is gender-labeled** — plenty to build Men's/Women's/Unisex category and keyword sets against the full catalog with confidence, not just a labeled subset.

- The remaining 367 items (12.9%) with no gender token in the name are a real, smaller gap — flag them for Amal/the catalog team as before: **not something to guess or infer from brand/product-line name** (e.g. assuming a Chanel line is "women's" because it's a common assumption). A manual pass or a supplier data field is the right fix, not an SEO agent's best guess.
- Gender-specific category pages (see `category-pages.md`) can now be built against the labeled 87.1% directly, with the unlabeled 12.9% called out as "brand/concentration pages only, no gender facet yet" rather than excluded from gender pages entirely.

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
