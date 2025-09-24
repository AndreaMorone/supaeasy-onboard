# Product Quantity Limits Function

## Function Name
**Product Quantity Limits**

## Function Type
- [ ] Discount Function (choose between Product/Order/Shipping)
- [ ] Payment Function  
- [ ] Delivery Function
- [x] Validation Function

## Description
This Function helps merchants define and enforce purchase rules across their store. It supports flexible per-product, per-customer, and daily limits, ensuring customers can’t exceed set thresholds. This prevents bulk buying abuse, protects inventory, and guarantees fair distribution of popular or limited-edition items, while allowing merchants to manage stock more effectively.

## Requirements Met
- [x] Primary requirement: Enforces defined rules (per-product, per-customer, bulk vs. non-bulk) that can't be escaped.
- [x] Secondary requirement: Blocks adding to the cart when customers exceed certain limits. 
- [x] Additional features: Clear, user-friendly error messages are displayed when limits are exceeded

## Implementation Details

### Business Logic
- Maximum 3 units per products for new customers
- Maximum 5 units per products for old customers
- Maximum 10 units per customer per day
- Maximum 50 units per customer if bulk product

### Conditions/Triggers
- **When does this function activate?** It runs when the buyer journey is in one of these steps CART_INTERACTION, CHECKOUT_INTERACTION and CHECKOUT_COMPLETION and he validation kicks in only after items are in the cart,
- **What conditions must be met?** Any of those conditions must exceed
- **Are there any exclusions or exceptions?**

### Configuration
- **Settings used in SupaEasy:**
- **Custom parameters:**

## Testing Scenarios

### Test Case 1: Within limits
- **Setup:** Add 3 units per product as a new customer
- **Expected Result:** Products can be added to cart and successfull checkout
- **Actual Result:** Products added to cart smoothly and successfull checkout
- **Status:** [✅ Pass]

### Test Case 2: Exceeds product limit
- **Setup:** Add 6 units per product as a old customer
- **Expected Result:** Shouldn't be able add more then 5 units
- **Actual Result:** Unable to add 6 units to the cart-limit 5
- **Status:** [✅ Pass]

### Test Case 3: Exceeds customer limit
- **Setup:** Add total 12 units of products in the cart
- **Expected Result:** Shouldn't be able add more then 10 units
- **Actual Result:** Unable to add 12 units to the cart-limit 10
- **Status:** [✅ Pass]

### Test Case 4: Limited edition
- **Setup:** Add 3 units of limited item
- **Expected Result:** Shouldn't be able add more then 2 units
- **Actual Result:** Unable to add 3 units to the cart-limit 2
- **Status:** [✅ Pass]

### Test Case 5: New customer
- **Setup:** Add 4 units per product as a new customer
- **Expected Result:** Shouldn't be able add more then 3 units
- **Actual Result:** Unable to add 3 units to the cart-limit 3
- **Status:** [✅ Pass]

### Test Case 6: Bulk item
- **Setup:** Add 60 units of bulk product
- **Expected Result:** Shouldn't be able add more then 50 units
- **Actual Result:** Unable to add 50 units to the cart-limit 50
- **Status:** [✅ Pass]



## Visual Proof

### Screenshots
- [x] Function configuration in SupaEasy
- [x] Admin view showing function is active
- [x] Various limit violation messaging 


### Video Walkthrough
- [x] 3:49-minutes video showing how this function works https://komododecks.com/recordings/NYmeW3EfttTNMHrkRQM6 
- [x] Video shows the implementation of customer metafield and Shopify Flow implementation to track customer's daily purchases
- [x] Video is clear and showes step by step process

## Challenges Encountered

### Technical Challenges
- **Issue:** Showing different error messaging for different limits isn't possbile with Supaeasy Wizard editor
- **Solution:** Used SupaEasy's "Editor" to create a custom function
- **Learning:** Conditionally showing different messages for various limits

### Business Logic Challenges
- **Issue:** There is no readymade solution to track customer daily orders and update for daily buying limitation 
- **Solution:** Used customer metafiled and Shopify flow app to solve this problem
- **Learning:** Learned how metafiled and Shopify flow app can be used to solve complex problems

## Limitations Encountered

**Features that were not possible to implement:**

## Additional Notes

## Required Information
- **Store Domain:** https://adnan-afsari-supaeasy-onboarding.myshopify.com
- **Store Password:** 1234
---

