---
weight: 311
meta_title: "API - Creates an E-invoicing order - Developers MultiSafepay"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for Payment Methods, Tools and General Questions as well as the contact details of our Support and Integration Teams."
---
{{< code-block >}}

> POST - /orders

```shell

{
    "type": "direct",
    "gateway": "EINVOICE",
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
        "email": "example@multisafepay.com"
    },
    "payment_options": {
        "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel", 
        "close_window": ""
    },
    ...
    },
    "shopping_cart": {
        "items": [
            {
                "name": "Item demo 1",
                "description": "",
                "unit_price": "90",
                "quantity": "2",
                "merchant_item_id": "666666",
                "tax_table_selector": "none",
                "weight": {
                    "unit": "KG",
                    "value": "12"
            },
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
            },
            "alternate": [
                {
                    "name": "none",
                    "rules": [
                        {
                            "rate": "0.00"
                        }
                    ]
                },
                {
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
        "transaction_id": 2340676,
        "order_id": "my-order-id-1",
        "created": "2017-09-29T16:13:10",
        "currency": "EUR",
        "amount": 26000,
        "description": "Test Order Description",
        "items": "",
        "amount_refunded": 0,
        "status": "completed",
        "financial_status": "initialized",
        "reason": "",
        "reason_code": "",
        "fastcheckout": "NO",
        "modified": "2017-09-29T16:13:10",
        "customer": {
        ...
        "payment_details": {
            "recurring_id": null,
            "type": "",
            "account_id": 10071970,
            "account_holder_name": null,
            "external_transaction_id": 2379429850
        },
        "shopping_cart": {
            "items": [
                {
                    "name": "Item demo 1",
                    "description": "",
                    "unit_price": "90.00",
                    "currency": "EUR",
                    "quantity": 2,
                    "merchant_item_id": 666666,
                    "tax_table_selector": "none",
                    "cashback": "",
                    "image": "",
                    "product_url": "",
                    "weight": {
                        "unit": "KG",
                        "value": 12
                    },
                    "options": []
                },
                {
                    "name": "Item shipping - Flat Rate - Fixed",
                    "description": "Shipping",
                    "unit_price": "10.00",
                    "currency": "EUR",
                    "quantity": 1,
                    "merchant_item_id": "msp-shipping",
                    "tax_table_selector": "none",
                    "cashback": "",
                    "image": "",
                    "product_url": "",
                    "weight": {
                        "unit": "KG",
                        "value": 0
                    },
                    "options": []
                }
            ]
        },
        "checkout_options": {
            "default": {
            },
            "alternate": [
                {
                {
                    "name": "none",
                    "rules": [
                        {
                            "rate": "0.00",
                            "country": ""
                        }
                    ]
                }
            ]
        },
        "order_adjustment": {
            "total_adjustment": "0.00",
            "total_tax": "0.00"
        },
        "order_total": "260.00",
        "costs": [],
        "payment_url": "http://www.example.com/client/?action=notification&type=redirect&transactionid=2340676",
        "cancel_url": "http://www.example.com/client/?action=notification&type=cancel&transactionid=2340676"
    }
}
```

> POST -/orders
```shell
{
    "type": "redirect",
    "gateway": "EINVOICE",
    "order_id": "my-order-id-1",
    "currency": "EUR",
    "amount": "26000",
    "description": "Test Order Description",
    "manual": "false",
    "gateway_info": {
        "email": "example@multisafepay.com"
    },
    "payment_options": {
        "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel", 
        "close_window": ""
    },
    ...
    },
    "shopping_cart": {
        "items": [
            {
                "name": "Geometric Candle Holders",
                "description": "",
                "unit_price": "90",
                "quantity": "2",
                "merchant_item_id": "11111",
                "tax_table_selector": "none",
                "weight": {
                    "unit": "KG",
                    "value": "12"
                }
            },
            {
                "name": "Flat Rate - Fixed",
                "description": "Shipping",
                "unit_price": "10",
                "quantity": "1",
                "merchant_item_id": "123456",
                "tax_table_selector": "none",
                "weight": {
                    "unit": "KG",
                    "value": "0"
                }
            }
        ]
    },
    "checkout_options": {
            },
            "alternate": [
                {
                    "name": "none",
                    "rules": [
                        {
                            "rate": "0.00"
                        }
                    ]
                },
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
        "order_id": "my-order-id-1",
        "payment_url": "https://payv2.multisafepay.com/connect/82v6HsoQhaR823uIZ7hexDMwQyielzLrdox/?lang=nl_NL"
    }
}
```

{{< /code-block >}}

{{< description >}}
## E-invoicing
### Direct

Creates a E-invocing [Direct](/faq/api/difference-between-direct-and-redirect/) order to be paid after delivery

* Direct transaction requires all fields completed properly

* All parameters shown are required field(s):

