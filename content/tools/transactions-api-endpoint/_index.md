---
title : "Transactions API endpoint"
layout : "single"
tags : "hidden"
---

## Introduction

The transactions API endpoint returns the data of transactions that are associated with your account. Using this endpoint, you can automate business operations by matching records at a transaction level. This page provides information about the endpoint and its usage.

To get started, we examine four common use cases:

* [**General overview**](#create-a-general-overview): Create an overview of all transactions
* [**Payout specification**](#generate-a-payout-specification): Gain insight into your payouts
* [**Reconciliation**](#perform-reconcilliation): Automate your bookkeeping by matching mutations
* [**Refunds overview**](#create-a-refund-overview): Create an overview of your refunds 

{{< br >}}

### Requirements

Requests to the transactions endpoint require a [valid API key](/tools/multisafepay-control/get-your-api-key/)  
In the API request, set your key to the `api_key` header value, like this:

```
curl -X GET "https://testapi.multisafepay.com/v1/json/transactions"
-H "Content-Type: application/json" \
-H "api_key: <your-api-key>" \
...
```

_Note: Make sure to use your test API key when making a request to our test API_

## Basic functionality

This API endpoint has no required parameters. Calls to the transactions endpoint retrieve an array of all transactions under your account. Use optional parameters to filter your requested transactions to include only those transactions relevant to your business operation.

The transactions returned by the Transactions endpoint are formatted as follows:

```
{
  "data": [
    {
      "amount": 0,
      "completed": "string",
      "costs": [
        null
      ],
      "created": "string",
      "currency": "string",
      "debit_credit": "D",
      "description": "string",
      "financial_status": "string",
      "invoice_id": "string",
      "order_id": "string",
      "payment_method": "string",
      "site_id": 0,
      "status": "string",
      "transaction_id": 0,
      "type": "string",
      "var1": "string",
      "var2": "string",
      "var3": "string"
    }
  ],
  "success": true
}
```

## Parameters 

The following parameters can be used to filter the returned transactions:

| Parameter | Description                  |
|------------------|-----------------------|
| debit_credit     | This value specifies the type of payment. Debit transactions are outgoing payments; credit transactions are incoming payments. {{< br >}} **Options:** `D`, `C`              |
| site_id | Only transactions for specified `site_id` are returned. Find your site IDs in MultiSafepay Control. By default, the transactions endpoint will return the transactions of all sites under your account. {{< br >}} **Format:** integer (e.g. `12345`) |
| start | Transactions created after `start` are returned. {{< br >}} **Format:** [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) (e.g. `2021-01-01T12:00:00`)  ||
| start_epoch  | Transactions created after `start_epoch` are returned. This parameter can be used as an alternative to `start`. If both values are specified, `start` overrules `start_epoch`. {{< br >}} **Format:** [Epoch](https://en.wikipedia.org/wiki/Unix_time) (e.g. `1609502400`)    |
| end     |  Transactions created before `end` are returned. {{< br >}} **Format:** [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) (e.g. `2021-01-01T12:00:00`)  |
| end_epoch | Transactions created before `end_epoch` are returned. This parameter can be used as an alternative to `end`. If both values are specified, `end` overrules `end_epoch`. {{< br >}} **Format:** [Epoch](https://en.wikipedia.org/wiki/Unix_time) (e.g. `1609502400`)    |
| financial_status  |  Transactions with matching [financial status](/api/#financial-statuses) are returned. {{< br >}} **Options:** `completed`, `created`, `declined`, `error`, `expired`, `initialized`, `manual`, `new`, `refunded`, `reserved`, `uncleared`, `void`                |
| status    |  Transactions with matching [transaction status](/api/#transaction-statuses) are returned. {{< br >}} **Options:** `completed`, `initialized`, `uncleared`, `declined`, `cancelled`, `void`, `expired`, `refunded`, `partial_refunded`, `reserved`, `chargeback`, `shipped`                |
| payment_method | Transactions with matching payment method are returned. {{< br >}} **Format:** Follows [gateway](/api/#retrieve-a-gateway) conventions (e.g. `VISA`) |
| type | Transactions with matching transaction type are returned. {{< br >}} **Options:** `admin_fee`, `affiliate_payout`, `automatic_payout`, `chargeback`, `coupon`, `currency_conversion`, `deposit`, `fastcheckout`, `monthly_fee`, `payment`, `refund`, `reserve_chargeback`, `singup_fee` |
| limit  | Set `limit` to specify the maximum number of returned results per page. {{< br >}} **Format:** integer (e.g. `10`) |

**Please note:** values `site_id`, `financial_status`, `status`, `payment_method`, and `type` can be specified both as single values or as arrays containing multiple values.

{{< br >}}

## Use cases

### Create a general overview

_I want to have a complete overview of all transactions which provide insights to debit and credit transactions from my MultiSafepay account._

* Debtors are customers and based on the *transaction_id*, you are able to see who has paid and how they have paid
* Creditors can be your suppliers e.g. MultiSafepay or the customers I owe a refund.


| Parameter  | Description                  |
|------------------|-----------------------|
| debit_credit | Credit/Debit |
| end:date/time | Transactions created to |
| end_epoch | Transactions created to (epoch) |

{{< br >}}

### Generate a payout specification

 _I want to have a overview of the payout file containing all transaction ID's so I am able to gain insights to the payout moments and all corresponding transactions._

* Gain insights into the complete batch of transactions for a specific payout
* Management of your accounting and bookkeeping


| Parameter  | Description                  |
|------------------|-----------------------|
| debit_credit            |  Credit/Debit         |
| end:date/time              |  Transactions created to         |
| end_epoch           |  Transactions created to (epoch)         |
| financial_status           |  Completed         |

{{< br >}}

### Perform reconciliation

_I want to match mutations to justify the balance in my accounting or bookkeeping records_

* Reconciliation may be required by law
* Automating the reconciliation process can save time and reduce errors

| Parameter  | Required value |
|------------------|-----------------------|
| type | Retrieve all by not specifying a value. Alternatively, retrieve only specified transaction types like `payment` and `refund`. |
| financial_status           |  `completed` |

Use parameters `end` and `start` to specify a range of dates.

{{< br >}}

### Create a refund overview

_I want to see the refunds associated with customer returns_

* View the orders that are to be paid back as a merchant
* Ability to pay back outstanding amounts for orders that have been returned

| Parameter | Required value |
|------------------|-----------------------|
| debit_credit | `D` |
| type (transaction type) | `refund` |

Use parameters `end` and `start` to specify a range of dates.

{{< br >}}

## Support

If you have any issues or questions, [contact our Integration Team](mailto:integration@multisafepay.com)
