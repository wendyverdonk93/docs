---
title: 'About Betaal per Maand'
breadcrumb_title: 'About Betaal per Maand'
weight: 10
meta_title: "About Betaal per Maand - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Key information, supported countries and currencies, product rules"
layout: 'child'
logo: '/logo/Payment_methods/betaalpermaand.svg'
---

Betaal per Maand is an online post-payment method in collaboration with Santander. MultiSafepay is the only payment service provider that supports Betaaal per Maand online.

Customers pay for orders after receiving them as a one-off post-payment or in monthly installments. They are only charged for the items they keep from the order. 

Betaal per Maand bears the risk and guarantees payout. 

### Summary

|   |   |   |
|---|---|---|
| **Payment type**   | Post-payment method  | |
| **API flow**  | `Direct`| [More information](/faq/api/difference-between-direct-and-redirect) |
| **Countries**  | The Netherlands  | |
| **Currencies**  | EUR | [More information](https://docs.multisafepay.com/faq/general/supported-currencies/) | 
| **Refunds**  | Full and partial  | [More information](/payment-methods/billing-suite/betaalpermaand/faq/processing-refunds/) | 
| **Recurring payments**  | No | [More information](/tools/recurring-payments)  |
| **Chargebacks**  | No | [More information](/faq/chargebacks)  |

### Product rules

- You cannot [adjust payment link lifetimes](/faq/api/lifetime-of-a-payment-link).

- See also User guide – [Known errors](/payment-methods/billing-suite/betaalpermaand/faq/known-errors/).

{{< details title="Gift cards" >}}
&nbsp;  
Post-payment methods do not generally support entering [gift card](/payment-methods/prepaid-cards/gift-cards) details **after** the order is placed (for a whole or partial payment). This is because, as the collecting party, Betaal per Maand requires very precise order specifications. 

Our platform would interpret the gift card as a discount (not included in the shopping cart specification) and wouldn't generate the correct order information, e.g. for tax purposes. 

Customers can enter gift card details **before** placing the order, i.e. on your checkout page, before the API request. You are solely responsible for enabling this feature. Failure to follow this rule so can produce unexpected errors and complications.

{{< /details >}}
