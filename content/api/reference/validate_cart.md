---
weight: 615
meta_title: "API Reference - Validate shopping cart - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
---

{{< code-block >}}

```json 
{
    "checkout_options": {
        "validate_cart": true
    }
}
```

{{< /code-block >}}

{{< description >}}

## Validate the shopping cart

**checkout_options.validate_cart** | boolean

If set to true (for non-Billing Suite payment methods), the value of `amount` is compared with the calculated total value of the shopping cart (returned as `order_total`).

If the values match, the order is submitted.

If the values don't match, the order is not submitted and error_code '1027' is returned.

{{< /description >}}