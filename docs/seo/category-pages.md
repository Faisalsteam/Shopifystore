# Category / Collection Pages (Real Catalog Structure)

New this batch. This is the actual list of category/collection pages the 2,855-item catalog can support today, built from the real concentration split, gender labeling, and top-brand frequency in `keyword-strategy.md` — not a generic taxonomy. Meta titles/descriptions below follow the templates in `content-templates.md` exactly (`{اسم المتجر}` / `{Store Name}` placeholders stay unfilled until Amal locks the brand name — see `docs/setup-checklist.md`). This is meant to be handed straight to whoever builds the actual Shopify collections (manual or smart collections keyed off the parsed concentration/brand/gender metafields from `docs/catalog-import.md`).

**Caveats that apply to every table below:**
- Meta descriptions use only generic, category-level claims ("authentic," "wide selection," "fast GCC delivery") — never a specific scent/ingredient claim, per the no-fabrication principle in `docs/catalog-import.md`.
- Arabic brand names use common/standard transliterations for now — they have **not** been checked against the catalog's own Arabic-draft dictionary (`docs/catalog-import.md`), so before publishing, reconcile these against that dictionary so on-site brand naming is consistent everywhere rather than reinvented per page.
- Counts are catalog-frequency (how many SKUs), same caveat as `keyword-strategy.md`: not sales data.

## 1. By concentration

| Page | Catalog count | Suggested slug | Meta title (AR) | Meta title (EN) | Meta description (AR) | Meta description (EN) |
|---|---|---|---|---|---|---|
| Eau de Parfum | 1,694 | `/collections/eau-de-parfum` | عطور أو دو بارفان EDP \| {اسم المتجر} | Eau de Parfum (EDP) Perfumes \| {Store Name} | تسوقي عطور أو دو بارفان الأصلية بثبات أطول على البشرة. تشكيلة واسعة من أفضل الماركات، توصيل سريع لدول الخليج. اطلبي الآن. | Shop genuine Eau de Parfum (EDP) fragrances with longer-lasting wear. Wide selection from top brands, fast GCC delivery. Order now. |
| Eau de Toilette | 625 | `/collections/eau-de-toilette` | عطور أو دو تواليت EDT \| {اسم المتجر} | Eau de Toilette (EDT) Perfumes \| {Store Name} | تسوقي عطور أو دو تواليت الأصلية، خفيفة ومثالية للاستخدام اليومي. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop genuine Eau de Toilette (EDT) fragrances — light and ideal for everyday wear. Wide selection, fast GCC delivery. Order now. |
| Parfum / Extrait de Parfum | 182 | `/collections/parfum-extrait` | عطور Parfum / Extrait مركزة \| {اسم المتجر} | Parfum / Extrait de Parfum \| {Store Name} | تسوقي عطور Parfum وExtrait الأصلية بأعلى تركيز وأطول ثبات. تشكيلة مختارة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop genuine Parfum / Extrait de Parfum — the highest concentration, the longest wear. Curated selection, fast GCC delivery. Order now. |
| Eau de Cologne | 25 | `/collections/eau-de-cologne` | عطور أو دو كولون EDC \| {اسم المتجر} | Eau de Cologne (EDC) \| {Store Name} | تسوقي عطور أو دو كولون الأصلية، منعشة وخفيفة. توصيل سريع لدول الخليج. اطلبي الآن. | Shop genuine Eau de Cologne (EDC) — fresh and light. Fast GCC delivery. Order now. |
| Perfume Oils / Attar | 12 | `/collections/oil-attar` | عطور زيتية ودهن عود (Attar) \| {اسم المتجر} | Perfume Oils / Attar \| {Store Name} | تسوقي العطور الزيتية الأصلية الخالية من الكحول. تشكيلة مختارة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop genuine alcohol-free perfume oils / attar. Curated selection, fast GCC delivery. Order now. |

EDC and Oil/Attar are small (25 and 12 items) but still worth a standalone page each — EDC rounds out the concentration set cleanly, and attar search intent (alcohol-free, Gulf-specific) is distinct enough from EDP/EDT that folding it into a bigger page would bury it. Build EDP and EDT first; these two can follow.

**Not built as a page:** Gift sets (6 items) — too small a slice to justify a dedicated collection/keyword push this round, per `keyword-strategy.md`. Revisit if that count grows.

## 2. By gender (labeled subset only)

