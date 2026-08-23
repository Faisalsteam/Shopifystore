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

**AR example skeleton:**

> {هوك بجملة واحدة}. {وصف من 2-3 جمل عن المنتج ولمن يناسب}.
> - الحجم: {الحجم}
> - العائلة العطرية: {العائلة}
> - مناسب لـ: {المناسبة}
>
> {فقرة قصيرة تدمج الكلمة المفتاحية الأساسية بشكل طبيعي}.

**EN example skeleton:**

> {One-line hook}. {2–3 sentence description of what it is and who it's for}.
> - Size: {size}
> - Scent family: {family}
> - Best for: {occasion}
>
> {Short paragraph naturally working in the primary keyword}.

## Image alt text template

`{Product Name} — {key attribute, e.g. scent/size} — {Store Name}` — one per image, describing what's actually shown (front view, cap off, in-hand scale, etc.), not copy-pasted identically across a product's whole gallery (matches `docs/design/wireframes.md` asset conventions).

## On-page SEO checklist (per product/collection page)

- [ ] One H1 per page, contains the primary keyword naturally
- [ ] Meta title/description filled per templates above
- [ ] Image alt text unique per image
- [ ] Internal links to 1–2 related products/collections
- [ ] URL slug is short, keyword-relevant, no stop-word clutter
- [ ] Content reviewed for natural language — no keyword stuffing

---

**Status:** templates only, placeholder tone. Real per-SKU content starts once the master catalog exists (`docs/agents/seo-content.md`).
