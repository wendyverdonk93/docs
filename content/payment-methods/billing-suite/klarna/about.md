---
title: 'About Klarna'
breadcrumb_title: 'About'
weight: 10
meta_title: "About Klarna - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Key information, supported countries and currencies, product rules"
layout: 'child'
logo: '/logo/Payment_methods/Klarna.svg'
---

Klarna is an online post-payment method that lets customers pay for orders after receiving them. Customers are only charged for the items they keep from the order. Klarna guarantees payout of the transaction.

## Summary

|   |   |   |
|---|---|---|
| **Payment type**   | Post-payment method  | |
| **API flow**  | `Direct`/`Redirect` {{< br >}} Both direct to the Klarna payment page| [More information](/faq/api/difference-between-direct-and-redirect) |
| **Countries**  | Austria, Belgium, Denmark, Germany, Italy, Norway, Spain, Sweden, Netherlands, UK  | |
| **Currencies**  | EUR, SEK, NOK, DKK | [Multi-currency setup](/payment-methods/billing-suite/klarna/faq/activating-multi-currency-setup/) {{< br >}} [More information](/faq/general/supported-currencies) | 
| **Refunds**  | Full and partial  | | 
| **Recurring payments**  | No | [More information](/tools/recurring-payments)  |
| **Chargebacks**  | No | [More information](/faq/chargebacks)  |

## Product rules

{{< details title="Gift cards" >}}
&nbsp;  
Post-payment methods do not generally support entering [gift card](/payment-methods/prepaid-cards/gift-cards) details **after** the order is placed (for a whole or partial payment). This is because, as the collecting party, Klarna requires very precise order specifications. 

Our platform would interpret the gift card as a discount (not included in the shopping cart specification) and wouldn't generate the correct order information, e.g. for tax purposes. 

Customers can enter gift card details **before** placing the order, i.e. on your checkout page, before the API request. You are solely responsible for enabling this feature. Failure to follow this rule so can produce unexpected errors and complications.

{{< /details >}}

{{< details title="Multiple order rules" >}}
&nbsp;  
If you supply multiple order rules with the same `merchant-item-id`and the customer requests a partial refund, this creates a conflict. 

To successfully process partial refunds for the same product with different specifications (e.g. size, color) via the shopping cart, each `merchant-item-id` must be unique.

**Example:** For different-sized products, differentiate the `merchant-item-id` with `-size`: 1001311-xxl, 1001311-m, 1001311-s.

{{< /details >}}