Covers only the ~1,177 items with a gender token in the source name (Unisex 500 + Men 365 + Women 312). The ~1,678 unlabeled items (59% of the catalog) are **not** represented in any of these three pages — see the open item below and in `keyword-strategy.md`. Do not route unlabeled items into one of these three by guessing.

| Page | Catalog count | Suggested slug | Meta title (AR) | Meta title (EN) | Meta description (AR) | Meta description (EN) |
|---|---|---|---|---|---|---|
| Women's Perfume | 312 | `/collections/womens-perfume` | عطور نسائية أصلية \| {اسم المتجر} | Women's Perfume \| {Store Name} | تسوقي عطورًا نسائية أصلية 100% من أفضل الماركات العالمية. توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine women's perfume from top global brands. Fast GCC delivery. Order now. |
| Men's Perfume | 365 | `/collections/mens-perfume` | عطور رجالية أصلية \| {اسم المتجر} | Men's Perfume \| {Store Name} | تسوق عطورًا رجالية أصلية 100% من أفضل الماركات العالمية. توصيل سريع لدول الخليج. اطلب الآن. | Shop 100% genuine men's perfume from top global brands. Fast GCC delivery. Order now. |
| Unisex Perfume | 500 | `/collections/unisex-perfume` | عطور للجنسين أصلية \| {اسم المتجر} | Unisex Perfume \| {Store Name} | تسوقي عطورًا للجنسين أصلية 100% تناسب الجميع. توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine unisex perfume, made for everyone. Fast GCC delivery. Order now. |

## 3. By brand — top 20 by catalog frequency

**Catalog-frequency proxy, not sales data** (same caveat as `keyword-strategy.md`). These 20 are the brands with enough SKUs in the catalog to justify a standalone page; below Givenchy-level frequency, fold the brand into the relevant concentration/gender page instead of giving it its own collection yet.

