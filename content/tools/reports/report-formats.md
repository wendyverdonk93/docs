---
title: "Which accountant export formats are available at MultiSafepay?"
weight: 63
meta_title: "Which accountant export formats are available at MultiSafepay? - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---


## Accountant export
Currently we provide several reports that are useful for accounts reconciliation and transaction analysis. Providing a quick and easy overview of income and costs per payment method.

### Included 
* Transaction cost per payment method.     
By selecting group cost, all costs related to payment methods will be shown in 1 line. When disabled, all costs will be shown per transaction 

* Refunds       
The amount and cost of all refunds that are successfully processed
   

* Chargebacks / Reversal          
The amount and cost of all chargebacks and reversals that are processed 

* Currency Exchange (credit or debit)        
The amount of all foreign exchange transactions between accounts that result in a credit or debit to this currency account

* Transaction fees are the total cost of all transactions processed successfully in the selected period              

* Withdrawal fees are the total cost of all payouts processed within a selected period

* VAT is calculated over a full month. You can retrieve the VAT invoice in your [MultiSafepay Control](https://merchant.multisafepay.com) under _Finance -> Invoices_.


### Effective Date 
Transactions should be included in the report only when the transaction status is marked as "Completed". This applies for all successful processed incoming and outgoing payments. Be aware that post payment methods will be delayed because of the payout. As for the transactions fees, the revenue should be displayed in the period that it is earned. For the post payment methods we will consider that to be the date the merchant marks the order as "Shipped".

The following formats are available when generating an (automated) accountant export:

## CAMT.053  
CAMT.053 is a Bank to Customer Statement, essentially providing you with a prior or previous day statement of your account   

CAMT.053 report has the following structure:
```shell 
<?xml version="1.0" encoding="ISO-8859-1"?>  
<Document xsi:schemaLocation="urn:iso:std:iso:20022:tech:xsd:camt.053.001.02 camt.053.001.02.xsd"                                                      xmlns="urn:iso:std:iso:20022:tech:xsd:camt.053.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <BkToCstmrStmt>
       ...actual message...
   <BkToCstrmrStmt> 
</Document>      
```
The following special formats are available for a CAMT.053 in your [Multisafepay Control]: 

1. Booking and value date 
2. Booking datetime
3. Booking date 
4. Value datetime
5. Value date. 

_A CAMT.053 can be generated from within your MultiSafepay Control. Also available as automated accounant export_.


## CODA    
CODA is an electronic file with extensive information about transactions. The CODA report is a report mainly used in Belgium which is similar to the CAMT and MT940 export. This export is used to show all balance mutations in a file format which can be easily read and processed.

For the CODA reports, we have 5 different versions available in your [Multisafepay Control](https://merchant.multisafepay.com)

1. Transaction ID 
2. Transaction details
3. Var1
4. Var2 
5. Var3.

A CODA report has the following structure:
```shell 
0000012081900005                              BBRUBEBB   00000000000 00000                          2
12000BE17399100100121              EUR0000000000082150050819Multisafepay              1001001     000
2100010000291384423-310770254  0000000000000990050819004920000Test Approved             05081900000 1
```

_Available in your MultiSafepay Control and as automated accountant export_.

## CSV    
A Comma-separated values stores tabular data in plain text. Each line of the file is a data record.  

A CSV report has the following structure:
```shell 
"COMPLETEDDATETIME","AMOUNT","CREDITDEBIT","TYPETRANSACTION","PAYMENTTYPE","DESCRIPTION","DESCRIPTION2","DESCRIPTION3","DESCRIPTION4","TR_STATUS","MS_DESCRIPTION","MT_MERCHANTTRANSACTIONID","FIRSTNAME","LASTNAME","MT_CUST CITY","MT_CUST CO CODE","INVOICEID" 
```

_A CSV report is only available as an automated accountant export_.


## MT940   
MT940 is a financial industry standard format for exporting financial transactions. The report is used to import transaction data into an accounting system.

In your [MultiSafepay Control](https://merchant.multisafepay.com), it is possible to export financial information according to format, date, currency and bank account number, among others.

An MT940 report has the following structure: 
```shell 
0000 01MSPANL2AXXXX00001
0000 01MSPANL2AXXXX00002
940 00
:20:MSPAY
:25:IBAN
:28C:1
:60F:C190805EUR000000000082,15
:61:190805C000000000000,99N002NONREF
:86:Testperson-nl Approved ,Gravenhage
:86:merchant order apitool_test
:86:MultiSafepay ID : PSP ID (Visa)
:86:Test Order Description
```

An MT940 report can be generated in a .mt940 or .txt file. 

_An MT940 is available in your MultiSafepay Control and as automated accountant export_. 

##  XLS / XLSX (Excel)      
The XLS file format is a spreadsheet file developed by Microsoft  

A XLS / XLSX report has the following structure:
```shell 
"COMPLETEDDATETIME","AMOUNT","CREDITDEBIT","TYPETRANSACTION","PAYMENTTYPE","DESCRIPTION","DESCRIPTION2","DESCRIPTION3","DESCRIPTION4","TR_STATUS","MS_DESCRIPTION","MT_MERCHANTTRANSACTIONID","FIRSTNAME","LASTNAME","MT_CUST CITY","MT_CUST CO CODE","INVOICEID" 
```

The XLSX is for a large amount of data. 

_A XLS / XLSX report is available in your MultiSafepay Contol and as an automated accountant export_.


For both the [manual download](/tools/reports/how-to-generate-a-mt940-export/) of an accountant export as an [automated accountant export](/tools/reports/automatic-reports/) additional special formats are available under the advanced option. This way you can supplement the report with desired data in addition to the standard that MultiSafepay generates.

For further information, please contact our support department at <support@multisafepay.com>
