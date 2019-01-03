# Types of Android Enrollment Intune

Android Enrollment options within Intune. Currently there are 3 types of Android Enrollment supported within Intune.

* Conventional Android
* Work Profiles \(Commonly referred to as Android for Work\)
* COSU \(Corporate Owned Single Use\)

![](../.gitbook/assets/image%20%287%29.png)

Work Profiles and COSU sit within the **Android Enterprise** category.

So What is the difference? Work Profiles separates corporate and personal data on an android phone. Intune only controls the “Work Profile” which contains the corporate apps and data and the user manages the personal apps and data on the device. This is different from conventional Android enrollment where Intune would manage the whole device and therefore an administrator would be able to factory reset the device and wipe both personal and corporate data. COSU is designed for single purpose devices i.e. digital signage, ticket printing, POS etc.  


If a device can enroll as Android Enterprise it can also be enrolled as a conventional android device. However not all devices which can be enrolled as conventional android devices can be enrolled as Android Enterprise.

A device will automatically attempt to enroll into Android Enterprise \(Work Profile\) if it is capable. This requires you to have connected the Intune Tenant to the Android Enterprise account \([https://docs.microsoft.com/en-us/intune/connect-intune-android-enterprise](https://docs.microsoft.com/en-us/intune/connect-intune-android-enterprise)\). If you wish to block devices from automatically enrolling as Work Profile devices you must block this in enrollment restrictions. \([https://docs.microsoft.com/en-us/intune/enrollment-restrictions-set](https://docs.microsoft.com/en-us/intune/enrollment-restrictions-set)\). If a device is not capable of enrolling into Work Profile it will automatically enroll as a conventional android device.

If you want to switch from Android Enterprise to Conventional the only way to do this is to unenroll the device, block work profile enrolment in restrictions and then re-enroll the device.

{% embed url="https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/How-does-Microsoft-Intune-transform-Android-enterprise/ba-p/299289?MC=Windows&MC=SysMagSof&MC=OfficeO365&MC=MSAzure&MC=EntMobile" %}