| Brand | Catalog count | Suggested slug | Meta title (AR) | Meta title (EN) | Meta description (AR) | Meta description (EN) |
|---|---|---|---|---|---|---|
| Chanel | 99 | `/collections/chanel` | عطور شانيل الأصلية \| {اسم المتجر} | Chanel Perfume \| {Store Name} | تسوقي عطور شانيل الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Chanel perfume. Wide selection, fast GCC delivery. Order now. |
| Marco Valentino | 94 | `/collections/marco-valentino` | عطور ماركو فالنتينو الأصلية \| {اسم المتجر} | Marco Valentino Perfume \| {Store Name} | تسوقي عطور ماركو فالنتينو الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Marco Valentino perfume. Wide selection, fast GCC delivery. Order now. |
| Dynamique | 63 | `/collections/dynamique` | عطور ديناميك الأصلية \| {اسم المتجر} | Dynamique Perfume \| {Store Name} | تسوقي عطور ديناميك الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Dynamique perfume. Wide selection, fast GCC delivery. Order now. |
| Mancera | 53 | `/collections/mancera` | عطور مانسيرا الأصلية \| {اسم المتجر} | Mancera Perfume \| {Store Name} | تسوقي عطور مانسيرا الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Mancera perfume. Wide selection, fast GCC delivery. Order now. |
| Tom Ford | 50 | `/collections/tom-ford` | عطور توم فورد الأصلية \| {اسم المتجر} | Tom Ford Perfume \| {Store Name} | تسوقي عطور توم فورد الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Tom Ford perfume. Wide selection, fast GCC delivery. Order now. |
| YSL | 41 | `/collections/ysl` | عطور YSL (إيف سان لوران) الأصلية \| {اسم المتجر} | YSL Perfume \| {Store Name} | تسوقي عطور YSL الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine YSL perfume. Wide selection, fast GCC delivery. Order now. |
| Ajmal | 35 | `/collections/ajmal` | عطور عجمل الأصلية \| {اسم المتجر} | Ajmal Perfume \| {Store Name} | تسوقي عطور عجمل الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Ajmal perfume. Wide selection, fast GCC delivery. Order now. |
| Rasasi | 35 | `/collections/rasasi` | عطور رصاصي الأصلية \| {اسم المتجر} | Rasasi Perfume \| {Store Name} | تسوقي عطور رصاصي الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Rasasi perfume. Wide selection, fast GCC delivery. Order now. |
| Bvlgari | 33 | `/collections/bvlgari` | عطور بولغاري الأصلية \| {اسم المتجر} | Bvlgari Perfume \| {Store Name} | تسوقي عطور بولغاري الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Bvlgari perfume. Wide selection, fast GCC delivery. Order now. |
| Guess | 33 | `/collections/guess` | عطور غيس الأصلية \| {اسم المتجر} | Guess Perfume \| {Store Name} | تسوقي عطور غيس الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Guess perfume. Wide selection, fast GCC delivery. Order now. |
| Dior | 30 | `/collections/dior` | عطور ديور الأصلية \| {اسم المتجر} | Dior Perfume \| {Store Name} | تسوقي عطور ديور الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Dior perfume. Wide selection, fast GCC delivery. Order now. |
| Xerjoff | 28 | `/collections/xerjoff` | عطور زيرجوف الأصلية \| {اسم المتجر} | Xerjoff Perfume \| {Store Name} | تسوقي عطور زيرجوف الأصلية 100%. تشكيلة مختارة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Xerjoff perfume. Curated selection, fast GCC delivery. Order now. |
| Giorgio Armani | 26 | `/collections/giorgio-armani` | عطور جورجيو أرماني الأصلية \| {اسم المتجر} | Giorgio Armani Perfume \| {Store Name} | تسوقي عطور جورجيو أرماني الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Giorgio Armani perfume. Wide selection, fast GCC delivery. Order now. |
| Byredo | 26 | `/collections/byredo` | عطور بايردو الأصلية \| {اسم المتجر} | Byredo Perfume \| {Store Name} | تسوقي عطور بايردو الأصلية 100%. تشكيلة مختارة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Byredo perfume. Curated selection, fast GCC delivery. Order now. |
| Gucci | 26 | `/collections/gucci` | عطور غوتشي الأصلية \| {اسم المتجر} | Gucci Perfume \| {Store Name} | تسوقي عطور غوتشي الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Gucci perfume. Wide selection, fast GCC delivery. Order now. |
| Hermès | 26 | `/collections/hermes` | عطور هيرمس الأصلية \| {اسم المتجر} | Hermès Perfume \| {Store Name} | تسوقي عطور هيرمس الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Hermès perfume. Wide selection, fast GCC delivery. Order now. |
| Versace | 25 | `/collections/versace` | عطور فيرساتشي الأصلية \| {اسم المتجر} | Versace Perfume \| {Store Name} | تسوقي عطور فيرساتشي الأصلية 100%. تشكيلة واسعة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Versace perfume. Wide selection, fast GCC delivery. Order now. |
| Guerlain | 24 | `/collections/guerlain` | عطور غيرلان الأصلية \| {اسم المتجر} | Guerlain Perfume \| {Store Name} | تسوقي عطور غيرلان الأصلية 100%. تشكيلة مختارة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Guerlain perfume. Curated selection, fast GCC delivery. Order now. |
| Creed | 22 | `/collections/creed` | عطور كريد الأصلية \| {اسم المتجر} | Creed Perfume \| {Store Name} | تسوقي عطور كريد الأصلية 100%. تشكيلة مختارة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Creed perfume. Curated selection, fast GCC delivery. Order now. |
| Givenchy | 20 | `/collections/givenchy` | عطور جيفنشي الأصلية \| {اسم المتجر} | Givenchy Perfume \| {Store Name} | تسوقي عطور جيفنشي الأصلية 100%. تشكيلة مختارة، توصيل سريع لدول الخليج. اطلبي الآن. | Shop 100% genuine Givenchy perfume. Curated selection, fast GCC delivery. Order now. |

**Just below the cutoff, worth flagging for a possible next-tier page:** Amouage (15), Lattafa (13), Khadlaj (8) — smaller than the 20 above but still real, recognizable brands; fold into concentration/gender pages for now, revisit as standalone pages once the top 20 are live and if catalog counts grow.

## 4. Open items carried forward

- **Gender-labeling gap:** ~1,678 catalog items (59%) have no gender token — the three gender pages above only reach ~1,177 items. This is the highest-priority open item for the next batch; see `keyword-strategy.md`.
- **Brand-frequency ≠ sales:** the brand list above ranks catalog breadth, not what actually sells or converts best — useful for deciding what pages are *buildable*, not for prioritizing marketing spend.
- **Arabic brand transliterations** used above are standard/common renderings, not yet checked against the catalog's own Arabic-draft dictionary (`docs/catalog-import.md`) — reconcile before publishing so brand naming is consistent between product pages and category pages.
- **Scent-family/attribute collections** (e.g. "woody," "oud," "fresh") aren't listed here at all — the catalog parse has no scent-note data, so there's nothing real to build such a page from yet, consistent with the no-fabrication principle throughout this batch.
