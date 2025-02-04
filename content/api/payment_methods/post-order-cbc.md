---
weight: 309
meta_title: "API Reference - Create a CBC order - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
---
{{< code-block >}}

> POST - /orders

```json

{
    "type": "redirect",
    "order_id": "my-order-id-1",
    "gateway": "CBC",
    "currency": "EUR",
    "amount": 1000,
    "description": "Test order description",
    "payment_options": {
       "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel", 
        "close_window": true
    },
    "customer": {
        "locale": "nl_BE"
    }
}
```
> JSON response

```json
{
    "success": true,
    "data": {
        "order_id": "my-order-id-1",
        "payment_url": "https://payv2.multisafepay.com/connect/13oElUaESR7YS2b4gUJV9oI4tUXeb1mj1D8/?lang=nl_NL"
    }
}
```
> POST - /orders

```json
{
    "type": "direct",
    "order_id": "my-order-id-1",
    "gateway": "CBC",
    "currency": "EUR",
    "amount": 1000,
    "description": "Test order description",
    "manual": false,
    "payment_options": {
        "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel",
        "close_window": true
    },
    "customer": {
        "locale": "nl_BE",
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
        "referrer": "https://example.com",
        "user_agent": "Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/38.0.2125.111 Safari/537.36"
    }
}
```

> JSON Repsonse
```json
{
  "success": true,
  "data": {
    "amount": 1000,
    "amount_refunded": 0,
    "costs": [
      {
        "amount":,
        "description": "",
        "transaction_id": 123456789
        "type": "SYSTEM"
      },
      {
        "transaction_id": 123456789,
        "amount":,
        "description": "",
        "type": "SYSTEM"
      }
    ],
    "created": "2019-03-08T10:15:37",
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
      "phone1": "0208500500",
      "locale": "nl_BE",
      "phone1": "0208500500",
      "zip_code": "1033SC"
    },
    "description": "Test order description",
    "fastcheckout": "NO",
    "financial_status": "initialized",
    "items": null,
    "modified": "2019-03-08T10:15:37",
    "order_id": "my-order-id-1",
    "payment_details": {
      "account_holder_name": null,
      "account_id": null,
      "external_transaction_id": 325062361,
      "recurring_id": null,
      "recurring_model": null,
      "type": "CBC"
    },
    "payment_methods": [
      {
        "amount": 1000,
        "currency": "EUR",
        "description": "Test order description",
        "external_transaction_id": 325062361,
        "payment_description": "CBC",
        "status": "initialized",
        "type": "CBC"
      }
    ],
    "reason": "",
    "reason_code": "",
    "related_transactions": null,
    "status": "initialized",
    "transaction_id": 123456789
    "payment_url": "https://www.cbc.be/olpayment?langWebSite=N&olpId=S132&olpCtx=%2FH8s4RM8GN%2FSKLOcUoTBBPus%2BWBbXCz9ChR12y5ozVDe8Rc70DjFQNQy2TaiSnTOEQkziFEQmgQy%2BHDxrqqzB%2F8I1yk5zE0%"
  }
}
```

{{< /code-block >}}

{{< description >}}
## CBC
See also Payment methods – [CBC](/payments/methods/banks/cbc).

### CBC - redirect

**Parameters**

----------------
`type` | string | required

The payment flow for the checkout process.  
Options: `direct`, `redirect`, `paymentlink`.  

----------------
`gateway` | string | required

The unique gateway identifier to direct the customer straight to the payment method.  
Fixed value: `CBC`.

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

### CBC - direct

**Parameters**

----------------
`type` | string | required

The payment flow for the checkout process.  
Options: `direct`, `redirect`, `paymentlink`.  

----------------
`gateway` | string | required

The unique gateway identifier to direct the customer straight to the payment method.  
Fixed value: `CBC`.

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

**Response**

----------------
`costs` | object

See [costs (object)](/api/#costs-object).

---------------- 
`payment_methods` | object

See [payment_methods (object)](/api/#payment_methods-object).

----------------


{{< /description >}}