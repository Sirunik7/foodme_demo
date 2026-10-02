# TC-02: Cart calculates subtotal, delivery fee and free-delivery threshold

**Priority:** Critical  **Area:** Storefront / Cart  **Type:** Acceptance, positive + boundary

**Preconditions**
- Cart is empty. On `/chef/24` (Alans Kitchen: delivery 500 AMD, free from 5,000 AMD).

**Steps**
1. Click **+** on **Pho Bo soup with beef** (3,500 AMD).
2. Click **+** next to the quantity in "Your order".
3. Click **−** next to the quantity.
4. Click **−** again (quantity is 1).

**Expected results**
1. Header cart badge shows 1. Panel: qty 1, Subtotal 3,500 AMD, Delivery 500 AMD,
   hint "Add 1,500 AMD more for free delivery", Total 4,000 AMD, **Go to checkout** enabled.
2. Badge 2. Line shows "7,000 AMD · 3,500 AMD each". Subtotal 7,000, Delivery **Free**,
   Total 7,000 AMD, hint gone.
3. Qty 1 again; totals back to step 1 values (delivery fee returns).
4. The item is removed and the panel shows "Your cart is empty"; badge 0.
5. (Extra) Reload the page at any step: the cart persists.

**Notes:** only one chef's dishes per cart. Also check a subtotal of exactly
5,000 AMD gets free delivery (boundary).
