---
title: "How to refund a Klarna transaction"
weight: 23
meta_title: "Klarna, how to refund a transaction - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---
# Request refund
There are 3 ways to refund a Klarna transaction in the [MultiSafepay Control](https://merchant.multisafepay.com).

In all three cases of a refund, only an amount will be refunded if a payment is linked to the transaction.
If no payment is linked to the transaction, only a credit on the invoice will take place.

## Full refund
The transaction can be fully refunded by the refund option.

1. Go to _transactions_ in the [MultiSafepay Control](https://merchant.multisafepay.com)
2. Select _transaction overview_
3. With the search function you can find the transaction
4. Click on the transaction to open it
5. Select _refund order_
6. _Full refund_
7. _Save_.

The transaction is cancelled.

## Partial refund
The Transaction can be partially refunded in the checkout editor.

1. Go to _transactions_ in the [MultiSafepay Control](https://merchant.multisafepay.com)
2. Select _transaction overview_
3. With the search function you can find the transaction
4. Click on the transaction to open it
5. Select _refund order_
6. Choose _Edit_
7. Choose the page(s) you want to deduct from the order
8. _Save._

The transaction shows the credited page with the deducted amount added to the transaction.
A new payment link is generated and send to the customer with the adjusted invoice.

## Add a discount
Instead of deleting an page in the checkout editor you may want to add a discount.

1. Go to _transactions_ in the [MultiSafepay Control](https://merchant.multisafepay.com)
2. Select _transaction overview_
3. With the search function you can find the transaction
4. Click on the transaction to open it
5. Select _refund order_
6. Choose _edit_
7. Add the discount as a new page in the checkout editor. For example, -1 -> discount -> amount -> VAT
8. Add the new order line to the order to deduct the amount given as a discount
9. _Save._

The discount is added to the transaction.
A new payment link is generated and sent to the customer with the adjusted invoice.

In most plugins you can also refund. See the [Plugin](/integrations/) FAQ for more information.

_When the process for returns are taking too long to verify, the collection period can be paused for 2 or 4 weeks by placing it on hold. This can only be done via <webwinkel@klarna.nl> or +31 208082853_
