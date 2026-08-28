# Catalog Import — Methodology

How the raw supplier price list (barcode + free-text item name, 2,855 rows) becomes a Matrixify-ready Shopify import. The actual catalog data is **not** kept in this repo — per `docs/roadmap.md` Phase 2, the master catalog lives in Amal's Google Sheet, not GitHub. This doc records the process so it's repeatable, not a one-off.

## Input

A two-column list: `Code` (barcode, used as Variant SKU / Barcode) and `Item Name` — an inconsistent free-text string like `CHANEL EGOISTE PLATINUM EDT-100ML M` or `ARD AL ZAAFARAN ROMANCEA EDP 100ML` (no fixed delimiter, gender/size/concentration not always present).

## What gets parsed automatically (safe — derived from the source data, nothing invented)

- **Concentration** (EDT / EDP / EDC / Extrait / Attar / Oil) — keyword match
- **Volume (ml)** — regex on the numeric + `ML` pattern
- **Gender** — token match (Men/Women/Unisex/Ladies/Kids) at or near the end of the string
- **Brand** — matched against a curated dictionary of ~150 brand names/phrases that actually appear in this list (checked by frequency first); unmatched brands fall back to the first word and are flagged, never guessed silently
- **English title** — brand + the remainder of the string, cleaned to title case
- **SEO title / description (English)** — templated from the parsed fields only (brand, product name, concentration, size, gender) — no fabricated scent notes, ingredients, or claims

## What's a best-effort draft (flagged, needs a human pass)

- **Arabic title** — dictionary-based transliteration/translation of the brand and common perfume terms (musk, oud, EDP, etc.); any word not in the dictionary (mostly fantasy/product-line names, e.g. "Egoiste", "Bamboo") is left in Latin script and the row is flagged `contains untranslated word(s)`
- Rows with a low-confidence brand match are flagged `brand not in dictionary`
- Rows missing a parsed size or gender are flagged accordingly

Every flagged row is listed on the output workbook's **Review flags** sheet with the reason, so Amal can triage quickly instead of re-reading all 2,855 rows.

## What's deliberately left blank

- **Price, Compare At Price, Inventory Qty** — not in the source data; pull from the real cost sheet
- **Image Src** — no product photos exist in the source data and none can be generated; see *Photos* below
- **Published / Status** — every row ships as `Published: FALSE`, `Status: draft` on purpose, so nothing reaches the live storefront without going through the approval flow in `CONTRIBUTING.md`

## Photos

Not something an AI can responsibly produce for a real commercial catalog — these need to be actual photos of the actual products, either supplier-provided (with usage rights confirmed) or shot directly. Once available, name them `<SKU>-1.jpg`, `<SKU>-2.jpg`, etc., 2000px+ on the long edge, per the field spec in `docs/roadmap.md` (Phase 2), and drop the filename into the Image Src column.

## Output

A 4-sheet workbook: **Read Me** (this summary, inline), **Products (Matrixify import)** (English, Matrixify's column format), **Arabic draft** (for Shopify's Translate & Adapt app or Matrixify's translation import), **Review flags**. Delivered directly, not committed to this repo.

## How to actually import it (Amal or Faisal, in Shopify Admin)

Claude's development session can't do this step directly — same network restriction covered in `docs/deployment.md` and `docs/payments-setup.md`. This is a few minutes of admin work:

1. Install the [Matrixify app](https://apps.shopify.com/excel-export-import) from the Shopify App Store (free for imports up to a certain size, paid tiers for larger/scheduled ones — check current pricing against the 2,855-row size).
2. In Matrixify, choose **Import** → upload the **Products (Matrixify import)** sheet from the delivered workbook.
3. On the column-mapping screen, Matrixify should auto-match the headers (Handle, Title, Vendor, Tags, Variant SKU, etc.) since they follow its standard format — review the mapping once before confirming, don't just click through.
4. Run the import.

**Every row imports as `Published: FALSE` / `Status: draft` on purpose** — nothing becomes visible or purchasable on the storefront from this import alone. That's deliberate: there's no real price yet (see *What's deliberately left blank* above), so importing live would either reject the rows or let them show as free. Draft import is safe to do now, before prices/photos exist — it gets the catalog structure (2,855 real products, correctly tagged/typed) into Shopify so collections, the theme, and layout can be worked against real data instead of nothing.

**This is not the same as having a sellable product.** For testing checkout/payments specifically, use the separate throwaway-product method in `docs/testing-checkout.md` instead — a draft product with no price won't exercise a real payment.

Once real prices/inventory/photos exist, re-run the same import (Matrixify updates existing rows by Handle/SKU rather than duplicating) and flip `Published`/`Status` to make them live, per the batch-by-product-line approach in `docs/roadmap.md` Phase 2.

## Scaling the Arabic dictionary

The brand/term dictionaries cover the highest-frequency words in the current list (~68% of rows got a dictionary-confident brand match on the first pass). If a new supplier list introduces a lot of newly-flagged brands, the dictionary in the build script is the thing to extend — not a reason to hand-translate 2,855 rows from scratch each time.
