---
title: "Second Chance, How does it work?"
weight: 61
meta_title: "Second Chance, how does it work? - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

When a customer starts a payment, but does not finish it for whatever reason, MultiSafepay will send a Second Chance email.
Included in these emails is a link that will allow the customer to complete the payment.
The first Second Chance email is sent after 1 hour and the second after 24 hours after the initial transaction was started.


## Second Chance emails are not sent when the main transaction has one of the following (financial) statuses:
1. Pending
2. Uncleared
3. Completed.

## Not all payment methods support Second Chance emails.    
The exceptions are as followed:

1. Klarna
2. Afterpay
3. Betaalplan
4. Pay After Delivery
5. Bank transfer
6. Direct Debit.

_The Second Chance email is enabled or disabled per site_.

## Can I influence the Second Chance?

The Second Chance email can be personalised through an email template.

## How long is a Second Chance active?

The payment link added in the Second Chance email has the same lifespan as the original payment request, by default 30 days. 

Full documentation on the lifetime of a payment link can be found on our FAQ page, [Lifetime of a payment link](/faq/api/lifetime-of-a-payment-link/)
