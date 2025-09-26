# Tiered Pricing Function

## Function Name
**Tiered Pricing**

## Function Type
- [x] Discount Function
- [ ] Payment Function  
- [ ] Delivery Function
- [ ] Validation Function

## Description
This function set up a volume-based tiered discount system that applies to the entire cart, offering progressively higher discounts as customers buy more. Clearly show customers their savings at each tier to encourage larger orders and boost lifetime value.

## Requirements Met
- [x] Primary requirement: Implement a volume-based discount system with multiple tiers and discount percentage increases with total quantity.
- [x] Secondary requirement: Discount should be applied to the entire cart, not individual products
- [x] Additional features: Show customers the savings they're getting at each tier and next tier indication and can't be combined with other percentage discounts.

## Implementation Details

### Business Logic
- When a customer adds more then 5 products, the tier discounts begains
- Minimum order value should be at lest $50. Gift Cards and digital products are excluded
- Can't not be combined with other percentage discounts
- Show current tier savings and percentage applied and how many more products to buy to unlock next tier.

### Conditions/Triggers
- **When does this function activate?** When cart contains 5+ products
- **What conditions must be met?**  Minimum order value should be $50
- **Are there any exclusions or exceptions?** Excludes digital products and gift cards

### Configuration
- **Settings used in SupaEasy:**
  - Discount type: Percentage discount
  - Discount value: 10%, 15%, 20%
  - Minimum quantity: 5
  - Product selection: All products
  - Exclusions: Digital products, gift cards
- **Custom parameters:**
  - Apply to: total cart value

## Testing Scenarios

### Test Case 1: Tier 1
- **Setup:** Added 3 items and total order value $75 to cart
- **Expected Result:** No discount should be applied
- **Actual Result:** Discount didn't apply
- **Status:** ✅ Pass

### Test Case 2: Tier 2
- **Setup:** Added 6 items and total order value $150 to cart
- **Expected Result:** 10% dicount should be applied
- **Actual Result:** 10% dicount applied cart total showes $135
- **Status:** ✅ Pass

### Test Case 3: Tier 3 
- **Setup:** Added 12 items and total order value ($300 + $150) to cart
- **Expected Result:** 15% dicount should be applied
- **Actual Result:** 15% dicount applied cart total showes $382.50
- **Status:** ✅ Pass

### Test Case 4: Tier 4 
- **Setup:** Added 25 items and total order value ($300 + $475) to cart
- **Expected Result:** 20% dicount should be applied
- **Actual Result:** 20% dicount applied cart total showes $620
- **Status:** ✅ Pass

### Test Case 5: Below minimum
- **Setup:** Added 8 items and total order value 40 to cart
- **Expected Result:** No discount should be applied
- **Actual Result:** Discount didn't apply
- **Status:** ✅ Pass

### Test Case 6: Excluded products
- **Setup:** Added Digital product to the cart
- **Expected Result:** No discount should be applied
- **Actual Result:** Discount didn't apply
- **Status:** ✅ Pass

## Visual Proof (Optional)

### Screenshots
- [x] Function configuration in SupaEasy
- [x] Admin view showing function is active
- [x] Cart at different tier levels

### Video Walkthrough
- [x] 2:27-minute video showing how Tiered function works https://komododecks.com/recordings/IdCOTXRxgZdvVHLDePn6?onlyRecording=1 
- [x] Video demonstrates adding items and seeing discount apply

## Challenges Encountered

### Technical Challenges
- **Issue:** Showing clear indication of current discount tier, saving amount and next tier info isn't possible with SupaEasy's "Wizard"
- **Solution:** Used SupaEasy's "Editor" to create a custom function and Show clear indications
- **Learning:** Understanding how SupaEasy handles Tier-based discounts

### Business Logic Challenges
- **Issue:** 
- **Solution:** 
- **Learning:** 

## Limitations Encountered


## Additional Notes

## Required Information
- **Store Domain:** https://adnan-afsari-supaeasy-onboarding.myshopify.com
- **Store Password:** 1234

---