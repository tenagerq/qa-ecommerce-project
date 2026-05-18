ID: TC_ATC_01
* **Title:** Successfully adding a single item to an empty cart
* **Preconditions:** The user is on the product detail page. The cart is empty (counter = 0).
* **Steps:**
  1. Click the "Add to cart" button.
* **Test data:** Product ID: 101
* **Expected result:** A success notification "Item added to cart" appears. The cart counter in the website header updates from 0 to 1.
* **Priority:** Critical
---
ID: TC_ATC_02
* **Title:** Adding the same item to the cart again (Quantity increment)
* **Preconditions:** The user is on the product detail page. This item is already in the cart (counter = 1).
* **Steps:**
  1. Click the "Add to cart" button again.
* **Test data:** Product ID: 101
* **Expected result:** The cart counter in the header updates to 2. Inside the cart page, the item quantity is correctly displayed as "2".
* **Priority:** High
---
ID: TC_ATC_03
* **Title:** Attempting to add an item without selecting required attributes
* **Preconditions:** The user is on a product page with optional sizes and colors, but none are selected.
* **Steps:**
  1. Click the "Add to cart" button.
* **Test data:** Product ID: 202 (Product with attributes)
* **Expected result:** The item is not added to the cart. The cart counter does not change. Required attributes (size/color) are highlighted in red with an error message.
* **Priority:** High
---
ID: TC_ATC_04
* **Title:** Cart counter synchronization when adding different items
* **Preconditions:** The user is on the website. The cart is empty.
* **Steps:**
  1. Open Product A page and click "Add to cart".
  2. Go to Product B page and click "Add to cart".
  3. Verify the item counter on the cart icon in the header.
* **Test data:** Product A (ID: 101), Product B (ID: 102)
* **Expected result:** After step 1, the counter is "1". After step 2, the counter updates to "2" in real-time.
* **Priority:** High
---
ID: TC_ATC_05
* **Title:** Cart persistence after page reload (Session check)
* **Preconditions:** The user has added 1 item to the cart. The cart counter displays "1".
* **Steps:**
  1. Refresh the web page (F5 / Reload).
  2. Check the cart counter state after the page fully reloads.
* **Test data:** None.
* **Expected result:** The cart state is preserved. The cart counter still displays "1" and the added item remains in the cart.
* **Priority:** High
---
ID: TC_ATC_06
* **Title:** Attempting to add more items than available in stock
* **Preconditions:** The user is on the product detail page. The database stock for this item is exactly 3 units.
* **Steps:**
  1. Click the "Add to cart" button 4 times consecutively.
* **Test data:** Product ID: 303 (Stock limit = 3)
* **Expected result:** The first 3 clicks successfully add items. On the 4th click, the system blocks the action and displays an error message: "Cannot add more items. Maximum stock limit reached."
* **Priority:** High
---
ID: TC_ATC_07
* **Title:** Adding an item to the cart from the catalog quick-view button
* **Preconditions:** The user is browsing the product catalog list page.
* **Steps:**
  1. Hover over a product card in the catalog and click the quick "Add to Cart" icon/button.
* **Test data:** Product ID: 104
* **Expected result:** The item is successfully added to the cart without opening the full product page. The header cart counter updates from 0 to 1.
* **Priority:** Medium
