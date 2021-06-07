---
title : "MultiSafepay OpenCart installation and configuration manual"
meta_title: "OpenCart plugin manual - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
aliases:
    - /support-tab/opencart/manual
    - /plugins/opencart/manual
    - /integrations/plugins/opencart/manual
    - /integrations/opencart/manual
---

This technical manual is for installing and configuring the MultiSafepay plugin for OpenCart.

We recommend first installing the plugin in a test environment following the recommended OpenCart installation procedure. Make sure you have made a backup.

### Technical support
Contact us:

- Telephone: +31 (0)20 8500 500
- Email: <integration@multisafepay.com>
- GitHub: Create a technical issue

<<<<<<< HEAD
### 4. Congratulations
For any questions about the plugin, email the Integration Team at <integration@multisafepay.com>
=======
### Requirements
- MultiSafepay account – See [Getting started](/guides/getting-started/).
- OpenCart 2.X, 3.X
- Tested on PHP 7.2, 7.3
>>>>>>> master

### Installation
1. For security, always create backup of your OpenCart application.
2. Download the Plugin_OpenCart_3.x.x.ocmod.zip.
<<<<<<< HEAD
3. Before you update the plugin, we strongly recommend have a backup of your production environment
4. Log in to your backend and navigate to _Extensions_ > _Installer_.
5. Click on the upload button and select in your computer the downloaded file.
6. Wait until the installation process finish. 
7. Click in the menu item _Dashboard_.
8. On the upper right corner of the screen, click on the blue button with a cog wheel icon, and then click on the refresh icon to clean both caches. 
9. Go to _Extensions_ > _Modifications_ and click on refresh button.
10. Go to _Extensions_ > _Payments_ > _MultiSafepay_ and click in the edit button to access the settings page.
11. You will see a warning notification message, indicating is needed to make some maintenance tasks to delete old plugin files. 
12. Go to _Maintenance_ tab and at the end of the list; click on the button to delete old plugin files. 
13. You just update the plugin. Now you need to configure the settings. 


#### Update the plugin from plugin version lower or equals than 2.1.0 to 3.x.x
1. For security, create backup of your OpenCart platform. Especially if you are doing this in a production environment.
2. Manually remove all the files from the MultiSafepay extension using an FTP program or server file administration program.
3. Follow the instruction to install our latest extension using the extension installer tool built in OpenCart.
=======
3. Log in to your OpenCart backend, and go to **Extensions** > **Installer**.
4. Click the **Upload** button, and then select the downloaded file.
5. Once installed, click the **Dashboard** menu.
7. To clear both caches, click the blue cog wheel button in the top-right corner, and then click the **Refresh** icon. 
8. Go to **Extensions** > **Modifications**, and then click the **Refresh** button.
9. Go to **Extensions** > **Payments** > **MultiSafepay**, and then click the **Install** button. 

### Configuration
1. Log in to your backend and go to **Extensions** > **Extensions** > **Payments** > **MultiSafepay**.
2. On the **MultiSafepay configuration** page, fill out each tab.  
    To retrieve your API key, see [Get your API key](/tools/multisafepay-control/get-your-api-key).
3. On the **Payment methods** tab, enable and configure the relevant payment methods.
4. Configure the **Order status** tab, matching each possible MultiSafepay callback status with one of the order statuses in your OpenCart webshop.
5. Configure the **Options** tab. 

For any questions about the plugin, email the Integration Team at <integration@multisafepay.com>

>>>>>>> master
