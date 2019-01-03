# Hybrid Enrolling Corporate Windows 10 Devices into Intune

How to enroll your corporate Windows 10 Active Directory joined devices into Intune MDM for Management. I am going to assume in this scenario you are not using SCCM for device management and if you are your approach will most likely be a different one to this post and you would be looking at implementing co-management \([https://docs.microsoft.com/en-us/sccm/core/clients/manage/co-management-overview](https://docs.microsoft.com/en-us/sccm/core/clients/manage/co-management-overview)\).

**Pre-Requisites:**  
Hybrid AD Joined Device  
Windows 10 1709 or Later  
Users have Intune/EMS Licence Assigned

**Setting up Hybrid AD Join**

In a nut shell Hybrid AD Join is a process which allows your on-premises active directory joined machines to automatically register in Azure AD. This is done by creating a Service Connection Point at the root of your Active Directory Forest. Any Windows 10 1607 or later client will automatically attempt to register with azure ad once the SCP has been setup correctly.

There are essentially a couple of ways you can setup the SCP. The preferred method is using the AD Connect Wizard, if you are not on one of the latest releases of AD Connect i would advise upgrading.

**Note: In my environment I am using Password Hash Sync \(Managed Domain\)**

* Log onto your AD Connect Server and Launch AD Connect
* Ensure you are syncing your device objects in the synchronization options

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-7.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-7.png)

* On the AD Connect Main Menu, Choose Configure Device Options

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-8.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-8.png)

* Sign in with your Global Administrator Credentials

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-9.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-9.png)

* Select Configure Hybrid AD Join

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-10.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-10.png)

* Select the Forest you want to set up the SCP in and Choose the Azure AD Service which will be used for authentication i.e your .onmicrosoft domain or your federated domain. then enter your Enterprise admin credentials.

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-11.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-11.png)

* Select whether you have both Windows 10 and down level devices in your environment. In this tutorial we are only focusing on Windows 10. _If you do require Hybrid Join for down level devices you must have seamless SSO enabled if using Password hash sync or pass through authentication as a sign in method._

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-12.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-12.png)

* You have now configured Hybrid AD Join.

To confirm the existance of the SCP you can run the following powershell command \(You need to change DC=Fabrikam,DC=com to match your own environment\):  
_**$scp = New-Object System.DirectoryServices.DirectoryEntry; $scp.Path = “LDAP://CN=62a0ff2e-97b9-4513-943f-0d221bd30080,CN=Device Registration Configuration,CN=Services,CN=Configuration,DC=fabrikam,DC=com”; $scp.Keywords;**_

If your Azure AD Tenant information is shown in the output then the SCP is configured.

**Confirming your devices are Hybrid AD Joined**

If you go to Azure Active Directory &gt; Devices you should see your devices start appearing in the console as Hybrid AD Joined. However one thing to note is if the registered field does not have a date and time yet then the join has not fully completed. It just means the object has been synced.

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-13.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-13.png)

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-14.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-14.png)

On the client you can also run a dsregcmd /status from the command prompt and look for Azure AD Joined = Yes

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-15.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-15.png)

**Enable Intune MDM Enrollment**

Now that the domain joined Windows 10 devices are Hybrid AD Joined we can now use a group policy to automatically enroll them into Intune. In Production you would use GPO but to demonstrate i am going to create a local group policy on a machine \(gpedit.msc\)

* Navigate to Computer Policy &gt; Administrative Templates &gt; Windows Components &gt; MDM
* Enable the MDM Autoenrollment Policy

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-16.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-16.png)

* Enabling this policy creates a Scheduled task which runs every 5 minutes for the duration of one day

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-17.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-17.png)

* In order for the device to successfully enroll into Intune you must login with a user who has a valid EMS/Intune License.

**Confirming Intune Enrollment**

* Once enrollment has completed successfully you will see the device appear in the Intune Portal under the Devices blade.
* On the client you can also go to Settings &gt; Account &gt; Access work or School and you should see an info button when you click your AD Domain.

[![image](https://triplesixseven.com/wp-content/uploads/2018/12/image_thumb-18.png)](https://triplesixseven.com/wp-content/uploads/2018/12/image-18.png)

* If you click on the Info button you can also manually force a sync with Intune



