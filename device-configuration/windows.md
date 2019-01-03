# Windows

## Intune: How to Enable Windows Hello for Business?

 Standard

https://portal.azure.com  &gt; Intune &gt; Device Enrollment &gt; Windows Enrollment &gt; Windows Hello for Business you can configure the default Windows Hello for Business policy which will be assigned to all users.

 At this moment the assignment cannot be changed. Below a screenshot of the settings you can configure within this policy:

[![image](https://www.vroege.biz/wp-content/uploads/image_thumb-73.png)](https://www.vroege.biz/wp-content/uploads/image-73.png)

 You can check this by going to the following registry key:

[![image](https://www.vroege.biz/wp-content/uploads/image_thumb-74.png)](https://www.vroege.biz/wp-content/uploads/image-74.png)

and

[![image](https://www.vroege.biz/wp-content/uploads/image_thumb-76.png)](https://www.vroege.biz/wp-content/uploads/image-76.png)

Now we see that Windows Hello for Business is disabled lets configure an custom OMA-URI policy to set the Windows Hello for Business settings. The following settings need to be added to the custom OMA-URI policy:

```text
./Device/Vendor/MSFT/PassportForWork/<AzureAD Tenant ID>/Policies/UsePassportForWork = true (Boolean)
./Device/Vendor/MSFT/PassportForWork/<AzureAD Tenant ID>/Policies/RequireSecurityDevice = true (Boolean)
./Device/Vendor/MSFT/PassportForWork/<AzureAD Tenant ID>/Policies/EnablePinRecovery = true (Boolean)
./Device/Vendor/MSFT/PassportForWork/<AzureAD Tenant ID>/Policies/UseCertificateForOnPremAuth = false (Boolean)
./Device/Vendor/MSFT/PassportForWork/<AzureAD Tenant ID>/Policies/PINComplexity/MinimumPINLength = 8 (Integer)
./Device/Vendor/MSFT/PassportForWork/<AzureAD Tenant ID>/Policies/PINComplexity/MaximumPINLength = 16 (Integer)
./Device/Vendor/MSFT/PassportForWork/<AzureAD Tenant ID>/Policies/PINComplexity/SpecialCharacters = 1 (Integer)
./Device/Vendor/MSFT/PassportForWork/<AzureAD Tenant ID>/Policies/PINComplexity/Digits = 1 (Integer)
./Device/Vendor/MSFT/PassportForWork/<AzureAD Tenant ID>/Policies/PINComplexity/History = 5 (Integer)
./Device/Vendor/MSFT/PassportForWork/<AzureAD Tenant ID>/Policies/PINComplexity/Expiration = 90 (Integer)
./Device/Vendor/MSFT/PassportForWork/Biometrics/UseBiometrics = true (Boolean)
./Device/Vendor/MSFT/PassportForWork/Biometrics/FacialFeaturesUseEnhancedAntiSpoofing = true (Boolean)
```

When you add the above entries to a custom Windows 10 policy it will look like this:

[![image](https://www.vroege.biz/wp-content/uploads/image_thumb-75.png)](https://www.vroege.biz/wp-content/uploads/image-75.png)

When you assign this policy to a group of users the Windows Hello for Business policy will arrive on the client and applying the above settings. You can also check this in the registry:

[![image](https://www.vroege.biz/wp-content/uploads/image_thumb-78.png)](https://www.vroege.biz/wp-content/uploads/image-78.png)

When the policy is applied and the users restarts his workstation the policy should be enforced and the user should get the Windows Hello for Business enrollment screens:

[![image](https://www.vroege.biz/wp-content/uploads/image_thumb-79.png)](https://www.vroege.biz/wp-content/uploads/image-79.png)

[![image](https://www.vroege.biz/wp-content/uploads/image_thumb-80.png)](https://www.vroege.biz/wp-content/uploads/image-80.png)

[![image](https://www.vroege.biz/wp-content/uploads/image_thumb-81.png)](https://www.vroege.biz/wp-content/uploads/image-81.png)

> The conclusion of above blogpost is that with using a custom OMA-URI policy we can configure Windows Hello for Business for a group of users.



