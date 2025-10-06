# Function Documentation

## Function Name
**Minimum Order Amount for Credit Cards**

## Function Type
- [ ] Discount Function (choose between Product/Order/Shipping)
- [x] Payment Function  
- [ ] Delivery Function
- [ ] Validation Function

## Description
This function hides the credit card payment method for orders under $25, renames some payment methods and sorts the payment methods according to the principle of the most cost-effective method first. This encourage use of more cost-effective payment options.

## Requirements Met
- [x] Primary requirement: Hide credit card option for orders for order under $25
- [x] Secondary requirement: Sort payment methods
- [x] Additional features: Descriptive payment method names

## Implementation Details

### Business Logic
Hide credit card when cart total < $25, rename supported payment methods and enforce preferred display order (COD > Credit card > PayPal > Wire Transfer)

### Conditions/Triggers
- **When does this function activate?** When checkout is in progress 
- **What conditions must be met?** The Credit card option is hidden when the shopping cart subtotal or total is below $25. The payment methods are renamed regardless.
- **Are there any exclusions or exceptions?** No

### Configuration
- **Settings used in SupaEasy:** I used the editor, not the UI
- **Custom parameters:** 

## Testing Scenarios

### Test Case 1: Below minimum (both registered user and guest user)
- **Setup:** Added 2 products to make the order under $25
- **Expected Result:** Credit card hidden, COD sorted first, payment methods renamed
- **Actual Result:** Credit card hidden, COD sorted first, new names and new order: "Cash on Delivery - No advance payment required" > "Credit Card - Minimum order $25" (in this test it's hidden) > PayPal > "Wire Transfer"
- **Status:** [✅ Pass]

### Test Case 2: At minimum
- **Setup:** Added 1 product to make the order of $25
- **Expected Result:** All payment methods visible, sorted by preference, payment methods renamed
- **Actual Result:** All payment methods visible, new names and new order: "Cash on Delivery - No advance payment required" > "Credit Card - Minimum order $25" > PayPal > "Wire Transfer"
- **Status:** [✅ Pass]

### Test Case 3: Above minimum (both registered user and guest user)
- **Setup:** Added n product to make order over $25
- **Expected Result:** All payment methods visible, sorted by preference
- **Actual Result:**  All payment methods visible, new names and new order: "Cash on Delivery - No advance payment required" > "Credit Card - Minimum order $25" > PayPal > "Wire Transfer"
- **Status:** [✅ Pass]

### Test Case 4: Edge case
- **Setup:** Added 3 product to make order of $24.99
- **Expected Result:** Credit card hidden, alternatives sorted
- **Actual Result:**  Credit card hidden, new names and new order: "Cash on Delivery - No advance payment required" > "Credit Card - Minimum order $25" (in this test it's hidden) > PayPal > "Wire Transfer"
- **Status:** [✅ Pass]

## Visual Proof

### Screenshots
- [x] Function in Editor 
- [x] Checkout page displaying test cases
- [x] Before function (both guest and registere user)
- [x] Admin view showing function is active

### Video Walkthrough
- [ ] Link to video demonstration (optional but recommended)
- [ ] Video shows complete user journey
- [ ] Video is clear and easy to follow

## Challenges Encountered

### Technical Challenges
- **Issue:** Initially, I used gid to identify payment methods. This worked correctly for guest users, but when a customer was logged in, the gid references shifted and the wrong payment methods were affected
- **Solution:** I asked Copilot about this behaviour, but I was not convinced by the answer, so I asked Codex. Codex wrote that, when a user is logged in, Shopify adds extra methods to the payload. This misaligns the ORDERED_IDS, causing incorrect moves, renames or hiding because the indexes fall out of sync. I replaced gid based identification with name based matching, targeting payment method names directly
- **Learning:** Gid remain consistent for a method, but Shopify can omit or swap entries at checkout depending on context; it’s safer to test both anonymous and logged-in users to cover every scenario

### Business Logic Challenges
- **Issue:** The main requirement was to restrict credit card payments for orders below $25, while ensuring other payment options weren't affected
- **Solution:** Parsed the cart subtotal, hid Shopify Payments below the threshold and renamed and reordered the payment methods. I took inspiration for this from the SupaEasy Functions Library, particularly the 'Filter and Modify Payment Method Display'
- **Learning:** Leaned on Shopify Functions payment customization primitives with optional chaining and filter(Boolean) to avoid null operations when data is missing

## Limitations Encountered

**Features that were not possible to implement:**
- I couldn't rename PayPal

## Required Information
- **Store Domain:** https://maricacinque-supaeasy-onboarding.myshopify.com (pswd 00000)

