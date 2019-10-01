---
weight: 210
meta_title: "API - Create an order - Developers MultiSafepay"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

## Create an order

> 
POST - /orders

```shell
{
    "type": "redirect",
    "order_id": "my-order-id-1",
    "gateway": "",
    "currency": "EUR",
    "amount": "1000",
    "description": "Test Order Description",
    "google_analytics": { 
      "account": "UA-XXXXXXXXX" 
      },
    "payment_options": {
       "notification_url": "http://www.example.com/client/notification?type=notification",
        "redirect_url": "http://www.example.com/client/notification?type=redirect",
        "cancel_url": "http://www.example.com/client/notification?type=cancel", 
        "close_window": ""
    },
    "customer": {
        "locale": "nl_NL",
        "ip_address": "89.20.162.110",
        "first_name": "Testperson-nl",
        "last_name": "Approved",
        "address1": "Kraanspoor",
        "house_number": "39C",
        "zip_code": "1033SC",
        "city": "Amsterdam",
        "country": "NL",
        "phone": "0208500500",
        "email": "test@example.com",
        "referrer": "http://test.com",
        "user_agent": "Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/38.0.2125.111 Safari/537.36"
    },
    "second_chance": {
        "send_email" : true
    }
}

```


> JSON Response


```shell
{
  "success": true,
  "data": {
    "order_id": "My-order-id-1",
    "payment_url": "https://payv2.multisafepay.com/connect/99wi0OTuiCaTY2nwEiEOybWpVx8MNwrJ75c/?lang=nl_NL"
  }
}
```


Creates redirect order. Default type is "redirect".


| Parameter                   | Type      | Description                                                                                |
|-----------------------------|-----------|--------------------------------------------------------------------------------------------|
| type                        | string    | Specifies the payment flow for the checkout process. Options: redirect, direct, checkout, paymentlink. |
| gateway                     | string    | The unique gateway id to immediately direct the customer to the payment method. You retrieve these gateways using a gateway request.  |
| order_id                    | string    | The unique identifier from your system for the order.                                     |
| currency                    | string    | The currency [ISO-4217](https://www.iso.org/iso-4217-currency-codes.html) you want the customer to pay with.   |
| amount                      | integer   | The amount (in cents) that the customer needs to pay.                                      |
| description                 | string    | A text which will be shown with the order in MultiSafepay Control. If the customer's bank supports it this description will also be shown on the customer's bank statement. Max. 200 characters. HTML is no longer supported. Use the 'items' or 'shopping_cart' objects for this.  |
| payment_options             | object    |                             |
| notification_url            | string    | Endpoint where we will send the notifications to. [notification_url](/faq/api/how-does-the-notification-url-work/)                                |
| redirect_url                | string    | Customer will be redirected to this page after a successful payment. |
| cancel_url                  | string    | Customer will be redirected to this page after a failed payment.  | 
| customer                    | object    |                                 |
| locale                      | string    | Displays the correct language and payment methods on the Payment page. It also has an influence on sending the set email templates. Use the format ab_CD with [ISO 639](https://www.iso.org/iso-639-language-codes.html) language codes and [ISO 3166](https://www.iso.org/iso-3166-country-codes.html) country codes. Default: en_US. | 
| ip_address                  | string    | The IP address of the customer. “Required” with post payment and credit card payment methods. Due to validation of the customer IP address, we need to receive the actual IP address of the end user within the ip_address field.  [More info](/faq/api/ip_address/) | 
| first_name                  | string    | The customer’s first name.                   |
| last_name                   | string    | The customer’s last name.                    |
| address1                    | string    | First line of customer’s provided address.   |
| house_number                | string    | Customer’s provided house number.            |
| zip_code                    | string    | Customer’s provided zip / postal code.       |
| city                        | string    | Customer’s provided city.                    |
| country                     | string    | Customer’s provided country code [ISO 3166-1](https://www.iso.org/iso-3166-country-codes.html) |
| phone                       | string    | Customer’s provided phone number.            |
| email                       | string    | Customer’s provided email address. Used to send Second Chance emails and in fraud checks.   |


