---
title: 'AfterPay payment flow'
breadcrumb_title: 'Payment flow'
weight: 30
meta_title: "AfterPay payment flow - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Flow from start to finish and status change descriptions"
layout: 'child'
logo: '/logo/Payment_methods/AfterPay.svg'
---

The table below shows a successful AfterPay payment flow from start to finish.  

In your MultiSafepay Control > **Transaction overview** > **Transaction details** page under **Status history**, there are two statuses that change as the flow progresses: 

- Order status: indicates the status of the customer's order with the merchant independent of the payment
- Transaction status: indicates the status of the payment

### Payment flow

|  | Flow | Order status | Transaction status |
|---|---|---|---|
| 1. | The customer initiates a transaction. |  |  |
| 2. | AfterPay approves or declines the transaction. No action is required. | Uncleared | Uncleared |
| | The transaction is successful.  | Completed  | Uncleared  |
| 3. | Ship the order. | | |
| 4. | [Change the order status to Shipped](/payment-methods/billing-suite/afterpay/faq/changing-order-status-to-shipped/).  | Shipped | Uncleared |
| 5. | MultiSafepay sends a capture to AfterPay. |  |   |
| 6. | AfterPay confirms the transaction. | | |
| 7. | MultiSafepay sends the customer an invoice with a standard payment period of 14 days. Your payout is now guaranteed. | | |
| 8. | The customer makes the payment to AfterPay  via [iDEAL](/payment-methods/banks/ideal/) or internet banking, within 14 days unless otherwise agreed in writing. |  |  |
| 9. | AfterPay pays the funds to MultiSafepay. |  |  |
| 10. | MultiSafepay adds the funds to your MultiSafepay balance.| Shipped | Completed |

### Other statuses

| Description | Order status | Transaction status |
|---|---|---|
| AfterPay has rejected the transaction. AfterPay only provides the reason directly to the customer, for privacy and compliance reasons. {{< br >}} **Or** {{< br >}} The transaction was cancelled. | Void | Cancelled |
| The customer did not complete the transaction within 90 days of initiating it and the transaction has expired. | Expired | Expired |

### Refund statuses

For how to process refunds, see [Processing refunds](/payment-methods/billing-suite/AfterPay/#processing-refunds).

| Description | Order status | Transaction status |
|---|---|---|
| The customer has requested a refund. | Initialized    | Completed   |
| The refund was successfully processed.  | Completed      | Completed   |

### Return process
If the customer returns some items from the order and this takes a long time to verify, you can pauze the collection period for 2 to 4 weeks. 

Phone +31 207230230 or email <merchant@afterpay.com> 
