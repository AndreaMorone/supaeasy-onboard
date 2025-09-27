# Function Documentation Example

## Function Name
**BOGO Discount**

## Function Type
- [x] Discount Function
- [ ] Payment Function  
- [ ] Delivery Function
- [ ] Validation Function

## Description
This function provides a "Buy One Get One" discount where customers get 50% off the second item when they purchase two or more of the same product. This encourages higher order values and helps move inventory.

## Requirements Met
- [x] Primary requirement: BOGO discount for same products
- [x] Secondary requirement: Minimum quantity of 2 items
- [x] Additional features: Works with product variants

## Implementation Details

### Business Logic
- When a customer adds 2 or more of the same product to cart
- The second item (and every subsequent item) gets 50% off
- Only applies to identical products (same product ID and variant)
- Automatically calculates and applies the discount

### Conditions/Triggers
- **When does this function activate?** When cart contains 2+ of the same product
- **What conditions must be met?** Product must be in stock and available
- **Are there any exclusions or exceptions?** Excludes sale items and gift cards

### Configuration
- **Settings used in SupaEasy:**
  - Discount type: Percentage discount
  - Discount value: 50%
  - Minimum quantity: 2
  - Product selection: All products
  - Exclusions: Sale items, gift cards
- **Custom parameters:**
  - Apply to: Second and subsequent items only
  - Maximum discount: $50 per item

## Testing Scenarios

### Test Case 1: Basic BOGO Functionality
- **Setup:** Added 2 identical Snowboard ($25 each) to cart
- **Expected Result:** First Snowboard price ($25), second Snowboard 50% off ($12.50)
- **Actual Result:** Cart total shows $37.50 (25 + 12.50)
- **Status:** ✅ Pass

### Test Case 2: Multiple Items BOGO
- **Setup:** Added 4 identical Snowboard ($25 each) to cart
- **Expected Result:** First Snowboard full price ($25), remaining 3 at 50% off ($12.50 each)
- **Actual Result:** Cart total shows $62.50 (25 + 37.50)
- **Status:** ✅ Pass

### Test Case 3: Different Products No Discount
- **Setup:** Added 1 Snowboard and 1 mobile to cart
- **Expected Result:** No discount applied (different products)
- **Actual Result:** Both items at full price
- **Status:** ✅ Pass

### Test Case 4: Excluded products
- **Setup:** Added 2 Digital products
- **Expected Result:** No discount applied
- **Actual Result:** items at full price
- **Status:** ✅ Pass

## Visual Proof (Optional)

### Screenshots
- [x] Function configuration in SupaEasy showing 50% BOGO settings
- [x] Admin view showing function is active
- [x] Cart page showing discount applied to second and subsequent items
- [x] Checkout page displaying the discount breakdown


### Video Walkthrough
- [x] 2-minute video showing complete BOGO flow
- [x] Video demonstrates adding items and seeing discount apply
- [x] Video is clear and shows both desktop and mobile views

## Challenges Encountered

### Technical Challenges
- **Issue:** Initially the discount was applying to all items instead of just the second and subsequent ones
- **Solution:** Used SupaEasy's "Editor" to create a custom function and apply only to subsequent ones
- **Learning:** Understanding how SupaEasy handles quantity-based discounts is crucial

### Business Logic Challenges
- **Issue:** Needed to ensure the discount only applied to identical products, not just same product type
- **Solution:** Configured the function to match exact product ID and variant
- **Learning:** Product variants need special consideration in discount logic

## Limitations Encountered

**Features that were not possible to implement:**
- **Maximum discount per item:** The requirement mentioned a $50 maximum discount per item, but SupaEasy's discount functions don't support per-item discount caps, so I had to create a custom function in the Editor of SupaEasy and calculate it manually
- **Alternative solution:** Use the Editor and a custom function
- **Product variant handling:** Had to test extensively to ensure the discount works correctly with product variants

## Additional Notes

This function works particularly well for fashion and lifestyle products where customers might want multiple colors or sizes. The 50% discount on additional items creates a strong incentive to buy more while still maintaining healthy margins.

## Required Information
- **Store Domain:** https://adnan-afsari-supaeasy-onboarding.myshopify.com
- **Store Password:** 1234

---
