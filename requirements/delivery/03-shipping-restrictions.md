# Shipping Method Restrictions Function

## Function Name
**Shipping Method Restrictions**

## Objective
Hide, sort, and rename shipping methods based on product type, order value, or customer location to ensure appropriate delivery methods are prioritized.

## Business Requirements

### Primary Functionality
- Hide inappropriate shipping methods based on product characteristics
- Sort shipping methods by appropriateness for different scenarios
- Rename shipping methods for clarity
- Show most relevant shipping options first

### Shipping Method Operations
- **Fragile items:** Hide standard shipping, sort express first
- **Heavy items:** Hide air shipping, sort ground shipping first
- **International orders:** Hide express shipping, sort standard first
- **Low-value orders:** Hide express shipping, sort standard first
- **Rename methods:** "Ground Shipping" → "Ground (5-7 days)", "Express" → "Express (1-2 days)"

### Business Rules
- **Product type hiding:** Hide inappropriate methods for product types
- **Order value sorting:** Sort methods by appropriateness for order value
- **Geographic considerations:** Different sorting for international orders
- **Method renaming:** Clear, descriptive names with delivery times
- **Display priority:** Most appropriate method shown first

## Technical Requirements

### Testing Scenarios
1. **Fragile items:** Glass products → Express shipping sorted first, standard hidden
2. **Heavy items:** Furniture → Ground shipping sorted first, air shipping hidden
3. **Digital products:** Downloads → All shipping methods hidden
4. **International order:** Non-US address → Standard shipping sorted first, express hidden
5. **Low-value order:** $20 order → Standard shipping sorted first, express hidden
6. **High-value order:** $100 order → All shipping methods visible, sorted by preference

## Success Criteria
- [ ] Shipping methods hidden based on product type
- [ ] Order value sorting works correctly
- [ ] Geographic sorting functions properly
- [ ] Only relevant shipping methods are shown
- [ ] Checkout experience remains smooth
- [ ] Function works across all product categories

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration showing all restrictions
- Screenshots of checkout with different product types

## Implementation Hints
- Use **product tags** to identify fragile items, heavy items, or digital products
- Consider using **collections** to group products that need specific shipping restrictions
- Test with **order value** triggers to ensure shipping sorting works for different order sizes
- Use **shipping method renaming** to make delivery times clear to customers

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
