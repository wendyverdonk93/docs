---
title : "PayPal, How does it work?"
weight: 21
meta_title: "PayPal, how does it work? - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---
# How does it work?
MultiSafepay supports seamless integration with PayPal with the PayPal API. Funds are transferred directly to the merchant’s PayPal business account, while the transaction statuses and payment validation are managed by MultiSafepay. In order to integrate your PayPal Business account with MultiSafepay, the PayPal account API settings must be configured. Once the integration is completed you can receive payments through this gateway by using one of our plugins, or by implementing a custom integration with our API.

The transaction status refers to the status of the actual payment. MultiSafepay uses the order status for PayPal transactions. Since we do not collect the funds of completed PayPal transactions (as they are directly sent to your PayPal account), the financial status will remain 'initialized'.

Please note the various descriptions of statuses and how they should be interpreted:

## Transaction flow
The transaction flow shows the different possibilities a transaction is able to process. This differs per payment method.

* Order status      
The order status indicates the status of the order, such as completed, pending or rejected. 
The order status is independent of the incoming or outgoing payment of the transaction.     

* Transaction status      
The transaction status indicates the payment status of the transaction, such as pending, completed or rejected. 
Once the transaction status shows as completed, the amount of the transaction is added to your MultiSafepay balance.

| Order Status                   | Transaction Status         | Description |
|--------------------------------|--------------------------|-----------------------------------------------------------------------------------------|
| Initialized                    | Initialized              | A payment link has been generated, but no payment has been received yet.  | 
| Completed                      | Initialized              | A successful PayPal transaction has been received and the funds will be added to your PayPal balance.   | 
| Declined                       | Declined                 | Transaction has been rejected   | 
| Expired                        | Expired                  | An unfinished transaction will automatically expire after a predefined period.  | 
| Void                           | Cancelled                | Transaction has been cancelled.   | 


### Refund flow


| Order Status                    | Transaction Status        | Description |
|---------------------------------|-------------------------|-----------------------------------------------------------------------------------------|
| Reserved                        | Initialized             | A refund has been requested. | 
| Completed                       | Initialized             | Refund has been successfully processed.  | 

Full [API reference](/api/#paypal) on the payment method PayPal.


## What is the Seller Protection
PayPal Seller Protection covers you in the event of claims, chargebacks, or reversals that are a result of unauthorized purchases or items your buyer did not receive. With PayPal Seller Protection, you are covered for the full amount of all eligible transactions.

Full documentation on [What is Seller Pretection](https://www.paypal.com/cs/smarthelp/article/what-is-the-seller-protection-policy-and-what-items-aren%E2%80%99t-covered-faq1156) with PayPal transactions. 

## Product rules
Some rules may apply to certain payment methods. These rules apply to the payment method PayPal.

* Refunding more than the stated amount of the original transaction is not possible with the payment method PayPal. More information available in [Refund more than original amount](/faq/finance/refund-more-than-original-amount/)

* Transactions successfully received with the payment method PayPal have an expiring date regarding refunding.  _A payment received with PayPal can be refunded within 60 days._ After the expired period, the refund needs to be processed in a different way

* A payment link with the payment method PayPal is valid for 14 days. The lifetime of the payment link is set by PayPal. Therefore, a payment link created with the payment method PayPal will automatically expire after 14 days.<br>    
The lifetime of PayPal exceeds the lifetime of MultiSafepay, unless the lifetime falls below the 14 days <br>        
Full documentation on the lifetime of a payment link can be found on our FAQ page, [Lifetime of a payment link](/faq/api/lifetime-of-a-payment-link/)
<br>

* Uncleared transactions can only be declined or accepted within your PayPal account

* For information on which currencies are supported within the payment method PayPal, please contact PayPal.

