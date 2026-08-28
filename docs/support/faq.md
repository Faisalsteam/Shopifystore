# FAQ (Arabic / English)

Shared source for both the WhatsApp bot flows and any human agent — one place, both languages, so answers stay identical everywhere. Also feeds the "Content that blocks payment gateway approval" checklist item in `docs/setup-checklist.md` (FAQ is required content for merchant KYC).

## Ordering

**Q (AR): كيف أقدر أطلب من الموقع؟**
A (AR): اختاري المنتج، حددي المقاس/الحجم، أضيفيه للسلة، ثم أكملي بيانات الدفع والشحن عند الدفع.

**Q (EN): How do I place an order?**
A (EN): Choose your product, select size/volume, add to cart, then complete payment and shipping details at checkout.

## Payment

**Q (AR): وش طرق الدفع المتوفرة؟**
A (AR): نقبل البطاقات الائتمانية/بطاقات الخصم، بالإضافة إلى وسيلة الدفع المحلية لدولتك (مثل KNET بالكويت، مدى بالسعودية، Benefit بالبحرين) — تظهر تلقائيًا حسب بلدك عند الدفع.

**Q (EN): What payment methods do you accept?**
A (EN): We accept credit/debit cards, plus your country's local payment method (e.g. KNET in Kuwait, mada in Saudi Arabia, Benefit in Bahrain) — shown automatically based on your country at checkout.

## Shipping & delivery

**Q (AR): كم تستغرق مدة التوصيل؟**
A (AR): {{delivery_estimate — يعتمد على الدولة، انظر docs/dispatch/courier-matrix.md}}

**Q (EN): How long does delivery take?**
A (EN): {{delivery_estimate — depends on country, see docs/dispatch/courier-matrix.md}}

**Q (AR): هل تشحنون إلى جميع دول الخليج؟**
A (AR): نشحن حاليًا إلى {{launch_countries}}. سيتم توسيع نطاق الشحن لاحقًا.

**Q (EN): Do you ship across the GCC?**
A (EN): We currently ship to {{launch_countries}}. Coverage will expand over time.

## Returns & exchanges

**Q (AR): وش سياسة الإرجاع؟**
A (AR): يمكن إرجاع أو استبدال المنتج خلال 14 يومًا من الاستلام، بشرط أن يكون غير مستخدم وبتغليفه الأصلي — للتفاصيل الكاملة انظر [سياسة الشحن والاسترجاع](../../content/legal/ar/refund-shipping-policy.md).

**Q (EN): What's your return policy?**
A (EN): Returns/exchanges accepted within 14 days of delivery, unused and in original packaging — full details in the [Shipping & Refund Policy](../../content/legal/en/refund-shipping-policy.md).

## Product

**Q (AR): هل المنتجات أصلية 100%؟**
A (AR): نعم، جميع منتجاتنا أصلية 100% ومصدرها موردون معتمدون.

**Q (EN): Are your products 100% authentic?**
A (EN): Yes, every product is 100% authentic, sourced from authorized suppliers.

## Account & support

**Q (AR): كيف أتواصل مع خدمة العملاء؟**
A (AR): تقدر تتواصل معنا عبر واتساب على {{whatsapp_number}} أو عبر البريد الإلكتروني {{support_email}}.

**Q (EN): How do I reach customer support?**
A (EN): Reach us on WhatsApp at {{whatsapp_number}} or by email at {{support_email}}.

---

Items in `{{double braces}}` are placeholders pending decisions still open in `docs/setup-checklist.md` and `docs/integrations.md` (courier/country breakdown, WhatsApp number). The 14-day return window above is filled in from `content/legal/{ar,en}/refund-shipping-policy.md` — that draft is grounded in Kuwait Law No. 39/2014 but still needs a licensed lawyer's sign-off before publishing (see `content/legal/README.md`), so treat "14" as highly likely but not 100% final until that review lands. The payment-methods answer is filled in for real now that MyFatoorah is live (interim) — see `docs/payments-setup.md`. Terms & Conditions and Privacy Policy are separate required legal documents (also listed in `docs/setup-checklist.md`) — not covered by this FAQ.
