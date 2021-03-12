---
title : "Filter the order request using the hook multisafepay_order_request"
meta_title: "WooCommerce plugin available payment methods - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
layout: "faqdetail"
read_more: "."
aliases: [/integrations/woocommerce/faq/how-can-i-customize-the-language-of-payment-page-and-emails/]
---

There may be cases in which a developer need to modify something in the transaction before it is processed.

If you want to change something in the OrderRequest it is possible using the filter hook “multisafepay_order_request” built in our plugin.

Ask your developer to read:

+ [Filters in Wordpress](https://developer.wordpress.org/plugins/hooks/filters/)
+ [MultiSafepay PHP-SDK](https://github.com/MultiSafepay/php-sdk/)
+ [MultiSafepay Order Request Filter](https://github.com/MultiSafepay/WooCommerce/blob/master/src/Services/OrderService.php#L108)

&nbsp;

A simple example of how to implement this and overwrite the Shopping Cart could be something like this: 

``` 
add_filter('multisafepay_order_request', 'return_my_multisafepay_order_request');
function return_my_own_locale( \MultiSafepay\Api\Transactions\OrderRequest $order_request) {
    // Your conditions and logic to return a valid order request
    // Register a CartItem
    $shopping_cart_items = array();
    $cart_item = new \MultiSafepay\ValueObject\CartItem();
    $cart_item->addName( 'The product name' )
              ->addQuantity( (int) 1 )
              ->addMerchantItemId( (string) 'SKU' )
              ->addUnitPrice( \MultiSafepay\WooCommerce\Utils\MoneyUtil::create_money( (float) 10.00, (string) 'EUR' ) )
              ->addTaxRate( '21' );
    $shopping_cart_items[] = $cart_item;
    // Register the CartItem in the ShoppingCart     
    $shopping_cart = new MultiSafepay\Api\Transactions\OrderRequest\Arguments\ShoppingCart($shopping_cart_items);
    // Overwrite the ShoppingCart    
    $order_request->addShoppingCart( $shopping_cart );
    // Overwrite the total amount of the transaction
    $order_request->addMoney(\MultiSafepay\WooCommerce\Utils\MoneyUtil::create_money( 12.10, 'EUR' ));
    return $order_request;
}
```