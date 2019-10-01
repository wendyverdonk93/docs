---
title : "Fastcheckout SDK Android configuration manual"
meta_title: "Fastcheckout SDK Android configuration manual - MultiSafepay Documentation Center"
meta_description: "In the MultiSafepay Documentation Center all relevant information regarding our Plugins and API. As well as Support pages for Payment Method, Tools and General Questions. You can also find the contact details of our Support Team and Integration Team."
---

## Introduction

The Fastcheckout SDK is a library that you can integrate into your native Android, iOS and/or React Native application providing connection to MultiSafepay services. The Fastcheckout SDK adds a smooth, fast and native checkout experience to your mobile app, and by storing and reusing data it is the fastest checkout process available for shopping apps.

As an integrator, you only need to provide a valid MSP transaction identifier or create a transaction. The Fastcheckout SDK leverages the checkout process for you, providing notifications for all possible outcomes (success, pending, cancelled, etc.) once it completes a transaction. The checkout process flow includes:

* Shipping details:
    * Preferred shipping details
    * Add shipping details
* Payment methods:
    * Preferred payment methods
    * Add payment methods
    * Coupons
* Confirmation details

### Additional details

The Fastcheckout SDK provides the additional following features:

* Authentication into Fastcheckout: 
    * It provides secure sign-up/login functionality
* Check orders:
    * Open seamless support tickets to related orders
* Support orders:
    * Easily open a support ticket related to an order
* Edit payment information:
    * List and edit user’s stored payment details
* Manage shipping addresses:
    * List, add and edit shipping information

*If you need more information, please check the documentation that you will find inside the SDK, which contains all classes, methods, common troubleshooting and more details.*

Please refer to the Multisafepay API Documentation to perform different calls through which you can start transactions, update transactions, perform refunds and receive information about transactions: https://docs.multisafepay.com/api/#orders

## Requirements

* Android Studio 3 and up
* Android version 4.4 and up
* Java or Kotlin


## Installation

First you have to access into your Back Office and get a valid API Key (Settings → Website Settings)
Once you have your valid API Key, simply download the Android and/or iOS SDK version.

Add the msp-android-sdk-release.aar as an embedded framework into your project. The next steps will guide you through the process:

1. Add the msp-android-sdk-release.aar into your library’s /lib folder.
2. In your build.gradle (Module.app) inside of the dependencies script add the following

   ```gradle
   implementation(name: 'msp-android-sdk-release', ext: 'aar')

   repositories {
      flatDir {
         dirs 'libs'
      }
   }
   ```

3. Sync Gradle

You can now start using the Android SDK in your App.

## Demo

You can easily integrate Fastcheckout Android SDK into your app, you just need to follow the next steps:

1. Setup the Android SDK. Add the following to your MainActivity or Class:

```java
import com.multisafepay.sdk.FastCheckoutSDK;

//declare the FastCheckoutSDK as a member variable:
private static FastCheckoutSDK SDK = FastCheckoutSDK.getInstance();

//you must implement this interface and then set the listener:
Public class MainActivity extends AppCompatActivity 
implements ISDKCommunicator.sdkStatus {

//in your onCreate method initialize the SDK:
SDK.setApiKey(API_KEY);

//set the listener for the interface:
SDKCommunicationListener sdkCommunicationListener = new SDKCommunicationListener();
sdkCommunicationListener.setSDKListener(this);
…
…
}
```

2. Start checkout and add callback interface to your Activity

```java
//your class should implement the FastCheckoutSDK.Callback interface 
FastCheckoutSDK.Callback

//add registration to your onCreate method:
sdk.registerCallback(this); 

//then, start your checkout:
sdk.startCheckout(transaction_id, this);

//get results in your callback method:
@Override
public void callback(FastCheckoutSDK.Result result) {

   if (result.getResult() == FastCheckoutSDK.Result.FCO_RESULT_UNCLEARED) {
      
   }

   if (result.getResult() == FastCheckoutSDK.Result.FCO_RESULT_OK) {
      
   }

   if (result.getResult() == FastCheckoutSDK.Result.FCO_RESULT_CANCELLED) {

   }
}
```
3. Setup styles in your Application class (these styles might be changed to suit your theme):

```java
Styles.Builder builder = new Styles.Builder();
builder.set("mainColor", "#FF7E03");
builder.set("mainFontSize", 30);

{
Typeface typeface = Typeface.createFromAsset(this.getAssets(), "fonts/nunito/Nunito-Medium.ttf");
   Styles.Font font = new Styles.Font("#000000", typeface, null);
   builder.setObject("labelFont", font);
}

{
 Typeface typeface = Typeface.createFromAsset(this.getAssets(), "fonts/nunito/Nunito-Medium.ttf");
   Styles.Font font = new Styles.Font("#FFFFFF", typeface, null);
   builder.setObject("buttonFont", font);
}

{
 Typeface typeface = Typeface.createFromAsset(this.getAssets(), "fonts/nunito/Nunito-ExtraLight.ttf");
   Styles.Font font = new Styles.Font("#000000", typeface, null);
   builder.setObject("editFont", font);
}

{
   Typeface typeface = Typeface.createFromAsset(this.getAssets(), "fonts/galada_regular.ttf");
   Styles.Font font = new Styles.Font("#000000", typeface, null);
   builder.setObject("titleFont", font);
   builder.set("title", "qwindo");
}
Styles styles = builder.build();
FastCheckoutSDK sdk = FastCheckoutSDK.getInstance();
sdk.setStyles(styles);
```

