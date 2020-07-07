---
title: "Klarna Expiration"
weight: 24
meta_title: "Klarna, Expiration - MultiSafepay Support"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for Payment Methods, Tools and General Questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
---

## Expiration

Once a Klarna order has been accepted, the order must be shipped within 28 days. If this is not possible, you have the option to extend this time period up until 180 days (after the initial order creation date). The financial status of the order will only go to _Completed_ after the order has been shipped.

If the order is not captured before the expiration time has been reached, it will go to the status Expired | Expired. This is to protect the consumer and allow for shipment within a certain time frame.


| Order Status                      | Transaction Status      |
|--------------------------------|-----------|
| Expired   | Expired  |

It is possible to extend the expiration time of an order manually per order via the [MultiSafepay Control](https://merchant.multisafepay.com/). Once an order has been expired, this is cannot be reverted and a new order should be made.
