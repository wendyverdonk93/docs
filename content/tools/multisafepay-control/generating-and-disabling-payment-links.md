---
title : "Generating and disabling payment links"
weight: 34
meta_title: "MultiSafepay Control- Generating and disabling payment links - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
aliases:
    - /tools/multisafepay-control/manually-generated-payment-link
---

Payment links create a unique transaction in your [MultiSafepay Control](https://merchant.multisafepay.com/) to match to a payment.

### Manually generating payment links

You might need to manually generate a payment link if:

- A customer wants to adjust an existing order and instead of starting over with a new order, you generate an adjusted (new) payment link.

- You have created an order manually for a customer.

- MultiSafepay receives a payment from a customer with an unmatching amount. If you accept the payment, you need to manually generate a payment link and email it to MultiSafepay.

- A bank transfer payment link has expired.

To manually generate a payment link, follow these steps:

1. Log in to your [MultiSafepay Control](https://merchant.multisafepay.com).
2. Go to **Tools** > **Payment link generator**.
3. Click the **New payment link** button.
4. From the **Site** dropdown menu, select the relevant website.
5. Under **Amount**, select the currency from the dropdown menu, and then enter the whole value and cents.
6. In the **Order ID** field, enter the order ID from your webshop. The Order ID in every payment link must be unique.
7. In the **Description** field, enter a description of the order. 
8. In the **Link expiration (days)** field, enter the number of days the link remains active.
9. If needed, select the **Second chance email** check box. 
10. Optionally, enter the customer's:

  - **First name**
  - **Last name**
  - **Email address**
  - **Country**
  - **Language**
11. Click **Generate payment link**.
13. Copy the newly generated link from the green bar and email it to the customer.

#### Creating a payment link by duplicating an order

If you want to send a payment link for an existing transaction, you can duplicate the transaction via the transaction itself. __The Order ID must also be unique.__

#### 'Simple Mode' or 'Advanced Mode'

The 'Simple Mode' is the default payment link mode with the minimum necessary information. 

In the 'Advanced Mode', you can fill in the order items and add extra information related to the customer such as articles, birthday, full address and phone number. 

#### Validity of a manually generated payment link 

The default validity of a manually generated payment link is 30 days. However, you can adjust this to a shorter or longer period depending on your preference. 

#### Summary of all manually generated payment links

1. Log in to your [MultiSafepay Control](https://merchant.multisafepay.com)
2. Click on _Tools_ > _Payment link generator_.

You will now be able to see a history of all generated payment links including the date of creation and status. 

#### Cancelling a payment link
On the summary page of the payment links, there is a red circle button next to each payment link.  After clicking on the button, the status will be changed to _Cancelled_. 

|  Status      | Description |
|-------------|---------------------------------------------------------------------------|
| Active      | A payment link has been generated, but the payment has not yet been fulfilled.  | 
| Completed   | The payment link has been successfully received. | 
| Cancelled   | The payment has been cancelled by the merchant.| 
| Expired     | The link has automatically expired after a predefined period.  | 

#### Payment methods and payment links 

In theory, for every payment method it's possible to add a manually generated payment link, depending on the availability of the payment methods in MultiSafepay Control. However, it is important to check your webshop's requirements in relation to a certain payment method and its support.

For example, post-payment methods such as AfterPay, Pay After Delivery and Klarna do not support manually generated payment links, due to the insolvency process requirement that creates a different flow and dynamics around these payment methods.

#### Disabling a payment link for a payment method
Disabling a payment link is only possible in the site profile. In this case, as a merchant you will need a separate Site ID in which only the desired payment methods are available. For more information you can contact the Integration Team at <integration@multisafepay.com>

#### Generating a payment link in the backend of a webshop

The short answer is yes. However, this depends on the webshop you are using.

For example, for Magento 1 or own integration, a payment link can be created in the backend of the webshop using our [API tool](https://docs.multisafepay.com/api/#create-an-order). The parameter _type_ must be filled with 'payment link'. 

For more information on this topic, please contact the Integration Team at <integration@multisafepay.com>

For the full API reference on manually creating a payment link, please refer to the [generating a payment link page](/api/#generating-a-payment-link).
