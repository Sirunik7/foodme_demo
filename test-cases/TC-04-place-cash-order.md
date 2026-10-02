# TC-04: Signed-in customer places a cash-on-delivery order

**Priority:** Critical  **Area:** Storefront / Orders  **Type:** Acceptance, end-to-end

**Preconditions**
- Signed in as the test customer. Cart: 1 × Pho Bo soup with beef (3,500 AMD)
  from Alans Kitchen.

**Steps**
1. Open `/checkout`, choose **Delivery**.
2. Clear City and Street; click **Place order**.
3. Fill City "Yerevan", Street, Building; keep name/phone/email; note "TC-04".
   Click **Place order**.
4. Click the tracking link on the success page.
5. Open **Orders** (`/orders`).
6. Repeat steps 1–3 with **Takeaway** (address fields hidden / not required).

**Expected results**
1. Payment is Cash only. Summary: subtotal 3,500, delivery 500, total 4,000 AMD.
2. "City is required" and "Street is required"; no order is created.
3. Button shows "Placing order..." and is disabled (no double submit). Redirect to
   `/orders/success?number=FM-...`: "Order placed!" with the order number. Cart is empty.
4. `/tracking/<number>` shows the order with status NEW.
5. The new order is listed with the right chef, total and status.
6. Order is placed with delivery fee 0 and no address.
