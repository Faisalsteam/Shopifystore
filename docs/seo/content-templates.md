# Content Templates (Arabic / English)

Reusable structures for meta tags and product descriptions. Placeholder tone until `docs/design/brief-template.md` comes back with the real brand voice.

## Meta title template

- AR: `{اسم المنتج} | {الفئة} | {اسم المتجر}` — target ≤ 60 characters (Arabic characters render narrower than Latin, but keep the limit as a ceiling).
- EN: `{Product Name} | {Category} | {Store Name}` — target ≤ 60 characters.

## Meta description template

- AR: `تسوقي {اسم المنتج} — {ميزة رئيسية 1}، {ميزة رئيسية 2}. توصيل سريع لدول الخليج. اطلبي الآن.` — target ≤ 155 characters.
- EN: `Shop {Product Name} — {key feature 1}, {key feature 2}. Fast GCC delivery. Order now.` — target ≤ 155 characters.

## Product description template

Structure (matches the PDP wireframe in `docs/design/wireframes.md`):

1. **One-line hook** — the single most compelling thing about the product (not generic — specific to this SKU).
2. **2–3 sentence description** — what it is, who it's for, the experience/benefit (not just a spec list).
3. **Bullet list of key attributes** — size/volume, scent family or key notes, ideal occasion.
4. **SEO paragraph** (short, natural — not keyword-stuffed) — works the primary keyword from `keyword-strategy.md` in naturally.
5. **Care/usage note** if relevant (e.g. how to apply, storage).

## Worked examples — real catalog SKUs

The abstract skeleton below has been replaced with three real worked examples, pulled directly from the supplier catalog (`docs/catalog-import.md`) rather than an invented product. **Every field used is one of the five parsed, factual fields only: brand, product line name, concentration, size, gender (where labeled).** Per the catalog's own safety principle — never fabricate scent notes, ingredients, or specific product claims not backed by actual data — anywhere the template calls for scent family/key notes or a specific occasion claim and no real data exists for it, the bullet is either flagged `[needs input from category team — not in supplier data]` or the gap is stated plainly (see Example 3). Storage/care notes below are generic fragrance-care facts (avoid heat/direct sun), not claims about any specific product, matching the general concentration facts already used in `sample-blog-en.md`/`sample-blog-ar.md`.

Three examples, mixing concentration and brand tier: two EDP, one EDT; one item has no gender label in the source data, which is used deliberately to show how the template handles a real gap rather than papering over it.

---

### Example 1 — Chanel Coco (EDP, Women)

**Source row:** barcode `3145891135305` — `CHANEL COCO-EDP-100ML-W` (Chanel: top brand by catalog frequency, 99 items)

**Meta title AR:** `كوكو شانيل EDP ١٠٠مل | عطور نسائية | {اسم المتجر}`
**Meta title EN:** `Chanel Coco EDP 100ml | Women's Perfume | {Store Name}`

**Meta description AR:** `تسوقي كوكو شانيل، عطر نسائي أو دو بارفان أصلي ١٠٠ مل. ضمان الأصالة 100%، توصيل سريع لدول الخليج. اطلبي الآن.`
**Meta description EN:** `Shop Chanel Coco, a genuine women's Eau de Parfum, 100ml. 100% authenticity guarantee, fast GCC delivery. Order now.`

**Product description (AR):**

> كوكو من شانيل — عطر نسائي أو دو بارفان أصلي بحجم ١٠٠ مل.
> كوكو هو عطر نسائي من دار شانيل الفرنسية، بتركيز أو دو بارفان (EDP)، المعروف عمومًا بثباته الأطول على البشرة مقارنة بتركيزات العطور الأخف مثل EDT. يأتي في عبوة ١٠٠ مل، وهو خيار مناسب لمن تبحث عن منتج أصلي 100% من ماركة عالمية معروفة.
> - الحجم: ١٠٠ مل
> - التركيز: أو دو بارفان (EDP)
> - الفئة: نسائي
> - العائلة العطرية: [يحتاج مدخلات من فريق التصنيف — غير متوفرة في بيانات المورد]
> - مناسب لـ: [يحتاج مدخلات من فريق التصنيف — غير متوفرة في بيانات المورد]
>
> إذا كنتِ تبحثين عن عطر نسائي أو دو بارفان أصلي بثبات أطول، فإن كوكو من شانيل خيار من ماركة معروفة عالميًا، متوفر بحجم ١٠٠ مل مع ضمان الأصالة 100%.
>
> يُفضّل حفظ العطر بعيدًا عن أشعة الشمس المباشرة والحرارة للحفاظ على ثباته لأطول فترة ممكنة.

