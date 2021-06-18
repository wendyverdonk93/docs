---
title: "Apple Pay Compatibility and Testing"
weight: 25
meta_title: "Apple Pay Compatibility and Testing - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
read_more: '.'
---

## Compatibility and testing

### Supported devices
For supported devices, see Apple – [Apple is compatible with these devices](https://support.apple.com/en-us/HT208531)

If you don't own an Apple device, we reccomend using [Appetize.io](https://appetize.io).

This emulator allows the pretransaction to be created when ordering and using the payment method Apple Pay. When attempting to complete the order, you will be blocked on the MultiSafepay payment page with the error "this device is not supported" but the pretransaction with Apple Pay as a gateway will be created to check whether a connection to our server exists. However, it is not possible to fully complete the test transaction.

### Requirements

- Use a [compatible device](https://support.apple.com/en-us/HT208531).
- Use Safari browser.
- The website uses HTTPS.
- Maestro is activated in your MultiSafepay Control.

If any of these requirements is not met, Apple Pay doesn't appear on the checkout page.

### Live environment

To test Apple Pay transactions, follow these steps:

1. Email the Integration Team at <integration@multisafepay.com> to activate Apple Pay.
2. Activate Apple Pay in your backend.
3. During checkout, select Apple Pay as the payment method. The payment screen appears with payment details. 
4. Click the **Apple Pay** button (You can ignore the 'Device is not supported' note.)
5. Complete the payment using real card data. **Note:** No actual payment is processed.
6. The transaction is completed.

### Test environment

We recommend using an [Apple Pay Sandbox account](https://developer.apple.com/apple-pay/sandbox-testing).

