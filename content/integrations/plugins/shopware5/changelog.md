---
title : "Release Notes Shopware 5 plugin"
meta_title: "Shopware 5 plugin changelog - MultiSafepay Documentation Center"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

## 2.1.0
Release date: Jul 3rd, 2019
### Added
+ PLGSHPS-97: Add Webshop gift card as a gift card
+ PLGSHPS-80: Implement customizable refund and shipment statuses
+ PLGSHPS-78: Add track trace code in shipment request
+ PLGSHPS-91: Add notification when update transaction status to shipped is declined
+ PLGSHPS-91: Add notification when refund is declined


### Fixes

+ PLGSHPS-118: Prevent sporadic CSRF token warning on checkout
+ PLGSHPS-86: Do not update payment status if it was already set to paid
+ PLGSHPS-87: Prevent duplicated calls to setting the cleared date on an order
+ PLGSHPS-134: Disable auto-submit for iDEAL issuers dropdown
+ PLGSHPS-129: Save iDEAL issuer choice when switching between shipment methods


### Changes

+ PLGSHPS-112: Correct spelling of ING Home'Pay
+ PLGSHPS-110: Use shipment name in shopping cart
+ PLGSHPS-114: Hide iDEAL issuers on preferred payment page

## 2.0.2
Release date: Mar 19th, 2019
### Fixes
PLGSHPS-130: Add support for Shopware 5.5.7
PLGSHPS-119: Fix refund and shipment didn't work for  5.5.x

## 2.0.1
Release date: Aug 24th, 2018
### Improvements
PLGSHPS-105: Add support for subshops

### Bugs
PLGSHPS-104: Remove spaces in quote number to prevent 1006 errors
PLGSHPS-107: Fix error 1000: optional ipaddress

## 2.0.0
Release date: Jul 24th, 2018
### Changes
Shopware MultiSafepay plugin 2.0.0

***

## 1.0.6
+ Fix PLGSHPS-51: Success page corrected for Bank transfer
+ Fix PLGSHPS-50: Improve time active layout

## 1.0.5
+ Fix PLGSHPS-48: Restore support for locale
+ Fix PLGSHPS-49: Improve shipping tax table logic

## 1.0.4
+ Fix PLGSHPS-47: payment missing for some orders
+ Fix PLGSHPS-46: correct tax when custom taxes are used
+ Fix PLGSHPS-45: correct shipping tax table when custom taxes are used
+ Fix PLGSHPS-36: Add seconds_active/days_active support
+ Fix PLGSHPS-43: Add support for subshops
+ Fix PLGSHPS-42: add support for shipping address

## 1.0.3
+ Made compatible with Shopware 5.3.x
+ Restored order creation to after transaction started (adheres to Shopware standard)

## 1.0.2
+ Added EPS, Ferbuy, Klarna Invoice.
+ Moved order creation to before transaction, which started to prevent missing orders.
+ Made compatible with 5.1+
+ Made compatible with 5.2+
+ Fixed PHP7 deprecated warnings.
