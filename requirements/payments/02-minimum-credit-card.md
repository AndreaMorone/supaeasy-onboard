# Minimum Order Amount for Credit Cards Function

## Function Name
**Minimum Order Amount for Credit Cards**

## Objective
Hide credit card payment methods for small orders and sort alternative payment methods to encourage use of more cost-effective payment options.

## Business Requirements

### Primary Functionality
- Hide credit card option for orders below minimum
- Sort alternative payment methods by preference
- Rename payment methods for clarity
- Show only relevant payment options

### Payment Method Operations
- **Hide credit cards:** For orders under $25
- **Sort alternatives:** COD first, then Credit Card
- **Rename methods:** "Bank Transfer" → "Wire Transfer"
- **Show messaging:** Clear indication of available methods

### Business Rules
- **Minimum order value:** $25 for credit card visibility
- **Sorting priority:** Most cost-effective methods first
- **Method visibility:** Hide credit cards below minimum
- **Clear naming:** Descriptive payment method names
- **Fallback options:** Ensure alternatives are prominently displayed

## Technical Requirements

### Testing Scenarios
1. **Below minimum:** $15 order → Credit card hidden, COD sorted first
2. **At minimum:** $25 order → All payment methods visible, sorted by preference
3. **Above minimum:** $50 order → All payment methods visible, sorted by preference
4. **Edge case:** $24.99 order → Credit card hidden, alternatives sorted
5. **Guest checkout:** Test without account → Hide/sort works for guests

## Success Criteria
- [ ] Credit card option hidden for orders under $25
- [ ] Alternative payment methods sorted by preference
- [ ] Payment method names are clear and descriptive
- [ ] Checkout experience remains smooth
- [ ] Hide/sort logic works consistently

## Documentation Requirements (Optional)
- Screenshot of SupaEasy configuration
- Screenshots of checkout below and above minimum

## Implementation Hints
- Use **order value** triggers to hide credit cards below the minimum threshold
- Consider using **payment method sorting** to prioritize alternative payment methods
- Test with **different order values** to ensure the hide/sort logic works correctly
- Use **payment method renaming** to make alternatives more appealing to customers

## Required Information
- **Store Domain:** [your-store-name].myshopify.com
