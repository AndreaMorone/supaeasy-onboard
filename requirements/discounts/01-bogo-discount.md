# BOGO Discount Function

## Function Name
**BOGO Discount**

## Objective
Create a "Buy One Get One" discount function that encourages customers to purchase multiple items by offering a discount on the second item.

## Business Requirements

### Primary Functionality
- When a customer adds 2 or more of the **same product** to their cart
- The second item (and every subsequent item) should receive a **50% discount**
- Only applies to identical products (same product ID and variant)
- Automatically calculates and applies the discount at checkout

### Business Rules
- **Minimum quantity:** 2 items of the same product
- **Discount type:** Percentage discount (50% off)
- **Scope:** Second and subsequent items only
- **Product exclusions:** Gift cards, digital products, and items already on sale
- **Maximum discount:** $50 per item (to prevent abuse)

### Customer Experience
- Discount should be clearly visible in the cart
- Checkout should show the discount breakdown

## Technical Requirements

### Testing Scenarios
1. **Basic BOGO:** 2 identical items → second item 50% off
2. **Multiple items:** 4 identical items → first full price, remaining 3 at 50% off
3. **Different products:** Mixed cart → no discount applied
4. **Excluded products:** Gift cards → no discount applied
5. **Edge case:** Single item → no discount applied

## Success Criteria
- [ ] Function activates when 2+ identical items are in cart
- [ ] 50% discount applies to second and subsequent items
- [ ] No discount applied to different products
- [ ] Excluded products don't trigger discount
- [ ] Discount is clearly visible to customer

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration
- Screenshot of cart showing discount applied
- Screenshot of checkout with discount breakdown

## Implementation Hints
- Use **product tags** to identify which products qualify for BOGO discounts
- Consider using **collections** to group products that should have BOGO discounts
- Test with products that have **variants** to ensure the discount applies correctly
- Use **product exclusions** to prevent BOGO on sale items or gift cards

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
