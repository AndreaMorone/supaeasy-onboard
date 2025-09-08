# Free Shipping for Subscribers Function

## Function Name
**Free Shipping for Subscribers**

## Objective
Sort and rename shipping methods for newsletter subscribers and loyalty program members to prioritize free shipping options and encourage subscription.

## Business Requirements

### Primary Functionality
- Sort free shipping first for subscribers
- Rename shipping methods to highlight subscriber benefits
- Hide paid shipping options for qualifying subscribers
- Show subscriber benefits prominently

### Subscriber Shipping Operations
- **Newsletter subscribers:** Sort "Free Standard Shipping" first, hide paid options
- **Loyalty members:** Sort "Free Standard Shipping" first for orders $25+
- **VIP subscribers:** Sort "Free Express Shipping" first for orders $50+
- **Rename methods:** "Standard Shipping" → "Free Standard Shipping (Subscriber)"
- **Hide paid options:** Hide paid shipping for qualifying subscribers

### Business Rules
- **Subscriber sorting:** Free shipping prioritized for subscribers
- **Method renaming:** Clear indication of subscriber benefits
- **Paid option hiding:** Hide paid shipping for qualifying subscribers
- **Geographic considerations:** Different sorting for international subscribers
- **Display priority:** Subscriber benefits shown first

## Technical Requirements

### Testing Scenarios
1. **Newsletter subscriber:** Any order → Free standard shipping sorted first
2. **Loyalty member:** $30 order → Free standard shipping sorted first
3. **VIP subscriber:** $60 order → Free express shipping sorted first
4. **New subscriber:** First order → Free standard shipping sorted first
5. **Non-subscriber:** Any order → Paid shipping options sorted normally
6. **International subscriber:** Non-US/CA → Standard shipping sorted first

## Success Criteria
- [ ] Free shipping sorted first for newsletter subscribers
- [ ] Loyalty members get free shipping sorted first on qualifying orders
- [ ] VIP subscribers get free express shipping sorted first
- [ ] New subscribers get free shipping sorted first on first order
- [ ] Geographic sorting works correctly
- [ ] Subscriber benefits are clearly displayed in method names

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration showing subscriber settings
- Screenshots of shipping options for different subscriber types

## Implementation Hints
- Use **customer tags** to identify newsletter subscribers and loyalty members
- Consider using **order value** triggers to determine when free shipping applies
- Test with **customer accounts** to ensure subscriber detection works correctly
- Use **shipping method renaming** to highlight subscriber benefits in the method name

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
