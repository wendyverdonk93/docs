---
title : "Can I refund orders?"
meta_title: "Lightspeed plugin - Can I refund orders? - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
read_more: "."
---
Yes, you can refund orders.  By default, you can create a refund in your [MultiSafepay Control](https://merchant.multisafepay.com). To enable refunding from your Lightspeed backend, follow the steps below.


### How to enable refund
By default the automatic refunds setting is disabled. This option can be enabled on the [settings page](https://lightspeed.multisafepay.com/settings).

1. Log in to [lightspeed.multisafepay.com](https://lightspeed.multisafepay.com/settings)
2. Navigate _Enable Refunds_ by scrolling down or click _Enable refunds_ on the sidebar.

When refunds are enabled, all Credit memos and order cancelations in the Lightspeed eCom backend will be processed and refunded.

If you need any help with refunds, feel free to contact us at <integration@multisafepay.com>

### Partial Refund
Partial refunds can be done by creating credit memos. In the Lightspeed eCom backend, go to the order you want to refund and select _Add a credit invoice_ in the payment section. When a credit invoice is created, MultiSafepay will receive a notification and create a refund.


### Canceling an order
When canceling an order in the Lightspeed eCom backend a Credit memo is created for the remaining open amount. After installing our app Multisafepay will be notified when this occurs. Afterwards we will obtain the credit memo, process the memo and create a full refund.

### Was my refund processed?
It can take a few minutes before a refund is processed. When we have processed and accepted the request the red dot next to the related credit memo will turn green. 


{{< screen src="../img/status-refund-dots.png" class="small-img desktop-radius" caption="Example of a succesfull and awaiting  credit invoice refund">}}

We also put a message in the notes section of the transaction to inform you about the refund. If a refund cannot be processed or an error occured this will be shown in the notes section. 
No worries, the customer can't see this field. We will not try to redo a refund if it fails. 
If you want to refund a previously failed refund, please try again via the MultiSafepay Merchant Panel.

{{< screen src="../img/status-refund-notes.png" class="small-img desktop-radius" caption="Example note succesfull refund">}}

_Please note it will take longer till the customer sees money returned to their back account._

### How long does it take before a customer get their money back?
The time of processing varies per payment method. For more info please visit our [page about refunds](https://docs.multisafepay.com/faq/refunds/how-long-does-a-refund-take-to-process/).

### I Created a refund in the MultiSafepay Merchant panel, can I still refund via Lightspeed?
Yes. MultiSafepay refunds cannot exceed the maximal transaction value. If a partial refund is done in the Merchant panel and later a refund is done via Lightspeed we will calculate maximum amount possible and use this amount if the original amount exceeds the maximal transaction value.
