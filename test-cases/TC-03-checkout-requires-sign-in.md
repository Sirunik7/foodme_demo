# TC-03: Checkout is gated behind sign-in

**Priority:** Critical  **Area:** Storefront / Auth  **Type:** Acceptance, positive + negative

**Preconditions**
- Signed out. Cart has 1 × Pho Bo soup with beef.
- A test customer account exists.

**Steps**
1. Click **Go to checkout**.
2. Click **Sign in** with the fields empty.
3. Enter the test email and a wrong password; click **Sign in**.
4. Enter the correct password; click **Sign in**.
5. Clear the cart and open `/checkout` directly.

**Expected results**
1. URL `/checkout`. An "Account" card with **Sign in / Create account** tabs, Email
   and Password fields. No delivery form or **Place order** button.
2. Validation errors on email and password; no request is sent.
3. An error message; the user stays signed out; the cart is kept.
4. The checkout form appears: "Signed in as <full name>", contact fields prefilled
   from the profile, order summary with the same item and totals as the cart.
5. "Nothing to check out" with a **Browse chefs** button.
