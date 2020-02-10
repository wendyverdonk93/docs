---
title: "Exact"
weight: 20
meta_title: "Exact - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
logo: '/svgs/Exact.svg'
layout: 'single'
title_short: "Exact"
read_more: "."
short_description: "Read about how you can generate a MultiSafepay export and import to your Exact platform"
description_short: "Read about how you can generate a MultiSafepay export manually or automatically and import to your Exact platform"
---

### Supported export formats

Exact supports one export format:

* MT940

### How to generate an Accountant Export Report

It is possible to generate an Accountant Export Report in your MultiSafepay Control. We invite you to follow these steps:

1. Login to your [MultiSafepay Control](https://merchant.multisafepay.com/) account
2. Go to Reports and select Accountant export
3. Fill in the date selection
4. Change the report type to MT940 format
5. Generate report

In the Accountant Export Report, all incoming and outgoing completed transactions are displayed in the specified period in which you generate the report. Therefore, you will have an insight into every processed and completed transaction, as well as their associated costs.

### Automated Accountant Export

If you would like for reports to be automatically generated, please visit our dedicated documentation page regarding the [Automated Accountant Export](https://docs.multisafepay.com/tools/reports/automatic-reports/).

### Exact Import MultiSafepay

If you would like to import a MultiSafapay accountant export, we would like to kindly ask you to follow the set of instructions below:

1. Log into your Exact Online account and go to _Financial_ -> _Banking & Cash_ -> _Statements_ -> _Import_
2. Click _Choose File_ and select the MT940 file you want to upload
3. _Click Import_

Exact Online and Exact Globe can both perfectly import and match our MT940 report if:

* your accounting package supports the processing of MT940 files (bank statements).
* the order numbering that appears in the exported accountant files (eg 200160526), also appears in the correct invoice fields in your accounting platform.
* the customer’s name and the order amounts that appear in the exported accountant files correspond to those in your accounting platform.

__Please note__: _Exact Basic / Standard package does not support the MT940 import function, at least Exact Advanced version is required to import an MT940 report. Lightspeed users must require Lightspeed to perform an adjustment to make sure the order number appears in the correct field in Exact for it to be matched with our MT940._