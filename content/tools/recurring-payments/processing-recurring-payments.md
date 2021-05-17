---
title : "Processing recurring payments"
weight: 52
meta_title: "Processing recurring payments - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
aliases:
    - /tools/recurring-payments/recurring-payments-how-does-it-work/
---

## Overview
|  Step | Description  |   
|---|---|
| 1.  | Ensure the payment gateway is configured to the payment method. {{ < br > }} SEPA Direct Debit: `DIRDEB` {{ < br > }}  Credit cards: `VISA`, `MASTERCARD`, or `AMEX`  |   
| 2.  | The customer initiates the first payment.  {{ < br > }} SEPA Direct Debit: iDEAL, SOFORT Banking {{ < br > }} Credit cards: Visa, Mastercard, American Express  |   
| 3.  | When the payment is complete, make a `GET /orders` request to retrieve the transaction details.   |  
| 4. | The response contains a `recurring_id` which is used to make recurring payments using the same payment details as the initial transaction.  |  


**Note:** MultiSafepay automatically uses the `Site Description` and `Order ID` to identify the transaction on the customer's bank statement.

### Retrying failed recurring payments
When the transaction is declined, the reason will be supplied in the response of the transaction. The transaction may, for example, be refused due to insufficient funds. MultiSafepay does not provide automated retry functionality for recurring payments. It is the responsibility of the merchant to contact the customer or try and charge the customer again after a sufficient period of time.


## Create an initial transaction
View the [API documentation](/api) on how to create a standard transaction.

###  The Initial Payment - Status update request
When recurring is enabled in your MultiSafepay Control, you will receive a recurring ID when you do a [retrieve an order request](/api/#retrieve-an-order) 

A sample response is shown below.

```shell 
GET - /orders/{order_id}

  "success": true,
  "data": {
    "transaction_id": "",

```

> Response 

```shell 

"payment_details": {
  "recurring_id": "",

```

### Processing Subsequent Payments - JSON request
The recurring request is similar to the initial payment. However, in order to submit a recurring payment, you need to include the recurring ID in the gateway info section of the request. By including the recurring ID in this request, you do not have to include any bank account or credit card details in the request. An example of this is shown below. You should still offer the customer details, amount and especially an order description.

_**All actual recurring payment transactions use parameter type "direct" instead of "redirect".**_

```shell 

POST - /orders

  "type": "direct", 
  "order_id": "", 
  "recurring_id": "" 

```

Always use the correct payment gateway for each payment method used. Visa, Mastercard or American Express should be sent as gateway within the JSON request. More information about this can be found in the standard integration manual on our [API Documentation page](/api/#recurring-payment).

### Processing recurring payments from another payment service provider

If you process recurring payments already with another payment service provider, you can not use recurring payments for these customers. However, you can make use of a 'Direct request' [Direct Debit](https://docs.multisafepay.com/api/#direct-sepa-direct-debit) instead with the retrieved IBAN and account holder name.



