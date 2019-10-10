---
title: "TrustPay, How does it work?"
weight: 21
meta_title: "TrustPay, how does it work? - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---
# How does it work?
If the transaction is approved by TrustPay, the transaction status will change to completed and MultiSafepay will add the funds to the balance of your MultiSafepay Control.

## Transaction flow
The transaction flow shows the different possibilities a transaction is able to process. This differs per payment method.

* Order status      
The order status indicates the status of the order, such as completed, pending or rejected. 
The order status is independent of the incoming or outgoing payment of the transaction.     

* Transaction status      
The transaction status indicates the payment status of the transaction, such as pending, completed or rejected. 
Once the transaction status shows as completed, the amount of the transaction is added to your MultiSafepay balance.

| Order Status | Transaction Status | Description                                                                                                          |
|--------------|------------------|----------------------------------------------------------------------------------------------------------------------|
| Initialized  | Initialized      | A payment link has been generated, but no payment has been received yet.                                             | 
| Completed    | Completed        | A successful Alipay transaction has been received and the funds will be added to your MultiSafepay Control balance.  | 
| Declined     | Declined         | Transaction has been rejected.                                                                                       | 
| Expired      | Expired          | An unfinished transaction will automatically expire after a predefined period.                                       | 
| Void         | Cancelled        | Transaction has been cancelled.                                                                                       | 


### Refund flow

| Order Status   | Transaction Status | Description                              |
|----------------|------------------|------------------------------------------|
| Reserved       | Reserved         | A refund has been requested.             | 
| Completed      | Completed        | Refund has been successfully processed.  | 

Full [API reference](/api/#trustpay) on the payment method TrustPay.

## Product Rules
Some rules may apply to certain payment methods. These rules apply to the payment method TrustPay.

* Refunding more than the stated amount of the original transaction is possible with the payment method TrustPay. More information available in [Refund more than original amount](/faq/finance/refund-more-than-original-amount/)

* Transactions successfully received with the payment method TrustPay have no expiring date regarding refunding, as long as the receiving bank is able to process the refund

* The days and seconds active does not apply to the payment method TrustPay. The customer processes the payment from his/her own banking environment. As a result, it has a different payment flow and the setting of a days or seconds active will have no influence. <br>        
Full documentation on the lifetime of a payment link can be found on our FAQ page, [Lifetime of a payment link](/faq/api/lifetime-of-a-payment-link/)
<br>

* As it is a standard bank transfer method, an expiry date exception for TrustPay transactions has been set to 10 days

* The payment method Dotpay processes the [currency](/faq/general/which-currencies-are-supported-by-multisafepay/) Czech Koruna (CZK). 
   
 