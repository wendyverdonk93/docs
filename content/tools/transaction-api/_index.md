---
title : "MultiSafepay Transaction API"
---

The Transaction API by MultiSafepay allows the possibility to automate your financial processes by matching records at a transaction level. Furthermore, the API is easy to implement in your environment. This way, you have less manual administrative work and financial data that is correct in your accounting. The possible use cases with this API consist of four possibilities:

* _Accountant export_: financial movements in a period / after last call opening and closing balances
* _Transactions in a payout_: when a merchant receives a payout he want to know what payments are in this payout
* _New completed orders_: what new orders i receive after my last check or between a period
* _All changes between a period_: this can be very useful to have financial insight into any given process.

## Environments

MultiSafepay provides a TEST environment and a LIVE environment. The TEST environment is useful for developing and testing a new integration with our API as no real transactions are able to be processed. Once the integration has been developed processing real transactions is as simple as addressing the LIVE API and updating the API key being used.

[TEST Merchant environment](https://testmerchant.multisafepay.com/)

[LIVE Merchant environment](https://merchant.multisafepay.com/)

## API Endpoints

All requests to the MultiSafepay API endpoint require authentication. Authentication is provided by including an API key as an HTTP header in your request. Each website has its own API key so if you are operating multiple websites make sure to use the correct corresponding key for each one of them. The API key can be found under the website settings in MultiSafepay Control

The HTTP header name for the API key is: api_key

Open a [TEST account](https://testmerchant.multisafepay.com/signup?_ga=2.247259138.706372755.1611570114-869152674.1598992978)

## Parameters 

| Parameter | Description                  |
|----------|-----------------------|
| debit_credit     | Debit or credit transaction. Available values: D, C              |
| end     | Transactions created to - end          |
| end_epoch     | Transactions created to (epoch)                  |
| financial_status                               |  Transaction financial status - available values: completed, created, declined, error, expired, initialized, manual, new, refunded, reserved, uncleared, void                |
| payment_method                              | VISA                   |
| start                              | transactions created from                  |
| start_epoch                              | transactions created from (epoch)                 |
| status                              |  transaction status                 |
| transaction type                              | available values: admin_fee, affiliate_payout, automatic_payout, chargeback, coupon, currency_conversion, deposit fastcheckout, monthly_fee, payment, refund, reserve_chargeback, singup_fee                  |
| limit                               | number of returned results                  |
| next                              |  next page URL                  |


## Contact

Do you have any questions regarding this process? Our Integration team will assist you with any issues you are currently facing. Contact us at <integration@multisafepay.com>