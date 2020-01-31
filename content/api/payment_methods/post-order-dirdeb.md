---
weight: 341 
meta_title: "API - Create a SEPA Direct Debit order - Developers MultiSafepay"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---
{{< code-block >}}
> POST - /orders

```shell
{
    "type": "redirect",
    "order_id": "my-order-id-1",
    "gateway": "DIRDEB",
    "currency": "EUR",
    "amount": "1000",
    "description": "Test Order Description",
    "payment_options": {
       "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel", 
        "close_window": ""
    },
    "customer": {
        "locale": "nl_NL"
    }
}
```
> JSON Response

```shell
{
    "success": true,
    "data": {
        "order_id": "my-order-id-1",
        "payment_url": "https://payv2.multisafepay.com/connect/13oElUaESR7YS2b4gUJV9oI4tUXeb1mj1D8/?lang=nl_NL"
    }
}
```

> POST - /orders

```shell

{
    "type": "direct",
    "order_id": "my-order-id-1",
    "gateway": "DIRDEB",
    "recurring_id": "9989709237996847064",
    "currency": "EUR",
    "amount": "1000",
    "description": "Test Order Description",
    "manual": "false",
    "payment_options": {
        "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel",
        "close_window": ""
    },
    "customer": {
        "locale": "nl_NL",
        "ip_address": "89.20.162.110",
        "forwarded_ip": "",
        "first_name": "Testperson-nl",
        "last_name": "Approved",
        "address1": "Kraanspoor",
        "house_number": "39C",
        "zip_code": "1033 SC",
        "city": "Amsterdam",
        "country": "NL",
        "email": "example@multisafepay.com",
        "referrer": "http://test.com",
        "user_agent": "Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/38.0.2125.111 Safari/537.36"
    }
}
```
> JSON Response

```shell
{
  "success": true,
  "data": {
    "amount": 1000,
    "amount_refunded": 0,
    "costs": [],
    "created": "2020-01-31T10:28:31",
    "currency": "EUR",
    "custom_info": {
      "custom_1": null,
      "custom_2": null,
      "custom_3": null
    },
    "customer": {
      "address1": "Kraanspoor",
      "city": "Amsterdam",
      "country": "NL",
      "country_name": "Netherlands",
      "email": "example@multisafepay.com",
      "first_name": "Testperson-nl",
      "house_number": "39C",
      "last_name": "Approved",
      "locale": "nl_NL",
      "phone1": "0208500500",
      "zip_code": "1033SC"
    },
    "description": "Test Order Description",
    "fastcheckout": "NO",
    "financial_status": "initialized",
    "items": null,
    "modified": "2020-01-31T10:28:31",
    "order_id": "my-order-id-1",
    "payment_details": {
      "account_bic": "ABNANL2A",
      "account_holder_name": "Testperson-nl",
      "account_iban": "NL87ABNA0000000001",
      "account_id": 1,
      "external_transaction_id": "7202003040376730",
      "issuer_id": 3151,
      "recurring_id": "9989672984696715704",
      "recurring_model": null,
      "type": "DIRDEB"
    },
    "payment_methods": [
      {
        "account_bic": "ABNANL2A",
        "account_holder_name": "Test-person-nl",
        "account_iban": "NL87ABNA0000000001",
        "account_id": 1,
        "amount": 1000,
        "currency": "EUR",
        "description": "Test Order Description",
        "external_transaction_id": "7202003040376730",
        "payment_description": "Direct Debit",
        "status": "initialized",
        "type": "DIRDEB"
      }
    ],
    "reason": "",
    "reason_code": "",
    "related_transactions": null,
    "status": "initialized",
    "transaction_id": 4037673,
    "payment_url": "http://www.example.com/client/notification?type=redirect&transactionid=my-order-id-12",
    "cancel_url": "http://www.example.com/client/notification?type=cancel&transactionid=my-order-id-12"
  }
}
```

