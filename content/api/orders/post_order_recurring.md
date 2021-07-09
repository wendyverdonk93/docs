---
weight: 230
meta_title: "API Reference - Recurring payments - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
---

{{< code-block >}}
>  POST - /orders

```json
{
   "type":"redirect",
   "gateway":"CREDITCARD",
   "order_id":"my-order-id-1",
   "currency":"EUR",
   "recurring_model":"unscheduled",
   "recurring_id":"hC6HdH7_5Tg",
   "recurring_flow":"token",
   "amount":10000,
   "description":"Tokenization - ALL - Original unscheduled",
   "payment_options":{
      "notification_url":"http://www.example.com/client/notification?type=notification",
      "redirect_url":"http://www.example.com/client/notification?type=redirect",
      "cancel_url":"http://www.example.com/client/notification?type=cancel",
      "close_window":true
   },
   "customer":{
      "locale":"en_NL",
      "ip_address":"85.149.25.654",
      "forwarded_ip":"",
      "first_name":"null",
      "last_name":"null",
      "address1":"Kraanspoor",
      "house_number":"39",
      "zip_code":"1033 SC",
      "city":"Amsterdam",
      "state":"",
      "country":"NL",
      "birthday":"07061993",
      "gender":"male",
      "phone":"0612345678",
      "email":"example@multisafepay.com",
      "referrer":"http://example.com",
      "user_agent":"Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/38.0.2125.111 Safari/537.36",
      "reference":"AutoQAReference"
   }
}
```

> JSON Response

```json
{
   "success":true,
   "data":{
      "order_id":"my-order-id-1",
      "payment_url":"https://payv2.multisafepay.com/connect/82v6HsoQhaR823uIZ7hexDMwQyielzLrdox/?lang=nl_NL"
   }
}
```

{{< /code-block >}}

{{< description >}}
## Recurring Payment

A recurring payment can be initiated using [tokenization](/tokenization/tokenization-api-level/) for the following payment methods:

* VISA
* MasterCard
* Maestro
* Bancontact
* American Express
* iDEAL
* SOFORT
* Direct debit

iDEAL, Bancontact and SOFORT can be used for an initial payment as well, and followed up by a recurring payment with SEPA Direct Debit. A standard transaction must first be created with recurring payments enabled. The token can then be requested by [retreiving an order](https://docs.multisafepay.com/api/#retrieve-an-order) and payments can be initiated repeatedly by using [recurring payments](/tools/recurring-payments)

For more information please visit our documentation page to read more about [recurring payments](/tools/recurring-payments) and the fields required for [tokenization](/tokenization/tokenization-api-level/).

**Parameters**

----------------

__type__ | string

Specifies the payment flow for the checkout process. Options: direct.

----------------
__gateway__ | string

Specifies the payment method used for the checkout process. Options: AMEX, DIRDEB, MASTERCARD, VISA. DIRDEB is to be used after initial payment with IDEAL, DIRECTBANK (Sofort) and DIRDEB. 

----------------
__order_id__ | integer / string

The unique identifier from your system for the order. If the values are only numbers the type will be integer, otherwise it will be string.

----------------
__recurring_id__ | integer

The unique recurring id used for recurring payments.

----------------
__recurring_flow__ | string

The tokenization method used to create a recurring payment. Options: token

----------------

__recurring_model__ | string

The type of recurring method used in the transaction request. Options: unscheduled, sunscription, cardonfile

----------------

__currency__ | string

The currency [ISO-4217](https://www.iso.org/iso-4217-currency-codes.html) you want the customer to pay with. 

----------------
__amount__ | integer

The amount (in cents) that the customer needs to pay.

----------------
__description__ | string

A text which will be shown with the order in your MultiSafepay account. If the customer's bank supports it this description will also be shown on the customer's bank statement. Max. 200 characters. HTML is not supported. Use the 'items' or 'shopping_cart' objects for this.

----------------
__payment_options__ | object

----------------
__notification_url__ | string

Endpoint where we will send the notifications to [notification_url](/developer/api/notification-url)

----------------
__notification_method__ | string

Sends push notification (POST,GET) default: GET.

----------------
__redirect_url__ | string

Customer will be redirected to this page after a successful payment. In the event that the transaction is marked with the status [uncleared](/faq/general/multisafepay-glossary/#uncleared), the customer will also be redirected to the thank-you page of the webshop. The uncleared status will not be passed on to the customer who will experience the payment as successful at all times.

----------------
__cancel_url__ | string

Customer will be redirected to this page after a failed payment.

----------------

__close_window__ | bool (optional)


Options: true, false. Set to true if you want to display the MultiSafepay payment page in a new window and want to close it automatically after the payment process.  

----------------

{{< /description >}}
