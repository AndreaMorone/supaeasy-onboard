# Product Compatibility Validation Function

## Function Name
**Product Compatibility Validation**

## Function Type
- [ ] Discount Function (choose between Product/Order/Shipping)
- [ ] Payment Function  
- [ ] Delivery Function
- [x] Validation Function

## Description
This function checks if products added to the cart are compatible with each other based on their tags.
If products aren't compatible, this function prevents checkout completion until compatibility is resolved by removing one of the conflicting products from the cart. This prevents users from buying conflicting products together.

## Requirements Met
- [x] Primary requirement: Prevent users from buying conflicting products together
- [x] Secondary requirement: Any product can be added to the cart smoothly in the cart.
- [x] Additional features: Display an error message and prevent checkout if there are incompatible products in the cart until one of them is removed.

## Implementation Details

### Business Logic
- Products with conflicting tags cannot be purchased together
- Shown specific error message only at checkout, not in cart
- Customers can add products to cart normally
- Must remove incompatible products to proceed

### Conditions/Triggers
- **When does this function activate?** It runs on CHECKOUT_INTERACTION and CHECKOUT_COMPLETION only if the cart has more than 1 line item
- **What conditions must be met?** Must be two products in the cart with Incompatible tags: "electronics" + "water-resistant"
- **Are there any exclusions or exceptions?**

### Configuration
- **Settings used in SupaEasy:**
- **Custom parameters:**

## Testing Scenarios

### Test Case 1: Compatible products
- **Setup:** Add two products in the cart with tags Electronics + accessories
- **Expected Result:** Products can be added to cart smoothly and successfull checkout
- **Actual Result:** Products added to cart smoothly and successfull checkout
- **Status:** [✅ Pass]

### Test Case 2: Incompatible products
- **Setup:** Add two products in the cart with tags Electronics + water-resistant 
- **Expected Result:** Products can be added to cart smoothly but prevent checkout and Show error message
- **Actual Result:** Products added to cart smoothly but prevented checkout and Showed error message until one of the products removed
- **Status:** [✅ Pass]

### Test Case 3: Single product
- **Setup:** Add single product in the cart
- **Expected Result:** Products can be added to cart smoothly and successfull checkout
- **Actual Result:** Products added to cart smoothly and successfull checkout
- **Status:** [✅ Pass]

### Test Case 4: Multiple compatible
- **Setup:** Add multiple products in the cart
- **Expected Result:** Products can be added to cart smoothly and successfull checkout
- **Actual Result:** Products added to cart smoothly and successfull checkout
- **Status:** [✅ Pass]

### Test Case 5: Mixed cart
- **Setup:** Add multiple products in the cart with tags Electronics + clothing + water-resistant
- **Expected Result:** Products can be added to cart smoothly but prevent checkout and Show error message
- **Actual Result:** Products added to cart smoothly but prevented checkout and Showed error message until one of the products removed
- **Status:** [✅ Pass]



## Visual Proof

### Screenshots
- [x] Function configuration in SupaEasy
- [x] Admin view showing function is active
- [x] Cart with incompatible products without any error
- [x] Checkout showes error message for incompatible products
- [x] Successful checkout after removing incompatible products


### Video Walkthrough
- [x] 2:32-minutes video showing how this function works https://komododecks.com/recordings/FnV0KTtOscF2l1OxCx6E
- [x] Video shows the implementation, cart and checkout process
- [x] Video is clear and step by step process

## Challenges Encountered

### Technical Challenges
- **Issue:** Checking products incompatiblility using SupaEasy's "Wizard" isn't possible
- **Solution:** Used SupaEasy's "Editor" and "AI' to create a custom function and had to fix some issues and logic by hand
- **Learning:** Understanding how SupaEasy's "Editor" and "AI' works and how it handles cart and checkout validation

### Business Logic Challenges
- **Issue:** Needed to ensure that checkout doesn't work if incompatible products are in the cart
- **Solution:** Used buyerJourney to solve it
- **Learning:** Learned how buyerJourney can be used with SupaEasy's "Editor"

## Limitations Encountered

**Features that were not possible to implement:**

## Additional Notes

## Required Information
- **Store Domain:** https://adnan-afsari-supaeasy-onboarding.myshopify.com

---
