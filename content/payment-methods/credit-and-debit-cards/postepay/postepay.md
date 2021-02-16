---
title: "Postepay, What it is"
meta_title: "Postepay, What it is - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
---

## Postepay
### What is Postepay
Postepay - a Visa or Mastercard co-branded product - is a commonly used Italian credit cards. Every credit card with the 'Verified by Visa' or 'MasterCard SecureCode' logo can be safely used for online payments.

| Payment type   | [Payment flow](https://docs.multisafepay.com/faq/api/difference-between-direct-and-redirect/)      | Countries | Currencies | Refund options  | [Recurring](https://docs.multisafepay.com/tools/recurring-payments/)   | [Chargebacks](https://docs.multisafepay.com/faq/chargebacks/)   |
|----------------|-------------------|-----------|------------|------------------|------------|---------------|
|Credit/Debit|Direct/Redirect|IT|[Multiple](https://docs.multisafepay.com/faq/general/which-currencies-are-supported-by-multisafepay/)|Full/Partial|No|No|

### How Postepay works
Postepay payments are processed through the Visa or Mastercard gateway.

### How to activate Postepay?
The payment method Postepay is shown as a payment option on the payment page of MultiSafepay depending on:

1. The Visa or Mastercard gateway needs to be enabled
2. The locale needs to be it_IT (Italy) in the transaction call received by MultiSafepay.

The [locale](/faq/api/locale) is leading in this to show the desired payment method Postepay on the payment page of MultiSafepay.

Upon adding Postepay as payment method on the checkout page, you can download the Postepay logo from MultiSafepay's [collection](/faq/general/where-find-logo-payment-methods/) and upload it to your ecommerce platform. 


### How to refund a Postepay transaction?
Transactions received with Postepay (Visa or Mastercard) as payment method can be refunded to the customer within 180 days.

Please follow these steps to refund a Postepay transaction.

1. Login into your [MultiSafepay Control](https://merchant.multisafepay.com)
2. Select _transaction -> transaction overview_
3. Find the transaction through search
4. Open transaction
5. Select _refund_
6. Fill in the amount that you want to refund to the customer  
7. _Confirm_.

_MultiSafepay does not allow you to refund more than the stated amount of the original transaction. Moreover, no credit card scheme allows refunds of more than the original transaction amount._

> _Please note that credit card payments that are refunded by the merchant to the customer, will be sent to the card issuing bank and its partners within 1 business day by MultiSafepay. Whether or not the refund will be visible to the customer depends on the reports, statements and online tools that are made available by the issuing bank_.

## Testing

Unfortunatley it is not possible to test with Postepay. However, you will still be able to place test transactions (e.g. 0,01 EUR amounts) in your [MultiSafepay Control](https://merchant.multisafepay.com/)