---
title : "Pay After Delivery, How does it work?"
weight: 21
meta_title: "Pay After Delivery, how does it work? - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---
# How does it work?
Pay After Delivery is a payment method developed and managed by our own developers at MultiSafepay.
Therefore, the payout of the transaction is guaranteed by MultiSafepay.

Pay After Delivery is an online payment method that allows the customer to pay a transaction after receiving the purchase. The customer only pays for the pages retained.

When an uncleared Pay After Delivery is received, no action is required. Our support team will process the transaction within two business days.

The customer has 14 days to complete the payment after receiving the invoice from MultiFactor.

## Shipped status

When receiving a transaction with Pay After Delivery as payment method, it is important to take the following steps.

If you agree with the received transaction (by actually sending the goods), you can change the order status from completed to shipped. More importantly, this allows Pay After Delivery to start billing the customer.

If you do not change the order status to shipped, the order will eventually expire.

* _The shipped status is therefore important for invoicing the customer and the payout of the transaction on your MultiSafepay balance._

You can adjust the order status in the original transaction in your [MultiSafepay Control](https://merchant.multisafepay.com/) via change order status.

## Payment flow
As soon as your customer selects the payment method Pay After Delivery, he or she agrees with the terms and conditions. 

1. The shipped status is important for invoicing the customer. 24 Hours after the shipped status has been set, the first email towards the customer will be sent. The customer originally has 14 days to finalize the payment

2. When no payment has been received to complete the transaction, MultiFactor will send a reminder. The second payment request is valid for 6 days     <br>             
_The first and second payment request are sent without additional cost_ 

3. When no payment has been successfully linked to the outstanding transaction after the second payment request, a third reminder will be sent. However, additional cost of &euro; 7.50 will be added to the invoice. <br>
The third payment request will be valid for 6 days

4. The fourth payment request will be increased with &euro; 12.50 and is also valid for 6 days 

5. If, after repeated payment requests, the customer does not complete the outstanding transaction, the total amount of the order will ultimately be transferred to a collection agency.


_A payment link is supplied in every invoice email we send to the customer_


## Payout transaction

The payout of a Pay After Delivery transaction will be added onto your MultiSafepay Balance. A Pay After Delivery payout will be processed 30 days after changing the status to shipped.

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
| Uncleared  | Uncleared  | When a Pay After Delivery transaction is marked with the status uncleared, Pay After Delivery will authorize or decline the transaction. No action is required.   |
| Completed  | Uncleared  | A successful Pay After Delivery transaction has been placed.   |
| Shipped    | Uncleared  | A capture has been sent to Pay After Delivery, the transaction has been confirmed. An invoice will be sent to the customer and your payout is guaranteed. |
| Shipped    | Completed  | Payout of a Pay After Delivery transaction has been received and added to your MultiSafepay Control balance.|
| Declined   | Declined   | Transaction has been rejected by Pay After Delivery. Behind the declined status in your [MultiSafepay Control](https://merchant.multisafepay.com/), the reason of the rejection is shown.     |
| Void       | Cancelled   | Transaction has been cancelled.  | 
| Expired    | Expired    | When no action is being taken within 90 days of receiving a transaction with the payment method Pay After Delivery, the transaction will automatically expire. | 

### Refund flow 

| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Initialized    | Initialized   | A refund has been requested. | 
| Completed      | Completed     | Refund has been successfully processed.  | 


Full [API reference](/api/#pay-after-delivery) on the payment method Pay After Delivery.


## Product rules
Some rules may apply to certain payment methods. These rules apply to the payment method Pay After Delivery.

* Refunding more than the stated amount of the original transaction is not possible with the payment method Pay After Delivery. More information available in [Refund more than original amount](/faq/finance/refund-more-than-original-amount/)

* Transactions successfully received with the payment method Pay After Delivery have no expiring date regarding refunding, as long as the receiving bank is able to process the refund

* The days and seconds active does not apply to the payment method Pay After Delivery. This is because the payment method is a post payment method. As a result, it has a different payment flow and the setting of a days or seconds active will have no influence. <br>        
Full documentation on the lifetime of a payment link can be found on our FAQ page, [Lifetime of a payment link](/faq/api/lifetime-of-a-payment-link/)
<br>

* When no action is being taken within 90 days of receiving a transaction with the payment method Pay After Delivery, the transaction will expire

* When a Pay After Delivery transaction has the order status shipped, there will be no time limit on refunding the transaction

* Pay After Delivery is processed in the [currency](/faq/general/which-currencies-are-supported-by-multisafepay/) Euros (EUR)

* Currently the payment method Pay After Delivery is offered in the Netherlands only.
