# Function Documentation Template

## Function Name
**Tiered Pricing**

## Function Type
- [x] Discount Function (Order)
- [ ] Payment Function  
- [ ] Delivery Function
- [ ] Validation Function

## Description
Apply percentage discounts to the entire shopping cart based on quantity products, informing the customer of the active level and how to reach the next one

## Requirements Met
- [ ] Primary requirement: Volume-based discount system with multiple tiers
- [ ] Secondary requirement: Minimum order value $50; gift cards and digital products excluded
- [ ] Additional features: 

## Implementation Details

### Business Logic
This function applies a tiered percentage discount based on the total quantity of eligible products in the cart. The discount increases progressively as the customer purchases more items, rewarding higher order volumes

### Conditions/Triggers
- **When does this function activate?** When other discounts are applicable and the order value is greater than $50
- **What conditions must be met?** There must be at least five products. Digital products and gift cards are excluded from the count
- **Are there any exclusions or exceptions?** Yes, the discount is not applicable to digital products or gift cards, and it cannot be combined with other percentage discounts

### Configuration
- **Settings used in SupaEasy:**
  - Discount type: Percentage Discount
  - Discount value: 3 tiers (10%, 15%, 20%)
  - Minimum quantity: 5 and $50
  - Product selection: All products
  - Exclusions: applied percentage discounts, gift cards, digital products
- **Custom parameters:**
  - Discount messages. To verify that this function does not activate if another percentage discount is applied, I've also created a simple Shopify function that offers a 20% discount on orders over $180. 

## Testing Scenarios

### Test Case 1: Tier 1
- **Setup:** Added 3 products, total amount $75
- **Expected Result:** no discount
- **Actual Result:** No discount
- **Status:** [✅ Pass]

### Test Case 2: Tier 2
- **Setup:** Added 6 products, total amount $120
- **Expected Result:** 10% off
- **Actual Result:** 10% off
- **Status:** [✅ Pass]

### Test Case 3: Tier 3
- **Setup:** Added 12 products, total amount $200
- **Expected Result:** 15% off
- **Actual Result:** 15% off
- **Status:** [✅ Pass]

### Test Case 4: Tier 4
- **Setup:** Added 25 products, total amount $300
- **Expected Result:** 20% off
- **Actual Result:** 20% off
- **Status:** [✅ Pass]

### Test Case 5: Below minimum
- **Setup:** Added 8 products, total amount $40
- **Expected Result:** no discount
- **Actual Result:** no discount
- **Status:** [✅ Pass]

### Test Case 6: Excluded products
- **Setup:** Added 7 products, total amount $160, one gift card in the cart
- **Expected Result:** no discount
- **Actual Result:** no discount
- **Status:** [✅ Pass]

### Test Case 7: Other percentage discount active
- **Setup:** 1st case: Added 5 products, total amount $145. 2nd case: added 5 products, total amount $215 and other percentage discount applied
- **Expected Result:** Tiered Pricing discount applied in the first case and not applied in the second
- **Actual Result:** Tiered Pricing discount applied in the first case and not applied in the second
- **Status:** [✅ Pass]

## Visual Proof

### Screenshots
- [x] Checkout page displaying test cases

### Video Walkthrough
- [ ] Link to video demonstration (optional but recommended)
- [ ] Video shows complete user journey
- [ ] Video is clear and easy to follow

## Challenges Encountered

### Technical Challenges
- **Issue:** [Description of problem]
- **Solution:** [How you solved it]
- **Learning:** [What you learned]

### Business Logic Challenges
- **Issue:** None
- **Solution:** 
- **Learning:** 

## Limitations Encountered

**Features that were not possible to implement:**
- The function is not active if another percentage discount is applied, because I have not selected the option to combine it with other order discounts. But this means that it's not activated even with discounts that are not percentage
- [Explain why each feature wasn't possible]
- [Describe any alternative solutions you found]

## Additional Notes

As a suggestion for future improvement, it might be useful to add the option to choose the type of discount (percentage, fixed, etc.) in the section at the bottom of the function wizard (*This discount can be combined with...*)

## Required Information
- **Store Domain:** https://maricacinque-supaeasy-onboarding.myshopify.com (pswd 00000)

---

**Note:** Replace all bracketed placeholders with actual information. Delete this note before submitting.
