# Tiered Pricing Function

## Function Name
**Tiered Pricing**

## Objective
Create a tiered pricing structure that offers better discounts as customers buy more items, encouraging larger orders and increasing customer lifetime value.

## Business Requirements

### Primary Functionality
- Implement a volume-based discount system with multiple tiers
- Discounts should increase with quantity purchased
- Apply to the entire cart, not individual products
- Show customers the savings they're getting at each tier

### Pricing Tiers
- **Tier 1:** 1-4 items → No discount
- **Tier 2:** 5-9 items → 10% off entire order
- **Tier 3:** 10-19 items → 15% off entire order
- **Tier 4:** 20+ items → 20% off entire order

### Business Rules
- **Discount type:** Percentage discount on entire order
- **Minimum order value:** $50 (to qualify for any discount)
- **Product exclusions:** Gift cards, digital products
- **Stacking:** Cannot be combined with other percentage discounts
- **Display:** Show current tier savings in cart

### Customer Experience
- Clear indication of current discount tier
- Show savings amount
- Display "Buy X more to reach next tier" in discount message

## Technical Requirements

### Testing Scenarios
1. **Tier 1:** 3 items, $75 order → No discount
2. **Tier 2:** 6 items, $120 order → 10% off ($108 total)
3. **Tier 3:** 12 items, $200 order → 15% off ($170 total)
4. **Tier 4:** 25 items, $300 order → 20% off ($240 total)
5. **Below minimum:** 8 items, $40 order → No discount (below $50)
6. **Excluded products:** Cart with gift cards → No discount

## Success Criteria
- [ ] Correct discount applied at each tier
- [ ] Minimum order value requirement enforced
- [ ] Excluded products don't qualify for discount
- [ ] Tier progression is clearly communicated
- [ ] Discount calculation is accurate
- [ ] Function works across all product categories

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration
- Screenshots of cart at different tier levels

## Implementation Hints
- Use **order value** triggers to determine which tier applies
- Consider using **product collections** to exclude certain items from tiered pricing
- Test with different **cart combinations** to ensure tier progression works correctly
- Use **minimum order value** settings to prevent abuse of tiered discounts

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
