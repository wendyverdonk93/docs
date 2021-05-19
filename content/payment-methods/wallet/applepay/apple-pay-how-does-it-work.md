---
title: "Apple Pay, How it works"
weight: 21
meta_title: "Apple Pay, How it works - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
---

## How it works

1. The customer enters their credit card information into the Apple Pay app, where it is stored as an encrypted token. 
2. The customer authorizes the payment on an iOS device using either [Touch ID or Face ID](https://www.apple.com/apple-pay). 
3. The tokenized data is encrypted and sent to MultiSafepay.
4. MultiSafepay decrypts the data and forwards it to the relevant payment method. 
5. MultiSafepay authorizes and validates the payment as a [standard credit card transaction](/payment-methods/credit-and-debit-cards), using the same transaction statuses.

For more information about using Apple Pay, see Apple – [How to use Apple Pay](https://support.apple.com/en-us/HT201239).

## Transaction flow

Transaction flow is the different ways Apple Pay transactions can be processed:

- Order status: The status of the customer's order: **Completed**, **Pending**, or **Rejected**. Independent of the incoming or outgoing payment for the transaction.

- Transaction status: The status of the payment for the transaction: **Completed**, **Pending**, or **Rejected**. Once the transaction status is **Completed**, the transaction amount is added to your MultiSafepay balance.

## Fraud filter

All Apple Pay transactions pass through our fraud filter and may receive one of the following statuses:

| Order status                      | Transaction status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Initialized | Initialized | A payment link has been generated to initialize an Apple Pay payment, but no payment has yet been received.  | 
| Completed   | Completed   | A successful Apple Pay payment has been received and the funds will be added to your MultiSafepay balance.   | 
| Uncleared   | Uncleared   |  Waiting for the merchant to manually accept or decline the payment. For more information, see [Accepting uncleared credit card payments](/faq/risk-and-fraud/how-to-accept-an-uncleared-transaction).  | 
| Declined    | Declined    | Rejected by the issuing bank. For more information, see [Declined status](/faq/general/declined-status). | 
| Expired     | Expired     | A transaction for which no payment is received automatically expires after a fixed period.  | 
| Void        | Void    | The transaction has been cancelled.   | 

## Refund flow

| Order status                      | Transaction status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Reserved       | Reserved    | The customer has requested a refund. | 
| Completed      | Completed   | The refund has been successfully processed.  | 
| Chargeback     | Completed   | The issuing bank initiated a forced reversal of funds. Only applicable to direct debit and credit card payments. For more information, see [About chargebacks](/faq/chargebacks/about-chargebacks).         |               

## API Reference

For information about using Apple Pay via our API, see API Reference – [Apple Pay](/api/#applepay).

## Product rules

Apple Pay transactions are like credit card transactions and follow similar product rules, with the following exceptions:

- An SSL secured connection (HTTPS) is required.

- American Express is **not** supported.

- You cannot refund more than the amount of the original transaction. For more information, see [Refunding more than original transaction value](/faq/finance/refunding-more-than-original-transaction-value).

- The maximum refund period for Visa, Mastercard, and Maestro transactions is 180 days. After this, we recommend processing refunds by bank transfer.

- You can adjust the lifetime of payment links using the `days_active` or `seconds_active` parameters. For more information, see [Adjusting payment link lifetimes](/faq/api/adjusting-payment-link-lifetimes/).

* You can process transactions in [standard standard currencies](/faq/general/currencies-supported).

- Customers must use the Safari browser.

- For most MultiSafepay plugins, if the customer is using an incompatible device, Apple Pay doesn't appear on the checkout page. For our [OpenCart](/integrations/ecommerce-integrations/opencart/) plugin, Apple Pay does appear on the checkout page on incompatible devices but throws an error when clicked and the payment button is disabled. 
