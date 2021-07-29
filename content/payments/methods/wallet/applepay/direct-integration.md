---
title: "Apple Pay direct integration"
breadcrumb_title: 'Apple Pay direct integration'
weight: 10
meta_title: "Apple Pay direct - Integration and testing - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Integrating and testing Apple Pay direct"
layout: 'single'
---

With direct integration, the ** Pay** button appears in your checkout page. Customers complete payment without being redirected to a payment page.

{{< screen src="/img/applePayHero.png" align="center" class="small-img desktop-radius" >}}
{{< br >}}

## Prerequisites

### Apple server requirements

- All pages that include Apple Pay must be served over HTTPS.
- Your domain must have a valid SSL certificate.
- Your server must support the TLS protocol version 1.2 or later.

For more information, see Apple Developer – [Setting up your server](https://developer.apple.com/documentation/apple_pay_on_the_web/setting_up_your_server).

### Validate your domain

**1.** Download the Apple Pay domain validation file for:

- [Test payments](https://testmedia.multisafepay.com/.well-known/test/apple-developer-merchantid-domain-association)
- [Live payments](https://media.multisafepay.com/.well-known/apple-developer-merchantid-domain-association)

**2.** Place the domain validation file at:
```
https://{your-domain}/.well-known/apple-developer-merchantid-domain-association
```

### Request registration 

To request registration for Apple Pay direct, email your account manager at <sales@multisafepay.com>

**Note**: You don't need an Apple Merchant ID to offer Apple Pay with MultiSafepay.

## Client-side implementation 

### Check if Apple Pay is supported

**1.** Check if Apple Pay is supported on the customer's device.
```
if (window.ApplePaySession && ApplePaySession.canMakePayments())
```

For more information, see Apple Developer – [Checking for Apple Pay availability](https://developer.apple.com/documentation/apple_pay_on_the_web/apple_pay_js_api/checking_for_apple_pay_availability).

**2.** If Apple Pay is supported, display the ** Pay** button in your checkout page.

**Note:** Disable the button after the customer clicks or taps it to prevent them creating multiple Apple Pay sessions.

For more styling the button, see Apple Developer – [Buttons&nbsp;and&nbsp;marks](https://developer.apple.com/design/human-interface-guidelines/apple-pay/overview/buttons-and-marks/#apple-pay-mark).

### Create an Apple Pay session

When the customer clicks or taps the ** Pay** button, run the following script:

{{< details title="Full script" >}}
```
 "var paymentRequest ="{
    "countryCode":"NL",
    "currencyCode":"EUR",
     "merchantCapabilities":[
         "supports3DS"
    ],
        
    "supportedNetworks":[
      "amex",
      "maestro",
      "masterCard",
      "visa",
      "vPay"
    ],
```
{{< /details >}}

**1.** Create a paymentRequest object containing details about the order.
```
"var paymentRequest ="{
    "countryCode":"NL",
    "currencyCode":"EUR",
     "merchantCapabilities":[
         "supports3DS"
    ],
        
    "supportedNetworks":[
      "amex",
      "maestro",
      "masterCard",
      "visa",
      "vPay"
    ],

    "requiredBillingContactFields":[
        "postalAddress"
    ],
    "total":{
        "label":"Demo",
        "type":"final",
        "amount":100 // The amount in the example code is in euros. The amount sent to MultiSafepay is in cents.
    }
};

var session = new ApplePaySession(1, paymentRequest);

```        
**2.** The Apple Pay API adds the billing address to the token. If the customer hasn't previously provided their billing address to Apple Pay, they are prompted to do so.
```
    "requiredBillingContactFields":[
        "postalAddress"
    ],
    "total":{
        "label":"Demo",
        "type":"final",
        "amount":100 // The amount in the example code is in euros. The amount sent to MultiSafepay is in cents.
    }
};

var session = new ApplePaySession(1, paymentRequest);
```
{{< details title="Parameters" >}}

|Name|Description|
|---|---|
|`countryCode`| Format: [ISO 3166](https://www.iso.org/iso-3166-country-codes.html) country code.|

{{< /details >}}

For more information, see Apple Developer – [Creating an Apple Pay session](https://developer.apple.com/documentation/apple_pay_on_the_web/apple_pay_js_api/creating_an_apple_pay_session).

**3.** Implement a merchant validation callback.
```
session.onvalidatemerchant = function (event) {

  // Send the following data to your server for later.
  var validationUrl = event.validationURL;
  var originDomain = window.location.hostname;        

  // From your server, pass the session request to MultiSafepay.

  //If the session is created successfully:
  session.completeMerchantValidation(<apple-pay-payment-session-data>);
};
```

For more information, see Apple Developer – [Providing merchant validation](https://developer.apple.com/documentation/apple_pay_on_the_web/apple_pay_js_api/providing_merchant_validation).

### Pass the token to MultiSafepay

**1.** Once the customer authorizes payment, implement a payment callback, which is executed after completeMerchantValidation. It receives the Apple Pay payment object, which includes the token.
```
    session.onpaymentauthorized = function (event) {

        // Pass the payment token to your server.
        var payment = event.payment;

        // From your server, create an order, including the token.

        // If the transaction is successful:
        session.completePayment(ApplePaySession.STATUS_SUCCESS);

        // If the transaction is unsuccessful:
        session.completePayment(ApplePaySession.STATUS_FAILURE);

        // If the payment is unsuccessful, re-enable the  Pay button for the customer.
    };
 
    session.begin();
}
```

## Pass the session data
Retrieve the session data:

**Request**
```
POST https://api.multisafepay.com/v1/json/wallets/sessions/applepay
Authorization: Bearer <api-key>

{
    "validation_url": "<data from browser>",
    "origin_domain": "<data from browser>"
}
```
**Response**
```
200 OK

{"data":{"session":"<apple-pay-payment-session-data>"},"success":true}
```

## Create an order

From your server, [submit a transaction request](/api/#create-a-direct-order) to MultiSafepay, including the token.

**Request**
```
POST https://api.multisafepay.com/v1/json/orders

{
    ...

    "gateway_info": {
        "payment_token": "<apple-pay-payment-token>"
    }
}
```


