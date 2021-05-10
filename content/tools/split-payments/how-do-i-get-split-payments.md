---
title : "Processing Split Payments"
weight: 82
meta_title: "Processing Split Payments - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
---

Split Payments is a feature in our [API](/api/#split-payments).

It is not incorporated in our [ecommerce integrations](/integrations/ecommerce-integrations) by default. You can add it as a custom feature.  

To process a split payment, you need:  

- Two active MultiSafepay accounts  
- Access to the code that creates the JSON request

Add the object `affiliate` object:

```shell
"affiliate": {
   "split_payments": [
        {
            "merchant": 987654321,
            "fixed": 123,
            "description": "Fixed fee"
        },
        {
            "merchant": 987654321,
            "percentage": 12.3,
            "description": "Relative fee"
        }
    ]
}
```

For more information, see API - [Split Payments](/api/#split-payments).

## Important

- The amount for "fixed" payments is in cents and follows the currency settings for the transaction.
- You can select "fixed", "percentage", or a combination of both.
- Our platform uses _var3_  to store this data. Any value you provide for _var3_ is overwritten.
