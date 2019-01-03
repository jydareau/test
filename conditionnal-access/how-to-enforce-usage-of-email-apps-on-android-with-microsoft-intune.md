# How to enforce usage of email apps on Android with Microsoft Intune

How to enforce usage of email apps to access Office 365 email.

* [**Scenario 1:** Allow use any email clients, redirect install Microsoft Intune Company Portal app, and enforce enroll device to Intune.](http://www.scconfigmgr.com/2018/03/17/how-to-enforce-usage-of-email-apps-on-android-with-intune/#Allow-NativeClient-and-Outlook)
* [**Scenario 2:** Allow setup any email client but block sync emails, enforce/redirect use Outlook app. When setup email in Outlook, redirect install Microsoft Intune Company Portal app, and enforce enroll device to Intune](http://www.scconfigmgr.com/2018/03/17/how-to-enforce-usage-of-email-apps-on-android-with-intune/#Block-NativeClient-Allow-Outlook).
* [**Scenario 3:** Allow usage of Android native email client only, redirect install Microsoft Intune Company Portal app, and enforce enroll device to Intune, block anything else.](http://www.scconfigmgr.com/2018/03/17/how-to-enforce-usage-of-email-apps-on-android-with-intune/#Allow-NativeClient-Block-Outlook)

**Requirement:**

* Office 365 licenses
* EMS or Intune licenses
* Android device.
* **Device compliance policy configured.**

**Scenario 1: Allow use any email clients, enforce enroll device to Intune.**

In this scenario, users can setup any email clients to access Office 365 email. User will receive an email redirecting them to download Microsoft Intune Company Portal, then guide them to enroll the device to Intune.

![](https://i1.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/03/img_5aab827be5480.png?w=1075)

This conditional policy will require the device to be marked as compliant. When the device is not enrolled to Intune \(device is not compliant\), Intune Conditional Access leverages Exchange ActiveSync to quarantine these legacy clients and sends an email into their inbox indicating that the they need to install **Microsoft Intune Company Portal** app and enroll their device in order to access Exchange mail and other resources.

1. Go to Azure Portal : [https://portal.azure.com/](https://portal.azure.com/)
2. Go to Intune and create new Conditional Access Policy  [![](https://i2.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/03/img_5aabb0392bb98.png?w=751)](https://i2.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/03/img_5aabb0392bb98.png)
3. Fill information as bellow:  
    Name: CA – Allow Email Basic and Modern Auth. requried enrolled \(Android\)  
    Assignments – Users and groups: choose user groups that you wish to assign this policy  
    Assignments – Cloud apps: Select apps – Office 365 Exchange Online  
    Assignments – Conditions: Client apps \(preview\) – Modern authentication clients, Exchange ActiveSync clients, other clients  
    Access controls – Grant: Grant access – Required device to be marked as compliant

   ![](https://i1.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/08/img_5b62fe117fe1b.png?w=633)

   ![](https://i2.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/08/img_5b62fe25e3ea8.png?w=627)

   ![](https://i2.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/08/img_5b62fe51bf860.png?w=938)

   ![](https://i1.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/08/img_5b62fe7f29547.png?w=626)

4. Enable policy

**Scenario 2: Allow setup email but block sync emails, enforce/redirect use Outlook, enforce enroll device to Intune.**

In this scenario, users can allow setup Android native email client for Office 365 email. The user will receive an email and will be redirected to download Outlook. When the user setup Outlook, it will enforce the download of the Microsoft Intune Company portal app and guide the user to enroll the device to Intune. The user will not be able to use Android native email client to sync Office 365 emails.

![](https://i1.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/03/img_5aab901deeeac.png?w=1076)

This conditional access policy will require the device to use an approved client app and be marked as compliant, in this case the approved email app is Outlook. If user is using other email client than outlook to access Office 365 Exchange Online, it will enforce usage of  Outlook app and will not allow to sync email. Intune Conditional Access leverages Exchange ActiveSync to quarantine these unapproved clients and sends an email into their inbox indicating that the they need to install **Outlook** app and enroll their device to access Exchange mail and other resources.

Configuration are quite similar as “Scenario 1: allow both Android native email client or Outlook”, only changes are:

Name: CA – Required Modern Auth. email client and enrolled \(Android\)  
 Access controls – Grant: Grant access – Require device to be marked as compliant  
 Access controls – Grant: Grant access – Require approved client app  
 For multiple controls: Require all the selected controls

![](https://i2.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/08/img_5b63001a69409.png?w=624)

**Scenario 3: Allow usage of only Android native email client, block anything else.**

In this scenario, users can setup Android native email client to access Office 365 email. User will receive an email redirecting them to download Microsoft Intune Company Portal, then guide them to enroll the device to Intune. User cannot access Office 365 email from any other method than native email client with basic authentication.

![](https://i2.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/03/img_5aad741247456.png?w=1078)

We will need to create two Conditional Access policies, one for allow Exchange ActiveSync basic authentication, another one for block modern authentication client and other clients.

**Conditional Access Policy for allow Exchange ActiveSync basic authentication**

Configuration are quite similar as “Scenario 1: allow both Android native email client or Outlook”, only changes are:

Name: CA – Allow Email Basic Auth. requried enrolled \(Android\)  
 Assignments – Conditions: Client apps \(preview\) – Exchange ActiveSync clients  
 Access controls – Grant: Grant access – Require device to be marked as compliant

![](https://i0.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/08/img_5b6307727996d.png?w=934)

**Conditional Access Policy for block modern authentication clients and other clients**

Configuration are quite similar as “Scenario 1: allow both Android native email client or Outlook”, only changes are:

Name: CA – Block modern Auth. and other emai clients \(Android\)  
 Assignments – Conditions: Client apps \(preview\) – Modern authentication clients, Other clients  
 Access controls – Grant: Block access

![](https://i2.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/08/img_5b63096d5340b.png?w=937)

![](https://i2.wp.com/www.scconfigmgr.com/wp-content/uploads/2018/08/img_5b6309a85f17f.png?w=628)

