---
weight: 120
meta_title: "API - Retrieve a gateway - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
---
{{< code-block >}}

> GET - /gateways/{id}

> JSON Response

```shell

{
    "success": true,
    "data": [
        {
            "id": null,
            "description": null
        }
    ]
}
```
{{< /code-block >}}

{{< description >}}
## Retrieve a gateway

**Parameter**

----------------

__id__ | string

The unique identifier of the gateway to be returned.

__country__ | string

Customer’s provided country code in [ISO 3166-1](https://www.iso.org/iso-3166-country-codes.html) format e.g. ‘NL’. This will provide a local bank account to the customer to pay to, where available.

__currency__ | string

The currency [ISO-4217](https://www.iso.org/iso-4217-currency-codes.html) you want the customer to pay with.

__amount__ | integer

The amount (in cents) that the customer needs to pay.


{{% /description %}}