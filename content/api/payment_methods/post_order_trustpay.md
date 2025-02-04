---
weight: 327
meta_title: "API Reference - Create a TrustPay order - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
---
{{< code-block >}}
> POST - /orders 

```json

{
    "type": "redirect",
    "order_id": "my-order-id-1",
    "currency": "CZK",
    "amount": 1000,
    "gateway": "TRUSTPAY",
    "description": "Test order description",
    "custom_info": {},
    "payment_options": {
       "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel", 
        "close_window": true
    },
    "customer": {
        "email": "simonsmit@example.com"
        "locale": "cs_CZ"
    }
}
```

> JSON response


```json
{
  "success": true,
  "data": {
    "order_id": "my-order-id-1",
    "payment_url": "https://payv2.multisafepay.com/connect/13oElUaESR7YS2b4gUJV9oI4tUXeb1mj1D8/?lang=en_CZ"
  }
}
```
{{< /code-block >}}

{{< description >}}
## TrustPay

- See also Payment methods – [TrustPay](/payments/methods/banks/trustpay).  
- Redirect only.

**Parameters**

----------------
`type` | string | required

The payment flow for the checkout process.  
Options: `redirect`.  

----------------
`gateway` | string | required

The unique gateway identifier.  
Fixed value: `TRUSTPAY`.

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

{{< /description >}}
