---
title : "How do I set-up my Exact Globe platform?"
meta_title: "FAQ Finance - Exact Globe - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

A full international bank account number is needed to import the generated accountant export from your MultiSafepay Control into your Exact Globe account.

_Create a separate bank in Exact Globe with the name MSPAY._

## Create your bank account number (IBAN) at [nl.ibancalculator.com](https://nl.ibancalculator.com).

1. Click on calculate an IBAN
2. Select the Netherlands as country
3. Choose ING bank as bank
4. Fill in your merchant ID
5. Click on calculate IBAN
6. A bank account number (IBAN) and BIC is generated

## How do I process the bank account number in my Exact Globe platform?

1. Go to bank accounts in your Exact Globe platform
2. Click new
3. Select payment service provider as type
4. Enter the full international bank account number
5. Synchronize by selecting the ING bank
6. Click save

You have created a bank account. All transactions linked to this bank account number can now be registered.

Exact Globe and Exact Online can both perfectly import and match our MT940 report if:

- your accounting package supports the processing of MT940 files _(bank statements)_.
- the order numbering that appears in the exported accountant files (eg 200160526), also appears in the correct invoice fields in your accounting platform.
- the customer's name and the order amounts that appear in the exported accountant files correspond to those in your accounting platform,

_Lightspeed users must require Lightspeed to perform an adjustment to make sure the order number appears in the correct field in Exact Globe for it to be matched with our MT940._
