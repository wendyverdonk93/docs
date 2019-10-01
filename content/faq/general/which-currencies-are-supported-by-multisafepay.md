---
title : "Currencies supported by MultiSafepay"
weight:
meta_description: "FAQ General - Currencies - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

MultiSafepay processes the following currencies as standard: Euros (EUR), Pounds (GBP) and Dollars (USD). However, the Dollar (USD) as currency is not supported within the payment method [Bank Transfer](/payment-methods/bank-transfer/bank-accounts/).

## Requirements

1. The currency is only processed when it is supported by the [payment method](/payment-methods/) selected
2. The desired currency is correctly processed within the transaction call, received by MultiSafepay when using [JSON](/api/#orders) requests
3. The plugin settings allow the currency selected
4. The currency is enabled/allowed within your [MultiSafepay Control](https://merchant.multisafepay.com/).

_When multiple currencies are enabled within your MultiSafepay Control, all currencies will be shown under Finance -> Balance_.  

## Add currency to your MultiSafepay Balance

Submit your request to add the currency in your MultiSafepay Control at our support department <support@multisafepay.com>

## Add Multi-currency business bank account to your MultiSafepay Control

Although MultiSafepay provides all currencies, all incoming and outgoing transactions are processed in Euros (EUR) as standard currency.
To process a payout, a business bank account must be able to receive the currency that is requested for payout.
When an extra currency is added and processed within your MultiSafepay Control, the following is required to process the amount received in that particular currency. Therefore, there is no currency conversion needed.

1. Add a business bank account in your [MultiSafepay Control](https://merchant.multisafepay.com/) that is able to receive the currency.
This can be done through _Finance -> Balance -> add bank account_.

2. Process a bank transfer in the requested currency to confirm the business bank account.

3. Once the above has been processed, you can inform the support department <support@multisafepay.com> to complete the verification procedure. The screening department will finalize your request.

## Payout

1. Within your MultiSafepay Control you will have the possibility to covert the currency to Euros (EUR). This can be done through _Finance -> Currency Conversion_. Take into account the exchange rate and/or costs involved

2. If a business bank account has been added to your MultiSafepay Control (and approved by our screening department) that can receive the currency as is, a payout can be processed without currency conversion.

_For example:_

_The currency dollar (USD) is paid out in dollar (USD) and received on your business bank account in the currency dollar (USD)_

## Currencies available at MultiSafepay

As standard currency:

* Euros (EUR)

As additional currency:

* Pounds (GBP)
* Dollar (USD)
* Australian Dollar (AUD)
* Canadian Dollar (CAD)
* Swiss franc (CHF)
* Czech koruna (CZK)
* Danish krone (DKK)
* Norwegian krone (NOK)
* Polish zloty (PLN)
* Swedish krona (SEK)
