---
title : "MultiSafepay Odoo installation & configuration manual"
meta_title: "Odoo plugin manual - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
aliases:
    - /support-tab/odoo/manual
    - /plugins/odoo/manual
    - /integrations/plugins/odoo/manual
    - /integrations/odoo/manual
---

This technical manual is for installing and configuring the MultiSafepay plugin for Odoo.

We recommend first installing the plugin in a test environment following the recommended Odoo installation procedure. Make sure you have made a backup.

### Technical support
Contact us:

- Telephone: +31 (0)20 8500 500
- Email: <integration@multisafepay.com>
- GitHub: Create a technical issue

### Requirements
- MultiSafepay account – See [Getting started](/guides/getting-started/).
- Odoo 13.0
- Tested on Python 3.6

### Installation
1. Download the ZIP archive with module.
2. Unpack the content of the .ZIP file.
3. In your Odoo server (`/mnt/extra-addons/`), under **Custom apps**, add the **payment_multisafepay_official** folder. 
4. Install the required Python dependencies:
    ```
    pip3 install -r requirements.txt
    ```
    Alternatively, you can install them manually:
    ```
    pip3 install multisafepay==0.2.0
    ```
<<<<<<< HEAD
    You can find all the information about the dependencies at this [link](https://pypi.org/project/multisafepay)
4.  Restart Odoo server
5.  Activate developer mode at Odoo platform
6.  Navigate to Apps menu and click _Update Apps List_
7.  Search and open MultiSafepay payments module (payment_multisafepay_official)
8.  Click _Install_.


### 3. Configuration
Configuration is possible within the _Invoicing_ menu or the _Website_ menu.
1.  Navigate to _Invoicing/Website_ menu and go to _Configuration_ > _Payment Acquirers_
2.  Select _MultiSafepay_ payment acquirer. Go to _Edit_ mode. By default acquirer state is disabled
3.  Change state, _Enabled_ or _Test_, and enter _Live_ and/or _Test_ _API key_, set Journal at Configuration tab, and save changes
4.  Click _Pull payment methods_ at Configuration tab to get payment methods from your MultiSafepay account
    
    Be sure that you have the desired payment methods active in your [MultiSafepay Control](https://testmerchant.multisafepay.com)
5.  Configure payment methods you wish to offer. Each payment method will have to be configured separately. 
    
You can configure name, state, supported currency, country, and customer group, which are appropriate for this payment method.

For some payment methods editing country and/or order amount is _disabled_. The reason is this payment method supported 
only in certain countries or it has amount limits.

Also, some payment methods process transactions only in _EUR_. 
For these payment methods, if the order was created not in euros, the amount will be _converted_ to the required currency. 
_Odoo platform currency rate_ is used for conversions and it is configured by a system administrator.

### 4. Congratulations
For any questions about the plugin, email the Integration Team at <integration@multisafepay.com>

### 5. Updates 
1.  Navigate to _Apps_ menu
2.  Search and open _MultiSafepay payments_ module
3.  Click _Upgrade_.
=======
    For more information about dependencies, see Python - [MultiSafepay](https://pypi.org/project/multisafepay).
5. Restart your Odoo server.
6. In your Odoo backend, activate developer mode.
7. Go to the **Apps menu** > **Update apps list**.
8. Search for and open the MultiSafepay payments module `payment_multisafepay_official`.
9. Click **Install**.

### Configuration
1. Log in to your Odoo backend. 
2. Go to the **Invoicing** or **Website** menu > **Configuration** > **Payment acquirers**.
3. Select **MultiSafepay** payment acquirer. 
4. Go to **Edit** mode. 
5. By default, acquirer state is disabled. To change the state, click **Enabled** or **Test**.
6. Enter **Live** and/or **Test** **API key**.
7. On the **Configuration tab**, set **Journal**.
8. Click **Save**.
9. To get payment methods from your MultiSafepay account,Oo the **Configuration** tab, click **Pull payment methods**.  
    Make sure you have activated the relevant payment methods in your [MultiSafepay Control](https://testmerchant.multisafepay.com).
10.  Configure for each payment method separately:  
    - Name  
    - State  
    - Country: Disabled for some payment methods  
    - Customer group  
    - Order amount: Disabled for some payment methods  
    - Supported currency: Some payment methods process transactions only in EUR. Orders not created in EUR are converted to the required currency, using **Odoo platform currency rate**. This can only be configured by a system administrator.

For any questions about the plugin, email the Integration Team at <integration@multisafepay.com>
>>>>>>> master
