---
title: "What does Locale do?"
weight:
meta_title: "FAQ API - Locale - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

A locale can be included to provide localized payment pages for the customer. Use the format ab_CD with [ISO 639 language codes](https://www.iso.org/iso-639-language-codes.html) and [ISO 3166 country codes](https://www.iso.org/iso-3166-country-codes.html). This will show the desired language for that customer (if supported by MultiSafepay) on both the payment page and the emails MultiSafepay sends. When left empty or with a unsupported value, en_US, meaning American English, is used.

In some cases, the locale is also used to show certain variants of payment methods, such as:

* [CartaSi](/payment-methods/branded-credit-cards/cartasi-what-is-it/) (it_IT needed)
* [Carte Bleue](/payment-methods/branded-credit-cards/carte-bleue-what-is-it/) (fr_FR needed) 
* [Dankort](/payment-methods/branded-credit-cards/dankort-what-is-it/) (da_DK needed)
* [Postepay](/payment-methods/branded-credit-cards/postepay/) (it_IT needed).


The locale is also important to send the correct email template to the customer.

For example: When an email template is set for the German customer, but the locale is received as *en_US*, the email template will be sent in English and not in German. 