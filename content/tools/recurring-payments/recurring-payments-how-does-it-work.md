---
title : "Recurring payments, How does it work?"
weight: 54
meta_title: "Recurring Payments, how does it work? - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

## Recurring payments process
The standard recurring payment process allows you to easily charge your customer on a recurring basis. This is a perfect solution for monthly or annually subscriptions.

The standard process is as follows:

1. Your customer makes an Initial Payment using a credit card (Visa, Mastercard or American Express), direct debit, iDEAL or SOFORT and submits the payment

2. If this payment succeeds you will receive a recurring payment ID which can be used for all subsequent payments

3. Subsequent payments are created using the recurring payment ID and will apply the charge using the same payment details as the initial payment.

### SEPA Direct Debit
Process description:

1. The customer selects SEPA Direct Debit as a payment method on the merchant website

2. The customer fills in his/her name, full IBAN number, city and submits payment

3. If the payment was successful, you will receive a recurring payment ID in the transaction details response, which can be used for recurring payments.

<i>MultiSafepay automatically uses the Site Description and Order_ID to show on the customers; bank statements. This way the customer can easily recognize the payment.</i>

Full API documentation on the payment method Direct Debit can be found on our payment page, [Direct Debit explained](/payment-methods/direct-debit/)

#### Mandates
According to European law merchants who use SEPA Direct Debit are required to store physical mandates.

#### Pre-notification

According to European law, merchants who use recurring payments should inform their customers about any charges being made. This can be done by email, but it is sufficient to include this in your General Terms & Conditions provided the customer has explicitly agreed to those Terms & Conditions.

### Using iDEAL as an Initial payment method
1. The customer select iDEAL as a payment method on the merchant website
2. The customer submits a payment
3. If the payment was successful, you will receive a recurring payment ID in the transaction details which can be used for recurring payments
4. When creating a recurring payment, you are obligated to use the Direct Debit gateway, since this is the payment method used to follow up on the initial iDEAL payment.

### Using SOFORT Banking as an Initial payment method
1. The customer select SOFORT Banking as a payment method on the merchant website
2. The customer manually creates a payment from their bank environment
3. If the payment was successful you will receive a recurring payment ID in the transaction details which can be used for recurring payments. The recurring payment ID will only be available after the funds have actually been received, this might take up to 3 business days
4. When creating a recurring payment, you are obligated to use the Direct Debit gateway, since this is the payment method used to follow up on the initial SOFORT Banking payment.

### Credit Cards (Visa, Mastercard or American Express)
1. The customer selects a credit card as a payment method on the merchant website

2. The customer submits a payment

3. If the payment was successful, you will receive a recurring payment ID in the transaction details which can be used for recurring payments.

_Note! MultiSafepay automatically uses the Site Description and Order ID to show on the customers bank statements. This way the customer can easily recognize the payment_.

### Retry a failed recurring payment
If a customer does not have sufficient funds to process the payment this will be indicated in the transaction response. MultiSafepay does not provide automated retry functionality for recurring payments. It is the responsibility of the merchant to contact the customer or try and charge the customer again after a sufficient period of time.
## Recurring payment implementation
### Create an initial transaction
View the [API documentation](/api/) on how to create a standard transaction.

###  The Initial Payment - Status update request
If recurring payments are enabled in your account, you will receive a recurring ID when you do a [retrieve an order request](/api/#retrieve-an-order). A sample response is shown below.

```shell 
GET - /orders/{order_id}

  "success": true,
  "data": {
    "transaction_id": "",

```

Response 

```shell 

"payment_details": {
  "recurring_id": "",

```

### Processing Subsequent Payments - JSON request
This request is similar to the initial payment. However, in order to do a recurring payment, you need to include the recurring ID in the gateway info section of the request. By including the recurring ID in this request, you do not have to include any bank account or credit card details in the request. An example of this is shown below. You should still offer the customer details, amount and especially an order description.

_Note: all actual recurring payment transactions are Direct transactions in- stead of Redirect._

```shell 

POST - /orders

  "type": "direct", 
  "order_id": "", 
  "recurring_id": "" 


```

_Note: Always use the correct payment gateway for each payment method used. iDEAL and SOFORT Banking should be followed up by SEPA Direct Debit and therefore the SEPA Direct Debit gateway should be send within the JSON request. More information about this can be found in the standard integration manual on our_.

View the [API documentation](/api/#direct-debit) on how to create a recurring transaction.
