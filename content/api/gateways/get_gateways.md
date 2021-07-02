---
weight: 110
meta_title: "API - Retrieve all gateways - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
---
{{< code-block >}}

> GET - /gateways

> JSON Response

```json
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

**Parameters**

---

__include__ | string

Specify comma delimited additional payment method types. Optional.

__Options:__ coupons

----------------

Adding the __coupons__ value to your GET request will **include** all your webshop's available gift cards in the response. See the response example on the side.

If the parameter __include=coupons__ is not added in the retrieve gateway request, only one coupon will be displayed in the response.


{{% /description %}}