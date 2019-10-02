# Managing Windows 10 with Intune – The Many Ways to Enrol

**There are many ways to enrol Windows 10 devices into Microsoft Intune for device management.** Some are User-driven and some controlled by IT administrators, Some exist to support BYOD programs and others to streamline modern provisioning scenarios and management for corporate-owned devices.

Each enrolment method can have different setup requirements and behaviours. I was going to title this blog **"The 9 ways to enrol in Intune"** – it had a nice ring to it but I knew the title would end up being wrong in no time.

The meat of this post is the enrolment matrix below. It's meant to be a be a good reference for IT admins and architects embarking on Windows 10 Management projects to view all the available scenarios and help find the right documentation needed to get started with Windows 10 enrolment into Intune. Hope it helps!

_Update 3 Sept 18 - The statement above proved to be right - Thanks to MSFT support gurus Radu and Mihai for pointing out to me a 10th scenario -- I've added Enrol in MDM Only \(Device Enrollment Manager\)_

_Update 14 Nov 18 - Added Hybrid Azure AD \(AutoPilot\)_

[![](https://msdnshared.blob.core.windows.net/media/2018/08/EnrolmentScenario5.png)](https://msdnshared.blob.core.windows.net/media/2018/08/EnrolmentScenario5.png)

**Here is a quick description of each of the scenarios mentioned in the grid:**

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p><b>Scenario 1: Add work or school Account (User Driven)</b>
        </p>
        <p>
          <img src="https://msdnshared.blob.core.windows.net/media/2018/08/083118_0616_ManagingWin1.png"
          alt/>
        </p>
        <p>This enrolment method is typically used in BYOD scenarios. Once configured,
          users can be provided instructions on how to access <b>&quot;set up a work or school account&quot; </b>from
          the settings.</p>
        <p><a href="https://docs.microsoft.com/en-us/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device">https://docs.microsoft.com/en-us/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device</a>
        </p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>Scenario 2: Modern App Sign-in (User Driven)</b>
        </p>
        <p>
          <img src="https://msdnshared.blob.core.windows.net/media/2018/08/UWP2.gif"
          alt/>
        </p>
        <p>This enrolment method is typically used for BYOD scenarios. Once configured,
          a logon to a Modern Windows 10 App (e.g. OneNote or Store), or Office ProPlus
          using a work account will trigger enrolment.</p>
        <p><a href="https://docs.microsoft.com/en-us/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device">https://docs.microsoft.com/en-us/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Scenario 3: Enrol in MDM Only (User Driven)</b>
        </p>
        <p>This method of enrolment is for enrolling directly into Intune. This form
          of enrolment is often used for BYOD, particularly in environments that
          do not have Azure AD Premium licenses required to perform the automated
          enrolment provided with other methods.</p>
        <p><a href="https://docs.microsoft.com/en-us/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-to-mdm-on-a-desktop-enrolling-in-device-management">https://docs.microsoft.com/en-us/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-to-mdm-on-a-desktop-enrolling-in-device-management</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Scenario 4: Azure AD Join (OOBE)</b>
        </p>
        <p>This method of setup and enrolment is a user driven enrolment via the
          Out of Box Experience. By choosing &quot;Setup for an organisation&quot;
          and using work account to sign in, the device becomes Azure AD Joined and
          automatically enrolled into Intune.</p>
        <p>
          <img src="https://msdnshared.blob.core.windows.net/media/2018/08/AADJ1.gif"
          alt/>
        </p>
        <p><a href="https://docs.microsoft.com/en-us/intune/windows-enroll">https://docs.microsoft.com/en-us/intune/windows-enroll</a>
        </p>
        <p><b>Scenario 4.1: Azure AD Join (After OOBE)</b>
        </p>
        <p>This method of enrolment is a variation of the above. It is initiated
          from the settings menu after a windows profile has already been setup.
          For cases where a user has already setup a Windows user profile, they can
          go to &quot;Add a work or School Account&quot; , then select &quot;Join
          this device to Azure Active Directory&quot;. Once rebooted, the user can
          logon with their Azure AD credentials and the device will become enrolled
          into Intune.</p>
        <p><a href="https://msdnshared.blob.core.windows.net/media/2018/08/Annotation-1.png"><img src="https://msdnshared.blob.core.windows.net/media/2018/08/Annotation-1.png" alt/></a>
        </p>
        <p><a href="https://docs.microsoft.com/en-us/azure/active-directory/user-help/user-help-join-device-on-network#to-join-an-already-configured-windows-10-device">https://docs.microsoft.com/en-us/azure/active-directory/user-help/user-help-join-device-on-network#to-join-an-already-configured-windows-10-device</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Scenario 5: Azure AD Join (AutoPilot)</b>
        </p>
        <p>
          <img src="https://msdnshared.blob.core.windows.net/media/2018/08/AutoP1.gif"
          alt/>
        </p>
        <p>This method of setup and Intune enrolment is user driven, however the
          OOBE experience is customised to the organisation. Many of the OOBE screens
          can be skipped to ensure a smoother setup experience for end users.</p>
        <p><a href="https://docs.microsoft.com/en-us/intune/enrollment-autopilot">https://docs.microsoft.com/en-us/intune/enrollment-autopilot</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Scenario 6: Hybrid Azure AD Join (AutoPilot)</b>
        <br />
        <br />This is the newest method of enrollment made available in Windows 10 1809.The
        end user experience is almost the same as Azure AD Join (AutoPilot) scenario
        above, the main difference is that the admin configures <b>Hybrid Azure AD Join </b>when
        creating the AutoPilot profile and configures a connector between AD -&gt;
        Intune.<a href="https://docs.microsoft.com/en-us/intune/windows-autopilot-hybrid">https://docs.microsoft.com/en-us/intune/windows-autopilot-hybrid</a> 
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Scenario 7: Enrol in MDM Only (Device Enrollment Manager)<br /></b>
        </p>
        <p>This method of setup is very simlilar to Scenario #3 except it is performed
          by IT admins using a special type of account - A Device Enrollment Manager
          (DEM) Account. This account can be used to enrol up to 1000 devices into
          Intune. The IT administrator who is performing the enrollment needs to
          have access to local administrator credentials to complete the enrollment
          from the settings menu.</p>
        <p><a href="https://docs.microsoft.com/en-us/intune/device-enrollment-manager-enroll">https://docs.microsoft.com/en-us/intune/device-enrollment-manager-enroll</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Scenario 8: Azure AD Device Registration + Automatic Enrolment Group Policy Object</b>
        </p>
        <p>Intune enrolment for Domain joined Windows 10 devices can be automated
          using a GPO <b>&quot;Enable Automatic MDM enrolment using default Azure AD Credentials&quot;<br /></b>
        </p>
        <p>
          <img src="https://msdnshared.blob.core.windows.net/media/2018/08/083118_0616_ManagingWin4.png"
          alt/>
        </p>
        <p>Note: This is different to Azure AD Device Registration GPO. That GPO
          will only control the registration of the device and make it &quot;Hybrid
          Azure AD Joined&quot;, it will not enrol the device into Intune.</p>
        <p><b>Before Enabling GPO<br /></b>
        </p>
        <p>Device Registration Cert (Local computer store)</p>
        <p>
          <img src="https://msdnshared.blob.core.windows.net/media/2018/08/083118_0616_ManagingWin5.png"
          alt/>
        </p>
        <p><b>After Enabling GPO<br /></b>
        </p>
        <p>Intune Certificate (SC_Online_Issuing) is present in local computer certificate
          store</p>
        <p>
          <img src="https://msdnshared.blob.core.windows.net/media/2018/08/083118_0616_ManagingWin6.png"
          alt/>
        </p>
        <p><a href="https://docs.microsoft.com/en-us/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy">https://docs.microsoft.com/en-us/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Scenario 9: SCCM Co-Management</b>
        </p>
        <p>
          <img src="https://msdnshared.blob.core.windows.net/media/2018/08/083118_0616_ManagingWin7.png"
          alt/>
        </p>
        <p>Co-management is the best way to enrol existing device fleet that is already
          being managed by Configuration Manager. Once enabled, the device will be
          able to be managed by SCCM and Intune, leveraging the best features of
          both.</p>
        <p>CoManagmementHandler.log can show successful enrolment via this method.</p>
        <p><a href="https://docs.microsoft.com/en-us/sccm/core/clients/manage/co-management-overview">https://docs.microsoft.com/en-us/sccm/core/clients/manage/co-management-overview</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Scenario 10: Azure AD Join (Bulk Enrolment)</b>
        </p>
        <p>
          <img src="https://msdnshared.blob.core.windows.net/media/2018/08/083118_0616_ManagingWin8.png"
          alt/>
        </p>
        <p>Bulk enrolment is the name given to devices Azure AD Joined using a Bulk
          enrolment token. A bulk enrolment token can be created by IT admins using <b>&quot;set up school PCs&quot; </b>or <b>Windows configuration Designer </b>apps
          from the store. In this scenario, the IT admin prepares Windows devices
          with a USB key (Azure AD Join and Intune enrolment) ready for first user
          logon.</p>
        <p><a href="https://docs.microsoft.com/en-us/windows/client-management/mdm/bulk-enrollment-using-windows-provisioning-tool">https://docs.microsoft.com/en-us/windows/client-management/mdm/bulk-enrollment-using-windows-provisioning-tool</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Scenario 11: Azure AD Join (AutoPilot Self Deploying Mode)</b>
        </p>
        <p>This enrolment scenario is primarily for userless devices such as kiosks.
          The setup experience is the most streamlined out of any of the others,
          allowing all OOBE screens to be skipped after the device is first powered
          on.</p>
        <p>The Azure AD Join and Intune enrolment is fully automated without any
          user interaction.</p>
        <p>It&apos;s currently in preview and can be configured by choosing these
          options in your autopilot profile in the Intune console:</p>
        <p>
          <img src="https://msdnshared.blob.core.windows.net/media/2018/08/083118_0616_ManagingWin9.png"
          alt/>
        </p>
        <p><a href="https://docs.microsoft.com/en-us/intune/enrollment-autopilot">https://docs.microsoft.com/en-us/intune/enrollment-autopilot</a>
        </p>
      </td>
    </tr>
  </tbody>
</table>