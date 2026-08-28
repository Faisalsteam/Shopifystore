# Payment Gateway Setup — MyFatoorah (Interim)

**Status: interim decision.** MyFatoorah confirmed as the payment gateway to get checkout working now, reusing the existing MyFatoorah merchant account already set up for Klinq (the other/sister store), until the new store's brand name is finalized. This unblocks checkout immediately instead of waiting on a fresh merchant KYC application — see the heads-up below before treating this as permanent.

This is an **Admin-side setup, not a code change** — Shopify's payment apps configure entirely in Settings, nothing in this repo needs to change for checkout itself to work. Claude's development session can't do this step directly (network policy blocks direct access to `*.myshopify.com`, same reason covered in `docs/deployment.md`) — it needs to be done by whoever has the Shopify admin login.

## Setup steps (Amal or Faisal, in the Shopify admin)

1. Go to the [MyFatoorah app on the Shopify App Store](https://apps.shopify.com/myfatoorah) and click **Add app**.
2. Confirm installation on `9gucqc-qy.myshopify.com`.
3. You'll be redirected to a MyFatoorah login screen — **log in with the existing Klinq MyFatoorah account credentials** (this is the "reuse the existing account" step).
4. Choose which payment icons/methods to display at checkout (cards, KNET, mada, Benefit, etc. — MyFatoorah shows the right local method automatically based on the customer's country).
5. Click **Activate MyFatoorah**.
6. Confirm it now appears under **Shopify Admin → Settings → Payments**.

No API keys need to be pasted into this repo or anywhere in the theme — the whole integration lives in Shopify's payment settings, hosted by MyFatoorah's checkout page (keeps card data out of PCI scope, per `docs/roadmap.md` Phase 3).

## Heads-up before treating this as more than temporary

Worth Faisal confirming directly with MyFatoorah support, not assuming:

- **One merchant account now serves two different storefronts/brands** (Klinq and the new store). Card networks and payment providers generally expect a merchant account's registered business name/website to match what's actually processing transactions — using one account across two differently-branded domains without telling MyFatoorah could trip a compliance review later, even if the underlying legal entity is the same. A quick message to MyFatoorah support ("we're temporarily processing for a second storefront under this account, here's the domain") is a cheap way to avoid a surprise hold on payouts.
- **Settlement reports will mix revenue from both stores** under one MyFatoorah account until this is split out — worth flagging to whoever reconciles Klinq's books (Faisal, per `docs/roadmap.md` Phase 6) so it isn't a surprise at reconciliation time.
- This was explicitly framed as **interim, pending the new brand name** — once the brand kit lands (`docs/setup-checklist.md`), the real decision (stay on MyFatoorah under its own dedicated merchant account, or switch to one of the other three compared in `docs/payment-gateway-comparison.md`) is still open, not settled by this interim step.

## What this unblocks

- Real checkout testing on staging becomes possible once this is live — worth doing before Amal approves anything for the live theme, per `CONTRIBUTING.md`.
- `docs/support/faq.md`'s payment-methods answer is now filled in for real (see that file) instead of a placeholder.

## What's still open

- Whether MyFatoorah stays the permanent choice, or the store moves to a dedicated account/different provider once the brand name is set — see `docs/payment-gateway-comparison.md`.
- Merchant KYC for a *dedicated* account under the new brand, if that's the eventual direction — the interim setup above sidesteps this for now, but it likely comes back once the brand is real.

## Sources

- [MyFatoorah on the Shopify App Store](https://apps.shopify.com/myfatoorah) — official, free app, developed by MyFatoorah (Kuwait), supports cards + KNET/mada/Benefit/NAPS/Meeza
- [MyFatoorah Shopify integration docs](https://docs.myfatoorah.com/docs/shopify)
