# Function Documentation Template

## Function Name
**Express Shipping for High-Value Orders**

## Function Type
- [ ] Discount Function (choose between Product/Order/Shipping)
- [ ] Payment Function  
- [x] Delivery Function
- [ ] Validation Function

## Description
Sort and rename shipping methods for orders US/CA of $150+

## Requirements Met
- [ ] Primary requirement: Prioritized express shipping for orders US/CA of $150+
- [ ] Secondary requirement: Renamed Standard and Express option
- [ ] Additional features: I renamed the "Free shipping" option (which was included in the setup as indicated) to "Economy 10-15 days" so that I could work on hiding and reordering this option as requested in the task.

## Implementation Details

### Business Logic
Consider order value, identifies shipping options and renames them. Hide economy shipping for orders US/CA of $150+. Reorder visible options

### Conditions/Triggers
- **When does this function activate?** When checkout is in progress
- **What conditions must be met?** Order above $150 and shipping address in US/CA
- **Are there any exclusions or exceptions?** No

### Configuration
- **Settings used in SupaEasy:** I used the editor
- **Custom parameters:**

## Testing Scenarios

### Test Case 1: Below threshold
- **Setup:** Added 1 product to make the order of $100, US customer
- **Expected Result:** Standard shipping sorted first, express hidden
- **Actual Result:** Standard shipping sorted first, express hidden
- **Status:** [✅ Pass]

### Test Case 2: At threshold
- **Setup:** Added 3 products to make the order of $150, US customer
- **Expected Result:** Express shipping sorted first, standard second
- **Actual Result:** Express shipping sorted first, standard second
- **Status:** [✅ Pass]

### Test Case 3: Above threshold
- **Setup:** Added 1 product to make the order of $200, US customer
- **Expected Result:** Express shipping sorted first, standard second
- **Actual Result:** Express shipping sorted first, standard second
- **Status:** [✅ Pass]

### Test Case 4: High value
- **Setup:** Added 2 products to make the order of $300, US customer
- **Expected Result:** Express shipping sorted first, economy hidden
- **Actual Result:** Express shipping sorted first, economy hidden
- **Status:** [✅ Pass]

### Test Case 5: International
- **Setup:** Added 2 products to make the order of $100, not US customer
- **Expected Result:** Standard shipping sorted first
- **Actual Result:** Standard shipping sorted first
- **Status:** [✅ Pass]

### Test Case 4: Edge case
- **Setup:** Added 5 products to make the order of $149.99, US customer
- **Expected Result:** Standard shipping sorted first
- **Actual Result:** Standard shipping sorted first
- **Status:** [✅ Pass]

## Visual Proof

### Screenshots
- [x] Checkout page displaying test cases
- [x] Before function (both US and International)

### Video Walkthrough
- [ ] Link to video demonstration (optional but recommended)
- [ ] Video shows complete user journey
- [ ] Video is clear and easy to follow

## Challenges Encountered

### Technical Challenges
- **Issue:** None

### Business Logic Challenges
- **Issue:** None

## Limitations Encountered

**Features that were not possible to implement:**
- I renamed the existing Free Shipping option to “Economy” to align with the challenge description, but its original price remained unchanged

## Additional Notes

This function and *Free Shipping Threshold* cannot be evaluated simultaneously due to opposite business rules for the same test scenario.  
In this function scenario, an order of $100 is expected to **hide the Express Shipping option**, while in the Free Shipping Threshold scenario the same order should **show it**.  
For this reason, both functions were tested independently, with one function disabled during the other’s validation. All screenshots and results provided in this submission refer to separate testing sessions, ensuring consistent and conflict-free outcomes.

## Required Information

- **Store Domain:** https://maricacinque-supaeasy-onboarding.myshopify.com (pswd 00000)
