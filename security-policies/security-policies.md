# Security Policies



#### Security Policies <a id="security-policies"></a>

A [security policy](https://azure.microsoft.com/en-us/documentation/articles/security-center-policies/) defines the set of controls, which are recommended for resources within the specified subscription or resource group. In Security Center, you define policies for your Azure subscriptions or resource group according to your company security needs and the type of applications or sensitivity of the data in each subscription.

For example, resources that are used for development or test might have different security requirements from resources that are used for production applications. Likewise, applications that use regulated data like personally identifiable information might require a higher level of security. Security policies that are enabled in Azure Security Center drive security recommendations and monitoring to help you identify potential vulnerabilities and mitigate threats.

By default, when you enable Security Center and data collection, all of the security policies will be enabled by default. The policies inherit from the subscription down to the resource groups. However, you can individually control the security policies at the resource group level, if desired. In the following screen capture, notice that some of the resource groups have inheritance turned on and some are set to be unique \(which means that the security policy settings might differ from the subscription\).

![Screenshot of the resource groups. The Inheritance setting \(unique or inherited\) is shown. ](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/ea6434d3c23642579f2eff4b99b2cc6b/asset-v1:Microsoft+AZURE208x+3T2018+type@asset+block/M3L2T1_VeH1hQS.png)

| ![Checkmark](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/f0fcce0131853bcf4dc919a3dd61834d/asset-v1:Microsoft+AZURE208x+3T2018+type@asset+block/CheckMarkWhite.png) | To modify a security policy at the subscription level or resource group level, you must be an Owner or Contributor of that subscription. |
| :--- | :--- |


