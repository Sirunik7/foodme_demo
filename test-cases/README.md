# FoodMe acceptance test cases

The 5 most critical acceptance tests for FoodMe, based on a walkthrough of
production (`https://foodme-armanayvazyan-xw9i.onrender.com`) on 2026-09-29.

| ID | Title | Area | Priority |
|---|---|---|---|
| [TC-01](TC-01-browse-chefs-and-menu.md) | Customer can browse active chefs and open a chef's menu | Storefront | Critical |
| [TC-02](TC-02-cart-totals-and-delivery-fee.md) | Cart calculates subtotal, delivery fee and free-delivery threshold | Storefront | Critical |
| [TC-03](TC-03-checkout-requires-sign-in.md) | Checkout is gated behind sign-in | Storefront / Auth | Critical |
| [TC-04](TC-04-place-cash-order.md) | Signed-in customer places a cash-on-delivery order | Storefront / Orders | Critical |
| [TC-05](TC-05-admin-order-status-lifecycle.md) | Admin sees the new order and moves it through its status lifecycle | Back office | Critical |

Together they cover the whole money path: find food → build cart → authenticate →
place order → restaurant processes it.

## Walkthrough notes

- Explored on prod: home, `/explore`, chef menu (`/chef/24`, Alans Kitchen), cart
  panel (add, +, −), `/checkout` (signed-out state), back office dashboard, order
  list and order detail.
- **Not exercised on prod:** signing in / registering and placing an order. Those
  steps of TC-03…TC-05 are written from the code (`apps/web/src/pages/Checkout`,
  `schemas/checkout-schema.ts`, `apps/admin/src/constants/OrderStatus.jsx`) and
  should be run with a test account.
- **Observed discrepancy:** `/explore` says "6 chefs cooking near you" but renders
  only 5 chef cards (page size is 12, so it isn't pagination). TC-01 would fail
  on prod today.

## Test data

- Chef: **Alans Kitchen** (`/chef/24`), delivery 500 AMD, free from 5,000 AMD,
  offers Delivery and Takeaway.
- Dish: **Pho Bo soup with beef**, 3,500 AMD.
- Customer: a dedicated test account (don't use a real person's account).
- Admin: the workshop admin account.

Note: `/api/**` and `/admin/**` have a deliberate 200–1500 ms delay, so use
waits on elements, not fixed sleeps.