**Product description (EN — adaptation, not a literal translation):**

> Chanel Coco — a genuine women's Eau de Parfum, 100ml.
> Coco is a women's fragrance from the French house Chanel, in Eau de Parfum (EDP) concentration — generally known for lasting longer on skin than lighter concentrations like EDT. It comes in a 100ml bottle, and it's a solid pick for anyone looking for a 100% authentic product from a globally recognized name.
> - Size: 100ml
> - Concentration: Eau de Parfum (EDP)
> - Category: Women's
> - Scent family: [needs input from category team — not in supplier data]
> - Best for: [needs input from category team — not in supplier data]
>
> Looking for a genuine women's eau de parfum with real staying power? Chanel Coco is a globally recognized name, available in a 100ml bottle with a 100% authenticity guarantee.
>
> Store away from direct sunlight and heat to help the fragrance hold its longevity as long as possible.

---

### Example 2 — Dior Sauvage (EDT, Men)

**Source row:** barcode `3348901250146` — `DIOR SAUVAGE-EDT-100ML-M` (Dior: 30 items in catalog)

**Meta title AR:** `سوفاج ديور EDT ١٠٠مل | عطور رجالية | {اسم المتجر}`
**Meta title EN:** `Dior Sauvage EDT 100ml | Men's Perfume | {Store Name}`

**Meta description AR:** `تسوق سوفاج ديور، عطر رجالي أو دو تواليت أصلي ١٠٠ مل. ضمان الأصالة 100%، توصيل سريع لدول الخليج. اطلب الآن.`
**Meta description EN:** `Shop Dior Sauvage, a genuine men's Eau de Toilette, 100ml. 100% authenticity guarantee, fast GCC delivery. Order now.`

**Product description (AR):**

> سوفاج من ديور — عطر رجالي أو دو تواليت أصلي بحجم ١٠٠ مل.
> سوفاج هو عطر رجالي من دار ديور الفرنسية، بتركيز أو دو تواليت (EDT)، وهو تركيز أخف نسبيًا من EDP ومناسب للاستخدام اليومي المتكرر. يأتي بحجم ١٠٠ مل، بضمان أصالة 100%.
> - الحجم: ١٠٠ مل
> - التركيز: أو دو تواليت (EDT)
> - الفئة: رجالي
> - العائلة العطرية: [يحتاج مدخلات من فريق التصنيف — غير متوفرة في بيانات المورد]
> - مناسب لـ: [يحتاج مدخلات من فريق التصنيف — غير متوفرة في بيانات المورد]
>
> إذا كنت تبحث عن عطر رجالي أو دو تواليت أصلي للاستخدام اليومي، فإن سوفاج من ديور خيار من ماركة عالمية معروفة، بحجم ١٠٠ مل ومع ضمان الأصالة 100%.
>
> يُفضّل حفظ العطر بعيدًا عن أشعة الشمس المباشرة والحرارة للحفاظ على ثباته.

**Product description (EN — adaptation):**

> Dior Sauvage — a genuine men's Eau de Toilette, 100ml.
> Sauvage is a men's fragrance from the French house Dior, in Eau de Toilette (EDT) concentration — a lighter concentration than EDP, well suited to frequent everyday use. It comes in a 100ml bottle, with a 100% authenticity guarantee.
> - Size: 100ml
> - Concentration: Eau de Toilette (EDT)
> - Category: Men's
> - Scent family: [needs input from category team — not in supplier data]
> - Best for: [needs input from category team — not in supplier data]
>
> Looking for a genuine men's eau de toilette for everyday wear? Dior Sauvage is a globally recognized name, available in a 100ml bottle with a 100% authenticity guarantee.
>
> Store away from direct sunlight and heat to help the fragrance hold its longevity.

---

### Example 3 — Ajmal Wisal (EDP, gender not labeled in source data)

**Source row:** barcode `6293708002092` — `AJMAL WISAL EDP-50ML` (Ajmal: 35 items in catalog; this specific row carries no gender token, unlike Examples 1–2)

Deliberately chosen to show the template applied to one of the 367 catalog rows (12.9% — a real but modest slice, not the ~59% first reported; see the correction note in `keyword-strategy.md`) with no gender indicator. The description states the gap plainly instead of guessing a gender to sound complete.

