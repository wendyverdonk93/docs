---
title: "Paysafecard, How does it work?"
weight: 21
meta_title: "Paysafecard, how does it work? - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---
# How does it work?
Paysafecard is a prepaid online payment method based on vouchers with a 16-digit PIN code, independent of bank account, credit card, or other personal information. Customers can purchase vouchers at local sales outlets and pay online by entering the code at the checkout of the respective website.

## Transaction flow
The transaction flow shows the different possibilities a transaction is able to process. This differs per payment method.

* Order status      
The order status indicates the status of the order, such as completed, pending or rejected. 
The order status is independent of the incoming or outgoing payment of the transaction.     

* Transaction status      
The transaction status indicates the payment status of the transaction, such as pending, completed or rejected. 
Once the transaction status shows as completed, the amount of the transaction is added to your MultiSafepay balance.

| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Initialized | Initialized | A payment link has been generated, but no payment has been received yet.  | 
| Completed   | Completed   | A successful Paysafecard transaction has been received and the funds will be added to your MultiSafepay Control balance.   | 
| Declined    | Declined    | Transaction has been rejected   | 
| Expired     | Expired     | An unfinished transaction will automatically expire after a predefined period.  | 
| Void        | Cancelled    | Transaction has been cancelled.   | 


### Refund flow 

| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Initialized    | Initialized | A refund has been requested. | 
| Completed      | Completed   | Refund has been successfully processed.  | 


## Product rules
Some rules may apply to certain payment methods. These rules apply to the payment method Paysafecard.

* Refunding more than the stated amount of the original transaction is possible with the payment method Paysafecard. More information available in [Refund more than original amount](/faq/finance/refund-more-than-original-amount/)

* Transactions successfully received with the payment method Paysafecard have no expiring date regarding refunding, as long as the receiving bank is able to process the refund

* The lifetime of a payment link can be adjusted. This might be beneficial for your inventory. The adjustment can be processed through the days or seconds active.<br>     
Full documentation on the lifetime of a payment link can be found on our FAQ page, [Lifetime of a payment link](/faq/api/lifetime-of-a-payment-link/)
<br>

* Paysafecard can be offered in the following [currencies](/faq/general/which-currencies-are-supported-by-multisafepay/)
  * Euros (EUR)
  * Pounds (GBP)
  * Dollars (USD).
