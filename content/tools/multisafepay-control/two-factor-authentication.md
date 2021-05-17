---
title : "Enabling two-factor authentication"
weight: 100
meta_title: "MultiSafepay Control - Enabling two-factor authentication - MultiSafepay Docs"
meta_description: "The MultiSafepay Documentation Center presents all relevant information about our Plugins and API. You can also find support pages for payment methods, tools and general questions as well as the contact details of our Support and Integration Teams."
read_more: '.'
description_short: "Two-factor authentication (2FA) requires users to verify their identity with two pieces of evidence. This authentication method is used to add an additional layer of security to your data. At MultiSafepay, the first piece of evidence users are asked to provide is a password. The second piece of evidence is a 6-digit token, generated in the MultiSafepay app on the user's mobile device."
aliases:
    - /tools/multisafepay-contro/two-factor-authentication
---

Two-factor authentication (2FA) is an additional layer of security for data in your MultiSafepay Control. When enabled, users must verify their identity with:

- A password
- A 6-digit token generated in the user's MultiSafepay mobile app for every log in

## Enabling 2FA

To enable 2FA in your MultiSafepay Control, follow these steps:

| Who  | Step  | Action  |  
|---|---|---|
| Administrator  | 1.  | Log in to your MultiSafepay Control and go to [User management](https://merchant.multisafepay.com/user-management).  |   
|   | 2.  | Click the name of the user you want to enable 2FA for.  |  
|   | 3.  | From the **Two-factor** dropdown menu, select **Enable**.  |  
|   |  4. | Click **Save changes**.  |  

{{< screen src="/gifs/MCP_2FA-1.gif" alt="Enabling Two-factor authentication in MultiSafepay Control" align="center" screen_size="desktop" >}}

| Who  | Step  | Action  |  
|---|---|---|
| User  | 1.  | The first time you log in to MultiSafepay Control after 2FA is enabled, you must configure 2FA. Log in to [MultiSafepay Control](https://merchant.multisafepay.com) on your laptop or PC. A dialog requesting a 6-digit token appears.   |  
|   | 2.  | Open or [download](https://docs.multisafepay.com/tools/multisafepay-control-app/how-to-download-the-app) the MultiSafepay Control app and log in.  |  
|   | 3.  | Tap **More** in the bottom-right corner.  |  
|   | 4.  | Tap **Authenticator**.  |  
|   | 5.  | Copy the 6-digit token from your mobile device to the 2FA dialog on your computer or laptop.  |  

{{< screen src="/gifs/MCP_2FA-3.gif" alt="Generating a 6-digit 2FA token the in MultiSafepay Control app" align="center" caption="The 6-digit token remains visible for 30 seconds" screen_size="mobile" >}}

## Frequently asked questions

### Can I use one device for multiple users?
Only one mobile device can only be connected to one user and only one user can be connected to one mobile device. This means there is a unique link between every one user and one device.

### Why can I not enable 2FA on my account?
To enable or disable 2FA, you must have administrator rights. If this doesn't answer your question, please [contact support](mailto:support@multisafepay.com)

### What happens after too many failed login attempts?
After 5 unsuccessful 6-digit token inputs, the account is blocked. Only users with administrator rights can unblock accounts. 

### Does every user need to use 2FA?
No, this is not required. 2FA provides an extra layer of security to your data. However, it is not mandatory to enable 2FA on every user account.

### Can I choose a different verification method?
Unfortunately, no. We implement 2FA through the use of a password and a 6-digit token. 

### In what countries is 2FA supported?
2FA is supported in every country. The MultiSafepay app is available for [iOS](https://apps.apple.com/nl/app/multisafepay-control/id929955963) and [Android](https://play.google.com/store/apps/details?id=com.multisafepay.control).

### What if a user loses their 2FA device?
If a user loses their 2FA device, disable and re-enable 2FA on their account. Follow [these steps](#how-to-enable-2fa) to do so (this requires administrator's rights). Once 2FA is disabled, the existing connection is broken. The user can now connect a new mobile device to their MultiSafepay Control. If you only have one MultiSafepay user account or in case any other problems arise, please [contact support](mailto:support@multisafepay.com)
