# Product Bundle Discount Function

## Function Name
**Product Bundle Discount**

## Objective
Create a bundle discount that offers savings when customers purchase specific product combinations together, encouraging cross-selling and increasing order value.

## Business Requirements

### Primary Functionality
- Offer a discount when customers purchase specific product combinations
- Apply discount automatically when bundle requirements are met
- Show bundle savings clearly to customers
- Allow for multiple bundle options

### Bundle Configuration
- **Bundle 1:** T-shirt + Hat → 15% off both items
- **Bundle 2:** 3 or more accessories → 20% off all accessories
- **Bundle 3:** Any 2 items from "Electronics" category → 10% off both items
- **Bundle 4:** Complete outfit (top + bottom + shoes) → 25% off entire outfit

### Business Rules
- **Discount type:** Percentage discount on bundle items
- **Minimum quantity:** Varies by bundle (1-3 items)
- **Product categories:** Specific products or categories

### Customer Experience
- Show current bundle savings
- Display "BUNDLE DISCOUNT {bundle}" in discount message

## Technical Requirements

### Testing Scenarios
1. **Bundle 1:** T-shirt + Hat in cart → 15% off both items
2. **Bundle 2:** 3 accessories in cart → 20% off all accessories
3. **Bundle 3:** 2 electronics in cart → 10% off both items
4. **Bundle 4:** Complete outfit in cart → 25% off entire outfit
5. **Partial bundle:** Only 1 item from bundle → No discount
6. **Multiple bundles:** Items from different bundles → Apply best discount

## Success Criteria
- [ ] Correct discount applied for each bundle type
- [ ] Bundle detection works accurately
- [ ] Discount only applies to bundle items
- [ ] Discount message is visible
- [ ] Multiple bundles can be detected simultaneously
- [ ] Function works with product variants

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration
- Screenshots of cart with different bundle combinations
- Screenshot of discount message
- Screenshot of checkout showing bundle discounts

## Implementation Hints
- Use **product tags** to identify products that belong to specific bundles
- Consider using **collections** to group products that should be bundled together
- Test with **product combinations** to ensure bundle detection works correctly
- Use **product exclusions** to prevent bundles from combining with other discounts

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
