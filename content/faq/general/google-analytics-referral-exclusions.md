---
title : "Can I exclude referrals in Google Analytics?"
meta_title: "FAQ General - Excluding referrals - MultiSafepay Support"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

In [Google Analytics](https://support.google.com/analytics/answer/1008015) it is possible to exclude referral domains. A common use for this feature is to prevent third-party shopping carts from starting second sessions. When the third-party shopping cart is in the exclusion list, a user will no longer initiate a new session, and won't be counted as a referral when they return to your order-confirmation page after checking out on the third-party site. This way, the customer is not counted as a new visitor to the landing page after a payment is done.

Instructions about this can be found on [https://support.google.com/analytics/answer/2795830](https://support.google.com/analytics/answer/2795830)

*This feature is only available for websites using gtag.js or analytics.js.</br>
Using ga.js (Classic Analytics) will stop Referral Exclusions from working.*

Domains to be excluded:

```
*.securecode.com
*.arcot.com
3dsecure.icscards.nl
paypal.com
belgium-uvp-3dsecure.wlp-acs.com
belgium-3dsecure-uvg.wlp-acs.com
cnce.wlp-acs.com
tpeweb.paybox.com
acs.netcetera.ch
3dsecure.paylife.at
3d-secure-code.de
clicksafe.lloydstsb.com
mastercardsecurecode.sparkassen-kreditkarten.de
3ds.e-cartebleue.com
acs-3dsecure.cm-cic.com
*.multisafepay.com
www.abnamro.nl
*.asnbank.nl
ideal.bunq.com
ideal.ing.nl
ideal.knab.nl
betalen.rabobank.nl
*.snsbank.nl
*.regiobank.nl
ideal.triodos.nl
ideal.vanlanschot.com
ideal.moneyou.nl
*.kbc.be
*.belfius.be
*.ing.be
*.paysafecard.com
*.alipay.com
*.trustly.com
```

Recently added: 
```
verified-by-visa.ing-diba.de
3d-secure.pluscard.de
3dsecure-cardprocess.de
3dsecure.bw-bank.de
3dsecure.deutsche-bank.de
german-3dsecure.wlp-acs.com
geschuetzteinkaufen.commerzbank.de
giropay.postbank.de
ideal.ing.nl
ps4acs.netcetera-payment.ch
sofort.com
verifiedbyvisa.comdirect.de
```

<br>
