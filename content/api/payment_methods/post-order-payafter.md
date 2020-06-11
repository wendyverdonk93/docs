---
weight: 322
meta_title: "API - Create a Pay After Delivery order - Developers MultiSafepay"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for Payment Methods, Tools and General Questions as well as the contact details of our Support and Integration Teams."
---
{{< code-block >}}
> POST - /orders 

```shell

{
    "type": "redirect",
    "gateway": "PAYAFTER",
    "order_id": "my-order-id-1",
    "currency": "EUR",
    "amount": "26000",
    "description": "Test Order Description",
    "items": "",
    "manual": "false",
    "gateway_info": {
        "birthday": "1980-01-30",
        "bankaccount": "0417164300",
        "phone": "0208500500",
        "email": "example@example.com"
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
                "name": "Item demo 1",
                "description": "",
                "unit_price": "90",
                "quantity": "2",
                "merchant_item_id": "111111",
                "tax_table_selector": "none",
                "weight": {
                    "unit": "KG",
                    "value": "12"
              }
            }
            {
                "name": "Item shipping - Flat Rate - Fixed",
                "description": "Shipping",
                "unit_price": "10",
                "quantity": "1",
                "merchant_item_id": "msp-shipping",
                "tax_table_selector": "none",
                "weight": {
                    "unit": "KG",
                    "value": "0"
                }
            }
        ]
    },
    "checkout_options": {
        "tax_tables": {
            "default": {
            },
            "alternate": [
                {
                    "name": "none",
                    "rules": [
                        {
                            "rate": "0.00"
                        }
                    ]
                }
            ]
        }
    }
}
```

> JSON Response

```shell
{
  "success": true,
  "data": {
    "order_id": "my-order-id-1",
    "payment_url": "https://payv2.multisafepay.com/connect/820UDg9zumqA13QovrRq1YVgpdTVxAlpJAP/?lang=nl_NL"
  }
}
```
> POST - /orders

```shell

{
    "type": "direct",
    "gateway": "PAYAFTER",
    "order_id": "my-order-id-1",
    "currency": "EUR",
    "amount": "26000",
    "description": "Test Order Description",
    "manual": "false",
    "gateway_info": {
        "birthday": "1979-02-22",
        "bank_account": "0417164300",
        "phone": "0208500500",
        "email": "example@multisafepay.com"
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
                "unit_price": "90",
                "quantity": "2",
                "merchant_item_id": "111111",
                "tax_table_selector": "none",
                "weight": {
                    "unit": "KG",
                    "value": "12"
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
                            "rate": "0.00"
                        }
                    ]
                }
            ]
        }
    }
}

```

> JSON Response

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
              "rate": "0.00"
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
        "amount":,
        "description": "",
        "transaction_id": 2045938,
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
{{< /code-block >}}

{{< description >}}
## Pay After Delivery
### Redirect

Creates a Pay After Delivery [Redirect](/faq/api/difference-between-direct-and-redirect/) order.

* Redirect transaction requires all fields completed properly

* All parameters shown are required field(s):

