---
title: "Activate Server to Server credit card payments"
weight: 72
meta_title: "Server to Server, how to active it? - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

>_Before you proceed with processing direct credit card transactions, check with your account manager at MultiSafepay if you are eligible for the payment method_.

## Requirements: PCI license required

In order to process direct credit card transactions, the following is required of the merchant:

1. Register for a [MultiSafepay Control](https://merchant.multisafepay.com/signup)
2. Be [PCI](/faq/risk-and-fraud/what-do-i-need-to-know-about-credit-card-payments/) compliant & receive final approval by MultiSafepay Risk department to enable this feature
3. Integrate with MultiSafepay via JSON [API](/api/#credit-cards) following the instructions provided in this documentation
4. Credit card transactions with MultiSafepay accounts are by default 3D secure enabled. Certain MultiSafepay accounts can be totally 3D disabled or can be processed with a 3D Dynamic filter based on a pre-configured set of rules.

>_All options require approval and enabling by our MultiSafepay Risk Department_.

## 3D Secure Processing

3D Secure is a protocol designed to reduce fraud and chargebacks during ecommerce Internet transactions. Cardholders are redirected during the payment process to their issuing bank in order to identify themselves before the purchase can be completed. This usually means entering a PIN or a password after entering their card details. In the event of a dispute with the transaction at a later date, the card issuer will usually take responsibility of the chargeback instead of the merchant, this is only for no authorization and fraud, not if the product is not delivered or customer dissatisfaction with the quality.

The liability issues involved with 3D secure transactions are outside of the scope of this document. For a detailed indication of the liabilities involved, contact our screening department at <screening@multisafepay.com>

>_MultiSafepay only supports Mastercard Secure Code, Verified by Visa and Bancontact 3D_.

<br>
