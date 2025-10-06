# Function Documentation

## Function Name
**Free Shipping Threshold**

## Function Type
- [x] Discount Function (Shipping)
- [ ] Payment Function  
- [ ] Delivery Function
- [ ] Validation Function

## Description
This function converts standard shipping to free shipping for orders totalling $75 or more with a shipping address in Canada or United States

## Requirements Met
- [x] Primary requirement: Offer free shipping when order value reaches $75 and automatically apply free shipping discount at checkout
- [x] Secondary requirement: Apply changes in real time when the customer modifies cart contents
- [ ] Additional features: 

## Implementation Details

### Business Logic
Calculates the order amount and verified country address. When the amount reaches the threshold of £75 and the Country is US or Canada, a 100% discount is applied to all delivery options whose title contains the word "standard"

### Conditions/Triggers
- **When does this function activate?** When checkout is in progress
- **What conditions must be met?** Subtotal amount is greater than (or equal to) $75, a "standard" delivery option is available in the current delivery group and shipping address country in CA/US
- **Are there any exclusions or exceptions?** No

### Configuration
- **Settings used in SupaEasy:** I used the editor for the discount function and the Function Creator to hide free shipping when the same conditions as those for "Free shipping threshold" are met.
- **Custom parameters:**

## Testing Scenarios

### Test Case 1: Below threshold
- **Setup:** Added 1 product to make the order of $50, US customer
- **Expected Result:** Standard shipping $5.99
- **Actual Result:** Standard shipping $5.99
- **Status:** [✅ Pass]

### Test Case 2: At threshold
- **Setup:** Added 2 product to make the order of $75, US customer
- **Expected Result:** Free standard shipping
- **Actual Result:** Free standard shipping 
- **Status:** [✅ Pass]

### Test Case 3: Above threshold
- **Setup:** Added 2 product to make the order of $100, US customer
- **Expected Result:** Free standard shipping
- **Actual Result:** Free standard shipping
- **Status:** [✅ Pass]

### Test Case 4: Express shipping
- **Setup:** Added 2 product to make the order of $100, US customer, Express shipping selected
- **Expected Result:** Express $12.99 (no free shipping)
- **Actual Result:** Express $12.99 (no free shipping)
- **Status:** [✅ Pass]

### Test Case 5: International (both registerd and guest customer)
- **Setup:** Added 1 product to make the order of $79, US and interntional customer
- **Expected Result:** No free shipping offer for not US customer
- **Actual Result:** No free shipping offer for not US customer
- **Status:** [✅ Pass]

## Visual Proof

### Screenshots
- [x] Checkout page displaying test cases
- [x] Before function (both guest and registere user)
- [x] Admin view showing function is active

### Video Walkthrough
- [x] Link to video demonstration https://www.loom.com/share/30fd3b75e7d246aa8bcbe127d0ba6d0a?sid=c92c8853-d9ed-40dc-ad9a-2c729d7d6d7e
- [ ] Video shows complete user journey
- [ ] Video is clear and easy to follow

## Challenges Encountered

### Technical Challenges
- **Issue:** As indicated in the provided setup file, my Shopify site offers free shipping for orders over £75, regardless of the shipping address. To avoid confusion, I would like to hide this option
- **Solution:** Ideally, I would have created a new shipping function that would be activated by the same criteria as the discount function (amount>$75 and shipping to US/CA). To speed things up, I created it in the Function section of SupaEasy rather than writing it in the editor. 
I have attached a screenshot here and you can view my backend directly (cfr *Hide FREE _ Free Shipping Threshold function*)
- **Learning:** In the same function, you cannot customise a discount and hide a shipping method

## Limitations Encountered

**Features that were not possible to implement:**
- Exactly what I wrote in the Technical Challenges section

## Additional Notes

This function and *Express Shipping for High-Value Orders Function* cannot be evaluated simultaneously due to opposite business rules for the same test scenario.  
In this function scenario, an order of $100 is expected to **show the Express Shipping option**, while in the Express Shipping scenario the same order should **hide it**.  
For this reason, both functions were tested independently, with one function disabled during the other’s validation. All screenshots and results provided in this submission refer to separate testing sessions, ensuring consistent and conflict-free outcomes.

## Required Information
- **Store Domain:** https://maricacinque-supaeasy-onboarding.myshopify.com (pswd 00000)

