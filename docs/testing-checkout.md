# Testing a Real Checkout — No Catalog Needed Yet

The full 2,855-item catalog isn't imported yet (needs prices/photos — see `docs/catalog-import.md`), but that shouldn't block confirming MyFatoorah actually works end to end. You don't need real inventory for that — one throwaway product is enough. This is entirely Shopify Admin work — nothing here needs a code change or this repo.

## ⚠️ Read this before placing a test order

MyFatoorah was activated by logging into the **existing live Klinq merchant account** (`docs/payments-setup.md`) — not a fresh sandbox account. That means a "test order" through it is very possibly a **real transaction with a real card**, not a harmless simulation.

**Before doing anything else:** open the MyFatoorah app inside Shopify Admin → Settings → Payments → MyFatoorah, and look for a **Test mode / Sandbox mode** toggle in its settings.

- **If a test-mode toggle exists:** turn it on before testing. This is the safe path — no real money moves.
- **If no test-mode toggle exists:** any test order is a genuine charge. In that case:
  - Use the smallest possible product price (e.g. 0.100–1.000 KWD)
  - Use a real card you control
  - Refund the transaction immediately after confirming it worked (from Shopify Admin → Orders, or directly in the MyFatoorah merchant dashboard)
  - Don't reuse a customer's real card for this under any circumstance

## Step 1 — Add one throwaway test product

In Shopify Admin → Products → Add product:

- **Title:** `TEST — do not sell` (unmistakable so it's never confused for real inventory)
- **Price:** smallest reasonable amount (see the money note above)
- **Track inventory:** off, or set quantity to 1
- **Publish to:** Online Store sales channel (needs to be published to reach checkout)

Takes about a minute — doesn't need Matrixify, doesn't need the real catalog.

## Step 2 — Run the checkout

Go through the actual storefront flow as a customer would: add the test product to cart → checkout → pay with MyFatoorah → confirm the order lands in Shopify Admin → Orders as paid.

If it fails, the error shown at checkout plus the order's payment status in Admin is what to send along (screenshot is fine) — that's enough to diagnose from here even without live store access.

## Step 3 — Clean up

- Unpublish or delete the `TEST — do not sell` product so it never appears to a real customer.
- If the test order was a real charge (no sandbox mode available), confirm the refund actually posted — don't just assume it did.

## After this passes

Checkout is confirmed working end to end. The next real blocker becomes what's already tracked in `docs/setup-checklist.md`: **prices, inventory counts, and product photos** for the real catalog import (see `docs/catalog-import.md`) — none of which can be generated, they need to come from you/the supplier.
