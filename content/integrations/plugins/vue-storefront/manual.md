---
title : "MultiSafepay Vue Storefront installation & configuration manual"
meta_title: "Vue Storefront plugin manual - MultiSafepay Documentation Center"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

### Introduction

{{% introduction_plugin "Vue Storefront" %}}

### 1. Requirements
Clone this git repository from within your vue-storefront-api root folder

```shell
git clone git@github.com:MultiSafepay/vsf-multisafepay-service-api.git src/api/extensions/vsf-multisafepay-service-api
```
__Run yarn to install dependencies__

#### Register the Vue Storefront API extension

Add the API extension to the registered extensions to `local/config.json`

```json
"registeredExtensions": [
  ...,
 "vsf-multisafepay-service-api"
]
```

#### Add the MultiSafepay settings for the [Test](https://testapi.multisafepay.com/v1/json) and [Live](https://api.multisafepay.com/v1/json) API.


```json
"extensions": {
  ,,,
  "multisafepay": {
    "api_key": "YOUR_MULTISAFEPAY_API_KEY",
    "api_url": "https://api.multisafepay.com/v1/json"
  }
}

```

### 2. Installation

Follow these steps to install this module in Vue Storefront.

First, make sure you meet these requirements for your Magento 2 installation.

#### Requirements for Magento 2

MultiSafepay Payments for Magento 2 module installed, you can get it here: https://github.com/MultiSafepay/Magento2Msp - you can follow the installation steps in the README file.

#### Requirements for Vue Storefront API

Add the Vue Storefront API extension we created for the MultiSafepay Payments API: https://github.com/MultiSafepay/vsf-multisafepay-service-api - you can follow the installation steps in the README.

#### Requirements for Vue Storefront

After making sure to meet the above mentioned requirements, please follow the next steps to integrate this module in Vue Storefront.

Clone this git repository from within your vue-storefront root folder

```shell
git clone git@github.com:MultiSafepay/vsf-payment-multisafepay.git src/modules/vsf-payment-multisafepay
```

#### Module registration

Open `src/modules/client.ts`

Add:

```ts
...
import { MultiSafePayPaymentModule } from './vsf-payment-multisafepay'
```

And make sure to also register the module in registerClientModules

```js
registerModule(MultiSafePayPaymentModule);
```

#### Add configuration settings

Add the config properties in `config/local.json`

```json
"paymentService": {
"endpoint": "http://localhost:8080/api/ext/vsf-multisafepay-service-api"
},
```

Make sure to set the correct location to your API and the routes to the CMS pages in case of an error or an invalid payment status check.

#### Integration to theme

We used the default theme, below we'll sum up the changes that are necessary to completely integrate this module to your own theme if you're not using Vue Storefront default theme. We create a isolate components for separate the logic from VSF core.

- Add a method to the currentPage mixin to hide header and footer when communication with MultiSafepay API is processing - add condition to show header and footer in components depending on this method
- Remove default ThankYouPage as the customer goes immediately to the MultiSafepay payment gateway to pay for the placed order. The customer comes back to a customized order status page.

- Add PaymentMethods component into Payment checkout component to display Multisafepay payment methods, you can do with two differents approaches:

1º You can copy/paste the Payment component from this module to your default theme

Or

2º The first one is removing the following code on Payment componet (core/blocks/Checkout/Payment.vue):

```html
<div v-for="(method, index) in paymentMethods" :key="index" class="col-md-6">
	<label class="radioStyled">
		{{ method.title ? method.title : method.name }}
		<input
			type="radio"
			:value="method.code"
			name="payment-method"
			v-model="payment.paymentMethod"
			@change="$v.payment.paymentMethod.$touch(); changePaymentMethod();"
		/>
		<span class="checkmark" />
	</label>
</div>
```

And adding this one:

```html
<payment-methods
	:payment-methods="this.paymentMethods"
	:payment="this.payment"
	:validate="$v.payment"
	:change-payment-method="changePaymentMethod"
></payment-methods>
```

Remember also to import the component and add it on component section:

```js
import PaymentMethods from "src/modules/vsf-payment-multisafepay/components/PaymentMethods";
```

![order-review](https://user-images.githubusercontent.com/54272995/77530313-69a5ac80-6e91-11ea-9999-b1b329fd61e7.png)

#### Manage payment methods

To enable payment methods in your Vue Storefront checkout you have to follow these steps:

1. Enable the payment method in your MultiSafepay dashboard
2. Enable the payment method in the MultiSafepay Payments for Magento 2 module in your Magento 2 backend system
3. Add the payment methods to the payment_methods_mapping property in the order property config.

Here is a example:

```json
...
"orders": {
    "payment_methods_mapping": {
      "MAESTRO": "maestro",
      "BANKTRANS": "banktrans",
      "DIRECTBANK": "directbank",
      "GIROPAY": "giropay",
      "MISTERCASH": "mistercash",
      "EPS": "eps",
      "IDEAL": "ideal",
      "TRUSTLY": "trustly",
      "MASTERCARD": "mastercard",
      "VISA": "visa"
    },
}

```

To display also the images of each payment methods you have to below payment_methods_mapping the mapping for images, just copy and paste this:

```json
    "payment_methods_mapping_img": {
      "MAESTRO": "maestro",
      "BANKTRANS": "banktransfer",
      "DIRECTBANK": "sofortbank",
      "GIROPAY": "giropay",
      "MISTERCASH": "mistercash",
      "EPS": "eps",
      "IDEAL": "ideal",
      "TRUSTLY": "trustly",
      "MASTERCARD": "master",
      "VISA": "visa"
    },
```

![payment-methods](https://user-images.githubusercontent.com/54272995/77526212-7ecb0d00-6e8a-11ea-8e9b-4d5fd9376c06.png)

#### Important notes

It's not yet possible to pay for orders that are placed when the user is offline.

### 4. Congratulations
You have installed and configured the plugin successfully. If you have any questions regarding the plugin, feel free to contact our Integration Team at <integration@multisafepay.com>
