---
weight: 229
meta_title: "API Reference - Direct: Flexible 3D enabled - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
aliases:
    - /api/#direct-server-to-server-flexible-3d-set-on-_true_
---
{{< code-block >}}

> POST - /orders 

```json 

{
    "type": "direct",
    "order_id": "my-order-id-1",
    "currency": "EUR",
    "amount": 10,
    "gateway": "CREDITCARD",
    "description": "Test order description",
    "payment_options": {
        "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel",
        "close_window": true
    },
    "customer": {
        "locale": "nl_NL",
        "ip_address": "123.123.123.123",
        "forwarded_ip": "",
        "first_name": "Simon",
        "last_name": "Smit",
        "address1": "Kraanspoor",
        "house_number": "39C",
        "zip_code": "1033SC",
        "city": "Amsterdam",
        "country": "NL",
        "phone": "0208500500",
        "email": "simonsmit@example.com",
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


> JSON response


```json
{
  "success": true,
  "data": {
    "amount": 10,
    "amount_refunded": 0,
    "costs": [],
    "created": "2020-02-24T15:11:23",
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
      "country_name": "The Netherlands",
      "email": "simonsmit@example.com",
      "first_name": "Simon",
      "house_number": "39C",
      "last_name": "Smit",
      "locale": "nl_NL",
      "phone1": "0208500500",
      "zip_code": "1033SC"
    },
    "description": "Test Product Description",
    "fastcheckout": "NO",
    "financial_status": "initialized",
    "items": null,
    "modified": "2020-02-24T15:11:23",
    "order_id": "my-order-id-1",
    "payment_details": {
      "account_holder_name": "",
      "account_id": null,
      "card_expiry_date": ,
      "external_transaction_id": null,
      "last4": ,
      "recurring_id": null,
      "recurring_model": null,
      "type": "MASTERCARD"
    },
    "payment_methods": [
      {
        "account_holder_name": "",
        "amount": 10,
        "card_expiry_date": ,
        "currency": "EUR",
        "description": "Test Product Description",
        "payment_description": "MasterCard",
        "status": "initialized",
        "type": "MASTERCARD"
      }
    ],
    "reason": "3DS Enrolled",
    "reason_code": "",
    "related_transactions": null,
    "status": "initialized",
    "transaction_id": 123456789
    "var1": null,
    "var2": null,
    "var3": null,
    "customer_verification": {
      "html": "<html>\n <head>\n <title>PaReq Form Submission</title>\n <script type=\"text/javascript\">\n function onLoadHandler(){ document.getElementById('PaReqForm').submit(); }\n </script>\n </head>\n <body onLoad=\"onLoadHandler();\">\n <form id=\"PaReqForm\" action=\"https://www.securesuite.co.uk/ing_retail/tdsecure/opt_in_dispatcher.jsp?VAA=B\" method=\"post\">\n <noscript>\n <center><br/>\n <h1>Processing your Transaction</h1>\n <h2>JavaScript is currently disabled or not supported by your browser.</h2><br/>\n <h3>Please click Proceed to continue the processing of your transaction.</h3>\n <input type=\"submit\" value=\"Proceed\"/>\n </center>\n </noscript>\n <input type=\"hidden\" name=\"PaReq\" value=\"eJxVkslu2zAQhl/FyL3iKss0JgTSOkhzUBEkvrg3mhrbCqwlFNXaefoOvdQtIAjzDZf5/xnCchcQ\r\nF2/ox4AWShwGt8VJXd3feZ1XxUZzqaZGy02+LtTaOOlm1bQQSvE7Cy8Pr/hh4ReGoe5aKzKeSWBX\r\npNuC37k2WnD+4+vzDyunRmracUFoMDwvrOA8fcDOCK1r0C4f35aT9AN2YvDd2MZwtLmcAbsCjGFv\r\ndzH2c8aacR/rwW2wd8cvFTZd5ruG9ftxW7fb0I09izhEillDFtvYMZEVZ8XpFmA3uS9jigaqeqgr\r\nu3r3n6v3/a5sHvXPxUqVy/KzfMrF+un3PbC0AyoX0UouOZdST4SeCzGXCtgpD65JcsknOT+H0KcK\r\nD7f8vww0i4CtP1pTJK9XAjz0XUvKLUn+G0OFg7d96KrRx0mCUPeR+k/V0wqwm5tv39MofKQua14I\r\nYZSQxmjNc5OGclpIVWpqrVSckhcAlo6yy7ypU6dnQtF/z+cPnVPCWQ==\"/>\n <input type=\"hidden\" name=\"TermUrl\" value=\"https://pay.multisafepay.com/direct/complete/?mspid=335263060\"/>\n <input type=\"hidden\" name=\"MD\" value=\"b73b9a2a8d671330null,c45d7f40236942f5b73b9a2a8d671330\"/>\n </form>\n </body>\n</html>\n",
      "type": "form"
    },
    "payment_url": "https://payv2.multisafepay.com/connect/99wi0OTuiCaTY2nwEiEOybWpVx8MNwrJ75c/?lang=nl_NL",
    "cancel_url": "http://www.example.com/client/notification?type=cancel&transactionid=apitool_"
  }
}
```
{{< /code-block >}}

{{< description >}}

### Direct: Flexible 3D enabled

Use [Flexible 3D](/payments/features/flexible-3ds/) to set whether or not to complete the transaction with [3D Secure](/security-and-legal/payment-regulations/about-3d-secure/) verification.

To enable 3D Secure, in the `POST /orders` request > `gateway_info` object, set the `flexible_3d` parameter to `true`.

**Notes:**  

- Activating Flexible 3D Secure overrides Dynamic 3D settings, so that payments are not enrolled with a 3D authentication.

- We no longer support [Flexible 3D](https://docs.multisafepay.com/tools/flexible_3d) for merchants based in Europe due to PSD2 regulations.

**Parameters**

----------------
`type` | string | required

The payment flow for the checkout process.  
Options: `direct`.

----------------
`gateway` | string | required

The unique gateway ID to direct the customer straight to the payment method.  
Option: `CREDITCARD`.

----------------
`order_id` | integer / string | required

Your unique identifier for the order.  
If the values are numbers only, the type is `integer`. Otherwise, it is `string`.  
Format: Maximum 50 characters.

----------------
`currency` | string | required

The currency you want the customer to pay in.   
Format: [ISO-4217 currency codes](https://www.iso.org/iso-4217-currency-codes.html).  

----------------
`amount` | integer | required

The amount (in cents) the customer needs to pay.

----------------
`description` | string | required

The order description that appears in your MultiSafepay account and on the customer's bank statement (if supported by the customer's bank).   
Format: Maximum 200 characters.   
HTML is **not** supported. Use the `items` or `shopping_cart` objects for this.

----------------
`payment_options` | object | required

See [payment_options (object)](/api/#payment-options-object).  

----------------
`customer` | object | required

See [customer (object)](/api/#customer-object).

----------------
`gateway_info` | object | required

Contains:  

`flexible_3d` | boolean | required

- `true`: enables 3D Secure verification
- `false`: disable 3D Secure verification

**Response**

----------------
`costs` | object

See [costs (object)](/api/#costs-object).

----------------
`payment_methods` | object

See [payment_methods (object)](/api/#payment_methods-object).

----------------

{{< /description >}}
