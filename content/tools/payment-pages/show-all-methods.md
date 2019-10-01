---
title : "How can I show all payment methods directly?"
weight: 43
meta_title: "Payment pages - Show all payment methods - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

When the country of your customer is not fully clear or your backend does not allow you to provide for the correct country code, you might want to offer all available payment methods directly on our Payment page. This is done by the following steps:

1. retrieve the payment link by [creating an order](/api/#create-an-order)
2. put _&methods=all_ behind it
3. redirect your customer to this adapted link.

The payment link should now look like:
https://payv2.multisafepay.com/connect/13wFwA57daBSY2mg6u7AFId47UvABvzbwMx/?lang=nl_NL&methods=all

Notes:
_This is not a standard option in our plugins. 
This will only work on our new Payment pages which start with payv2. If you see no option to switch to our [new Payment pages](/tools/payment-pages/what-is-payv2/), please contact us at <integration@multisafepay.com>_.
