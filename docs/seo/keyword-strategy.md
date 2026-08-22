# Keyword Strategy Framework (Arabic / English)

A repeatable framework to fill in once the master product catalog exists (`docs/roadmap.md` Phase 2, owned by Amal, outside this repo). Arabic-first per the site's language priority — English keywords secondary, not a straight translation (search behavior differs).

## Structure per category

For each product category/collection, capture:

| Field | Example (perfume category, illustrative only) |
|---|---|
| Primary keyword (AR) | عطور نسائية فخمة |
| Primary keyword (EN) | luxury women's perfume |
| Secondary/long-tail (AR) | عطر نسائي بريحة الفانيليا |
| Secondary/long-tail (EN) | best long-lasting perfume for women |
| Search intent | Transactional (ready to buy) vs. informational (researching scent families) |
| Local modifiers | + country/city name where relevant (e.g. "عطور دبي", "perfume shop UAE") |

## Keyword categories to build out per product line

1. **Category/collection keywords** — broad (e.g. "men's cologne", "عطور رجالية")
2. **Attribute keywords** — scent family, size/volume, occasion, gift-worthy
3. **Comparison/consideration keywords** — "best X for Y", "افضل عطر ل..."
4. **Brand/authenticity keywords** — "أصلي 100%", "authentic perfume UAE" (ties to the FAQ's authenticity answer)
5. **Local/GCC-specific keywords** — country and city modifiers per launch market

## Arabic-specific notes

- Modern Standard Arabic (MSA) as the baseline, since dialect preference varies by GCC country — confirm with Amal once the launch country is fixed whether local dialect terms should be layered in for search (many GCC shoppers search in a mix of MSA and dialect).
- Check both diacritic-free and common misspelling variants — Arabic search behavior includes more spelling variation than English.
- Right-to-left doesn't affect keyword research itself, only how the content is laid out (`docs/design/wireframes.md`).

## Where this plugs in

- Feeds meta title/description templates in `content-templates.md`.
- Feeds blog topic selection (`sample-blog-en.md` / `sample-blog-ar.md` show the target structure).
- Category groupings here should match the ones used in `docs/support/whatsapp-flows.md` §4 (scent guidance) — same taxonomy everywhere, not reinvented per agent.

---

**Status:** framework only — real keywords need the actual product catalog and category list, which doesn't exist yet. First real pass happens the run after the master catalog lands (`docs/agents/seo-content.md`).
