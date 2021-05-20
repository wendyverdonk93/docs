---
title : "MultiSafepay Craft Commerce 3 installation and configuration manual"
meta_title: "Craft Commerce 3 plugin manual - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
aliases: 
    - /plugins/craftcommerce/manual
    - /integrations/plugins/craftcommerce/manual
    - /integrations/craftcommerce/manual

---

This technical manual is for installing and configuring the MultiSafepay plugin for Craft Commerce 3.

You can install the plugin via:

+ [Craft Plugin Store](https://plugins.craftcms.com/multisafepay)
+ Composer

To install the plugin using Composer:

### Requirements
- Craft CMS version 3.2 or higher
- PHP 7.0 and higher
- Tested with PHP 7.0 

### Installation
Run the following commands in the CLI:

```
composer require multisafepay/craft-commerce
./craft plugin/install multisafepay
```

The latest stable release is downloaded and installed in your Craft Commerce webshop.

### Configuration
1. Log in to the backend of your Craft Commerce webshop.
2. To configure the plugin settings, go to **MultiSafepay** > **Settings**.  
3. To add payment methods activated in your [MultiSafepay Control](https://merchant.multisafepay.com) and configure gateways, go to **Commerce** > **System settings** > **Gateways**.  
  
For any questions about the plugin, email the Integration Team at <integration@multisafepay.com>
