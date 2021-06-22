---
weight: 110
meta_title: "API - Retrieve all gateways - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
---
{{< code-block >}}

> GET - /gateways

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

## Retrieve gateways

__include__ | string

Specify comma delimited additional payment method types. Optional.

__Options:__ coupons

----------------

Adding the __coupons__ value to your GET request will **include** all your webshop's available gift cards in the response. See the response example on the side.

If the parameter __include=coupons__ is not added in the retrieve gateway request, only one coupon will be displayed in the response.


{{% /description %}}