#### Complete example

```java
import com.multisafepay.sdk.FastCheckoutSDK;

public class MainActivity extends AppCompatActivity implements FastCheckoutSDK.Callback{

private static FastCheckoutSDK SDK;
private Button btnStartNewTransaction;

@Override
protected void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   setContentView(R.layout.main_activity);

   btnStartNewTransaction = findViewById(R.id.btn_transaction);

   SDK = FastCheckoutSDK.getInstance();
   SDK.setApiKey(API_KEY);

   btnLogOut.setOnClickListener(view -> SDK.startCheckout(transaction_id, this));

   }

@Override
public void callback(FastCheckoutSDK.Result result) {

   if (result.getResult() == FastCheckoutSDK.Result.FCO_RESULT_UNCLEARED) {
      
   }

   if (result.getResult() == FastCheckoutSDK.Result.FCO_RESULT_OK) {
      
   }

   if (result.getResult() == FastCheckoutSDK.Result.FCO_RESULT_CANCELLED) {

   }

  }
}
```

```java
import com.multisafepay.sdk.FastCheckoutSDK;

public class YourApplicationClassName extends Application {

@Override
protected void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   setContentView(R.layout.main_activity);

   Styles.Builder builder = new Styles.Builder();
   builder.set("mainColor", "#FF7E03");
   builder.set("mainFontSize", 30);

{
Typeface typeface = Typeface.createFromAsset(this.getAssets(), "fonts/nunito/Nunito-Medium.ttf");
   Styles.Font font = new Styles.Font("#000000", typeface, null);
   builder.setObject("labelFont", font);
}

{
 Typeface typeface = Typeface.createFromAsset(this.getAssets(), "fonts/nunito/Nunito-Medium.ttf");
   Styles.Font font = new Styles.Font("#FFFFFF", typeface, null);
   builder.setObject("buttonFont", font);
}

{
 Typeface typeface = Typeface.createFromAsset(this.getAssets(), "fonts/nunito/Nunito-ExtraLight.ttf");
   Styles.Font font = new Styles.Font("#000000", typeface, null);
   builder.setObject("editFont", font);
}

{
   Typeface typeface = Typeface.createFromAsset(this.getAssets(), "fonts/galada_regular.ttf");
   Styles.Font font = new Styles.Font("#000000", typeface, null);
   builder.setObject("titleFont", font);
   builder.set("title", "qwindo");
}
Styles styles = builder.build();
FastCheckoutSDK sdk = FastCheckoutSDK.getInstance();
sdk.setStyles(styles);

   }
}

```
## SDK Snapshots:

1. The following snapshots will walk you through some of features offered by the Fastcheckout Android SDK. The Fastcheckout iOS SDK provides the same functionalities.
    * Logging in with a registered email: 
        
      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-1.png" title="screenshot 1">}}
      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-2.png" title="screenshot 2">}}

    * Logging in with a non-registered email will automatically take the user to the register SDK screen: 

      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-3.png" title="screenshot 3">}}
      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-4.png" title="screenshot 4">}}
      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-5.png" title="screenshot 5">}}

    * If the user is registered and resets its email account, the SDK  will automatically send a new security code to new entered email: 

      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-6.png" title="screenshot 6">}}
      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-7.png" title="screenshot 7">}}

    * Once the user enters the security code received by email (if the security code is received via SMS it will automatically get added to appropriate field, and the SDK will move into the following state) the SDK will ask for a new security PIN, once entered, the SDK will provide Biometric options (in iOS face recognition is also available):

      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-8.png" title="screenshot 8">}}
      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-9.png" title="screenshot 9">}}

    * The checkout process follows. From a merchant’s shop checkout option, the SDK enters into the checkout process. The first view will be the delivery view with shipping options if available. Once the continue button is selected, the SDK moves into the Payment screen and the payment logic follows.

      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-10.png" title="screenshot 10">}}
      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-11.png" title="screenshot 11">}}
      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-12.png" title="screenshot 12">}}
      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-13.png" title="screenshot 13">}}
    
    * Once the payment process is completed the SDK will proceed to the “transaction is complete” screen. The SDK callback will notify the client App about this or any other results (uncleared, cancel, etc.). Pressing the button “Back to Shop” will redirect the user to the Merchant’s shop.

      {{< zoomable class="img-size" url="/integrations/fastcheckout-android/fastcheckout-android-14.png" title="screenshot 14">}}


    




