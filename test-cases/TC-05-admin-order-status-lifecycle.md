# TC-05: Admin sees the new order and moves it through its status lifecycle

**Priority:** Critical  **Area:** Back office  **Type:** Acceptance, end-to-end

**Preconditions**
- The order from TC-04 exists (status NEW).
- Signed in to `/backoffice` as admin.

**Steps**
1. Open **Dashboard**.
2. Open **Orders**; filter Status = NEW.
3. Click the TC-04 order number.
4. Click **Mark as ACCEPTED**.
5. Click **Mark as DELIVERED**.
6. On a second new order: **Mark as REJECTED**, try to confirm with an empty
   reason, then enter a reason and confirm.
7. In the storefront, open tracking for both orders.

**Expected results**
1. Total orders / recent revenue include the new order; "Orders by status" NEW count
   went up by 1.
2. The order is listed with number, chef, receiver, total (AMD) and status NEW.
3. Detail matches what the customer entered: chef, receiver, phone, email, CASH,
   delivery method, address, note, items with quantity and price, total.
   Buttons: **Mark as ACCEPTED**, **Mark as REJECTED**.
4. "Order status updated"; chip ACCEPTED; buttons now DELIVERED and REJECTED.
5. Chip DELIVERED; no further status buttons (final state).
6. A reason is required; after confirming, the chip is REJECTED, no further
   buttons, and the reason is saved.
7. The customer sees DELIVERED and REJECTED respectively.
