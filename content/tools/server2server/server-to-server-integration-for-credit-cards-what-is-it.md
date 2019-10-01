---
pagetitle: "Server to Server integration for credit card"
weight: 74
title: "Server to Server"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Methods, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---
## What is it?
By requesting the credit card details on the webshop, a 'direct' transaction can be created. Customers can finalize a credit card payment without being redirected to the payment page of MultiSafepay, resulting in a faster checkout experience and a higher level of control from the merchant’s perspective.

### Types of Credit & Debit Cards supported for Server to Server direct payments.

| Debit / Credit cards | Supported for server to server direct payments |
|---|---|
|Visa | 3D verified by Visa and NON 3D |
|Mastercard | 3D secure code and NON 3D |
|Maestro | Only 3D |
|American Express | NON 3D = No Safekey |
|Bancontact | Only 3D |

## Transaction flow
The transaction flow shows the different possibilities a transaction is able to process. This differs per payment method.

* Order status     
The order status indicates the status of the order such as: completed, pending or rejected. The order status is independent of the incoming or outgoing payment of the transaction.

* Transaction status     
The transaction status indicates the payment status of the transaction such as: pending, completed or rejected. Once the transaction status shows as completed, the amount of the transaction is added to your MultiSafepay balance.

Credit card transactions received by MultiSafepay, will be processed through our fraud filter. The following statuses are important when receiving a credit card payment:

| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Initialized | Initialized | A payment link has been generated, but no payment has been received yet.  | 
| Completed   | Completed   | A successful credit card  transaction has been received and the funds will be added to your MultiSafepay Control balance.   | 
| Uncleared   | Uncleared   |  Waiting for manual permission of the merchant to approve/disapprove the payment. [Read more on accepting uncleared credit card payments, how and why?](/faq/risk-and-fraud/how-to-accept-an-uncleared-transaction/)  | 
| Declined    | Declined    | Transaction has been rejected. [read more on credit card status 'declined'. What does this mean?](/payment-methods/creditcards/creditcard-status-declined-what-does-this-mean-/) | 
| Expired     | Expired     | An unfinished transaction will automatically expire after a predefined period.  | 
| Void        | Cancelled    | Transaction has been cancelled.   | 


### Transaction flow when processing on own MID 
> When using an own MID (MerchantID) from American Express, the funds are not processed by MultiSafepay. In stead the funds will be added to your own balance at American Express.


| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Initialized | Initialized | A payment link has been generated, but no payment has been received yet.  | 
| Uncleared   | Initialized | Waiting for manual permission of the merchant to approve/disapprove the payment. [Read more on accepting uncleared credit card payments, how and why?](/faq/risk-and-fraud/how-to-accept-an-uncleared-transaction/)  | 
| Completed   | Initialized | A successful credit card  transaction has been received and the funds will be added to your MultiSafepay Control balance.   | 


### Refund flow

| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Reserved       | Reserved    | A refund has been requested. | 
| Completed      | Completed   | Refund has been successfully processed.  | 
| Chargeback     | Completed   | Forced reversal of funds initiated by customer’s bank (issuer). Only applicable to Direct Debit and credit card payments. Information on [how to proceed when receiving a chargeback](/payment-methods/creditcards/what-is-a-chargeback/)         |      

Read more about 3D Secure in our page [What is 3D Secure?](/payment-methods/creditcards/what-is-3d-secure)

###  Credit Card Settings to allow direct credit card 3D secure payments.
3D Secure is a technical standard to enhance security. Credit card transactions which are processed with the 3D Secure protocol require a form of authentication of the customer during the payment process. This is usually done via a password connected to the card.

By default, all card orders are processed with 3D Secure.    
_Except: American Express orders, 3D Secure 'Safekey' is currently not supported for American Express transaction_.

Read more about Dynamic 3D Secure in our FAQ page [Dynamic 3D Secure](/tools/server2server/3d-dynamics/)

<br>
