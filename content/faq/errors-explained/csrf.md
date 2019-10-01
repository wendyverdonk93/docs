---
title: 'CSRF'
weight: 10
meta_title: "FAQ CSRF - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

CSRF, also known as Cross-Site Request Forgery.
 
The warning CSRF is displayed on our Payment page when the customer is reaching the payment page through a POST request.
This can occur when you are having a HTML form through which you send the customer to `https://payv2.multisafepay.com` with a POST request.
 
* `https://api.multisafepay.com` will accept POST and GET requests
* `https://payv2.multisafepay.com` will only accept GET requests.
 
If you are seeing this issue and are having difficulties resolving this error, do not hesitate to contact us at <integration@multisafepay.com>

For more information about our API, see our [Full API Documentation](/api/)