| Parameter                        | Type     | Description                                                                            |
|----------------------------------|----------|----------------------------------------------------------------------------------------|
| type                             | string | Specifies the payment flow for the checkout process. Options: direct, redirect.        |
| gateway                          | string | The unique gateway id to immediately direct the customer to the payment method. You retrieve these gateways using a gateway request. Option: PAYAFTER. |
| order_id                         | integer / string | The unique identifier from your system for the order. If the values are only numbers the type will be integer, otherwise it will be string.                                  |
| currency                         | string | The currency ([ISO-4217](https://www.iso.org/iso-4217-currency-codes.html)) you want the customer to pay with. |
| amount                           | integer | The amount (in cents) that the customer needs to pay.                                  |
| description                      | string | A text which will be shown with the order in MultiSafepay Control. If the customer's bank supports it this will also be shown on the bank statement. Max 200 characters. HTML is not supported. Use the required 'shopping-cart' object for this. |
| payment_options                  | object | Contains the redirect_url, cancel_url and [notification_url](/faq/api/how-does-the-notification-url-work/) |
| custom_info                      | object | custom_info is a 'placeholder' where the merchant can input specific data related to the transaction |
| customer                         | object | Contains the personal information of the customer. <i>Values for first_name and last_name require minimum two characters.</i> |  
| delivery                         | object | Contains the delivery information for the shipment. <i>Values for first_name and last_name require minimum two characters.</i> |
| shopping_cart                    | object | Contains all purchased items including tax class.                                      |
| checkout_options                 | object | Defines all tax classes to be used for the shopping cart items.                        |
| gateway_info                     | object | Defines certain customer data (issuer_id) needed for the credit check.                             |
| birthday                         | string | The birth date of the customer in the format yyyy-mm-dd. This is required for credit checks. (Required for Klarna & Pay After Delivery, optional for E-Invoicing on request). |
| bank_account                     | string | The formatted IBAN for the customer. This is required for credit checks. (Required for Pay After Delivery). |
| phone                            | string | The phone number where the customer can be reached. This is required for credit checks and to contact the customer in case of non-payment. |
| email                            | string | The email address where the system can send payment instructions to the customer.      |
| ip_address                       | string  | The IP address of the customer. "Required" with post payment and credit card payment methods. Due to validation of the customer IP address, we need to receive the actual IP address of the end user within the ip_address field. [More info](/faq/api/ip_address/)                                                                                              |
| forwarded_ip                     | string  | The X-FORWARDED-FOR header of the customer request when using a proxy. [More info](/faq/api/ip_address/)                                                                                                                           |

Please note that <i>first_name</i> and <i>last_name</i> in both _customer_ and _delivery_ objects require minimum two characters per entry. Failing to do so might result in unexpected errors. Given the nature of this payment method, we recommend you to always require full names (not initials, abbreviations, acronyms).

Read more about [Pay After Delivery](/payment-methods/billing-suite/pay-after-delivery/) on our documentation page.

### Direct

Creates a Pay After Delivery [Direct](/faq/api/difference-between-direct-and-redirect/) order.

* Direct transaction requires all fields completed properly

* All parameters shown are required field(s):

| Parameter                        | Type     | Description                                                                            |
|----------------------------------|----------|----------------------------------------------------------------------------------------|
| type                             | string | Specifies the payment flow for the checkout process. Options: direct, redirect.        |
| gateway                          | string | The unique gateway id to immediately direct the customer to the payment method. You retrieve these gateways using a gateway request. Option: PAYAFTER. |
| order_id                         | integer / string | The unique identifier from your system for the order. If the values are only numbers the type will be integer, otherwise it will be string.                                  |
| currency                         | string | The currency ([ISO-4217](https://www.iso.org/iso-4217-currency-codes.html)) you want the customer to pay with. |
| amount                           | integer | The amount (in cents) that the customer needs to pay.                                  |
| description                      | string | A text which will be shown with the order in MultiSafepay Control. If the customer's bank supports it this will also be shown on the bank statement. Max 200 characters. HTML is not supported. Use the required 'shopping-cart' object for this. |
| payment_options                  | object | Contains the redirect_url, cancel_url and [notification_url](/faq/api/how-does-the-notification-url-work/) |
| custom_info                      | object | custom_info is a 'placeholder' where the merchant can input specific data related to the transaction |
| customer                         | object | Contains the personal information of the customer. <i>Values for first_name and last_name require minimum two characters.</i> |  
| delivery                         | object | Contains the delivery information for the shipment. <i>Values for first_name and last_name require minimum two characters.</i> |
| shopping_cart                    | object | Contains all purchased items including tax class.                                      |
| checkout_options                 | object | Defines all tax classes to be used for the shopping cart items.                        |
| gateway_info                     | object | Defines certain customer data (issuer_id) needed for the credit check.                             |
| birthday                         | string | The birth date of the customer in the format yyyy-mm-dd. This is required for credit checks. (Required for Klarna & Pay After Delivery, optional for E-Invoicing on request). |
| bank_account                     | string | The formatted IBAN for the customer. This is required for credit checks. (Required for Pay After Delivery). |
| phone                            | string | The phone number where the customer can be reached. This is required for credit checks and to contact the customer in case of non-payment. |
| email                            | string | The email address where the system can send payment instructions to the customer.      |
| ip_address                       | string  | The IP address of the customer. "Required" with post payment and credit card payment methods. Due to validation of the customer IP address, we need to receive the actual IP address of the end user within the ip_address field. [More info](/faq/api/ip_address/)                                                                                              |
| forwarded_ip                     | string  | The X-FORWARDED-FOR header of the customer request when using a proxy. [More info](/faq/api/ip_address/)                                                                                                                           |

Please note that <i>first_name</i> and <i>last_name</i> in both _customer_ and _delivery_ objects require minimum two characters per entry. Failing to do so might result in unexpected errors. Given the nature of this payment method, we recommend you to always require full names (not initials, abbreviations, acronyms).

Read more about [Pay After Delivery](/payment-methods/billing-suite/pay-after-delivery/) on our documentation page.

{{< /description >}}