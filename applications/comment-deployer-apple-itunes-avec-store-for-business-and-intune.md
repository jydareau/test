# Comment deployer Apple iTunes avec Store for Business and Intune

In the past is has not been possible to deploy Apple iTunes from Microsoft Store for Business do to availability. iTunes has only been available in the public part of Microsoft Store and not the private store, that has now changed so this blog post is about how to deploy Apple iTunes from Microsoft Store for Business with Intune as the delivery engine.

The reason why it is a great idea to deploy iTunes from Microsoft Store for Business in a company is, you do not as an admin need to repackages the application every time that Apple releases a new version, that is not up to the application vendor to keep the application up to date.

**How to get Apple Itunes:**

Start by going to your Microsoft Store for Business portal [https://aka.ms/msfb](https://aka.ms/msfb)

Search for iTunes and select the application

![Deploy Itunes With Intune - 01](https://osddeployment.files.wordpress.com/2018/12/deploy-itunes-with-intune-01.png?w=1024)

Click get the app

![Deploy Itunes With Intune - 02](https://osddeployment.files.wordpress.com/2018/12/deploy-itunes-with-intune-02.png?w=1024)

Click close – iTunes is now in your company private store

![Deploy Itunes With Intune - 03](https://osddeployment.files.wordpress.com/2018/12/deploy-itunes-with-intune-03.png)

Start Microsoft 365 Device Management portal [https://devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/)

1. Select Client apps
2. Select Microsoft Store for Business
3. Click sync

![Deploy Itunes With Intune - 04](https://osddeployment.files.wordpress.com/2018/12/deploy-itunes-with-intune-04.png?w=1024)

After the sync is done you can find iTunes under Client Apps – Apps

![Deploy Itunes With Intune - 04a](https://osddeployment.files.wordpress.com/2018/12/deploy-itunes-with-intune-04a1.png?w=1024)

Now you just need to assign iTunes to the end user that are allowed to see it in Intune Company Portal or needs to have the application pushed out.

![Deploy Itunes With Intune - 04b](https://osddeployment.files.wordpress.com/2018/12/deploy-itunes-with-intune-04b1.png?w=1024)

**How is the end user experience:**

The end user just need to start Company Portal in there Intune enrolled Windows 10 devices – and the iTunes is ready for the user to install.![Deploy Itunes With Intune - 05](https://osddeployment.files.wordpress.com/2018/12/deploy-itunes-with-intune-05.png?w=1024)

After the installation Microsoft Store will keep the iTunes updated on the devices at all time.

[https://businessstore.microsoft.com/fr-fr/store](https://businessstore.microsoft.com/fr-fr/store)

