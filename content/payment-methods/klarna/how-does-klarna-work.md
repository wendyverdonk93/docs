---
title : "Klarna, How does it work?"
weight: 21
meta_title: "Klarna, how does it work? - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---
# How does it work?
## Integration
Before the integration can start, every merchant needs to sign an additional agreement with Klarna for the pricing and in order to get a Klarna Merchant Number (EID) and Shared Secret (Password). These credentials should be sent to MultiSafepay in order for us to be able to configure the Klarna Gateway within your Merchant Account. MultiSafepay will give all the necessary support during this process and when it is possible, facilitates the contract.

Once the Klarna Gateway is configured you can start your integration using our plugins or by creating your own implementation with our [API](/api/).

## Activate an order
After a customer has chosen to pay with Klarna, MultiSafepay will create a Klarna transaction which is "Not Shipped". After a merchant ships the products to the customer, the order needs to be activated to start the communication process to the customer. After 14 Business days MultiSafepay will receive the funds from Klarna and add the amount to your MultiSafepay Control balance.

To activate a Klarna Order you need to log in to [MultiSafepay Control](https://merchant.multisafepay.com) and go to the transaction details of the Klarna order. In the Order Details section there is a _Change Order Status_ button. Here you can change the status to _Shipped_ and provide Track & Trace details if desired.

Klarna does not support an Auto-Ship function, all Klarna Orders have to be manually activated.

## Reservation Number & Invoice Number
For every Klarna Transaction Klarna will generate a Reservation Number and Invoice Number. Once the transaction has been created at Klarna but the order has not yet been activated by Klarna the Reservation Number can be found in MultiSafepay Control under the specific Klarna order in the Transaction details. This Reservation Number can be used for merchants to contact Klarna about any questions in this stage of the process.

Once a Klarna Order has been Shipped you can view the Klarna Invoice Number in MultiSafepay Control under the specific Klarna order in the Transaction details. This Klarna Invoice Number can be used for merchants to contact Klarna about any questions in this stage of the process.

All questions related to Klarna Orders and Transactions should be communicated directly to Klarna via <merchant@klarna.com>

## Statuses
MultiSafepay uses both Order and Transaction statuses for Klarna Transactions. The Transaction Status refers to the status of the actual payment while the order status only refers to the Order Status. Below you can find a description of what the statuses are and how they should be interpreted.

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
| Completed  | Initialized  | A successful Klarna transaction has been placed.   |
| Shipped    | Initialized  | A capture has been sent to Klarna, the transaction has been confirmed. An invoice will be sent to the customer and your payout is guaranteed. |
| Shipped    | Completed  | Payout of a Klarna transaction has been received and added to your MultiSafepay Control balance.|
| Declined   | Declined   | Transaction has been rejected by Klarna. Behind the declined status in your [MultiSafepay Control](https://merchant.multisafepay.com/), the reason of rejection is shown.     |
| Void       | Cancelled   | Transaction has been cancelled.  | 
| Expired    | Expired    | When no action is being taken when receiving a transaction with the payment method Klarna, the transaction will automatically expire. | 

### Refund flow 

| Order Status                      | Transaction Status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Initialized    | Completed   | A refund has been requested. | 
| Completed      | Completed   | Refund has been successfully processed.  | 


Full [API reference](/api/#klarna) on the payment method Klarna.


## Reconciliation & Reporting
MultiSafepay supports a fully reconciled implementation of Klarna. This means that all Klarna Payments are received by MultiSafepay and forwarded to the specific merchant accounts. By having a fully reconciled implementation of Klarna we are able to add Klarna to all existing reports like the financial report and an MT940 report.

After 14 business days MultiSafepay will receive funds from Klarna and make them available to all merchants. After 18-19 days, funds are made available in your merchant account balance.

## Customisation of invoices
Klarna enables all merchants to customise the Invoices which are being send to your customers. In order to change the styling, you need to log in to your Klarna Merchant Account and make the changes there. All questions related to this subject should be referred directly to Klarna.

## Product rules
Some rules may apply to certain payment methods. These rules apply to the payment method Klarna.

* Refunding more than the stated amount of the original transaction is not possible with the payment method Klarna. More information available in [Refund more than original amount](/faq/finance/refund-more-than-original-amount/)

* Transactions successfully received with the payment method Klarna have no expiring date regarding refunding, as long as the receiving bank is able to process the refund

* The days and seconds active does not apply to the payment method Klarna. This is because the payment method is a post payment method. As a result, it has a different payment flow and the setting of a days or seconds active will have no influence. <br>        
Full documentation on the lifetime of a payment link can be found on our FAQ page, [Lifetime of a payment link](/faq/api/lifetime-of-a-payment-link/)
<br>

* Klarna is processed in the [currency](/faq/general/which-currencies-are-supported-by-multisafepay/) Euros (EUR).

* Currently the payment method Klarna is offered in Austria, Germany and the Netherlands.
