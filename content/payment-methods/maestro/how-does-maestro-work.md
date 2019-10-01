---
title: "Maestro, How does it work?"
weight: 21
meta_title: "Maestro, how does it work? - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---
# How does it work?
>_Maestro payments are processed as a credit card payment. Therefore, credit card payments must be enabled within your MultiSafepay Control to process a Maestro payment. Submit your request to enable credit cards (Visa, Mastercard en Maestro) to your account manager or contact us at <sales@multisafepay.com>_

A Maestro payment is always validated with the 3D secure code. The 3D secure is a requirement of Maestro.

## Transaction flow
The transaction flow shows the different possibilities a transaction is able to process. This differs per payment method.

* Order status      
The order status indicates the status of the order, such as completed, pending or rejected. 
The order status is independent of the incoming or outgoing payment of the transaction.     

* Transaction status      
The transaction status indicates the payment status of the transaction, such as pending, completed or rejected. 
Once the transaction status shows as completed, the amount of the transaction is added to your MultiSafepay balance.

Credit card transactions received by MultiSafepay, will be processed through our fraud filter. The following statuses are important when receiving a credit card payment:

| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Initialized | Initialized | A payment link has been generated, but no payment has been received yet. | 
| Completed   | Completed   | A successful Maestro transaction has been received and the funds will be added to your MultiSafepay Control balance.   | 
| Uncleared   | Uncleared   |  Waiting for manual permission of the merchant to approve/disapprove the payment. [Read more on accepting uncleared credit card payments, how and why?](/faq/risk-and-fraud/how-to-accept-an-uncleared-transaction/)
| Declined    | Declined    | Transaction has been rejected. [read more on credit card status 'declined'. What does this mean?](/payment-methods/creditcards/creditcard-status-declined-what-does-this-mean-/) | 
| Expired     | Expired     | An unfinished transaction will automatically expire after a predefined period.  | 
| Void        | Cancelled    | Transaction has been cancelled.   | 
| 


### Refund flow 

| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Reserved       | Reserved    | A refund has been requested. | 
| Completed      | Completed   | Refund has been successfully processed.  | 
| Chargeback     | Completed   | Forced reversal of funds initiated by customer’s bank (issuer). Only applicable to Direct Debit and credit card payments. Important information on [how to proceed when receiving a chargeback](/payment-methods/creditcards/what-is-a-chargeback/)              |


Full [API reference](/api/#credit-cards) on the payment method Maestro.

## Product rules
Some rules may apply to certain payment methods. These rules apply to the payment method Maestro.

* Refunding more than the stated amount of the original transaction is not possible with the payment method Maestro. More information available in [Refund more than original amount](/faq/finance/refund-more-than-original-amount/)

* Transactions received Maestro as payment method have an expiring date regarding refunding. All cards can be refunded within 180 days. After the expired period, it is advised to process the requested refund through a bank transfer

* The lifetime of a payment link can be adjusted. This might be beneficial for your inventory. The adjustment can be processed through the days or seconds active.   
Full documentation on the lifetime of a payment link can be found on our FAQ page, [Lifetime of a payment link](/faq/api/lifetime-of-a-payment-link/)
<br>

* Maestro is processed in the [currency](/faq/general/which-currencies-are-supported-by-multisafepay/) Euros (EUR).
