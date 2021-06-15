---
title: 'Klarna payment flow'
breadcrumb_title: 'Payment flow'
weight: 30
meta_title: "Klarna payment flow - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Flow from start to finish, including order and transaction status changes"
layout: 'child'
logo: '/logo/Payment_methods/Klarna.svg'
---

The table below shows a successful Betaal per Maand payment flow from start to finish.  

In your MultiSafepay Control > **Transaction overview** > **Transaction details** page under **Status history**, there are two statuses that change as the flow progresses: 

- Order status: indicates the status of the customer's order with the merchant independent of the payment
- Transaction status: indicates the status of the payment

### Payment flow

|                       | Flow      | Order status | Transaction status |
|--------------------------------|-----------|---|-----------------------------------------------------------------------------------------|
|  1. | The customer initiates a transaction. {{< br >}} Betaal per Maand has not yet received payment. {{< br >}} You cannot reject orders at this stage. | Uncleared   | Initialized  |
|  2. | Betaal per Maand approves or declines the transaction. | Uncleared   | Uncleared  |
| | The transaction is successful. {{< br >}} You can reject orders at this stage. | Completed  | Uncleared  |
|  | The transaction appears in both your MultiSafepay Control and the backend of your ecommerce integration via the [Notification URL](/faq/api/notification-url/). | | |
| 3. | Ship the order. | | |
| 4. | [Change the order status to Shipped](/payment-methods/billing-suite/betaalpermaand/faq/changing-order-status-to-shipped/).  | Shipped | Uncleared | 
| 5. | [Provide the track-and-trace code](/payment-methods/billing-suite/betaalpermaand/faq/providing-track-and-trace/) to MultiSafepay. | | |
| 6. | MultiSafepay sends the track-and-trace code to Betaal per Maand to confirm shipment. | | |
| 7. | MultiSafepay sends a capture to Betaal per Maand. |  |  |
| 8. | Betaal per Maand confirms the transaction. | | |
| 9. | Betaal per Maand sends the customer an invoice. Your payout is now guaranteed.  | | |
| 10. | The customer selects their preferred period and payment method for the monthly payment to Betaal per Maand. | | |
| 11. | Betaal per Maand pays the funds to MultiSafepay within 5 business days after the order status changes to **Shipped**. | Shipped    | Completed  |
| 12. | MultiSafepay adds the funds to your MultiSafepay balance within 5 business days.| | |

### Return process 
If the customer returns some items from the order, you can [pauze the collection period](/payment-methods/billing-suite/betaalpermaand/faq/pauzing-collection-period/) for 2 to 4 weeks.

### Other statuses

| Description | Order status | Transaction status |
|---|---|---|
| Betaal per Maand has rejected the transaction. Betaal per Maand only provides the reason directly to the customer, for privacy and compliance reasons. | Declined   | Declined   |
| The transaction was cancelled.   | Void   | Cancelled   |
| The customer did not complete the transaction, and it expired. | Expired    | Expired    |

### Refund statuses

For how to process refunds, see [Processing refunds](/payment-methods/billing-suite/betaalpermaand/#processing-refunds).

| Description                      | Order status      | Transaction status |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| The customer has requested a refund. | Reserved    | Reserved   |
| The refund was successfully processed.  | Completed      | Completed   |
