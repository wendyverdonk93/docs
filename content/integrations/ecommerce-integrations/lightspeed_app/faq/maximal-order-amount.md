---
title : "Can I set a maximum order value for a payment method to show up?"
meta_title: "Lightspeed plugin - Can I set a maximum order value for a payment method to show up? - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
read_more: "."
---
Yes, you can change the maximum order amount for a payment method to be shown in the checkout. To do so, please follow these instructions:

1. Open the desired payment method in the _Payment methods ordering_ list by clicking on the "+" sign
2. Enter an amount in EUR cents in the maximum field. If you do not want a maximum amount, enter “-1”.

_For example, iDEAL with a maximum value of 1500 means that iDEAL will not be displayed in the checkout unless the total order amount is less then 15,00 EUR._

If you want different maximum order amounts for different languages, you can configure this in the dropdown menu under the _Payment methods ordering_ header where you need to select a country and make a change on a per language basis.
_Default_ is used if no specific ruleset for a language is set up.
