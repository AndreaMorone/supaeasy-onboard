# Payment Method Reordering Function

## Function Name
**Payment Method Reordering**

## Objective
Sort and rename payment methods at checkout to prioritize the most cost-effective or preferred options, improving conversion rates and reducing processing costs.

## Business Requirements

### Primary Functionality
- Sort payment methods based on order value
- Prioritize preferred payment methods for different scenarios
- Rename payment methods for clarity
- Optimize payment method display for conversion

### Payment Method Operations
- **Orders under $50:** Sort COD first, then Credit Card
- **Orders $50-$200:** Sort Credit Card first, then COD
- **Orders over $200:** Rename "Bank Transfer" → "Wire Transfer" then sort Bank Transfer first, then Credit Card, then COD
- **International orders:** Sort COD first, then Credit Card

### Business Rules
- **Order value-based sorting:** Different priorities for different order values
- **Geographic considerations:** International orders have different sorting
- **Method renaming:** Clear, descriptive names
- **Display logic:** Show most relevant methods first
- **Consistency:** Ensure sorting works across all scenarios

## Technical Requirements

### Testing Scenarios
1. **Low value order:** $30 order → COD sorted first, then Credit Card
2. **Medium value order:** $100 order → Credit Card sorted first, then COD
3. **High value order:** $300 order → Bank Transfer sorted first and renamed, then Credit Card
4. **International order:** Non-US address → COD sorted first, then Credit Card
5. **High value international:** $300 order, non-US → Bank Transfer first and renamed, then COD

## Success Criteria
- [ ] Payment methods sorted based on order value
- [ ] Geographic considerations work correctly
- [ ] Payment method names are clear and descriptive
- [ ] Checkout experience remains smooth
- [ ] Sorting logic works consistently

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration
- Screenshots of checkout with different order values

## Implementation Hints
- Use **order value** triggers to determine payment method sorting priority
- Consider using **customer tags** to identify international customers for different sorting
- Test with **geographic restrictions** to ensure sorting works for different regions
- Use **payment method renaming** to rename Bank Transfer

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
