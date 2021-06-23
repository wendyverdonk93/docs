---
weight: 40
meta_title: "API - Authentication - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
---
{{< code-block >}}

> Test API

``` shell
curl -X POST "https://testapi.multisafepay.com/v1/json/" \
-H "Authentication: Bearer <your-test-API-key>"
```

> Live API

``` shell
curl -X POST "https://api.multisafepay.com/v1/json/" \
-H "Authentication: Bearer <your-live-API-key>"
```

{{< /code-block >}}

{{< description >}}
## Authentication

All requests to the MultiSafepay [API](/faq/general/multisafepay-glossary/#api) endpoint require authentication. Authentication is provided by including an [API key](/faq/general/multisafepay-glossary/#api-key) as an HTTP header in your request. Each website has its own API key so if you are operating multiple websites make sure to use the correct corresponding key for each one of them. The API key can be found under the website settings in [MultiSafepay Control](/faq/general/multisafepay-glossary/#multisafepay-control)

The HTTP header name for the API key is: **api_key**

[Sign up for a test account](https://testmerchant.multisafepay.com/signup)
{{% /description %}}