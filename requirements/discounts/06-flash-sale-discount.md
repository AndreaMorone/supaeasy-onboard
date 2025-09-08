# Time-Limited Flash Sale Function

## Function Name
**Time-Limited Flash Sale**

## Objective
Create a time-limited flash sale discount that creates urgency and drives immediate sales, helping to clear inventory and boost revenue during specific periods.

## Business Requirements

### Primary Functionality
- Offer a significant discount for a limited time period (you can choose the period)
- Apply discount manually with a discount code during the sale period

### Flash Sale Configuration
- **Discount amount:** 30% off entire order
- **Sale duration:** 24 hours
- **Minimum order value:** $50
- **Product exclusions:** Gift cards, digital products
- **Maximum discount:** $100 per order

### Business Rules
- **Discount type:** Percentage discount on entire order
- **Time restrictions:** Only active during specified time period
- **Quantity limits:** No quantity restrictions
- **Stacking:** Cannot combine with other discounts

### Customer Experience
- Manual discount application at checkout

## Technical Requirements

### Testing Scenarios
1. **During sale:** Order placed within 24-hour window → 30% off applied
2. **Below minimum:** $30 order during sale → No discount (below $50)
3. **Excluded products:** Gift card during sale → No discount
4. **Maximum discount:** $500 order → $100 discount (capped at maximum)

## Success Criteria
- [ ] Discount only applies during specified time period
- [ ] Minimum order value requirement enforced
- [ ] Maximum discount cap works correctly

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration
- Screenshot of checkout showing flash sale discount

## Implementation Hints
- Use **time-based triggers** to set the start and end times for the flash sale
- Consider using **product tags** to identify which products are included in the flash sale
- Use **product exclusions** to prevent flash sale items from combining with other discounts

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
