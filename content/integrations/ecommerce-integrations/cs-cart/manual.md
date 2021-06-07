---
title : "MultiSafepay CS-Cart installation and configuration manual"
meta_title: "CS-Cart plugin manual - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
aliases:
    - /plugins/cs-cart/manual
    - /integrations/plugins/cs-cart/manual
    - /integrations/cs-cart/manual
---

This technical manual is for installing and configuring the MultiSafepay plugin for CS-Cart.

We recommend first installing the plugin in a test environment following the recommended Shopware 6 installation procedure. Make sure you have made a backup.

### Technical support
Contact us:

- Telephone: +31 (0)20 8500 500
- Email: <integration@multisafepay.com>
- GitHub: Create a technical issue

### Requirements
- MultiSafepay account – See [Getting started](/guides/getting-started/).
- CS-Cart 4.x
- Tested on PHP 7.0

<<<<<<< HEAD
### 2. Installation
 1. Unpack the content of the .ZIP file in the root of your webshop
 2. Go to yourdomain.com/msp_installer.php. This will trigger the installation
 3. Delete the msp_installer.php file
 4. Enter your notification URL in your [MultiSafepay Control](https://merchant.multisafepay.com)<br> 
 More information can be found on [our Notification URL page](/tools/multisafepay-control/set-your-notification-url)

### 3. Configuration
1. Log in to your backend and navigate to _Adminination_ > _Payment Method_
2. Then click on the _+_ symbol to add a payment method
3. In the next screen you enter a name that will be shown during checkout. In the _Processing unit_ field, you specify the desired payment method. The other fields can be filled according to your own wishes. Click on _Create_
4.  Then click on the _Configure_ tab
5. Enter your Account ID, Site ID & Site Code. {{% account_info %}}
Your Account ID is shown in the dashboard of your MultiSafepay Control in the top right corner

Note:
There are also a number of extra options such as _IP-Validation_ and _debugmode_. These serve especially for developers and can remain unchanged.

### 4. Congratulations
=======
### Installation
 1. Unpack the content of the .ZIP file in the root of your CS-Cart webshop.
 2. To trigger the installation, go to `yourdomain.com/msp_installer.php`. 
 3. Delete the `msp_installer.php` file.
 4. In your [MultiSafepay Control](https://merchant.multisafepay.com), provide your [notification URL](/tools/multisafepay-control/set-your-notification-url).

### Configuration
1. Log in to your CS-Cart backend.
2. Go to **Administration** > **Payment methods**.
3. To add payment methods, click the **+** button.
4. In the next screen, enter a name for the payment method to display during checkout. 
5. In the **Processing unit** field, specify the payment method. 
6. Fill out the other fields as required.
7. Click **Create**.
8. In the **Configure** tab, enter your account ID, site ID, and site code. {{% account_info %}}
Your account ID appears in the top right corner of your MultiSafepay Control.

Extra options such as **IP-Validation** and **debugmode** are intended for developers. Leave them unchanged.

>>>>>>> master
For any questions about the plugin, email the Integration Team at <integration@multisafepay.com>
