---
title : "Which tax settings should I use?"
meta_title: "Magento 2 - Recommended tax settings - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
layout: "faqdetail"
read_more: "."
---

To prevent discrepancies between item amounts inside MultiSafepay transactions and Magento orders, we recommend you to use certain tax settings inside Magento.

Tax settings in Magento can be found under **Stores** > **Configuration** > **Sales** > **Tax** > **Calculation Settings**

If you want to show prices **excluding tax**, use the following settings:

+ **Tax Calculation Method Based On**: Row Total
+ **Catalog Prices**: Excluding Tax
+ **Apply Customer Tax**: After Discount
+ **Apply Discount On Prices**: Excluding Tax

If you want to show prices **including tax**, use the following settings:

+ **Tax Calculation Method Based On**: Row Total
+ **Catalog Prices**: Including Tax
+ **Apply Customer Tax**: After Discount
+ **Apply Discount On Prices**: Including Tax

Our recommended settings are based on Magento's standards. For more information, see [Magento's documentation on tax settings](https://docs.magento.com/user-guide/tax/warning-messages.html).
