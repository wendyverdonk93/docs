---
title: "Flexible 3D"
weight: 11
meta_title: "Flexible 3D - MultiSafepay Support"
meta_description: "Flexible 3D is a feature that allows you to enable/disable 3D secure at an API level. The Flexible 3D forces whether or not to complete a transaction with the 3D secure verification."
---

## What is it?

Flexible 3D is a feature that allows you to enable/disable 3D secure at an API level. The Flexible 3D forces whether or not to complete a transaction with the 3D secure verification.

[3D secure, what is it?](/payment-methods/creditcards/what-is-3d-secure/)

## How does it work?

[Fraud related chargebacks](/payment-methods/creditcards/what-is-a-chargeback/) can be avoided altogether by using 3D Secure, whereby the cardholder needs to identify him or herself. Fraud-based chargebacks are no longer possible when using the 3D secure.

**Example 1:**  
Credit card transactions which are processed with the 3D Secure verification, require a form of authentication of the customer during a payment process. When the 3D secure is required upon releasing a payment, setting the Flexible 3D to false, will disable the 3D secure verification process. Resulting in releasing a payment that is **"Not Enrolled, Liability".**

**Example 2:**   
When Flexible 3D is "set on true" the verification is mandatory to finalize and release a successful payment. Credit card transactions which are processed without the 3D Secure protocol, are now required to complete the 3D secure verification.
Resulting in releasing a payment that is enrolled with the 3D authentication. Forcing to finalize a payment by completing the 3D secure verification. **3D Secure Result: Enrolled Liability**

**Activating Flexible 3D secure will override the rules of the Dynamic 3D settings.** 
[Dynamic 3D, what is it?](/tools/server2server/3d-dynamics/)

## Available for?

Flexible 3D is a feature that allows you to enable/disable 3D secure at an API level. 

[Full API documentation on Flexible 3D](/api/#flexible-3d)

| Parameter                      | Type      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| type               | string |  Specifies the payment flow for the checkout process. Options: redirect and direct. |
| gateway            | string | The unique gateway_id to immediately direct the customer to the payment method. You retrieve these gateways using a gateway request. Option: VISA and MASTERCARD. |
| 

An extra step is required when processing a direct credit card transactions. Because a direct "server to server" credit card payment takes place on the checkout page of the webshop instead of on the Payment page of MultiSafepay, it is up to the merchant to refer the customer to the verification page to complete the payment.

#### Complete callback

| Parameter                      | Type      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| reference_id      | string | Authorise 3D response reference_id |
| MD                | string | Authorise 3D response MD  |
|








