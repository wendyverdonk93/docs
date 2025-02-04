---
weight: 228
meta_title: "API Reference - Credit card server to server requests - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
aliases:
    - /api/#credit-cards-server-to-server
    - /api/#credit-card-requests
---
{{< code-block >}}
> POST - /orders

```json

{
    "type": "direct",
    "order_id": "my-order-id-1",
    "currency": "EUR",
    "amount": 1000,
    "gateway": "CREDITCARD",
    "description": "product description",
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
        "address2": "",
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
        "card_number": "5555555555554444",
        "card_holder_name": "MasterCard-Test-Order",
        "card_expiry_date": "2512",
        "card_cvc": "123"
    }
}
```

> JSON response

```json
{
  "success": true,
  "data": {
    "amount": 1000,
    "amount_refunded": 0,
    "costs": [
      {
        "transaction_id": 123456789,
        "amount": ,
        "description": "",
        "type": "SYSTEM"
      }
    ],
    "created": "2020-01-28T09:01:07",
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
      "locale": "nl_NL",
      "phone1": "0208500500",
      "zip_code": "1033SC"
    },
    "description": "product description",
    "fastcheckout": "NO",
    "financial_status": "initialized",
    "items": null,
    "modified": "2020-01-28T09:01:07",
    "order_id": "my-order-id-1",
    "payment_details": {
      "account_holder_name": "MasterCard-Test-Order",
      "account_id": null,
      "card_expiry_date": 2512,
      "external_transaction_id": "6652390295520298",
      "last4": 4444,
      "recurring_id": null,
      "recurring_model": null,
      "type": "MASTERCARD"
    },
    "payment_methods": [
      {
        "account_holder_name": "Testperson-nl",
        "amount": 1000,
        "card_expiry_date": 2512,
        "currency": "EUR",
        "description": "Product Description",
        "external_transaction_id": "6652390295520298",
        "last4": 4444,
        "payment_description": "MasterCard",
        "status": "initialized",
        "type": "MASTERCARD"
      }
    ],
    "reason": "3D Secure Authorization",
    "reason_code": "",
    "related_transactions": null,
    "status": "initialized",
    "transaction_id": 123456789
    "customer_verification": {
      "type": "form",
      "html": "",
    },
    "payment_url": "https://payv2.multisafepay.com/connect/99wi0OTuiCaTY2nwEiEOybWpVx8MNwrJ75c/?lang=nl_NL",
    "cancel_url": "http://www.example.com/client/notification?type=cancel"
  }
}
```

{{< /code-block >}}

{{< description >}}

### Credit card requests

**Parameters**

----------------
`type` | string | required

The payment flow for the checkout process.  
Options: `direct`.  

----------------
`gateway` | string | required

The unique gateway ID to direct the customer straight to the payment method.  
Options: `VISA`, `MASTERCARD`, `AMEX`, `MAESTRO`, `CREDITCARD`.  
When set to `CREDITCARD`, the type of credit card is detected based on the first four digits.

----------------
`customer` | object | required

See [customer (object)](/api/#customer-object).

----------------
`gateway_info` | object

Contains:  

`card_number` | string

The customer's full credit card number.

`card_holder_name` | string

The name of the cardholder on the credit card.

`card_expiry_date` | string

The expiry date on the credit card.

`card_cvc` | string

The card verification code (CVC) is a 3 or 4 digit number used as an additional security feature for card-not-present transactions.  
For some cards, like MAESTRO, this may not be required.  
CVC is also not required for recurring transactions.

**Response**

----------------
`costs` | object

See [costs (object)](/api/#costs-object).

----------------
`payment_methods` | object

See [payment_methods (object)](/api/#payment_methods-object).

----------------

{{% /description %}}