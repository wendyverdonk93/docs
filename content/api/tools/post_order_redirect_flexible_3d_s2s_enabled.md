---
weight: 1320
---
{{< code-block >}}
> POST - /orders 

```shell 

{
    "type": "redirect",
    "order_id": "my-order-id-1",
    "currency": "EUR",
    "amount": 100,
    "gateway": "CREDITCARD",
    "description": "Test Product Description",
    "payment_options": {
        "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel",
        "close_window": true
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
        "phone": "0208500500",
        "email": "example@multisafepay.com",
        "referrer": "http://example.com",
        "user_agent": "Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/38.0.2125.111 Safari/537.36"
    },
    "gateway_info": {
	"flexible_3d": true,
        "card_number": "",
        "card_holder_name": "",
        "card_expiry_date": "",
        "card_cvc": ""
    }
}

```
> JSON Response

```shell 
{
  "success": true,
  "data": {
    "order_id": "my-order-id-1",
    "payment_url": "https://payv2.multisafepay.com/connect/12bqtNOrXKvw23VfjRgt1ELeOlUcHfmZwM7/?lang=nl_NL"
  }
}

```
{{< /code-block >}}

{{< description >}}

### Redirect Server to Server, Flexible 3D set on _true_

Flexible 3D is a feature that allows you to enable/disable 3D secure at API level. The Flexible 3D mandates whether or not a transaction should be completed with the 3D secure verification or not.

Credit card transactions which are processed with the 3D Secure protocol require a form of authentication of the customer during the payment process. Setting Flexible 3D to _false_ will disable the verfication process, while activating Flexible 3D secure will override the rules of the Dynamic 3D settings, meaning that payments will not be enrolled with a 3D authentication.


| Parameter                      | Type      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| type                           | string    | Specifies the payment flow for the checkout process. Options: direct.       |
| gateway                        | string    | The unique gateway id to immediately direct the customer to the payment method. You retrieve these gateways using a gateway request. Option: VISA and MASTERCARD. |
| order_id                       | integer / string    | The unique identifier from your system for the order. If the values are only numbers the type will be integer otherwise it will be string.                   |
| currency                       | string    | The currency [ISO-4217](https://www.iso.org/iso-4217-currency-codes.html) you want the customer to pay with. |
| amount                         | integer   | The amount (in cents) that the customer needs to pay.        |
| description                    | string    | A text which will be shown with the order in MultiSafepay Control. If the customer's bank supports it this will also be shown on the bank statement. Max 200 characters. HTML is no longer supported. Use the 'items' or 'shopping_cart' objects for this. |
| payment_options                | object    | Contains the redirect_url, cancel_url and [notification_url](/faq/api/how-does-the-notification-url-work/)         |
| customer                       | object    | Contains personal information about the customer. |
| gateway_info                   | object    | Defines certain customer data (payment details). |
| flexible_3d                    | boolean   | True, enable the 3D secure authentication. False, disable the 3D secure authentication.  |
| term_url                       | string    | URL that is used to instruct the card issuer where to redirect the authorisation query. |

{{< description >}}