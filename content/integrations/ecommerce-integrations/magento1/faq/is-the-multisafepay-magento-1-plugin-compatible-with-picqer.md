---
title : "Is the MultiSafepay Magento 1 plugin compatible with Picqer?"
meta_title: "Magento 1 plugin Picqer compatibility - MultiSafepay Docs"
meta_description: "Sign up. Build and test your payments integration. Explore our products and services. Use our API Reference, SDKs, and wrappers. Get support."
read_more: "."
aliases: 
    - /integrations/magento1/faq/how-can-i-update-the-plugin-for-magento1/
    - /integrations/magento1/faq/is-the-multisafepay-magento-1-plugin-compatible-with-picqer/
---

Yes, but you will have to follow two additional steps, because orders should not go to the Cancel state.

1. Go the the MultiSafepay Connect settings in you Magento 1 backend and link the status expired to Waiting
2. Open "app\code\community\MultiSafepay\Msp\Model\Base.php", copy the file to the local folder in the Magento structure
3. Find the line $order > cancel(); at the expired signal and remove it.

Now all the expired orders will keep the waiting status until you cancel them. You can do this by hand, schedule it with a custom cronjob or by using a plugin.
