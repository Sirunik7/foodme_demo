# TC-01: Customer can browse active chefs and open a chef's menu

**Priority:** Critical  **Area:** Storefront  **Type:** Acceptance, positive

**Preconditions**
- Storefront is reachable at `/`.
- At least one active chef with active dishes exists (e.g. Alans Kitchen).

**Steps**
1. Open `/`.
2. Click **Explore chefs**.
3. Compare the "N chefs cooking near you" count with the number of chef cards shown.
4. Click the **Alans Kitchen** card.

**Expected results**
1. Home page loads with the hero and "Explore chefs" / "How it works" buttons.
2. URL is `/explore`. Chef cards show image, name, "500 AMD delivery" and "25–40 min".
3. The count equals the number of cards (when there is one page).
4. URL is `/chef/24`. The page shows the chef name, delivery terms
   ("500 AMD delivery · free from 5,000 AMD"), Takeaway, phone, and a menu grouped
   by category (Soups, Salad, Noodles, ...). Each dish shows name, price in AMD and
   a **+** button. The "Your order" panel says "Your cart is empty".

**Current prod result:** step 3 fails: the header says 6 chefs, 5 cards render.
