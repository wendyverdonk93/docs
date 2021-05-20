---
title: "How to refund an AfterPay transaction"
weight: 23
meta_title: "Afterpay, how to refund a transaction - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
aliases: [/payment-methods/afterpay/refund-afterpay/]
---

## Refunds 

You can process refunds using most MultiSafepay ecommerce integrations. For more information, see the relevant [ecommerce integration FAQ](/integrations/ecommerce-integrations).

The payment must be linked to a transaction, or the customer only receives a credit on their invoice.

There are 3 ways to refund AfterPay transactions in your [MultiSafepay Control](https://merchant.multisafepay.com):

### Full refunds

1. Go to **Transactions** > **Transaction overview**.
2. Search for the transaction and click it to open the **Transaction details** page.
3. Click **Refund order** > **Full refund**.
4. Click **Save**.  

The transaction is cancelled.

### Partial refunds 

1. Go to **Transactions** > **Transaction overview**.
2. Search for the transaction and click it to open the **Transaction details** page.
3. Click **Refund order** > **Edit**.
4. In the checkout editor, select the item(s) you want to deduct from the order.
5. Click **Save**.  

The transaction shows the credited item(s) and the deducted amount.  
A new payment link is generated and sent to the customer for the adjusted amount.

### Discounts 

1. Go to **Transactions** > **Transaction overview**.
2. Search for the transaction and click it to open the **Transaction details** page.
3. Click **Refund order** > **Change order**.
4. In the checkout editor, add the discount as a new line, e.g. -1 > discount > amount > VAT.
5. Add the new order line to the order to deduct the discounted amount
9. Click **Save**.

The discount is added to the transaction.  
A new payment link is generated and sent to the customer for the adjusted amount.



