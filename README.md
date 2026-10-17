# Funnel Performance Report

**Scope:** 900 sessions with a product view (2,161 event rows). All figures use distinct sessions.
**Overall purchase conversion: 27.8%** (250 purchase sessions / 900 product-view sessions). Revenue EUR 11,097, average order value EUR 44.39.

| Stage | Sessions | Step conversion | Sessions lost |
|---|---|---|---|
| Product view | 900 | – | – |
| Add to cart | 586 | 65.1% | 314 |
| Payment selected | 425 | 72.5% | 161 |
| Purchase | 250 | 58.8% | 175 |

## Three most important findings

1. **The two biggest leaks are the first and the last step.** The largest absolute loss is view → cart (314 sessions, 34.9%). The highest loss *rate* is payment → purchase: 41.2% of sessions that picked a payment method never complete the order (175 sessions). These are people who already intended to buy, so this is the most expensive loss.
2. **Mobile is the clear underperformer, and it is the biggest segment.** Mobile converts at 24.8% (n=596, 66% of traffic) against 32.9% on desktop and 37.0% on tablet. The device gap is statistically significant (chi-square p = 0.019). The gap is largest at checkout: mobile completes 55.2% of payment-selected sessions versus 64.4% on desktop.
3. **Country and category differences are visible but not yet proven.** Italy (22.0%) and Sneakers (23.4%) are weakest; France (32.2%) and Accessories (31.6%) are strongest. With 80–450 sessions per segment, the confidence intervals overlap heavily (country p = 0.52, category p = 0.32), so these rankings are indicative only. Sneakers is worth watching because it is the largest category (282 views) and also loses the most at cart → payment (68.9%) and payment → purchase (54.1%).

**Payment method caveat.** Payment method exists only from the payment-selected stage onward, so it cannot be compared across all visitors. Among sessions that selected a method, purchase completion was SEPA 68.4% (n=38), Credit Card 60.8%, PayPal 60.5%, Klarna 50.5% (n=105). The differences are not significant (p = 0.18). This is a comparison inside an already-engaged group, not a conversion rate by method. Klarna is the weakest and worth a closer look, but it is not proven.

## Two recommended actions

1. **Fix the mobile checkout.** Audit the mobile payment → purchase path (form length, wallet/express options such as PayPal, Apple Pay, Google Pay, error handling, page speed) and A/B test a simplified flow. If mobile completion rose from 55.2% to the desktop level of 64.4%, that would mean roughly 25 extra purchases per month from the same traffic (268 payment-selected mobile sessions × 9.2 points).
2. **Run targeted tests on the two largest leaks.** (a) Recover post-payment abandoners with a cart-reminder email or on-page reassurance (delivery cost, returns, trust badges), starting with Klarna and Sneakers where completion is weakest. (b) Test product-page improvements for the view → cart step (clearer size and availability information, reviews, delivery estimate), prioritising Sneakers and Italy.

## Additional data to request before a final decision

- **Payment failure and error logs** (declined, timeout, 3-D Secure abandonment, Klarna eligibility rejections) to separate technical failure from change of mind.
- **Traffic source and campaign data** to check whether the mobile and country gaps are driven by acquisition mix.
- **Shipping costs, delivery times and stock/size availability per session**, which commonly drive late-stage abandonment.
- **A longer time window (3–12 months)** to confirm the country and category rankings and rule out seasonality.
- **A reliable customer key**: 197 customer IDs appear in more than one country, so new vs returning analysis is unreliable until this is resolved.
- **Cost and margin data**, so that action priorities can be ranked by profit and not only by conversion.

## Data quality notes

No missing values other than payment_method (1,486 blanks, which are expected before payment selection), no duplicate event IDs, no negative or invalid values, and no inconsistent sessions. Every session follows a valid sequence (no skipped stages, no stage repeated, timestamps in order): 314 sessions stop at view, 161 at cart, 175 at payment and 250 purchase. The one anomaly is the multi-country customers noted above.
