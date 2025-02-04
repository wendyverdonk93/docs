---
title : "Release Notes WooCommerce plugin"
meta_title: "WooCommerce plugin changelog - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
aliases: [/integrations/woocommerce/changelog/]
---

## 4.8.0
Release date: Aug 4th, 2021

### Added
+ PLGWOOS-723: Declare support for WooCommerce 5.5.2 and Wordpress 5.8
+ PLGWOOS-711: Add missing titles in setting pages

### Changed
+ PLGWOOS-718: Remove PSP ID string when register the transaction ID in WC_Order->payment_complete()

***

## 4.7.0
Release date: Jun 23th, 2021

### Added
+ PLGWOOS-706: Declare support for WooCommerce 5.4.1

### Changed
+ PLGWOOS-672: Change notification method from GET to [POST](https://docs.multisafepay.com/faq/api/notification-url/#get-vs-post-notification) by default

### Fixed
+ PLGWOOS-704: Log errors in the MultiSafepay log file, when processing notifications.

***

## 4.6.0
Release date: May 19th, 2021

### Added
+ PLGWOOS-625: Add log section in MultiSafepay settings page
+ PLGWOOS-666: Add MultiSafepay system status section in settings page
+ PLGWOOS-376: Add support to show upgrade notices in plugin list
+ PLGWOOS-657: Add nl_BE language

### Fixed
+ PLGWOOS-694: Fix notifications for order fully paid with gift cards
+ PLGWOOS-692: Fix Second Chance within the orderRequest object
+ PLGWOOS-654: Fix the gateway_id assigned to the properties of each token

***

## 4.5.1
Release date: Apr 7th, 2021

### Fixed
+ PLGWOOS-661: Fix payment methods ids to match list of gateway lists keys, which was producing an error to process notification for Sofort payments
+ PLGWOOS-663: Fix stock decreasing error, in relation with Bank Transfer gateway and notification flows

***

## 4.5.0
Release date: Mar 31th, 2021

### Fixed
+ PLGWOOS-659: Fix initialization of the plugin on multisite environments in which WooCommerce has been activated network-wide


### Added
+ PLGWOOS-534: Add generic gateway

***

## 4.4.1
Release date: Mar 25th, 2021

### Fixed
+ PLGWOOS-653: Fix overwriting initial order status when transaction is initialized

***

## 4.4.0
Release date: Mar 23th, 2021

### Fixed
+ PLGWOOS-648: Return 0 as tax rate, if WooCommerce taxes are disabled but tax rules are registered
+ PLGWOOS-647: Add verification to check if the token used in the transaction belongs to the customer

### Added
+ PLGWOOS-651: Add setting to select type of transaction in SEPA Direct Debit, E-Invoicing, in3, Santander Consumer Finance, AfterPay and iDEAL
+ PLGWOOS-644: Add setting to select type of transaction in Pay After Delivery
+ PLGWOOS-640: Add setting to select type of transaction in Bank Transfer

***

## 4.3.0
Release date: Mar 18th, 2021

### Fixed
+ PLGWOOS-626: Fix order not being canceled when customer cancels the order
+ PLGWOOS-630: Fix include shipping item in full refund of billing suite payment methods

### Added
+ PLGWOOS-629: Add shipping item to the order request, even if this one is free
+ PLGWOOS-631: Add delivery address in order request even if the shipping amount is 0
+ PLGWOOS-634: Add settings field to redirect to checkout page or cart page on cancelling the order
+ PLGWOOS-635: Add suggestion to set default initial order status for bank transfer to wc-on-hold
+ PLGWOOS-636: Add notification endpoint from version 3.8.0 to process deprecated notifications

### Changed
+ PLGWOOS-622: Change notification url for all payment methods to a single notification url

***

## 4.2.2
Release date: Mar 16th, 2021

### Fixed
+ PLGWOOS-632: Fix undefined method get_the_user_ip
+ PLGWOOS-621: Fix division by zero when fee price is 0

***

## 4.2.1
Release date: Mar 11th, 2021

### Fixed
+ PLGWOOS-613: Fix error related with multiple forwarded IPs by updating the PHP-SDK to 5.0.1

### Added
+ PLGWOOS-398: Add support to change the data in the OrderRequest using Wordpress filters

### Changed
+ PLGWOOS-614: Avoid changing order status if transaction is partially refunded

***

## 4.2.0
Release date: Mar 9th, 2021

### Changed
+ PLGWOOS-602: Move invoice and shipped settings field from order status tab to options tab
+ PLGWOOS-602: Remove completed status from order status tab in settings page
+ PLGWOOS-601: Change default status for declined transactions from wc-canceled to wc-failed

### Fixed
+ PLGWOOS-599: Fix typo in string message when payment method changes
+ PLGWOOS-598: Replace hardcoded url using plugins_url function
+ PLGWOOS-605: Fix description of country filter field

### Added
+ PLGWOOS-603: Add setting field for custom order description
+ PLGWOOS-604: Add forwarded ip to the CustomerDetails object
+ PLGWOOS-597: Support for orders with is_vat_exempt
+ PLGWOOS-606: Add chargedback transaction status in plugin settings

***

## 4.1.8
Release date: Mar 5th, 2021

### Changed
+ PLGWOOS-593: Register PSP ID in WooCommerce order using order complete payment method 
+ PLGWOOS-593: Change notification method on completed status to use $order->complete_payment()

### Fixed
+ PLGWOOS-594: Fix Credit Card payment method form, to show description if customer is not logged in

***

## 4.1.7
Release date: Mar 3th, 2021

### Changed
+ PLGWOOS-579: Remove warning message on validation, when enabling CREDITCARD gateway

### Fixed
+ PLGWOOS-584: Fix conflict with third party plugins related with Discovery exception 
+ PLGWOOS-585: Set MultiSafepay transaction as shipped or invoiced using order number instead of order id

***

## 4.1.6
Release date: Mar 2nd, 2021

### Added
+ PLGWOOS-574: Add locale support

### Changed
+ PLGWOOS-575: Change settings page capability requirement from manage_options to manage_woocommerce

### Fixed
+ PLGWOOS-580: Show credit card payment method description in checkout
+ PLGWOOS-569: Remove class that trigger validation styles for ideal select in checkout page

***

## 4.1.5
Release date: Feb 24th, 2021

### Fixed
+ PLGWOOS-552: Fix product item price with discounts introduced by third party plugins (#252)

***

## 4.1.4
Release date: Feb 23th, 2021

### Fixed
+ PLGWOOS-563: Remove some nonce validations to support custom checkouts forms (#249)
+ PLGWOOS-550: Typecast cart item quantity to int to avoid errors in the PHP-SDK (#248)

### Changed
+ PLGWOOS-556: Change composer dependencies to avoid conflicts with other plugins (#247)  
+ PLGWOOS-562: Add fallback for in3, in case no fields is filled in checkout, convert the transaction to redirect type (#250)  

***

## 4.1.3
Release date: Feb 23th, 2021

### Fixed
+ PLGWOOS-549: Support custom order numbers generated by third party plugins in notification method
+ PLGWOOS-551: Resize logo if theme used by merchant do not support WooCommerce

***

## 4.1.2
Release date: Feb 19th, 2021

### Fixed
+ PLGWOOS-548: Fix iDEAL gateway if no issuer selected in checkout

***

## 4.1.1
Release date: Feb 18th, 2021

### Changed
+ PLGWOOS-545: Remove API Key validation

***

## 4.1.0
Release date: Feb 17th, 2021

### Added
+ PLGWOOS-512: Add support for tokenization.
+ PLGWOOS-521: Change order status on callback even if merchant did not save the settings, using defaults.
+ PLGWOOS-530: Process notification, even when the payment method returned by MultiSafepay is not registered as WooCommerce gateway.
+ PLGWOOS-531: Avoid process refund if amount submited in backend is 0

### Fixed
+ PLGWOOS-535: Fix bug min_amount filter
+ PLGWOOS-536: Fix instructions in multi select country field
+ PLGWOOS-518: Fix protocol of notification URL
+ PLGWOOS-526: Fix typo error in AfterPay payment method title
+ PLGWOOS-523: Fix type of transaction to redirect for Dotpay payment method

### Changed
+ PLGWOOS-519: Improvement for coupons support in ShoppingCart.
+ PLGWOOS-528: Refactor gender and salutation fields to process different validation messages
+ PLGWOOS-503: Move debug mode field to options section

### Removed
+ PLGWOOS-525: Remove validation in backend for MultiSafepay payment method
+ PLGWOOS-516: Avoid initialize the plugin if WooCommerce is not active

***

## 4.0.0
Unreleased

### Added
+ Full and partial refunds for non billing suite payment methods
+ Full refunds for billing suite payment methods
+ Set MultiSafepay transactions as shipped when order reach the defined status in settings
+ Set MultiSafepay transaction as invoiced when order reach the defined status in settings
+ Filter payment methods by country
+ Filter payment methods by maximum amount of order
+ Filter payment methods by minimum amount of order
+ Custom initialized status for each payment method 
+ Validations in backend settings fields
+ Support for compound taxes

### Changed
+ Complete rewrite of the plugin
+ PLGWOOS-410: Refactor plugin using the [PHP-SDK](https://github.com/MultiSafepay/php-sdk)

### Removed
+ Remove FastCheckout

***

## 3.8.0
Release date: Oct 29th, 2020

### Added
+ PLGWOOS-421: Add Good4fun Giftcard

### Changed
+ DAVAMS-313: Rebrand Klarna to Klarna - buy now, pay later
+ DAVAMS-296: Rebrand Direct Bank Transfer to Request to Pay
+ DAVAMS-282: Update name and logo for Santander

***

## 3.7.0
Release date: Aug 14th, 2020

### Added
+ DAVAMS-237: Add in3 payment method

***

## 3.6.1
Release date: Aug 5th, 2020

### Fixed
+ PLGWOOS-404: Fix setting order to shipped when DHL is used

***

## 3.6.0
Release date: Jul 22nd, 2020

### Added
+ DAVAMS-266: Add CBC payment method

### Fixed
+ PLGWOOS-403: Fix FastCheckout not working
+ PLGWOOS-400: Apply set to shipped status only for MultiSafepay orders

***

## 3.5.2
Release date: Jun 25th, 2020

### Fixed
+ PLGWOOS-401: Fix rounding issues in shopping cart
+ PLGWOOS-394: Fix issue with translations not correctly loaded
+ PLGWOOS-397: Fix database already exists error

***

## 3.5.1
Release date: Apr 24th, 2020

### Fixed
+ PLGWOOS-395: Javascript error when Apple Pay is disabled
+ PLGWOOS-389: Fix addressparser not parsing housenumber extension correctly

### Changed
+ PLGWOOS-240: Improve plugin loading by using PSR-4 autoloader

### Removed
+ PLGWOOS-391: Remove TrustPay
+ PLGWOOS-390: Remove FerBuy
+ PLGWOOS-380: Remove Erotiekbon
+ PLGWOOS-327: Remove Lief Cadeaukaart
+ PLGWOOS-326: Remove Fijncadeau

***

## 3.5.0
Release date: Mar 30th, 2020

### Added
+ PLGWOOS-363: Add Apple Pay
+ PLGWOOS-384: Add Direct Bank Transfer

***

## 3.4.0
Release date January 6th, 2020

### Added
+ PLGWOOS-287: Add maximum amount restriction for credit cards
+ PLGWOOS-321: Add Ohmygood Cadeaukaart

### Changed
+ PLGWOOS-115: Make suitable for WordPress.org Plugin Directory
+ PLGWOOS-260: Change VVV Bon to VVV Cadeaukaart

### Fixed
+ PLGWOOS-319: Disable payment fields when payment description is empty

## 3.3.0
Release date December 13th, 2019
### Added
+ PLGWOOS-291: Add IP validation when WooCommerce returns multiple IP addresses
+ PLGWOOS-203: Add compatibility with WPML

### Changed
+ PLGWOOS-245: Change Klarna from direct to redirect
+ PLGWOOS-275: Improve Dutch translation for 'Activate'
+ PLGWOOS-263: Correct ING Home'Pay spelling

### Removed
+ PLGWOOS-208: Remove the send invoice option from the backend

### Fixed
+ PLGWOOS-285: Fix the fatal error "Cannot redeclare error_curl_not_installed"
+ PLGWOOS-102: Prevent the Notification URL from executing when not initialized by MultiSafepay
+ PLGWOOS-266: Prevent errors from appearing in logs for notifications of pre-transactions
+ PLGWOOS-290: Resolve DivisionByZeroError bug occurring with fees 
+ Fix PHP notice incorrect use of reset in function parseIpAddress
+ Fix PHP notice undefined property when order set to shipped

## 3.2.0
Release date July 5th, 2018
### Improvements
+ PLGWOOS-232: Add TrustPay payment method
+ PLGWOOS-213: Add support for external fee plugin(s)
### Fixes
+ PLGWOOS-176: Restrict autoload to load only MultiSafepay classes
+ PLGWOOS-191: Refactor the way an order and transaction are retrieved
+ PLGWOOS-241: Remove status request on setting to shipped
+ PLGWOOS-195: Update Klarna Invoice link
+ PLGWOOS-231: Update Klarna payment method logo
+ PLGWOOS-197: Correct MultiFactor Terms and Condition link
+ PLGWOOS-242: Remove terms and conditions for E-Invoicing
+ PLGWOOS-244: Shipment name now used on Payment page instead of type
+ PLGWOOS-243: Payment page shopping cart reorganized
+ PLGWOOS-253: FastCheckout load correct first and last name
+ PLGWOOS-235: Rename KBC/CBC to KBC
+ PLGWOOS-236: Rename ING-Homepay to ING HomePay
+ PLGWOOS-247: Notice message 'Undefined variable' for E-Invoice, Pay After Delivery and Klarna
+ PLGWOOS-249: Remove whitespace at file headers
***

## 3.1.0
Release date: June 8th, 2018
### Improvements
+ PLGWOOS-215 Add support for Santander Betaal per Maand
+ PLGWOOS-214 Add support for AfterPay
+ PLGWOOS-216 Add support for Trustly

### Fixes
+ PLGWOOS-221: Do not add Klarna invoice link when setting order to Completed
+ PLGWOOS-218: Fixed undefined property in error logs when cancelling order
+ PLGWOOS-226: getTimeActive didn't respect seconds
***

Release date: Feb 2nd, 2018
### Improvements
+ PLGWOOS-169 Support direct transactions for Alipay/ING/Belfius/KBC
+ PLGWOOS-174 Remove usage of deprecated functions
+ PLGWOOS-175 Remove unnecessary use of file_exists
+ PLGWOOS-178 Order status is only changed to 'expired' in case the current status is 'pending' or 'on-hold'.
+ PLGWOOS-179 Add text domain for iDEAL issuer error message
+ PLGWOOS-182 Add Alipay as payment method
+ PLGWOOS-186 Add dynamic retrieve of shipping methods during Fast Checkout
+ PLGWOOS-187 Do not allow refund when amount is zero or less
+ PLGWOOS-192 Check/add all translations

### Fixes
+ PLGWOOS-173 Fix deprecated notice getRealPaymentMethod
+ PLGWOOS-180 Incorrect order-id used to load the order for updating
+ PLGWOOS-181 function getGatewayCode not implemented for FastCheckout
+ PLGWOOS-183 Update version number of plugin failed
+ PLGWOOS-184 Incorrect check if field is empty
+ PLGWOOS-193 Fix deprecated notice FastCheckout
+ PLGWOOS-194 Refund function checks wrong variable to determine if refund was successful
+ PLGWOOS-199 Correct wc_get_cart_url and wc_get_checkout_url
+ PLGWOOS-200 FastCheckout doesn't redirect to order-confirmation screen
+ PLGWOOS-202: Payment method updated for Second Chance on Processing

### Changes
+ PLGWOOS-189 Update version number to 3.0.4
+ PLGWOOS-198 Update ING gateway to INGHOME

***

## 3.0.3
Release date: Oct 10th, 2017

(Requires WooCommerce 2.2+)

### Fixes

+ Menus are able to edit again.
+ In some cases, the customer was redirected to the cancel-url after a successful iDEAL transaction.

***

## 3.0.2
Release date: Okt 10nd, 2017
### Improvements
+ Add ING Home'Pay as payment method.
+ Add Belfius as payment method.
+ Add KBC/CBC as payment method.
+ Add configuration option for Google-Analytic code.
+ Add shopping-cart information to the transaction.
+ Update payment method in order, in case a customer pays the Second Chance with another payment method.
+ Update the Dutch translations.

### Fixes
+ Fixed issue to prevent a warning message when the title of a gateway wasn't filled in the config.
+ Fixed issue with retrieve the correct external transaction ID.
+ Fixed issue on error 1027 (Invalid cart amount) caused by an invalid shipping-tax.
+ Fixed issue in function to set order-status to shipped for Pay After Delivery, Klarna and E-Invoiced.
+ Fixed warning issue on function setToShipped.
+ Fixed issue on not accepting Pay After Delivery orders caused by a divide by zero error.

Changes
+ Remove (beta)functionality to determine if there is a new version available.
+ Restrict use of the plugin to WooCommerce 2.2 and above.

***

## 3.0.0
Release date: April 5nd, 2017
### Improvements
+ Compatible with PHP-7
+ Installation by standard Wordpress method
+ Added Dutch language file
+ Added configuration option Karna Merchant-EID (for future use.)
+ Added Terms and Conditions for Klarna, Pay After Delivery and E-Invoicing.
+ Improve the way errors are logged.
+ Added PaySafeCard as payment method.
+ Added Nationale bioscoopbon as a gift card.
+ Added option to the global MultiSafepay settings to enable/disable the gift cards as payment method.

### Fixes
+ Better algorithm to split address into street, house number
+ After complete FastCheckout transaction no order confirmation page was showed

Changes
+ General plugin settings moved to the general checkout-options
+ Remove Baby gift card as payment method

***

## 2.2.7
Release date: November 2nd, 2016
### Improvements
+ Added EPS and FerBuy as payment methods
+ Added support for E-Invoicing
+ Added an extra payment method gateway called "Credit cards"; grouping credit card payment methods as a single dropdown option.

### Fixes
+ Resolved an issue resulting in not being able to pay using Direct iDEAL.
+ Resolved an issue where expiring payment sessions result in orders being marked as new after 30 days.

### Changes
+ Changed Bank transfer to direct bank transfer

***

## 2.2.6
Release date: July 14th, 2016
### Improvements
+ Added support for WooCommerce version 2.6.2.

### Fixes
+ Resolved an issue resulting in not being able to pay using Direct iDEAL.

***

## 2.2.5
Release date: June 24th, 2016
### Improvements
+ Added support for partial refunds for orders paid using Klarna and Pay After Delivery.
+ Added support for Fast Checkout order refunds.
+ ### Improvements were made to the iDEAL banklist selector, and a notice will be shown if no bank was selected.

### Fixes
+ Updated the Bancontact logo

### Fixes
+ Resolved issues occurring with Pay After Delivery and Klarna when using discounts.
+ Made compatible with WooCommerce version 2.6.



## 2.2.4
Release date: March 8th, 2016
### Improvements
+ Pay After Delivery is now only visible for orders placed in The Netherlands.
+ Textual ### Improvements for the option "Send the order confirmation".
+ Started orders with bank transfer, are now set to On Hold, rather than "Pending Payment".
+ Uncleared orders are now set to On Hold, rather than "Pending Payment".
+ Improved the iDEAL description shown when no iDEAL issuer/bank has been selected.

### Fixes
+ Resolved a bug causing Error 1035 when refunding.
+ Changed the way coupons are applied, which previously resulted in a mismatch in paid totals.

***

## 2.2.3
Release date: Feb 18, 2016
### Improvements
+ Added Dotpay as a payment method
+ Klarna and Pay After Delivery transactions are now set to Shipped, if enabled and the order is set to Completed.
+ Pay After Delivery is now only available as a payment method if the selected country is "The Netherlands".
+ Multistores in WooCommerce are now supported.
+ Added bunq as a supported iDEAL issuer

### Fixes
+ Refunds from within WooCommerce now also work when using the WooCommerce Sequential Order Numbers plugin.
+ Issues with Gateway restrictions based on minimum and maximum amount are resolved for Klarna and Pay After Delivery.
+ Fixed a bug causing the postalcode not to be added to the order when using Fast Checkout.
+ Removed WooCommerce mailer functions in the plugin, which was added to avoid mailing issues.

***

## 2.2.2
Release date: Dec 14, 2015

### Improvements
+ Added Klarna reservationcode and link to the invoice in the order comments.
+ For KLARNA and Pay After Delivery the order status is set to shipped when order status is set to completed and this option is enabled in the configuration.
+ Added Goodcard as gift card.

### Fixes
+ Fixed performance issue due to our plugin loaded the iDEAL issuers on every page.
+ Fixed house number is now correct parsed when using both address fields.
+ Fixed issue with wrong processing of some order statuses.
+ Fixed the FastCheckout button was not completely visible with latest updates of WooCommerce default template.

***

## 2.2.1
Release date: Sep 30, 2015

### Improvements
+ Added Klarna as payment method.

### Fixes
+ Fixed issue that prevents MultiSafepay to add the order status in the order comment.

***

## 2.2.0
Release date: May 21, 2015
### Improvements
+ Added an extra check to determine if the MultiSafepay class exists.
+ Debug option added to the plugin for troubleshooting purposes.
+ Added improved payment method icons.
+ Added the MultiFactor agreement hyperlink.
+ Added Refund API support. Refunds via MultiSafepay can now be executed from the WooCommerce backend.
+ Added a check to see if WooCommerce is active. The plugin will not be loaded if not the case.

Changes
Changed add_error(); to wc_add_notice();

### Fixes
+ Fixed some undefined notices and improved checks for page_id and the loading of the plugins.
+ Resolved the 'Cannot redeclare class' error.

***

## 2.1.0
Release date: Oct 15, 2014
### Improvements
+ Added Fast Checkout
+ Added coupon support for FCO
+ Added option to enable/disable fco button
+ Added DB Table to check if order is already created and if so, go to normal updating process when using Fast Checkout
+ Added amount check that compares the calculated order total after creating the order and the transaction amount. If they are not equal, then set to wc-on-hold status and add a note about the mismatch in amounts
+ Added Pay After Delivery as a separate plugin
+ Added American Express as a separate plugin
+ Added PayPal as a separate plugin
+ Added Visa as a separate plugin
+ Added Mistercash as a separate plugin
+ Added Mastercard as a separate plugin
+ Added Maestro as a separate plugin
+ Added Giropay as a separate plugin
+ Added SOFORT Banking as a separate plugin
+ Added DirectDebit as a separate plugin
+ Added Bank transfer as a separate plugin
+ Added iDEAL as a separate plugin

### Changes
+ Changed the processing of the offline actions so that FCO transactions work
+ Process stock on process_payment
+ Use ordernumber instead of orderid so that the plugin is compatible with third-party sequential ordernumbers plugins
+ Removed gateway method from the main module. Gateways are now separate plugins
+ Removed images from main module. These are now loaded from each separate plugin
+ Removed version checks as this version is only for 2.2 and higher
+ Removed useless code from all plugins
+ Removed country and amount restrictions. WooCommerce changed things and broke the function

### Fixes
+ Fixed bug with status updates
+ Fixed new bug with coupons not being processed because of extra check on cart or order discount
+ Small ### Fixes (o.a. reported by Mark Roeling)

***

## 1.0.6
Release date: Apr 15, 2014
### Improvements
+ Added support for direct Pay After Delivery

***

## 1.0.5
Release date: Mar 21, 2014
### Improvements
+ Added support for
+ Added house number check

### Fixes
+ Fixed bug when customer canceled a payment
+ Fixed bug that causes an empty status
+ Fixed bug in refund check

***

## 1.0.4
Release date: Mar 06, 2014
### Improvements
+ Auto spit house number from address if needed

### Fixes
+ Fixed bug when customer canceled a payment
+ Fixed bug that causes an empty status
+ Fixed bug in refund check

***

## 1.0.3
Release date: Feb 19, 2014
### Improvements
+ Added support for WooCommerce 2.1.x
+ Added payment method Pay After Delivery
+ Changed payment name 'directebanking' to 'SOFORT Banking
+ Added support for third-party payment surcharge module
+ Added support for dollars and GBP
+ Added check for available issuers when paying by iDEAL
+ added orderid to the return URL

### Fixes
+ Fixed bug that caused no order data to show on success page

***

## 1.0.2
Release date: Aug 21, 2013
### Improvements
+ Optional send an invoice email

### Fixes
+ Fixed bug in update order status
