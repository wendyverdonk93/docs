---
title: "ING Home Pay payment flow"
breadcrumb_title: 'Payment flow'
weight: 30
meta_title: "ING Home Pay payment flow - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Flow from start to finish, including order and transaction status changes"
layout: 'child'
logo: '/logo/Payment_methods/ING_Homepay.svg'
aliases: 
    - /payment-methods/ing-home-pay/how-does-ing-home-pay-work/
---


The table below shows a successful payment flow from start to finish.  

{{< details title="About order and transaction statuses" >}}

- Order status: the progression of the customer's order with you, independent of the payment
- Transaction status: the progression towards settlement in your MultiSafepay balance

For more information, see [About MultiSafepay statuses](/api/multisafepay-statuses/).

{{< /details >}}

|   | Flow | Order status | Transaction status |
|---|---|---|---|
| 1. | The customer initiates a transaction. | Initialized | Initialized |
| 2. | MultiSafepay generates a payment link and redirects the customer to a [MultiSafepay payment page](/payments/checkout/payment-pages/activating-payv2). |   |  |
| 3. | The customer authenticates their account and completes the payment. {{< br >}} **Note:** If the customer doesn't click the **Return to website** button, MultiSafepay doesn't receive an update and the transaction status remains **Initialized**. We import our bank statements daily and all incoming payments are then finalized. | | |
| 4. | The transaction is successful. |  |  |
| 5. | MultiSafepay collects the funds and adds them to your MultiSafepay balance.| Completed | Completed |

## Unsuccessful statuses

| Description | Order status | Transaction status |
|---|---|---|
| The transaction has been canceled. | Void   | Cancelled   |
| The customer didn't complete the payment and the transaction expired after the predetermined period. | Expired | Expired |

## Refund statuses

| Description | Order status | Transaction status |
|---|---|---|
| The customer has requested a refund. | Reserved | Reserved |
| The refund has been successfully processed. | Completed | Completed |




