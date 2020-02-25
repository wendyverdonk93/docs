---
title: "Apple Pay, How it works"
weight: 21
meta_title: "Apple Pay, How it works - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
read_more: '.'
---

## How it works

Apple Pay is a payment method that works on the basis on acting as a virtual wallet that enables seamless NFC payments. 

Consumers input their credit card information into the Apple Pay app where it is digitized in the form of an encrypted token. Consumers can authorize payments by using either [Touch ID] or [Face ID] on a payment terminal. The tokenized data is encrpyted and sent to MultiSafepay where it is then decrypted and forwarded to the relevant payment scheme. MultiSafepay supports the [Visa], [Mastercard] and [Maestro] payment schemes for Apple Pay.

MultiSafepay authorizes and validates the payment as a standard credit card transaction. Therefore, transaction statuses remain the same as that of a credit card transaction.

In order to integrate your Apple Pay with MultiSafepay, the Apple Pay account API settings must be configured. Once the integration is completed, you can receive payments through this gateway by using one of our plugins or by implementing a custom integration with our API.

## Transaction Flow

The transaction flow shows the different ways a transaction can be processed. This differs per payment method.

* Order status      
The order status indicates the status of the order, such as _completed_, _pending_ or _rejected_. The order status is independent of the incoming or outgoing payment of the transaction.

* Transaction status       
The transaction status indicates the payment status of the transaction, such as _completed_, _pending_ or _rejected_. Once the transaction status is _completed_, the amount of the transaction is added to your MultiSafepay balance.

Apple Pay transactions received by MultiSafepay will be processed through our fraud filter. The following statuses are important when receiving a credit card payment:

| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Initialized | Initialized | A payment link has been generated, but no payment has been received yet.  | 
| Completed   | Completed   | A successful credit card  transaction has been received and the funds will be added to your MultiSafepay Control balance.   | 
| Uncleared   | Uncleared   |  Waiting for manual permission of the merchant to approve/disapprove the payment. [Read more on accepting uncleared credit card payments, how and why?](/faq/risk-and-fraud/how-to-accept-an-uncleared-transaction/)  | 
| Declined    | Declined    | Transaction has been rejected. [read more on credit card status 'declined'. What does this mean?](/payment-methods/creditcards/creditcard-status-declined-what-does-this-mean-/) | 
| Expired     | Expired     | An unfinished transaction will automatically expire after a predefined period.  | 
| Void        | Cancelled    | Transaction has been cancelled.   | 

### Refund flow

| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Reserved       | Reserved    | A refund has been requested. | 
| Completed      | Completed   | Refund has been successfully processed.  | 
| Chargeback     | Completed   | Forced reversal of funds initiated by customer’s bank (issuer). Only applicable to Direct Debit and credit card payments. Information on [how to proceed when receiving a chargeback](/payment-methods/creditcards/what-is-a-chargeback/)         |               

The full API reference for Apple Pay can be found [here]

## Product Rules

To be continued