**Meta title AR:** `وصال عجمل EDP ٥٠مل | عطور | {اسم المتجر}`
**Meta title EN:** `Ajmal Wisal EDP 50ml | Perfume | {Store Name}`

**Meta description AR:** `تسوق وصال عجمل، عطر أو دو بارفان أصلي ٥٠ مل. ضمان الأصالة 100%، توصيل سريع لدول الخليج. اطلب الآن.`
**Meta description EN:** `Shop Ajmal Wisal, a genuine Eau de Parfum, 50ml. 100% authenticity guarantee, fast GCC delivery. Order now.`

**Product description (AR):**

> وصال من عجمل — عطر أو دو بارفان أصلي بحجم ٥٠ مل.
> وصال هو عطر من دار عجمل الإماراتية، بتركيز أو دو بارفان (EDP). يأتي بحجم ٥٠ مل، بضمان أصالة 100%. لم يُحدَّد تصنيف الفئة (رجالي/نسائي/للجنسين) في بيانات المورد لهذا المنتج — سيُراجَع لاحقًا مع فريق التصنيف بدلًا من افتراضه.
> - الحجم: ٥٠ مل
> - التركيز: أو دو بارفان (EDP)
> - الفئة: غير محددة في بيانات المورد — بانتظار مراجعة يدوية
> - العائلة العطرية: [يحتاج مدخلات من فريق التصنيف — غير متوفرة في بيانات المورد]
> - مناسب لـ: [يحتاج مدخلات من فريق التصنيف — غير متوفرة في بيانات المورد]
>
> تبحث عن عطر أو دو بارفان أصلي من ماركة معروفة؟ وصال من عجمل متوفر بحجم ٥٠ مل وبضمان الأصالة 100%.
>
> يُفضّل حفظ العطر بعيدًا عن أشعة الشمس المباشرة والحرارة للحفاظ على ثباته.

**Product description (EN — adaptation):**

> Ajmal Wisal — a genuine Eau de Parfum, 50ml.
> Wisal is a fragrance from the UAE-based house Ajmal, in Eau de Parfum (EDP) concentration. It comes in a 50ml bottle, with a 100% authenticity guarantee. Gender category (men's/women's/unisex) isn't specified in the supplier data for this item — flagged for a manual review with the catalog team rather than guessed here.
> - Size: 50ml
> - Concentration: Eau de Parfum (EDP)
> - Category: not specified in supplier data — pending manual review
> - Scent family: [needs input from category team — not in supplier data]
> - Best for: [needs input from category team — not in supplier data]
>
> Looking for a genuine eau de parfum from a well-known Arabian perfume house? Ajmal Wisal comes in a 50ml bottle with a 100% authenticity guarantee.
>
> Store away from direct sunlight and heat to help the fragrance hold its longevity.

---

## Image alt text template

`{Product Name} — {key attribute, e.g. scent/size} — {Store Name}` — one per image, describing what's actually shown (front view, cap off, in-hand scale, etc.), not copy-pasted identically across a product's whole gallery (matches `docs/design/wireframes.md` asset conventions).

**Worked example** (Example 1 above, front-view image): `Chanel Coco EDP 100ml — front view — {Store Name}`. A second image of the same product (e.g. box + bottle) would get its own distinct alt text, not a copy of this one — per the "not copy-pasted identically" rule above.

## On-page SEO checklist (per product/collection page)

- [ ] One H1 per page, contains the primary keyword naturally
- [ ] Meta title/description filled per templates above
- [ ] Image alt text unique per image
- [ ] Internal links to 1–2 related products/collections
- [ ] URL slug is short, keyword-relevant, no stop-word clutter
- [ ] Content reviewed for natural language — no keyword stuffing

---

**Status:** templates unchanged (they held up fine); the three abstract example skeletons have been replaced with real worked examples grounded in actual catalog SKUs. Still placeholder: brand voice/tone (blocked on `docs/design/brief-template.md`), and scent-family/key-notes content everywhere, which needs real sourced data before it can be written at all — see `docs/catalog-import.md`'s no-fabrication principle. Next batch: apply this same worked-example pattern across a full brand/concentration batch once Amal signs off on this first pass, and revisit the gender-category bullet once the 367 unlabeled items (12.9% — see corrected numbers in `keyword-strategy.md`) get a manual pass.
