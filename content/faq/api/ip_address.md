---
title: "Why request the IP address of the customer?"
weight:
meta_title: "FAQ API - Customer ip_address - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

#### ip_address
Due to validating the <i>ip_address</i> of the customer within post payment and credit card payment methods, we need the actual IP address of the end user within the <i>ip_address</i> field.

Meaning, the optional parameter <i>"ip_address (optional)</i> within the JSON is now a <i>"required"</i> field when processing post payment and/or credit card payment methods.

Upon validating the <i>ip_address</i>, localhost IP address instead of the end user, may result in transactions end up being marked with the status uncleared or even be rejected/declined.


```shell
   "customer": {
        "ip_address": "31.148.195.10",
        "forwarded_ip": "" 
```

#### forwarded_ip

The X-FORWARDED-FOR header of the customer request when using a proxy.

<i>forwarded_ip</i> is to be used when there is a proxy. In all other cases they need to use the <i>ip_address</i> to retrieve the IP address of the customer.


#### Uncleared status or Declined 
Due to the validation on the IP address of the end user (customer) a transaction can unnecessarily be marked with the status uncleared or even be declined. 

Before a payment is accepted, a fraud check will take place on the transaction. The required ip_address field is one of the checks processed in the validation of the payment. When supplied as empty or incorrect (by providing the ip_address of the webshop instead of the customer) the chances are high the transaction will be marked with the status uncleared. 

Credit cards and post payment methods are high risk for fraud. Therefore, the validation of each transaction will automatically take place to protect the merchants processing with MultiSafepay. 

<br>

