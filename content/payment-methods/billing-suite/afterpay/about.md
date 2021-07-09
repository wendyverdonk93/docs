---
title: 'About AfterPay'
breadcrumb_title: 'About AfterPay'
weight: 10
meta_title: "About AfterPay - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Key information, supported countries and currencies, product rules"
layout: 'child'
logo: '/logo/Payment_methods/AfterPay.svg'
---

AfterPay is the largest online post-payment method in the Netherlands, and recently launched in Belgium. Customers pay for orders after receiving them, and are only charged for items they keep from the order. AfterPay bears the risk and guarantees settlement.

### Summary

|   |   |   |
|---|---|---|
| **Payment type**   | Post-payment method  | |
| **API flow**  | `Direct`/ `Redirect`| [More information](/faq/api/difference-between-direct-and-redirect) |
| **Countries**  | The Netherlands, Belgium  | |
| **Currencies**  | EUR | [More information](/faq/general/supported-currencies) | 
| **Refunds**  | Full and partial  | [More information](/payment-methods/billing-suite/afterpay/faq/processing-refunds/) | 
| **Recurring payments**  | No | [More information](/tools/recurring-payments)  |
| **Chargebacks**  | No | [More information](/faq/chargebacks)  |

## Product rules

{{< details title="Gift cards" >}}
&nbsp;  
Post-payment methods do not generally support entering [gift card](/payment-methods/prepaid-cards/gift-cards) details **after** the order is placed (for a whole or partial payment). This is because, as the collecting party, AfterPay requires very precise order specifications. 

Our platform would interpret the gift card as a discount (not included in the shopping cart specification) and wouldn't generate the correct order information, e.g. for tax purposes. 

Customers can enter gift card details **before** placing the order, i.e. on your checkout page, before the API request. You are solely responsible for enabling this feature. Failure to follow this rule so can produce unexpected errors and complications.

{{< /details >}}

{{< details title="Multiple order rules" >}}
&nbsp;  
If you supply multiple order rules with the same `merchant-item-id`and the customer requests a partial refund, this creates a conflict. 

To successfully process partial refunds for the same product with different specifications (e.g. size, color) via the shopping cart, each `merchant-item-id` must be unique.

**Example:** For different-sized products, differentiate the `merchant-item-id` with `-size`: 1001311-xxl, 1001311-m, 1001311-s.

{{< /details >}}

- You cannot [adjust payment link lifetimes](/faq/api/lifetime-of-a-payment-link).

- AfterPay requires an additional API key for Belgium. Contact AfterPay.

- You must [activate MultiSafepay PayV2 payment pages](/payment-methods/billing-suite/afterpay/faq/activating-payv2/) at website level in your MultiSafepay account. 

- Customers can provide different invoice and delivery addresses, but the customer's first and last name must share at least two characters. The **Transaction details** page in your MultiSafepay account only shows the invoice address. To retrieve other transaction details, make a GET `/orders` request. See API Reference – [Retrieve an order](/api/#retrieve-an-order).
