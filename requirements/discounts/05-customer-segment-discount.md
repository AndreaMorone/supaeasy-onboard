# Customer Segment Discount Function

## Function Name
**Customer Segment Discount**

## Objective
Create targeted discounts for specific customer segments to increase loyalty, encourage repeat purchases, and personalize the shopping experience.

## Business Requirements

### Primary Functionality
- Offer different discount levels based on customer segments
- Automatically detect customer segment and apply appropriate discount
- Show segment-specific messaging and offers
- Track segment performance and conversion rates

### Customer Segments
- **VIP Customers:** 20% off entire order (spent $500+ lifetime)
- **Frequent Buyers:** 15% off entire order (3+ orders)
- **New Customers:** 10% off first order (first-time customers)
- **Loyalty Members:** 12% off entire order (subscribed to newsletter)
- **High-Value Customers:** 18% off entire order (average order $100+)

### Business Rules
- **Discount type:** Percentage discount on entire order
- **Minimum order value:** $25 for all segments
- **Segment detection:** Automatic based on customer data
- **Stacking:** Cannot combine with other percentage discounts

### Customer Experience
- Personalized discount based on customer history
- Clear indication of why they're receiving the discount

## Technical Requirements

### Testing Scenarios
1. **VIP Customer:** $500+ lifetime spend → 20% off order
2. **Frequent Buyer:** 3+ orders in 6 months → 15% off order
3. **New Customer:** First-time visitor → 10% off order
4. **Loyalty Member:** Newsletter subscriber → 12% off order
5. **High-Value Customer:** $100+ average order → 18% off order
6. **Regular Customer:** No segment match → No discount

## Success Criteria
- [ ] Correct discount applied for each customer segment
- [ ] Customer segment detection works accurately
- [ ] Segment-specific messaging displays correctly
- [ ] Minimum order value requirement enforced
- [ ] Function works for both logged-in and guest customers

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration
- Screenshots of different customer segments receiving discounts
- Screenshot of segment-specific messaging
- Screenshot of checkout showing segment discount

## Implementation Hints
- Use **customer tags** to identify different customer segments (VIP, frequent-buyer, new-customer)
- Consider using **order history** triggers to detect customer behavior patterns
- Test with **customer accounts** to ensure segment detection works correctly
- Use **customer exclusions** to prevent certain segments from getting discounts

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
