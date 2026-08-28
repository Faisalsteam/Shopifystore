# WhatsApp Conversation Flows

Scripted flows for the highest-volume intents, Arabic-first with English shown alongside. These are the conversation *logic* — once a WhatsApp BSP (Zoko/WATI) account exists, they get loaded as templates/flows there (`docs/agents/chatbot-callcenter.md`).

Placeholders in `{{curly braces}}` are variables the BSP or a webhook fills in at send time.

## 1. Order status

**Trigger:** customer sends an order number, or taps "Track my order" from a template button.

- AR: مرحبًا {{first_name}}! 👋 طلبك رقم {{order_number}} حالته الآن: {{order_status}}. تاريخ التسليم المتوقع: {{eta_date}}. هل تحتاج مساعدة إضافية؟
- EN: Hi {{first_name}}! 👋 Your order #{{order_number}} is currently: {{order_status}}. Estimated delivery: {{eta_date}}. Need anything else?

**Fallback (no order found):** ask for the phone number/email used at checkout, then hand off to human if still not found — see `escalation-matrix.md`.

## 2. Shipping / delivery time

- AR: مدة التوصيل المتوقعة إلى {{country}} هي {{delivery_estimate}}. سيصلك رابط تتبع فور شحن الطلب.
- EN: Estimated delivery time to {{country}} is {{delivery_estimate}}. You'll get a tracking link as soon as your order ships.

## 3. Returns / exchange

- AR: يمكنك استرجاع أو استبدال المنتج خلال 14 يومًا من الاستلام، بشرط أن يكون غير مستخدم وبتغليفه الأصلي. لبدء الإجراء أرسل رقم الطلب وسبب الإرجاع.
- EN: You can return or exchange within 14 days of delivery, unused and in original packaging. To start, send your order number and the reason for return.

(14 days per `content/legal/{ar,en}/refund-shipping-policy.md` — grounded in Kuwait Law No. 39/2014, still pending a lawyer's final sign-off, same caveat as `docs/support/faq.md`.)

**Hand off to human** once a return is confirmed — payment/refund actions aren't bot-automated at launch.

## 4. Product / scent guidance

- AR: أهلاً! يسعدنا مساعدتك باختيار العطر المناسب. هل تفضل عطرًا: (1) منعش وخفيف (2) دافئ وحلو (3) خشبي وقوي؟
- EN: Hi! Happy to help you pick the right scent. Do you prefer something: (1) fresh & light (2) warm & sweet (3) woody & bold?

Follow-up recommends 2–3 products by category once the master catalog exists (`docs/seo/keyword-strategy.md` groups categories the same way, so both agents stay consistent).

## 5. Sizing / volume guidance

- AR: هذا المنتج متوفر بحجم {{available_sizes}}. إذا كانت هذه أول مرة تجربينه/تجربينه، ننصح بالحجم الأصغر للتجربة.
- EN: This product is available in {{available_sizes}}. If it's your first time trying it, we recommend starting with the smaller size.

## 6. Promo codes

- AR: الكود {{promo_code}} يمنحك {{discount}} عند الدفع. الكود صالح حتى {{expiry_date}}.
- EN: Code {{promo_code}} gets you {{discount}} at checkout. Valid until {{expiry_date}}.

## 7. Human handoff phrase (used across all flows)

- AR: سأحوّلك الآن إلى أحد أفراد فريقنا للمتابعة معك مباشرة. 🙏
- EN: I'm connecting you with a member of our team to help further. 🙏

See `escalation-matrix.md` for exactly when each flow above hands off instead of continuing automated.
