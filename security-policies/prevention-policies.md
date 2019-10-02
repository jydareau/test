# Prevention Policies

#### Prevention Policies <a id="prevention-policies"></a>

By default, all prevention policies are turned on. [Prevention policies](https://azure.microsoft.com/en-us/documentation/articles/security-center-policies/#set-security-policies-for-subscriptions) and recommendations are tied to each other. In other words, if you enable a prevention policy, such as OS vulnerabilities, then that enables recommendations for that policy.  In most situations, you will want to enable all policies, even though some might be more important to you than others depending on the Azure resource you’ve deployed.

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <img src="https://prod-edxapp.edx-cdn.org/assets/courseware/v1/7bd229f947d3ff3fd1d825418fa3c03e/asset-v1:Microsoft+AZURE208x+3T2018+type@asset+block/M3L2T3_AuGwILY.png"
        alt="Screenshot of the Prevention Policy page showing the selections described in the text. "
        />
      </th>
      <th style="text-align:left">
        <p><b>System updates</b>. Retrieves a daily list of available security and
          critical updates from Windows Update or Windows Server Update Services.</p>
        <p><b>OS vulnerabilities</b>. Analyzes operating system configurations daily
          to determine issues that could make the virtual machine vulnerable to attack.</p>
        <p><b>Endpoint protection</b>. Recommends endpoint protection to be provisioned
          for all Windows virtual machines to help identify and remove viruses, spyware,
          and other malicious software.</p>
        <p><b>Disk encryption.</b> Recommends enabling disk encryption in all virtual
          machines to enhance data protection at rest.</p>
        <p><b>Network Security Groups</b>. Recommends that network security groups
          be configured to control inbound and outbound traffic to VMs that have
          public endpoints. In addition to checking that a network security group
          has been configured, this policy assesses inbound security rules.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

| ![Checkmark](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/f0fcce0131853bcf4dc919a3dd61834d/asset-v1:Microsoft+AZURE208x+3T2018+type@asset+block/CheckMarkWhite.png) | While the generated list of recommendations may be long, it provides you with full visibility into the security health of your environment. |
| :--- | :--- |


<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <img src="https://prod-edxapp.edx-cdn.org/assets/courseware/v1/ccd2671106a6bc14b25f968b45795bc1/asset-v1:Microsoft+AZURE208x+3T2018+type@asset+block/M3L2T4_GSJQT0U.png"
        alt="Screenshot of the Prevention Policy page showing the selections described in the text."
        />
      </th>
      <th style="text-align:left">
        <p><b>Web application firewall.</b> Extends network protections beyond network
          security groups, which are built into Azure. Security Center will discover
          deployments for which a next generation firewall is recommended and enable
          you to provision a virtual appliance.</p>
        <p><b>Next generation firewall.</b> Extends network protections beyond network
          security groups, which are built into Azure. Security Center will discover
          deployments for which a next generation firewall is recommended and enable
          you to provision a virtual appliance.</p>
        <p><b>Vulnerability Assessment</b>. Recommends that you install a vulnerability
          assessment solution on your VM.</p>
        <p><b>SQL auditing &amp; Threat detection</b>. Recommends that auditing of
          access to Azure Database be enabled for compliance and advanced threat
          detection, for investigation purposes.</p>
        <p><b>SQL Encryption</b>. Recommends that encryption at rest be enabled for
          your Azure SQL Database, associated backups, and transaction log files.
          Even if your data is breached, it will not be readable.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>