---
title: "AfterPay, How it works"
weight: 21
meta_title: "AfterPay, How it works - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
aliases: [/payment-methods/afterpay/how-does-afterpay-work/]
---
## How it works

Pay-after-delivery methods let customers pay only for the items from their order that they keep. Sometimes the customer journey involves returning items. If a return takes too long to verify, you can place the invoice on hold to pause the collection period for 2 to 4 weeks. Email AfterPay at <merchant@afterpay.com> or phone +31 207230230.

If an AfterPay transaction receives **Uncleared** status, AfterPay accepts or declines the transaction.

- If declined, only the customer can ask AfterPay for the reason due to privacy rules.

- If accepted, AfterPay takes on the merchant risk. The customer must make the full payment to AfterPay within 14 days of the invoice date, unless otherwise agreed in writing.

## Transaction flow
Transaction flow is the different ways transactions can be processed.

- Order status: Indicates the status of the order: **Completed**, **Pending**, or **Rejected**. Independent of incoming or outgoing payments for the transaction.

- Transaction status: Indicates the payment status of the transaction: **Completed**, **Pending**, or **Rejected**. When the transaction status changes to **Completed**, the transaction amount is added to your MultiSafepay balance.


| Order status                      | Transaction status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Uncleared  | Uncleared  | AfterPay will accept or decline the transaction. No action is required.   |
| Completed  | Uncleared  | The transaction was successfully completed.   |
| Shipped    | Uncleared  | A capture has been sent to AfterPay, and the transaction is confirmed. MultiSafepay will send an invoice to the customer. Your payout is guaranteed. |
| Shipped    | Completed  | MultiSafepay has received the payout from AfterPay and added it to your MultiSafepay balance.|
| Declined   | Declined   | AfterPay has declined the transaction. View the reason in the declined status in your [MultiSafepay Control](https://merchant.multisafepay.com).     |
| Void       | Cancelled   | The transaction was cancelled.  | 
| Expired    | Expired    | If no action is taken within 90 days of receiving the transaction, it automatically expires. | 

## Refunds

| Order status                      | Transaction status      | Description |
|--------------------------------|-----------|-----------------------------------------------------------------------------------------|
| Initialized    | Completed   | A refund has been requested. | 
| Completed      | Completed   | The refund has been successfully processed.  | 

## Payouts

AfterPay guarantees payouts. Payouts are added to your MultiSafepay balance once received from AfterPay. The timeline is determined by AfterPay.

## API Reference

See API Reference – [AfterPay](/api/#afterpay).

## Product rules

* You cannot refund more than the original transaction amount. For more information, see FAQ – [Refunding more than the original transaction value](/faq/finance/refund-more-than-original-amount).

* There is no maximum period for refunding successful AfterPay transactions provided that the receiving bank can process the refund.

* You cannot adjust the lifetime of payment links. For more information, see FAQ – [Adjusting payment link lifetimes](/faq/api/adjusting-payment-link-lifetimes).

* If no action is taken within 90 days of receiving an AfterPay order, the transaction automatically expires.

* When the order status changes to **Shipped**, there is no time limit for refunding the transaction.

* Post-payment methods generally don't support [gift cards](/payment-methods/prepaid-cards/gift-cards) on payment pages because they require very accurate order specifications. MultiSafepay's platform would interpret gift cards as a discount and not reflect the correct order information, e.g. for taxation purposes. You can support gift cards on your checkout page **before** the customer places the order. You are responsible for enabling this feature. You must follow this rule to avoid errors.

* In Belgium, AfterPay requires an additional API key. Request the key from AfterPay.

* To process a partial refund for the same product with different specifications (e.g. size, color) via the shopping cart, each `merchant-item-id` must be unique.

* You must activate [PayV2 payment pages](/tools/payment-pages/activating-payv2/) for your website in your [MultiSafepay Control](https://merchant.multisafepay.com/switch-connect-v2). Go to **Settings** > **Payment pages**.

- The customer can provide different invoice and delivery addresses, but the customer's first and last name must share at least two characters. The **Transaction details** page for the transaction in your MultiSafepay Control only displays the invoice address. To retrieve the transaction details, make a [retrieve an order](/api/#retrieve-an-order) request using our API. 

- If you accept an order and ship it, you must change the order status from **Completed** to **Shipped** or the order can expire. This lets AfterPay initiate the billing process with the customer. For all MultiSafepay ecommerce integrations, you can change the order status:

    - Manually in your [MultiSafepay Control](https://merchant.multisafepay.com) on the **Transaction details** page
    - Automatically in your backend 
    - Automatically by making an [update an order](https://docs.multisafepay.com/api/#update-an-order) request to our API. Your MultiSafepay Control is automatically updated when the plugin makes a correct API call to change the order status to **Shipped**. 