{{< /code-block >}}
{{< description >}}
## SEPA Direct Debit
### Redirect
When submitting a [SEPA Direct Debit](https://www.ecb.europa.eu/paym/integration/retail/sepa/html/index.en.html), the transaction data is checked.    

* If approved, we return the status `initialized`.
* After midnight, the transaction will be forwarded to our bank and the status changes to `uncleared`.
* Once the funds are received on our bank account, the status changes to `completed`.

* All parameters shown are required field(s) for a SEPA _Redirect_ Direct Debit transaction.

| Parameter                      | Type      | Description                                                                             |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| type                           | string  | Specifies the payment flow for the checkout process. Options: direct, redirect, checkout, paymentlink.
| gateway                        | string  | The unique gateway id to immediately direct the customer to the payment method. You retrieve these gateways using a gateway request. Options: IDEAL. |
| order_id                       | integer / string  | The unique identifier from your system for the order. If the values are only numbers the type will be integer otherwise it will be string.                                    |
| currency                       | string  | The currency [ISO-4217](https://www.iso.org/iso-4217-currency-codes.html) you want the customer to pay with. |
| amount                         | integer  | The amount (in cents) that the customer needs to pay.                                   |
| description                    | string  | A free text description which will be shown with the order in MultiSafepay Control. If the customers bank supports it this description will also be shown on the customer`s bank statement. |
| payment_options             | object    |                             |
| notification_url            | string    | Endpoint where we will send the notifications to. [notification_url](/faq/api/how-does-the-notification-url-work/)                                |
| redirect_url                | string    | Customer will be redirected to this page after a successful payment. |
| cancel_url                  | string    | Customer will be redirected to this page after a failed payment.  | 
| customer                    | object    |                                 |
| locale                      | string    | Displays the correct language and payment methods on the Payment page. It also has an influence on sending the set email templates. Use the format ab_CD with [ISO 639](https://www.iso.org/iso-639-language-codes.html) language codes and [ISO 3166](https://www.iso.org/iso-3166-country-codes.html) country codes. Default: en_US. | 


### Direct

* All parameters shown are required field(s) for a SEPA Direct Debit _Direct_ transaction.

| Parameter                       | Type     | Description                                                                             |
|---------------------------------|----------|-----------------------------------------------------------------------------------------|
type                             | string | Specifies the payment flow for the checkout process. Options: direct, redirect, checkout, paymentlink. |
gateway                           | string | The unique gateway id to immediately direct the customer to the payment method. You retrieve these gateways using a gateway request. Options: DIRDEB. |
order_id                          | integer / string | The unique identifier from your system for the order. If the values are only numbers the type will be integer otherwise it will be string.                                   |
currency                          | string | The currency ([ISO-4217](https://www.iso.org/iso-4217-currency-codes.html)) you want the customer to pay with. |
amount                            | integer | The amount (in cents) that the customer needs to pay.                                   |
description                       | string | A text which will be shown with the order in MultiSafepay Control. If the customer’s bank supports it this will also be shown on the bank statement. Max. 200 characters. HTML is no longer supported. Use the 'items' or 'shopping_cart' objects for this.  |
payment_options                   | object | Contains the redirect_url, cancel_url and [notification_url](/faq/api/how-does-the-notification-url-work/)                             |
customer                          | object | Contains the personal information of the customer.                                      |
| ip_address                      | string  | The IP address of the customer. "Required" with post payment and credit card payment methods. Due to validation of the customer IP address, we need to receive the actual IP address of the end user within the ip_address field. [More info](/faq/api/ip_address/)  |
| locale	|  string | Displays the correct language and payment methods on the Payment page. It also has an influence on sending the set email templates. Use the format ab_CD with [ISO 639](https://www.iso.org/iso-639-language-codes.html) language codes and [ISO 3166](https://www.iso.org/iso-3166-country-codes.html) country codes. | 
gateway_info                      | object |
recurring_id                       | string | The unique recurring id used for recurring payments.                                               |


Please make sure you check out our dedicated documentation for [Direct Debit](/payment-methods/direct-debit/)

### SEPA Direct Debit transaction with an IBAN

It is possible to process a Direct Debit transaction with an IBAN. In that case, the following parameters are required:

| Parameter                       | Type     | Description                                                                             |
|---------------------------------|----------|-----------------------------------------------------------------------------------------|
| gateway_info                    | object | Contains the issuer_id. |
|account_id	| string |	IBAN to be charged for the transaction.|
|account_holder_name	|  string  | The customer’s name here if provided in transaction request. |
| account_holder_city | string | The customer’s city here if provided in transaction request.
| account_holder_country	| string | The customer’s country here if provided in transaction request. |
|  account_holder_iban	 |  string |  IBAN to be charged for the transaction. |
| account_holder_bic  | string | The BIC code related to the IBAN | 
|  emandate  | string | For your own adminstration, put the e-mandate here. |


{{< /description >}}