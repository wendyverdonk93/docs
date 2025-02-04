---
title: MultiSafepay glossary
breadcrumb_title: MultiSafepay glossary
weight: 60
meta_title: "FAQ General - MultiSafepay glossary - MultiSafepay Docs"
layout: 'single'
short_description: "Get familiar with payments terminology and specific MultiSafepay uses."
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
logo: '/svgs/Guides.svg'
read_more: "."
aliases:
    - /faq/general/glossary
    - /faq/general/glossary/#3d-secure
    - /faq/general/glossary/#acquirer
    - /faq/general/glossary/#api
    - /faq/general/glossary/#api-key
    - /faq/general/glossary/#cron-job
    - /faq/general/glossary/#customer
    - /faq/general/glossary/#closed-loop-gift-card
    - /faq/general/glossary/#cvc
    - /faq/general/glossary/#e-mandate
    - /faq/general/glossary/#issuer
    - /faq/general/glossary/#json
    - /faq/general/glossary/#merchant
    - /faq/general/glossary/#multisafepay-account
    - /faq/general/glossary/#open-loop-gift-card
    - /faq/general/glossary/#payment-method
    - /faq/general/glossary/#payment-service-provider
    - /faq/general/glossary/#payout
    - /faq/general/glossary/#plugin
    - /faq/general/glossary/#payment-services-directive-2
    - /faq/general/glossary/#payment-card-industry-data-security-standard
    - /faq/general/glossary/#strong-customer-authentication
    - /faq/general/glossary/#surcharge
    - /faq/general/glossary/#ultimate-beneficial-owner
    - /faq/general/glossary/#uncleared
    - /faq/general/glossary/#website
---

### acquirer
A financial institution that processes credit and debit card payments with card issuers on behalf of merchants. MultiSafepay is an acquirer for Visa, Mastercard, and Bancontact.

### affiliated merchant
A merchant referred to MultiSafepay and controlled by a primary merchant account or a partner account. 

### API endpoint
A specific URL in [our API](/api/) where merchants send requests to exchange information, e.g. about /orders, /gateways.

### backend
The part of a merchant's integration not accessible to customers. Here you can connect with MultiSafepay, configure settings, process refunds, make API requests, and receive notifications.

### cardholder
A customer who uses a card issued by a bank to make cashless payments to a merchant.

### card scheme
A financial institution that issues credit cards, provides infrastructure, and processes payments for a fee, e.g. Visa, Mastercard, American Express.

### card verification code (CVC)
A 3 or 4 digit code customers enter as an additional layer of security for online credit or debit card payments. Not required for all cards, or for recurring payments.

### chargeback
When a customer disputes a credit card transaction and the transaction is reversed. See [Chargebacks](/faq/chargebacks/).

### collecting party
The party that receives the funds for a transaction directly from the customer, before transferring them to the merchant.

### conversion rate
How often customers visiting a merchant's integration place an order and complete payment.

### credit card
A card issued by a bank, building society, or card scheme that lets the holder pay for products or services on credit.

### customer
A person or company that buys products and services from merchants.

### custom integration
A merchant's bespoke integration with MultiSafepay's services built using [our API](/api), SDKs, or wrappers.

### debit card
A card issued by a bank that transfers funds directly from the customer's bank account.

### developer
A software developer a merchant employs to work on the technical side of their integration.

### dispute
If a customer wants a merchant to return funds that have already been captured, the customer can request a refund. If the merchant refuses, the customer may request their bank to make a chargeback. If the merchant disagrees, they can dispute the chargeback.

### ecommerce platform
An online [platform](/payments/integrations/ecommerce-platforms/) merchants use for accepting payments, e.g. website, mobile app, [PWA](/payments/integrations/pwa/). 

### fraud
When a person tries to receive products without paying for them by tricking a customer or merchant.

### integration
Software merchants use to sell products and services and accept payments, e.g website, mobile app, [PWA](/payments/integrations/pwa/). Merchants may use [ecommerce platforms](/payments/integrations/ecommerce-platforms/) or build a custom integration.

### item
A product or service in a customer's shopping cart and/or order.

### issuer
The customer's bank, which verifies transaction information and sends funds to the collecting party. For credit or debit card payments, the bank issues the card.

### liability
The risk of accepting credit card payments and responsibility for paying for [chargebacks](/faq/chargebacks/).

### merchant
A company (legal entity) that sells products and services to customers.

### MultiSafepay account
A merchant's account with MultiSafepay, managed via a [web dashboard](/tools/multisafepay-account/).

### MultiSafepay balance
The balance of funds held in a MultiSafepay account.

### onboarding
When MultiSafepay checks and approves information submitted by merchants and partners applying for a live account.  

### order
All information related to a single instance of products and/or services sold to a customer that is linked to one or more transactions.

### partner account
The account of a company that is not itself a merchant, but refers affiliated merchants to MultiSafepay on commission.

### payment
The industry and the product MultiSafepay sells. For customers: When you confirm to transfer funds.

### payment details
The payment information for a specific customer, e.g. credit card number, CVC code.

### payment gateway
Transfers the customer's payment details to where the payment method is processed.

### payment page
A webpage the customer is redirected to from the merchant's checkout page where they complete payment. The page may be hosted by MultiSafepay (see [PayV2](/payments/checkout/payment-pages/activating-payv2/)), the issuer, or the payment method. 

### payment service provider (PSP)
MultiSafepay is a PSP and provides services that let merchants accept payments using different payment methods.

### payout
When a merchant transfers funds from their MultiSafepay balance to their business bank account. See [Paying out funds from your MultiSafepay balance](/faq/finance/paying-out-funds-from-your-multisafepay-account/). 

### point of sale (POS) terminal
A terminal that accepts payments, usually by card or near-field communication (NFC), at a merchant's physical location, e.g. a store.

### RESTful API (application programming interface)
The interface and set of protocols merchants use to exchange data with the MultiSafepay server. Our [API Reference](/api/) specifies the content and format of requests to our server and the responses the server sends back.

### SEPA
The Single Euro Payments Area (SEPA) is a European Union payment-integration initiative. Customers can quickly and securely transfer euros within the EU and to a number of non-EU countries.

### shopping cart
A container in the merchant's integration where customers place items for an order preparing for payment.

### token/tokenization
Tokenization is storing customer payment details as a token (a unique string of numbers). For customers, it makes future payments faster and easier. For merchants, it enables repeatedly debiting customers, e.g. for subscriptions. 

### transaction
An instance of funds being transferred, e.g. customers paying merchants, merchants refunding customers. In our system, the [transaction status](/api/multisafepay-statuses/) changes as the funds move through the different stages of the payment flow.

### ultimate beneficial owner (UBO)
A person who ultimately benefits from a merchant's company, and owns or controls 25% or more of affairs, shares, or voting rights. 

### we
MultiSafepay

### you
Merchants and developers
