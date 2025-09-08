# Express Shipping for High-Value Orders Function

## Function Name
**Express Shipping for High-Value Orders**

## Objective
Sort and rename shipping methods for high-value orders to prioritize express shipping options and improve the perceived value of premium purchases.

## Business Requirements

### Primary Functionality
- Sort express shipping first for orders above threshold
- Rename shipping methods for clarity
- Hide irrelevant shipping options
- Show most appropriate shipping methods first

### Shipping Method Operations
- **High-value threshold:** $150
- **Sort express first:** For orders $150+
- **Rename methods:** "Express Shipping" → "Express (1-2 days)", "Standard" → "Standard (5-7 days)"
- **Hide slow options:** Hide "Economy" shipping for orders $150+
- **Geographic sorting:** Different order for international orders

### Business Rules
- **Order value trigger:** $150+ orders get express shipping sorted first
- **Method sorting:** Express shipping prioritized for high-value orders
- **Method renaming:** Clear, descriptive names with delivery times
- **Geographic considerations:** Different sorting for international orders
- **Display priority:** Most appropriate method shown first

## Technical Requirements

### Testing Scenarios
1. **Below threshold:** $100 order → Standard shipping sorted first, express hidden
2. **At threshold:** $150 order → Express shipping sorted first, standard second
3. **Above threshold:** $200 order → Express shipping sorted first, standard second
4. **High value:** $300 order → Express shipping sorted first, economy hidden
5. **International:** Non-US/CA address → Standard shipping sorted first
6. **Edge case:** $149.99 order → Standard shipping sorted first

## Success Criteria
- [ ] Express shipping sorted first for orders $150+
- [ ] Shipping method names are clear and descriptive
- [ ] Irrelevant shipping options are hidden appropriately
- [ ] Geographic sorting works correctly
- [ ] Express shipping is prioritized in the list
- [ ] Function works across all product categories

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration showing function settings
- Screenshots of shipping options for different order values

## Implementation Hints
- Use **order value** triggers to determine when to sort express shipping first
- Use **order value** triggers to determine when to hide shipping rates

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
