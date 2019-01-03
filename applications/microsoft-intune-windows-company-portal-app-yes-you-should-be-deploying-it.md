# Microsoft Intune: Windows Company Portal App – Yes! you should be deploying it!

Over the last month or so I’ve fielded some questions about the [Company Portal](https://www.microsoft.com/en-us/p/company-portal/9wzdncrfj3pz?activetab=pivot:overviewtab) app on Windows. The main one – “Do we need it?”. The reason for the confusion is mainly due to the fact that downloading the company portal on iOS and Android is almost always a critical step for users to get their devices enrolled into Intune for management, but on Windows it’s optional for enrolment because of the native integration of Intune with the Windows 10 MDM platform \(See [my other post](https://micro-scott.azurewebsites.net/2018/08/31/managing-windows-10-with-intune-the-many-ways-to-enrol/) on the many ways to enroll a Windows device in Intune\).

This post is for IT admins and architects to highlight the key reasons to include the company portal app in your modern managed Windows 10 deployment.

**TLDR;**

If you’re not deploying the Company Portal app to your M365 powered devices, you are missing out on this stuff:

[![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/CPFeatures2.png)](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/CPFeatures2.png)

You should deploy it as a Required app and make sure your users know about the benefits!

Here’s what you will get with the Windows Company Portal:

**Self Service Apps**  


This is the most **obvious** reason but important to point out here for completeness. If you want to give your users a curated list of applications \(All the app types: Win32, Web Apps, Windows Apps from the Store or [Store for Business](https://businessstore.microsoft.com/en-us/store) or your own Line-Of-Business Apps uploaded to Intune\) that they can choose to install on demand you will definitely need to deploy the company portal to them and send them shopping there! As an IT pro, you just need to deploy the apps as “Available for Enrolled devices”.

![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn2.png)

**Device Compliance Remediation**

Are you using Conditional Access? If the term is new to you, I suggest checking out [this doc](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview). Or I’ll give you my 4 second spin:

Conditional Access is like a bouncer at a night club. He stands at the front door and checks your ID, makes sure your old enough to get in, makes sure your dressed according to the dress code, and makes sure you’re not too drunk. If you don’t meet those conditions \(Say you wore sandals to a nightclub\) he would say to you “Sorry mate, you can’t come in here with those shoes!, you need to go home and change them”.

In the same way, An IT admin can create a Conditional Access policy \(bouncer\) for a resource such as Exchange Online \(The club\). You can define the conditions under which Azure AD will look at access \(the front door\) and define the checks/compliance policies that will be verified \(no sandals allowed!\).

So as an IT admin managing Intune you can deploy compliance policies to your Windows 10 devices and make sure they are 100% compliant against them before being allowed to access corporate stuff!

The part that the Company Portal App plays in Conditional Access scenarios is helping end users get compliant \(or swap their sandals for shoes\). The Company Portal gives users a view of their overall compliance state, alert them based on no-compliance and even drives them to the right area of Windows to remediate the issue – Thus restoring access to corporate resources.

![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn3.png)**Remotely Reset your mobile devices**

Ever left your work phone or tablet in a taxi? Did you lock it? Were you looking at some sensitive work stuff? The Company Portal in Windows lets users trigger remote actions on other enrolled devices. Users can choose to lock their device or if it’s completely lost they can trigger a self-service remote factory reset.

![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn4.png)

**Help and Support**  


The Company Portal allows IT admins to publish help and support details to end users such that if they have any issues, they know what to do. IT admins can publish a link to self-help docs or supply phone and email contact info for users. If users are having issues with the Company Portal itself \(such as installing an available app\), they can use the Company Portal to send logs for investigation. The Company Portal also notifies end-users about requests for inbound remote assistance sessions via the Intune/Teamviewer integration.

![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn5.png)**Guided Enrollment**The Company Portal can be used to assist users in the enrollment process for their Windows devices. The user interface will detect if the device is enrolled or not, then guide them through the enrollment process..

![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn6.png)**Device Categories**I’m calling this out because I feel like it’s a not widely known and frankly a little underrated. This feature passes on device categorization work from IT admins to end-users. When an IT admin deploys this feature, end users \(upon first launch of the Company Portal\) will be prompted to choose a category where this device belongs. The device category can then be used to target specific applications or policy to the device.

![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn7.png)

**Password Reset**

The Company Portal provides your users with a quick way to see their Azure AD profile and change their password!

[![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn8.png)](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn8.png)

**App Inventory**

Users can keep track of the applications that they installed \(or started installing\) via the Company Portal

![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn9.png)

**Sync!**

Lastly, as an IT admin you can direct users to the Sync \(or “Check Access”\) in Intune to resolve any issues they may be experiencing. Yes – “Sync” is also available in Windows settings but the company portal has a couple of extra benefits like allowing users to trigger it on other enrolled devices too!

![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn10.png)

**In summary:** Yes – you will very likely want to add the Company Portal to your Intune deployment.

If you have some other ideas about how the Company Portal app can help your organization, we would love to hear it! – Just use the App feedback feature to send your ideas!

![](https://micro-scott.azurewebsites.net/wp-content/uploads/2018/11/110918_0029_MicrosoftIn11.png)

