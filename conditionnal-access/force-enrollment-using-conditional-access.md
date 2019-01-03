# Force Enrollment using Conditional Access

Companies often want a solution which forces users to enrol a device which is used for corporate work. In order to Force enrolment into Intune you can use conditional access. This stops a user from accessing any corporate resources until they have enrolled their device. Using conditional access you can set the conditions in which the user needs to be enrolled. As well an enrolment the user is also forced to ensure the device meets any compliance policies which have been set before being able to access the corporate resources.

### Steps to Setting up the Policy

* Login to the [Azure Portal](https://portal.azure.com/)
* Navigate to Azure Active Directory
* Click on the Conditional Access Blade
* Under the policies tab choose new policy and type an appropriate name
* On the users and groups tab assign the policy to an azure group. I would recommend starting with a small pilot whilst testing the policy
* On the cloud apps tab choose the apps in which you want to trigger the enrolment. You can choose all cloud apps.
* Under the conditions tab you can add further customisation. I.e. device type or location etc.
* On the grant tab choose “Require Device to be Marked as compliant”

![](https://triplesixseven.com/wp-content/uploads/2018/08/Capture2.jpg)Require Device to be marked as compliant  


Now enable the policy and the end result is when a targeted user tries to use the specified cloud apps to access corporate resources they are required to have a compliant device. This essentially means the device has to be enrolled into Intune and must also be compliant with any assigned compliant policies. Only then will the user be able to access corporate resources.

