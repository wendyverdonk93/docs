---
weight: 301
meta_title: "API Reference - Create AfterPay order - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
---
{{< code-block >}}

> POST - /orders

```json

{
    "type": "direct",
    "gateway": "AFTERPAY",
    "order_id": "my-order-id-1",
    "currency": "EUR",
    "amount": 26000,
    "description": "Test order description",
    "manual": "false",
    "gateway_info": {
        "birthday": "1970-07-10",
        "gender": "mr",
        "phone": "0612345678",
        "email": "rejection@afterpay.nl"
    },
    "payment_options": {
        "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel", 
        "close_window": ""
    },
    ...
    "shopping_cart": {
        "items": [
            {
                "name": "Geometric Candle Holders",
                "description": "",
                "unit_price": 90,
                "quantity": 2,
                "merchant_item_id": "111111",
                "tax_table_selector": "none",
                "weight": {
                    "unit": "KG",
                    "value": 12
                }
            },
        ]
    },
    "checkout_options": {
        "tax_tables": {
            "alternate": [
                {
                    "name": "none",
                    "rules": [
                        {
                            "rate": 0.00
                        }
                    ]
                }
            ]
        }
    }
}

```

> JSON response

```shell

{
  "success": true,
  "data": {
    "amount": 26000,
    "amount_refunded": 0,
    "checkout_options": {
      "alternate": [
        {
          "name": "none",
          "rules": [
            {
              "country": "",
              "rate": 0.00
            }
          ]
        }
      ],
      "default": {
        "rate": 0.21,
        "shipping_taxed": true
      }
    },
    "costs": [
      {
        "transaction_id": 2045938,
        "amount": ,
        "description": "",
        "type": "SYSTEM"
      },
      {
        "amount":,
        "description": "",
        "transaction_id": 2045939,
        "type": "SYSTEM"
      }
    ],
    "created": "2019-01-12T13:55:38",
    "currency": "EUR",
    "custom_info": {
    },
    ...
    
    "status": "uncleared",
    "transaction_id": 4022655,
    "payment_url": " https://payv2.multisafepay.com/connect/99wi0OTuiCaTY2nwEiEOybWpVx8MNwrJ75c/?lang=en_US",
    "cancel_url": " http://www.example.com/client/notification?type=cancel&transactionid=apitool"
  }
}
```
> POST - /orders

```json

{
    "type": "redirect",
    "gateway": "AFTERPAY",
    "order_id": "my-order-id-1",
    "currency": "EUR",
    "amount": 26000,
    "description": "Test order description",
    "items": "",
    "manual": "false"
    ...
    "shopping_cart": {
        "items": [
            {
                "name": "Item demo 1",
                "description": "",
                "unit_price": 90,
                "quantity": 2,
                "merchant_item_id": "111111",
                "tax_table_selector": "none",
                "weight": {
                    "unit": "KG",
                    "value": 12
                }
            },
            {
                "name": "Item shipping - Flat Rate - Fixed",
                "description": "Shipping",
                "unit_price": 10,
                "quantity": 1,
                "merchant_item_id": "msp-shipping",
                "tax_table_selector": "none",
                "weight": {
                    "unit": "KG",
                    "value": 0
                }
            }
        ]
    },
    "checkout_options": {
        "tax_tables": {
            "alternate": [
                {
                    "name": "none",
                    "rules": [
                        {
                            "rate": 0.00
                        }
                    ]
                }
            ]
        }
    }
}
```
> JSON response

```json
{
  "success": true,
  "data": {
    "order_id": "my-order-id-1",
    "payment_url": "https://payv2.multisafepay.com/connect/13sEMtA491h823BLOx5Upa9H9XGEpYeUEg9/?lang=en_US"
  }
}
```
{{< /code-block >}}
{{< description >}}

## AfterPay
See also Payment methods – [AfterPay](/payments/methods/billing-suite/afterpay/).

### AfterPay - direct 

**Parameters**

----------------
`type` | string | required

The payment flow for the checkout process.  
Options: `redirect`, `direct`.

----------------
`gateway` | string | required

The unique gateway identifier that directs the customer straight to the payment method.  
Fixed value: `AFTERPAY`. 

----------------
`order_id` | integer / string | required

Your unique identifier for the order.  
If the values are numbers only, the type is `integer`, otherwise it is `string`.  
Format: Maximum 35 characters.

----------------
`currency` | string | required

The currency you want the customer to pay in.   
Format: [ISO-4217 currency codes](https://www.iso.org/iso-4217-currency-codes.html).  

----------------
`amount` | integer | required

The amount (in cents) the customer needs to pay.

----------------
`description` | string | required

Text displayed with the order in your MultiSafepay account, and on the customer's bank statement (if supported by the bank).  
Max. 200 characters.  
HTML formatting is not supported. To add descriptions in HTML format, use the `items` or `shopping_cart` objects instead.

----------------
`manual` | string | required

Fixed value: `false`.

----------------
`gateway_info` | object  | required

The customer data (`issuer_id`) required for conducting credit checks.

Contains:

`birthday` | object | required

The customer's date of birth.  
In the Netherlands and Belgium, this is required for credit checks.  
Format: yyyy-mm-dd. 

`gender` | string | required

The customer's personal title.  
Options: `mr`, `mrs`, `miss`. 

`phone` | string | required

The customer's phone number.  
Required for credit checks and to contact the customer in case of non-payment.

`email` | string | required

The email address for sending payment instructions to the customer.

----------------
`payment_options` | object | required

See [payment_options (object)](/api/#payment-options-object). 

----------------
`shopping_cart` | object

See [shopping_cart.items (object)](/api/#shopping_cartitems).

----------------
`customer` | object | required

See [customer (object)](/api/#customer-object).

----------------
`delivery` | object

See [delivery (object)](/api/#delivery-object).

----------------
`items` | object

See [items (object)](/api/#items-object/).

----------------
`checkout_options` | object

The definitions for the VAT class.  

----------------

### AfterPay - redirect

**Parameters**

----------------
`type` | string | required

The payment flow for the checkout process.  
Options: `redirect`, `direct`.

----------------
`gateway` | string | required

The unique gateway ID that immediately directs the customer to the payment method.  
Fixed value: `AFTERPAY`. 

----------------
`order_id` | integer / string | required

Your unique identifier for the order.  
If the values are numbers only, the type is `integer`, otherwise it is `string`.  
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
`delivery` | object

See [delivery (object)](/api/#delivery-object).

----------------
`shopping_cart` | object

See [shopping_cart.items (object)](/api/#shopping_cartitems).

----------------
`items` | object

See [items (object)](/api/#items-object/).

----------------
`checkout_options` | object

The definitions for the VAT class.

**Response**

----------------
`costs` | object

See [costs (object)](/api/#costs-object).

----------------

{{< /description >}}
