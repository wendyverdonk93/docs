---
title: "Accountant export"
weight: 40
meta_title: "Reports - Accountant export - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
aliases:
    - /tools/reports/accountant-report-export
    - /tools/reports/report-validity
    - /tools/reports/N-codes
    - /tools/reports/automatic-reports
---

An Accountant export, containing all successful incoming and outgoing transactions, as well as corresponding costs (where applicable), can be generated to serve your bookkeeping needs. 

## Generate an accountant export

To generate an accountant export, follow these steps:

1. Log in to [MultiSafepay Control](https://merchant.multisafepay.com)
2. Go to **Reports** > **Accountant export**
3. Fill in the date selection
4. Choose the report format: CAMT053, CODA, CSV, MT940, XLS, XLSX
5. Generate report

In the report, all (processed) incoming and outgoing completed transactions are displayed in the specified period in which you generate the report, providing you insights on an individual level, as well as of all the associated costs.

## Report validity

The accountant export report can be exported until 2 years ago. It is not possible to generate reports beyond 2 years.

MultiSafepay offers the possibility to export Accountant reports in several formats: __CAMT053, CODA, CSV, MT940, XLS, XLSX.__

## N-Codes and validity

In the accountant export you can use filters to select a specific payment method or period. This allows you to quickly get the data you need. To filter your transactions you can use the **N-codes** filter in the accountant export.

{{< details title="View all N-Codes" >}}
Below you can find an overview of the N-Codes and their meaning. 

| N-Code | Transaction type                                        |   |
|--------|---------------------------------------------------------|---|
| N001   | [MASTERCARD](/payment-methods/credit-and-debit-cards/mastercard)             |   |
| N002   | [VISA](/payment-methods/credit-and-debit-cards/mastercard)                   |   |
| N003   | [MAESTRO](/payment-methods/credit-and-debit-cards/maestro)                    |   |
| N004   | WALLET                                                  |   |
| N006   | [DANKORT](/payment-methods/credit-and-debit-cards/dankort)       |   |
| N016   | [ALIPAY](/payment-methods/wallet/alipay)                      |   |
| N017   | [DOTPAY](/payment-methods/banks/dotpay)                      |   |
| N018   | [POSTEPAY](/payment-methods/credit-and-debit-cards/postepay)      |   |
| N021   | [IDEAL](/payment-methods/banks/ideal)                        |   |
| N031   | [GIROPAY](/payment-methods/banks/giropay)                    |   |
| N081   | [BANKTRANS](/payment-methods/banks/bank-transfer)            |   |
| N085   | [AMEX](/payment-methods/credit-and-debit-cards/american-express)                   |   |
| N086   | [KLARNA](/payment-methods/billing-suite/klarna)                      |   |
| N088   | [PAYAFTER](/payment-methods/billing-suite/pay-after-delivery)        |   |
| N089   | [SANTANDER](/payment-methods/billing-suite/betaalpermaand)               |   |
| N092   | [DIRECTBANK](/payment-methods/banks/sofort-banking)          |   |
| N093   | CURRENCY CONVERSION                                     |   |
| N094   | [MISTERCASH](/payment-methods/banks/bancontact)              |   |
| N095   | [CHARGEBACK](/faq/chargebacks) |   |
| N096   | WITHDRAWAL                                              |   |
| N097   | Refund                                                  |   |
| N098   | [COUPON](/payment-methods/prepaid-cards/gift-cards)                  |   |
| N101   | [DIRDEB](/payment-methods/banks/sepa-direct-debit)                |   |
| N102   | [iDEAL QR](/payment-methods/banks/idealqr)                   |   |
| N102   | [BELFIUS](/payment-methods/banks/belfius)                    |   |
| N103   | [EPS](/payment-methods/banks/eps)                            |   |
| N104   | [EINVOICE](/payment-methods/billing-suite/e-invoicing)               |   |
| N105   | [AFTERPAY](/payment-methods/billing-suite/afterpay)                  |   |
| N106   | [INGHOME](/payment-methods/banks/ing-home-pay)               |   |
| N107   | FERBUY                                                  |   |
| N108   | [TRUSTLY](/payment-methods/banks/trustly)                    |   |
| N109   | [KBC](/payment-methods/banks/kbc)                            |   |
| N913   | FEE                                                     |   |

{{< /details >}}

**Note:** MultiSafepay does not collect funds for PayPal. Therefore, PayPal transactions do not appear in the accountant export. Make sure that the financial status is set to _Completed_ in your backend. This will then be reflected in the accountant export.

If you have any questions regarding this process and/or require any assistance, feel free to contact our Support team at <support@multisafepay.com>

## Sending an Automated Accountant Export
As a MultiSafepay client, you can benefit from three ways of accessing/receiving the automated accountant export:

1. Via SFTP - Pull request _(With this method you will receive access to an SFTP server from MultiSafepay)_
2. Via SFTP - Push request _(With this method MultiSafepay would like to receive access to an SFTP server from you)_.
3. Transaction API using the [transactions API endpoint](/tools/transactions-api-endpoint/) (_The associated transaction costs are not included in the returned data_) 

We support SFTP by username/password and username/SSH keys.

_We only support port 22 & 2222 for SFTP connections_

### Requirements

__SFTP - Push Request: For SFTP reporting the following protocol is required:__

sh-ed25519,
rsa-sha2-512,
rsa-sha2-256,
ecdsa-sha2-nistp521,
ecdsa-sha2-nistp384,
ecdsa-sha2-nistp256,
ssh-rsa

This must be supported on the SFTP server otherwise a report cannot be delivered.

### Frequency
MultiSafepay can send the Automated Accountant Export daily, weekly or monthly.  You have the option of choosing the frequency and time. Our reference time is Central Eastern Summer Time (CEST).

### Accountant Export format
The following formats are available for automatically generating an export:

* CAMT053
* CODA
* CSV
* MT940
* XLS
* XLSX

For information regarding the different exports, check out our [export page](/tools/accounting/reports/accountant-report-export)   

### How to request an Automated Accountant Export

Automated Accountant Export activation checklist:

* Choice of email, SFTP push or SFTP pull            
* Frequency - daily, weekly or monthly
* Desired file format: CAMT053, CODA, CSV, MT940, XLS or XLSX
* Desired time (_Please note our reference time is CEST_).
* Costs breakdown per transaction OR total costs 


Send the requested to our Integration Team via <integration@multisafepay.com> 

_Don't forget to add your Account ID which can be found in the dashboard of your MultiSafepay Control in the top right corner_.


### Whitelisting

If your method of choice is via SFTP, please make sure our IP is whitelisted. For more information, please refer to our [IP ranges documentation](/faq/general/ip-ranges)

## Testing

It is possible to export accountant reports in the test mode of the [MultiSafepay Control](https://testmerchant.multisafepay.com)

Exporting Klarna Payments reports is also included within this test mode.
