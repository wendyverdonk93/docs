---
title: 'E-Invoicing payment flow'
breadcrumb_title: 'Payment flow'
weight: 30
meta_title: "E-Invoicing payment flow - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Flow from start to finish, including order and transaction status changes"
layout: 'child'
---

The table below shows a successful payment flow from start to finish.  

{{< details title="About order and transaction statuses" >}}

- Order status: the progression of the customer's order with you, independent of the payment
- Transaction status: the progression towards settlement in your MultiSafepay balance

For more information, see [About MultiSafepay statuses](/api/multisafepay-statuses/).

{{< /details >}}

|   | Flow | Order status | Transaction status |
|---|---|---|---|
| 1. | The customer initiates a transaction. | Initialized   | Initialized  |
| 2. | E-Invoicing authorizes the payment. | Completed  | Initialized  |
| 3. | Once authorized, MultiSafepay sends a capture to E-Invoicing. |  |  |
| 4. | Ship the order. |  |  |
| 5. | [Change the order status to Shipped](/payments/methods/billing-suite/e-invoicing/user-guide/changing-order-status--to-shipped/).  | Shipped | Initialized | 
| 6. | E-Invoicing invoices the customer. |     |   |
| 7. | The customer completes the payment. |     |   |
| 8. | MultiSafepay collects the funds and adds them to your MultiSafepay balance. | Completed    | Completed  |

See also:

- [Viewing transactions](/payments/methods/billing-suite/e-invoicing/user-guide/viewing-transactions/)
- [Batching transactions for subscriptions](/payments/methods/billing-suite/e-invoicing/user-guide/batching-transactions/)

## Unsuccessful statuses
You can cancel payments before the funds are captured. After the funds are captured you can only process a refund.

| Description | Order status | Transaction status |
|---|---|---|
| E-Invoicing has declined the payment. | Declined | Declined |
| The payment has been canceled. | Void | Cancelled |
| The payment was not completed and it expired. | Expired | Expired |

## Refund statuses

| Description | Order status | Transaction status |
|---|---|---|
| The customer has requested a refund. | Initialized | Initialized |
| The refund has been successfully processed.  | Completed | Completed |

