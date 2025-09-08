# Free Shipping Threshold Function

## Function Name
**Free Shipping Threshold**

## Objective
Create a free shipping incentive that encourages customers to add more items to their cart to reach a minimum order value, reducing cart abandonment and increasing average order value.

## Business Requirements

### Primary Functionality
- Offer free shipping when order value reaches a specific threshold
- Automatically apply free shipping discount at checkout

### Shipping Thresholds
- **Free shipping threshold:** $75
- **Standard shipping cost:** $5.99
- **Express shipping cost:** $12.99
- **Free shipping method:** Standard shipping only

### Business Rules
- **Minimum order value:** $75 to qualify for free shipping
- **Shipping method:** Only applies to standard shipping
- **Product exclusions:** None (all products count toward threshold)
- **Geographic restrictions:** US and Canada only

### Customer Experience
- Clear "Free shipping at $75" discount message
- Automatic application of free shipping at checkout

## Technical Requirements

### Testing Scenarios
1. **Below threshold:** $50 order → Standard shipping $5.99
2. **At threshold:** $75 order → Free standard shipping
3. **Above threshold:** $100 order → Free standard shipping
4. **Express shipping:** $100 order with express → Express $12.99 (no free shipping)
5. **International:** Non-US/CA address → No free shipping offer
6. **Edge case:** Exactly $75.00 → Free shipping applied

## Success Criteria
- [ ] Free shipping applied at $75 threshold
- [ ] Only applies to standard shipping method
- [ ] Geographic restrictions work correctly
- [ ] Checkout clearly shows free shipping applied

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration
- Screenshots of cart below and above threshold
- Screenshot of checkout showing free shipping

## Implementation Hints
- Use **order value** triggers to determine when free shipping applies
- Test with **shipping method exclusions** to ensure only standard shipping gets the free upgrade
- Use **geographic restrictions** to limit free shipping to specific countries

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
