---
title : "How do I set-up my Exact Online platform?"
meta_title: "FAQ Finance - Exact Online - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

A full international bank account number is needed to import the generated accountant export from your MultiSafepay Control into your Exact online account.

## Create your bank account number (IBAN) at [nl.ibancalculator.com](https://nl.ibancalculator.com).

* Click on _calculate an IBAN_
* Select the Netherlands as country
* Choose ING bank as bank
* Fill in your merchant ID
* Click on _calculate IBAN_
* A bank account number (IBAN) and BIC is generated.

## How do I process the bank account number in my Exact online platform?

* Go to bank accounts in your Exact online platform
* Click _new_
* Select payment service provider as type
* Enter the full international bank account number
* Synchronize by selecting the ING bank
* Click _save_.

You have created a bank account. All transactions linked to this bank account number can now be registered.

Exact Globe and Exact Online can both perfectly import and match our MT940 report if:

- your accounting package supports the processing of MT940 files _(bank statements)_.
- the order numbering that appears in the exported accountant files (eg 200160526), also appears in the correct invoice fields in your accounting platform.
- the customer's name and the order amounts that appear in the exported accountant files correspond to those in your accounting platform,

_Exact Basic / Standard package does not support the MT940 import function, at least Exact Advanced version is required to import an MT940 report_.

_Lightspeed users must require Lightspeed to perform an adjustment to make sure the order number appears in the correct field in Exact for it to be matched with our MT940_.
