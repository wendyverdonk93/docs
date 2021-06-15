---
title: 'Pay After Delivery payment flow'
breadcrumb_title: 'Payment flow'
weight: 30
meta_title: "Pay After Delivery payment flow - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Flow from start to finish and status change descriptions"
layout: 'child'
logo: '/logo/Payment_methods/Pay_After_Delivery.svg'
---

In your MultiSafepay Control > **Transaction overview** > **Transaction details** page under **Status history**, there are two statuses that change as the flow progresses:

- Order status: indicates the status of the customer’s order with the merchant independent of the payment
- Transaction status: indicates the status of the payment

### Payment flow

The table below shows a successful Pay After Delivery payment flow from start to finish.

|   | Flow  | Order status  | Transaction status  |
|---|---|---|---| 
| 1. | The customer agrees with the terms and conditions and initiates a transaction. | Uncleared   | Uncleared | 
| 2. | MultiSafepay approves or declines the transaction within 2 business days. |  |  | 
|  | The transaction is successful. | Completed | Uncleared | 
| 3. | Ship the order. {{< br >}} The order can no longer be cancelled. {{< br >}} See also [Closing transactions](/payment-methods/billing-suite/pay-after-delivery/faq/closing-transactions). | Shipped | Uncleared |
| 4. | [Change the order status to Shipped](/payment-methods/billing-suite/pay-after-delivery/faq/changing-order-status-to-shipped/). |  |  |
| 5. |MultiSafepay sends Pay After Delivery a capture, and Pay After Delivery confirms the transaction. |  |  |
| 6. |MultiFactor emails the customer an invoice containing a payment link within 24 hours of changing to **Shipped** status. {{< br >}} Your payout is now guaranteed. |  |  |
| 7. | The customer has 14 days to pay the invoice. {{< br >}} See also [Failure to pay](#failure-to-pay) below.  |  |  |
| 8. | MultiSafepay adds the funds to your MultiSafepay balance within 30 days of changing to **Shipped** status.  | Shipped | Completed |


### Failure to pay

If the customer fails to pay within the initial 14 day period, MultiFactor emails them reminders with new payment links, each valid for 6 days: 

- The first and second reminders are free. 
- With the third, we add a fee of 7.50 EUR to the invoice. 
- With the fourth, we add a fee of 12.50 EUR to the invoice. 

If the customer still fails to pay, the amount of the total invoice is transferred to a debt collection agency. 

To stop sending reminders, credit the invoice for a zero amount. 

### Other statuses

| Description  | Order status  | Transaction status  |
|---|---|---| 
| The transaction has been cancelled. | Void   | Cancelled | 
| The customer did not complete the transaction within 90 days of initiating it and the transaction has expired. | Expired | Expired | 

### Refund statuses

For how to process refunds, see [Processing refunds](/payment-methods/billing-suite/pay-after-delivery/faq/processing-refunds/).

| Description | Order status | Transaction status |
|---|---|---|
| The customer has requested a refund. | Initialized | Initialized |  
| The refund is successfully processed. | Completed | Completed | 
