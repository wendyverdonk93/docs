---
title: "Apple Pay direct integration"
breadcrumb_title: 'Apple Pay direct integration'
weight: 10
meta_title: "Apple Pay direct - Integration and testing - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Integrating and testing Apple Pay direct"
layout: 'single'
---

With a direct integration of Apple Pay, customers can click the " Pay” button in your checkout and finalize the payment without being redirected to a payment page. 

{{< screen src="/img/applePayHero.png" align="center" class="small-img desktop-radius" >}}
{{< br >}}

## Prerequisites

### Server requirements

Apple has the following server requirements for incorporating Apple Pay in your integration:

- All pages that include Apple Pay must be served over HTTPS
- Your domain must have a valid SSL certificate
- Your server must support the TLS protocol version 1.2 or later

For more information, see Apple Developer - [Setting Up Your Server](https://developer.apple.com/documentation/apple_pay_on_the_web/setting_up_your_server).

### Domain validation

To prepare for Apple Pay domain validation:

1. Download the _domain validation file_ for:
	- [Test payments](https://testmedia.multisafepay.com/.well-known/test/apple-developer-merchantid-domain-association)
	- [Live payments](https://media.multisafepay.com/.well-known/apple-developer-merchantid-domain-association)
2. Place the domain validation file at `https://{your-domain}/.well-known/apple-developer-merchantid-domain-association`.

### Request registration for Apple Pay

Once you meet the server requirements and the domain validation file is in place, request registration for Apple Pay.

To request registration for Apple Pay, email your account manager at <sales@multisafepay.com>

**Note**: To offer Apple Pay with MultiSafepay, you don't need an Apple Merchant ID.

## Initialization

**1.** To check whether Apple Pay is supported on the customer's device, use the following conditional statement:
```
if (window.ApplePaySession && ApplePaySession.canMakePayments())
```

For more information, see Apple Developer - [Checking for Apple Pay Availability](https://developer.apple.com/documentation/apple_pay_on_the_web/apple_pay_js_api/checking_for_apple_pay_availability).

**2.** If Apple Pay is supported, show the " Pay” button.

For styling the button, see Apple&nbsp;Pay - [Buttons&nbsp;and&nbsp;Marks](https://developer.apple.com/design/human-interface-guidelines/apple-pay/overview/buttons-and-marks/#apple-pay-mark).


### Create an Apple Pay session

When a customer clicks the " Pay” button, create an Apple Pay session.

First, create a `paymentRequest` object containing order details

```
var paymentRequest = {
        "countryCode": "NL",
        "currencyCode": "EUR",
        "merchantCapabilities": ["supports3DS"],
        "supportedNetworks": [ --> Only supported MSP networks can be used (For example discover is not allowed)
            "visa",
            "masterCard",
            "amex",
            "discover"
        ],
 
        // Request additional data you need
        "requiredBillingContactFields": [
            "postalAddress"
	    
	    --> This info will be required from applepay to the customer, if customer does not have that info in the device, applepay will not allow to pay untill that is filled.
        ],
        "total": {
            "label": "Demo",
            "type": "final",
            "amount": 100  --> This amount is in euros, amount sent to MSP is in cents
        }
    };
    var session = new ApplePaySession(1, paymentRequest);
```

var request = {
  countryCode: 'US',
  currencyCode: 'USD',
  supportedNetworks: ['visa', 'masterCard', 'amex', 'discover'],
  merchantCapabilities: ['supports3DS'],
  total: { label: 'Your Merchant Name', amount: '10.00' },
}
var session = new ApplePaySession(3, request);


{{< details title="Parameters" >}}

|Name|Description|
|---|---|
|countryCode|ISO-1234 Country code|

{{< /details >}}

For more information, see Apple Developer - [Creating an Apple Pay Session](https://developer.apple.com/documentation/apple_pay_on_the_web/apple_pay_js_api/creating_an_apple_pay_session).