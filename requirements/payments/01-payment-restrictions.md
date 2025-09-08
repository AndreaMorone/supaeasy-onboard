# Payment Method Restrictions Function

## Function Name
**Payment Method Restrictions**

## Objective
Hide, sort, and rename payment methods based on order value, customer location, or product type to optimize the checkout experience and guide customers toward preferred payment options.

## Business Requirements

### Primary Functionality
- Hide payment methods based on order value
- Sort payment methods by preference for different scenarios
- Rename payment methods for clarity
- Show only relevant payment options

### Payment Method Operations
- **Hide credit cards:** For orders under $25
- **Hide bank transfers:** For orders under $500
- **Sort payment methods:** Prioritize Cash on Delivery (COD) for international orders
- **Rename methods:** "Bank Transfer" → "Wire Transfer"
- **Hide buy now, pay later:** For orders over $1000

### Business Rules
- **Order value triggers:** Hide/sort based on order value
- **Geographic sorting:** Different order for different countries
- **Method renaming:** Clear, descriptive names
- **Display logic:** Show only relevant methods
- **Sorting priority:** Most appropriate method first

## Technical Requirements

### Testing Scenarios
1. **Low value order:** $20 order → Credit cards hidden, COD first
2. **Medium value order:** $100 order → All payment methods visible, sorted by preference
3. **High value order:** $600 order → Buy now, pay later hidden, bank transfer first
4. **Digital products:** Digital download → Only relevant payment methods shown
5. **International order:** Non-US address → COD sorted first, local methods hidden
6. **High value order:** $1200 order → Buy now, pay later hidden, bank transfer first

## Success Criteria
- [ ] Payment methods hidden based on order value
- [ ] Payment methods sorted correctly for different scenarios
- [ ] Payment method names are clear and descriptive
- [ ] Only relevant payment methods are shown
- [ ] Checkout experience remains smooth
- [ ] Function works across all product categories

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration showing all restrictions
- Screenshots of checkout with different order values

## Implementation Hints
- Use **order value** triggers to determine which payment methods to hide or show
- Consider using **shopify market** to identify international customers for different payment sorting
- Test with **product tags** to ensure payment restrictions work with different product types
- Use **geographic restrictions** to hide certain payment methods for specific countries

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
