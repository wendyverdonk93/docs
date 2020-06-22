---
title: "Klarna Expiration"
weight: 24
meta_title: "Klarna, Expiration - MultiSafepay Support"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for Payment Methods, Tools and General Questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
---

## Expiration

A Klarna order after acceptance; one that is not shipped but instead 'uncleared', has an expiration time, by default 28 days but can be modified by Klarna on merchant level. This is the time you would have to ship the order. If the order is not captured before the expiration time has been reached, it will go to the status Expired | Expired. This is to protect the consumer and allow for shipment within a certain time frame.

| Order Status                      | Transaction Status      |
|--------------------------------|-----------|
| Expired   | Expired  |

It is possible to extend the expiration time of an order manually per order via the [MultiSafepay Control](https://merchant.multisafepay.com/). Once an order has been expired, this is cannot be reverted and a new order should be made. 
An order can only be extended once; the period of extension is a setting maintained by Klarna and is by default 28 days. After clicking on the extend button, the new expiration period will be displayed directly.