| Parameter                      | Type     | Description                                                                              |
|--------------------------------|----------|------------------------------------------------------------------------------------------|
| type                           | string   | Specifies the payment flow for the checkout process. Options: direct, redirect.        |
| gateway                        | string   | The unique gateway_id to immediately direct the customer to the payment method. You retrieve these gateways using a gateway request. Options: EINVOICE. |
| order_id                       | integer / string   | The unique identifier from your system for the order. If the values are only numbers the type will be integer, otherwise it will be string.                                   |
| currency                       | string   | The currency [ISO-4217](https://www.iso.org/iso-4217-currency-codes.html) you want the customer to pay with. |
| amount                         | integer  | The amount (in cents) that the customer needs to pay.                                  |
| description                    | string   | A text which will be shown with the order in MultiSafepay Control. If the customer's bank supports it this will also be shown on the bank statement. Max. 200 characters. HTML is not supported. Use the 'items' or 'shopping_cart' objects for this. |
| payment_options                | object   | Contains the redirect_url, cancel_url and [notification_url](/faq/api/how-does-the-notification-url-work/) |
| customer                       | object   | Contains the personal information of the customer. <i>Values for first_name and last_name require minimum two characters.</i> |
| delivery                       | object   | Contains the delivery information for the shipment. <i>Values for first_name and last_name require minimum two characters.</i> | 
| shopping_cart                  | object   | Contains all order rules and applicable tax classes.                                   |
| checkout_options               | object   | Contains the definitions for the VAT class.
| gateway_info                   | object   | Contains the issuer_id.                                                                 |
| birthday                       | string   | The birthdate of the customer in the format yyyy-mm-dd.                                |
| bank_account                   | string   | The formatted IBAN for the customer. This is required for credit checks.               |
| phone                          | string   | The phone number where the customer can be reached. This is required for credit checks and to contact the customer in case of non-payment. |
| email                          | string   | The email address to which the system can send payment instructions to the customer.   |
| ip_address                     | string   | The IP address of the customer. "Required" with post payment and credit card payment methods. Due to validation of the customer IP address, we need to receive the actual IP address of the end user within the ip_address field. [More info](/faq/api/ip_address/)                                                                                                                                                                                                                                           |
| forwarded_ip                   | string   | The X-FORWARDED-FOR header of the customer request when using a proxy. [More info](/faq/api/ip_address/)                                                                                                                           |

Please note that <i>first_name</i> and <i>last_name</i> in both _customer_ and _delivery_ objects require minimum two characters per entry. Failing to do so might result in unexpected errors. Given the nature of this payment method, we recommend you to always require full names (not initials, abbreviations, acronyms).

Read more about [E-Invoicing](/payment-methods/billing-suite/e-invoicing/) on our documentation page.

### Redirect

Creates an E-invoicing [Redirect](/faq/api/difference-between-direct-and-redirect/) order to be paid after delivery.

* Redirect transaction requires all fields completed properly

* All parameters shown are required field(s):

| Parameter                      | Type     | Description                                                                              |
|--------------------------------|----------|------------------------------------------------------------------------------------------|
| type                           | string   | Specifies the payment flow for the checkout process. Options: direct, redirect.        |
| gateway                        | string   | The unique gateway_id to immediately direct the customer to the payment method. You retrieve these gateways using a gateway request. Options: EINVOICE. |
| order_id                       | integer / string   | The unique identifier from your system for the order. If the values are only numbers the type will be integer, otherwise it will be string.                                   |
| currency                       | string   | The currency [ISO-4217](https://www.iso.org/iso-4217-currency-codes.html) you want the customer to pay with. |
| amount                         | integer  | The amount (in cents) that the customer needs to pay.                                  |
| description                    | string   | A text which will be shown with the order in MultiSafepay Control. If the customer's bank supports it this will also be shown on the bank statement. Max. 200 characters. HTML is not supported. Use the 'items' or 'shopping_cart' objects for this. |
| payment_options                | object   | Contains the redirect_url, cancel_url and [notification_url](/faq/api/how-does-the-notification-url-work/) |
| customer                       | object   | Contains the personal information of the customer. <i>Values for first_name and last_name require minimum two characters.</i> |
| delivery                       | object   | Contains the delivery information for the shipment. <i>Values for first_name and last_name require minimum two characters.</i> | 
| shopping_cart                  | object   | Contains all order rules and applicable tax classes.                                   |
| checkout_options               | object   | Contains the definitions for the VAT class.
| gateway_info                   | object   | Contains the issuer_id.                                                                 |
| email                          | string   | The email address to which the system can send payment instructions to the customer.   |
| ip_address                     | string   | The IP address of the customer. "Required" with post payment and credit card payment methods. Due to validation of the customer IP address, we need to receive the actual IP address of the end user within the ip_address field. [More info](/faq/api/ip_address/)                                                                                                                                                                                                                                           |
| forwarded_ip                   | string   | The X-FORWARDED-FOR header of the customer request when using a proxy. [More info](/faq/api/ip_address/)                                                                                                                           |

Please note that <i>first_name</i> and <i>last_name</i> in both _customer_ and _delivery_ objects require minimum two characters per entry. Failing to do so might result in unexpected errors. Given the nature of this payment method, we recommend you to always require full names (not initials, abbreviations, acronyms).

Read more about [E-Invoicing](/payment-methods/billing-suite/e-invoicing/) on our documentation page.
{{< /description >}}