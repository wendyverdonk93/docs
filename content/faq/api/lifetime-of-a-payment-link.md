---
title: "Lifetime of a payment link"
weight:
meta_title: "FAQ API - days_active / seconds_active - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

## days_active / seconds_active
The parameter days_active indicates the lifetime of a payment link. This will be 30 days by default. The parameter seconds_active is equal to the days_active, only instead of minutes it is specified in seconds. Example: 86.400 seconds_active is 1 days_active. 


### _There are exceptions to the rule._

## Bank transfer
The bank transfer as payment method is valid for 60 days by default. After 60 days the transaction will automatically expire. However, the payment link that is provided in the bank transfer email to the customer can be adjusted by setting a days_active or seconds_active. Meaning, that the transaction with the bank transfer as payment method is active for 60 days, while the payment link expires after 30 days by default. 

## PayPal    
A payment link with the payment method PayPal is valid for 14 days. The lifetime of the payment link is set by PayPal. Therefore, a payment link created with the payment method PayPal will automatically expire after 14 days.      

The lifetime of PayPal exceeds the lifetime of MultiSafepay, unless the lifetime falls below the 14 days

## Second Chance email
The [Second Chance](/tools/second-chance/) email is a gentle payment reminder sent to the customer. The Second Chance email will include a payment link, if the customer desires he or she can finalize the payment. 
The email regarding the Second Chance is sent once after 1 hour and once after 24 hours. This is not adjustable and is enabled or disabled. If the days_active or seconds_active are set under 24 hours, the payment link will display an error message when opened. 

When a payment link is set to expires within 24 hours but the Second Chance is enabled, the customer will receive an expired payment link in the Second Chance email that is sent. 

## Post payment method 
Post payment methods are excluded when setting a lifetime on a payment link. Post payment methods have an own payment flow and can therefore not be influenced via a days or seconds active.


## API 
Full API documentation on the lifetime of a payment link can be found on our API page, [days_active / seconds_active](/api/#days-active-seconds-active)









