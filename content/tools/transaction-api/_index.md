---
title : "Transaction API"
layout : "single"
tags : "hidden"
---

## Introduction

Our Transaction API endpoint allows you to automate your financial processes by matching records at a transaction level. This saves manual administrative work and standardizes your business operations. This page provides information about the endpoint and its parameters. To get started using the transactions API endpoint, let's examine four common use cases:

* _Reconciliation_: financial movements in a period / after last call opening and closing balances
* _Transactions in a payout_: when a merchant receives a payout he want to know what payments are in this payout
* _Completed orders_: orders received after my last check or between a period of GET completed orders
* _All changes between a period_: this can be very useful to have financial insight into any given process.


## Requirements

The [TEST environment](https://testmerchant.multisafepay.com/) and [LIVE environment](https://merchant.multisafepay.com/) are both readily available for testing with the Transaction API.

The TEST environment is useful for developing and testing a new integration with our API, as no real transactions are processed. Once the integration has been developed, processing real transactions is as simple as addressing the LIVE API and updating the API key being used.

All requests to the MultiSafepay [API endpoint](https://api.multisafepay.com/v1/json/transactions) require authentication. Authentication is provided by including your API key as an HTTP header in your request. Each website has its own API key so if you are operating multiple websites, make sure to use the correct corresponding key for each one of them. The API key can be found under the website settings in [MultiSafepay Control](https://merchant.multisafepay.com/)

The HTTP header name for the API key is: api_key


## Filters 

The following parameters can be used to filter requests and retrieve information through a GET request:

API Endpoint: https://api.multisafepay.com/v1/json/transactions

| Parameter | Description                  |
|------------------|-----------------------|
| debit_credit     | Debit or credit transaction. Available values: D, C              |
| end     | Transactions created to - end          |
| end_epoch     | Transactions created to (epoch)                  |
| financial_status                               |  Transaction financial status - available values: completed, created, declined, error, expired, initialized, manual, new, refunded, reserved, uncleared, void                |
| payment_method                              | VISA                   |
| start                              |Transactions created from                  |
| start_epoch                              | Transactions created from (epoch)                 |
| status                              |  Transaction status                 |
| transaction type                              | Available values: admin_fee, affiliate_payout, automatic_payout, chargeback, coupon, currency_conversion, deposit fastcheckout, monthly_fee, payment, refund, reserve_chargeback, singup_fee                  |
| limit                               | Number of returned results                  |
| next                              |  Next page URL                  |

## Use cases

### Creating an overview

_I want to have a complete overview of all transactions which provide insights to debit and credit transactions from my MultiSafepay account._

* Debtors are customers and based on the *transaction_id*, you are able to see who has paid and how they have paid
* Creditors can be your suppliers e.g. MultiSafepay or the customers I owe a refund.

__Required parameters__

| Parameter  | Description                  |
|------------------|-----------------------|
| debit_credit            |  Credit/Debit         |
| end:date/time              |  Transactions created to         |
| end_epoch           |  Transactions created to (epoch)         |


### Payouts

 _I want to have a overview of the payout file containing all transaction ID's so I am able to gain insights to the payout moments and all corresponding transactions._

* Gain insights into the complete batch of transactions for a specific payout
* Management of your accounting and bookkeeping.


__Required parameters__

| Parameter  | Description                  |
|------------------|-----------------------|
| debit_credit            |  Credit/Debit         |
| end:date/time              |  Transactions created to         |
| end_epoch           |  Transactions created to (epoch)         |
| financial_status           |  Completed         |


### Reconciliation

_I want to match mutations that belong to eachother, so that the balance in my accounting or bookkeeping can be explained._

* May be required by law to administer reconcilliation
* Automating the reconcilliation process can save time.

| Parameter  | Description                  |
|------------------|-----------------------|
| end: date/time            |  Transactions created to       |
| end_epoch              |  Transactions created to (epoch)         |
| type (transaction type)          |  GET all __or__ separately: admin_fee, affiliate_payout, automatic_payout, chargeback, coupon, currency_conversion, deposit, fastcheckout, monthly_fee, payment, refund, reverse_chargeback, signup_fee         |
| financial_status           |  Completed         |

### Refunds

_I would like to see the refunds associated with customer returns_

* View the orders that are to be paid back as a merchant
* Ability to pay back outstanding amounts for orders that have been returned.

| Parameter  | Description                  |
|------------------|-----------------------|
| debit_credit           |  Debit       |
| end: date/time              |  Transactions created to          |
| end_epoch          |  Transactions created to epoch         |
| type (transaction type)           |  Refund         |



## Support

If you encounter any issues, problems or questions, you can create an issue on this repository or contact us at <integration@multisafepay.com>

