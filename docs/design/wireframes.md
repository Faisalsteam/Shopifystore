# Section Wireframes (brand-agnostic)

Layout specs for the core templates, written without real brand values so they can be reviewed now and built the moment `docs/design/brief-template.md` comes back filled in. Every section has an RTL note — RTL is a build requirement, not a checkbox (`CONTRIBUTING.md`).

## Homepage

1. **Announcement bar** — one-line promo/shipping message, dismissible, localized AR/EN.
2. **Hero** — full-width image or video, headline + subhead + one primary CTA. RTL: text block and CTA mirror to the right; if the hero image has embedded directional elements (arrows, motion lines), mirror or swap for a symmetric asset.
3. **Featured collections** — 3–4 cards, image + title + "Shop now". Grid reflows right-to-left in RTL, not just text-aligned right.
4. **Best sellers / new arrivals carousel** — swipeable product cards (image, title, price, quick-add). RTL: swipe direction reverses (next = swipe left-to-right).
5. **Trust strip** — icons: authentic products, GCC delivery time, secure payment, easy returns. Icon-first so it reads fine in both languages.
6. **Editorial/story block** — brand story or campaign tie-in, image + short copy, one CTA.
7. **Email/WhatsApp signup** — single field + consent checkbox, feeds Klaviyo capture per `docs/marketing/klaviyo-flows.md`.
8. **Footer** — nav columns, social links, payment method icons, language switcher (AR/EN) with clear current-state indicator.

## Product page (PDP)

1. **Gallery** — image carousel/grid, zoom on hover/tap, thumbnail strip. RTL: thumbnail strip and gallery-nav arrows mirror.
2. **Buy box** — title, price (+ compare-at if on sale), variant selectors (size/volume × scent), quantity, Add to Cart, stock/urgency indicator if low stock.
3. **Trust row** — delivery estimate for the customer's country, secure payment badges, return policy link.
4. **Description** — structured, scannable (not a wall of text) — matches the product description template in `docs/seo/content-templates.md`.
5. **Scent/ingredient details** — expandable accordion, bilingual.
6. **Reviews** — star summary + list; ties to the delivery-rating flow in `docs/dispatch/dispatcher.md` eventually feeding review content.
7. **Cross-sell** — "Complete the set" / "You may also like", 4 products max, doesn't compete visually with the buy box.
8. **Sticky mobile buy bar** — price + Add to Cart pinned on scroll (mobile only).

## Collection page

1. **Header** — collection title, short description (SEO-relevant, see `docs/seo/content-templates.md`), hero image optional.
2. **Filter/sort bar** — filters relevant to perfumes/cosmetics (scent family, size, price, gender/occasion if applicable). RTL: filter drawer opens from the right.
3. **Product grid** — 2-up mobile / 3–4-up desktop, image + title + price + quick-add; wishlist/heart icon if loyalty app (Phase 5) is active.
4. **Empty state** — "no products match your filters" with a clear reset action, bilingual.
5. **Pagination or infinite scroll** — decide once traffic/catalog size is known; default to pagination for SEO-crawlability.

## Cart drawer

1. **Slide-in from the right in LTR, from the left in RTL** — the one interaction that must genuinely mirror, not just visually flip.
2. Line items: image, title, variant, qty stepper, price, remove.
3. Free-shipping progress bar if a threshold is set.
4. Order note field (optional) — useful for gift orders.
5. Checkout CTA — prominent, sticky within the drawer if the cart list scrolls.
6. Upsell slot (optional, one row) — small, doesn't block checkout CTA visibility.

## Asset conventions (applies everywhere)

- Product images: 2000px+ on the long edge, `sku-1.jpg`, `sku-2.jpg`, … naming (`docs/roadmap.md` Phase 2 data model).
- Alt text: `{product title} — {key attribute, e.g. scent/size} — {brand}`, written per image, not copy-pasted across variants (feeds SEO agent's checklist).
- Icons: single style/weight throughout — pick one icon set once the brief lands, don't mix.
