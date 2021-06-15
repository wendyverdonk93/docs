---
title: 'Klarna payment flow'
breadcrumb_title: 'Payment flow'
weight: 30
meta_title: "Klarna payment flow - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
short_description: "Flow from start to finish and status change descriptions"
layout: 'child'
logo: '/logo/Payment_methods/Klarna.svg'
---

The table below shows the Klarna payment flow from start to finish.  

In your MultiSafepay Control > **Transaction overview** > **Transaction details** page under **Status history**, there are two statuses that change as the flow progresses: 

- Order status: indicates the status of the customer's order with the merchant independent of the payment
- Transaction status: indicates the status of the payment

|                       | Flow      | Order status | Transaction status |
|--------------------------------|-----------|---|-----------------------------------------------------------------------------------------|
|  1. | The customer initiates a transaction on the Klarna payment page. {{< br >}} See also [Reservation and invoice numbers](/payment-methods/billing-suite/klarna/faq/reservation-and-invoice-number/). | Uncleared   | Initialized  |
| | The transaction is successful, but Klarna hasn't received payment yet. | Completed  | Uncleared  |
| 2. | Ship the order within 28 days, or [extend the shipping period](/payment-methods/billing-suite/klarna/faq/extending-shipping-period/). {{< br >}} See also [Supported addresses](/payment-methods/billing-suite/klarna/faq/supported-addresses/). | | |
| 3. | [Change the order status to Shipped](/payment-methods/billing-suite/klarna/faq/changing-order-status-completed-to-shipped/).  | | | 
| 4. | MultiSafepay sends a capture to Klarna. | Shipped    | Uncleared  |
| 5. | Klarna confirms the transaction. | | |
| 6. | MultiSafepay sends the customer an invoice. Your payout is now guaranteed. {{< br >}} See also [Customizing invoices](/payment-methods/billing-suite/klarna/faq/customizing-invoices/). | | |
| 7. | Klarna pays the funds to MultiSafepay (after 14 business days). | Shipped    | Completed  |
| 8. | MultiSafepay deducts the transaction fee and adds the remaining funds to your MultiSafepay balance (after 18-19 days). {{< br >}} **Note:** In your MultiSafepay Control > **Transaction details** page, the merchant fee always displays as 0,00.| | |
| 9. | If the customer returns some items from the order, you can [place the collection period on hold](/payment-methods/billing-suite/klarna/faq/placing-collection-period-on-hold/) for 2 to 4 weeks.  | | |

### Other statuses

| Description                      | Order status      | Transaction status |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Klarna has rejected the transaction. See Klarna&nbsp;–&nbsp;[Contact customer service](https://www.klarna.com/international/contact-customer-service). {{< br >}} **Or** {{< br >}} The customer or merchant cancelled the transaction.    | Void   | Cancelled   |
| The transaction was not completed or the [order status did not change to Shipped]((/payment-methods/billing-suite/klarna/faq/changing-order-status-completed-to-shipped/)), and the transaction expired. {{< br >}} Expired transactions cannot be reactivated but still appear in your MultiSafepay Control **Transaction overview**. Create a new order, if required.  | Expired    | Expired    |

### Refund statuses

For how to process refunds, see [Processing refunds](/payment-methods/billing-suite/klarna/#processing-refunds).

| Description                      | Order status      | Transaction status |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| The customer requests a refund. | Initialized    | Completed   |
| The refund is successfully processed.  | Completed      | Completed   |
