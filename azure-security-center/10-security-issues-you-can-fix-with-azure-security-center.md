# 10 Security Issues You Can Fix with Azure Security Center

### 1 Absent Antimalware

Security experts agree that operating systems need antimalware installed. Modern antimalware is more sophisticated and does more than yesterday’s antivirus software – so you need to make sure that it’s installed. It’s not hard to install and maintain antimalware. What’s hard is finding the operating systems and virtual machines that _don’t have_ antimalware installed. Azure Security Center has you covered here!

In the figure below, notice that there is a recommendation to **Install Endpoint Protection** \(we’ll talk about recommendations later\).

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb569.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image682.png)

When you click that recommendation it will show you all the VMs that need antimalware. No more poking around trying to figure this out – it’s all right there.

Remediation? Just click the **Install on “X” VMs”** and Azure Security Center takes care of the heavy lifting – no scripts, no command lines, no extra tools, no learning curve – just install!

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb570.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image683.png)

### 2 Unintended endpoints

If you’re a networking pro, an endpoint is any networked device. In Azure world, an endpoint is a virtual machine that has an open _inbound_ connection _from_ the Internet. In many cases that’s exactly what you want. In many more cases, it’s exactly what you _don’t_ want.

Azure Security Center helps you with endpoints. In the figure below, you see that we provide a number of networking recommendations. Several of the recommendations refer to endpoints, such as **NGFW not installed** \(NGFW means “next generation firewall”\), **Finalize Internet facing endpoints**, and **Healthy Internet facing endpoints**. You can drill down on each of them to get more information and remediate the situation from within Azure Security Center.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb571.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image684.png)

Azure Security Center also provides you a very clear view of your Internet facing endpoints. In the figure below you can see a complete list of your Internet facing endpoints. You also get information on whether there is a **NSG** \([Network Security Group](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-nsg)\) or **NGFW** \([next generation firewall](https://en.wikipedia.org/wiki/Next-Generation_Firewall)\) in place. And if If there’s a NSG or NGFW in place, you’ll get a warning that you might need to do more with it.

All this visibility makes it easier than ever than ever to figure out if you have inadvertently allowed potentially dangerous inbound connections from the Internet to your virtual machines. Try that on-premises!

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb572.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image685.png)

### 3 In Search of the Unpatched

Just like making sure that Antimalware is installed, operating system security updates are standard security practice. Installing updates is relatively easy and we have many years of experience doing it.

What isn’t so easy is finding what virtual machines need updates installed!

If you have dozens, hundreds or thousands of VMs, there’s the chance more than few have slipped through the cracks.

Azure Security Center helps you close those cracks – check out the figure below. In the **VIRTUAL MACHINES RECOMMENDATIONS** section you see that Azure Security Center has identified virtual machines that have missing updates. Just click on that entry and you’ll see the exact machines that are missing the updates and a list of the missing updates.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb573.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image686.png)

### 4 No Security Experts

Azure is for companies of all sizes. In fact, you don’t even need to be a company to use Azure. You can be a single person who’s ready to make the Next Big Thing that’s going to change the world.

But one thing everyone needs, from giant companies to a clever college student, is good security. The problem is that good security advice is hard to find – some large companies have established security organizations and that’s great for them \(although we know that even the largest security org can benefit from Azure Security Center\).

What about companies and individuals who don’t have access to security experts?

You could pay a security expert – but that can get pretty expensive. And remember, security is a journey, not a destination – so you’ll have to keep that security expert on board long term.

The good news is that Azure Security Center automatically scans your Azure deployment and provides expert security advice. It’s like a security expert in a box – or like having me sitting next to you! ![Smile](https://msdnshared.blob.core.windows.net/media/2016/11/wlEmoticon-smile14.png)

Just click **Recommendations** as seen in the figure below and you’ll see security recommendations from Azure Security Center.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb574.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image687.png)

Whoa! Look at that – an impressive set of security recommendations that are specific to the security issues found in _your_ Azure deployments.

When you click down into these recommendations, you’ll get more information on the specific recommendation and what you can do to remediate them. In many cases, the remediation will be a click away to a fix.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb575.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image688.png)

### 5 Web Sites and Services Naked on the Web

When you develop and deploy web services, you’re focused on getting the applications coded right and deployed to the web. Agile means getting work done and in front of customers, and often security is a complication that is taken care of later, if ever.

It doesn’t have to be that way.

Even if it seemed like a hassle in the past, you can’t let your web apps hang naked on the web. It’s cold out there and it’s a setup for [bad things happening](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project). Azure Security Center will help you secure your web applications.

Just click on **Applications** in Azure Security Center and see what it recommendations for web applications.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb576.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image689.png)

Aha! A recommendation appears that says **Web application firewall not installed**. You might want to check that out.

Azure Security Center makes it easy to deploy a WAF, so securing your web apps isn’t going to slow you down. The figure below also shows your web applications and which ones have a WAF installed to protect them and which ones don’t.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb577.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image690.png)

### 6 If You Don’t Audit, it Didn’t Happen \(even when it did!\)

Azure Security Center can also help you with threat detection and auditing of your [Azure SQL databases](https://azure.microsoft.com/en-us/services/sql-database/).

Start by clicking **Data** in the Azure Security Center console as seen in the figure below.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb578.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image691.png)

Here you see recommendations such as **Server Auditing & Threat Detection on SQL Servers** and **Enable Auditing & Threat detection on SQL databases**.

Remember, if you don’t audit, there’s no evidence that anything happened, even if it did. Auditing is crucial and often required by regulatory compliance requirements. Azure Security Center also makes it easy for you to fix the problem. You don’t have to go to some other console to fix it – you’ll be able to carry out the recommendation right within Azure Security Center.

How’s that for making security easy? \#BOOM!

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb579.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image692.png)

### 7 Hanging out with the wrong crowd \(communicating with malicious machines\)

One thing you don’t want is your virtual machine doing is hanging out with the wrong crowd – and by that I mean you don’t want them communicating with malicious servers on the Internet.

In many cases this indicates that the virtual machine has been compromised and is communicating with a [botnet](https://en.wikipedia.org/wiki/Botnet) command and control server. Of course, it doesn’t have to be a botnet infection, there are many types of malware that communicate back to a controller of some sort. This type of malware can be very stealthy – so stealthy that it doesn’t even live on disk, which makes it very difficult for conventional antimalware solutions to find it.

Azure Security Center has your back – we use [Threat Intelligence feeds](http://whatis.techtarget.com/definition/threat-intelligence-feed) to identify if your virtual machines are communicating with suspicious characters and alert you if we find that they are. If you do get this alert, you should quickly evaluate that VM for possible compromise and begin your incident response routine.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb580.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image693.png)

## 8 No \(encryption at\) Rest for the Wicked

Data privacy is a cornerstone of security, whether that be on-premises or in the cloud. To keep that data private, it needs to be encrypted. The wicked bad guys love to find unencrypted information.

One the key places where information needs to be encrypted is when it’s on disk \(also known as “at rest”\).

You can encrypt data at rest in Azure with [Azure Storage Service Encryption](https://docs.microsoft.com/en-us/azure/storage/storage-service-encryption). This Azure storage security feature makes sure than any data you write to Azure storage is encrypted.

Of course, the challenge is to find what storage accounts haven’t been encrypted. You might have a lot of storage accounts, and sifting through all of them to see which ones aren’t encrypted isn’t really what you had in mind for a Friday night.

No problem! Azure Security Center will look for those unencrypted storage accounts and let you know about them. Then when you drill down, you’ll be able to turn on storage service encryption with a single click. The figure below shows the security recommendation **Storage encryption not enabled** – drill down on that and turn on encryption.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb581.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image694.png)

Virtual machines contain a lot of data – data you need to keep private. You can double-down on privacy by enabling [Azure Disk Encryption](https://docs.microsoft.com/en-us/azure/security/azure-security-disk-encryption).

The Azure Disk Encryption feature will encrypt the virtual disk files that comprise you virtual machines – and that includes both Windows and Linux virtual machines.

Again – when you’ve got a army of virtual machines doing your bidding – how are you going to find the ones that need to be encrypted?

Yep – Azure Security Center finds them and let’s you know, as seen in the figure below.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb582.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image695.png)

### 9 Feeling Vulnerable?

Azure Security Center goes a long way toward discovering security issues with your deployments in Azure. However, sometimes it’s a good idea to get a second opinion.

While we think our “expert in a box” is great, you might want to see if there are other security problems lurking within your virtual machines and PaaS deployments.

Sometimes we all feel a little vulnerable.

We’ve got your six here – we now support partner vulnerability assessment \(VA\) solutions. You can find them by clicking the **Partner Solutions** tile in the Azure Security Center console, as seen in the figure below.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb583.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image696.png)

Aha! Looks like we’ve already configured a vulnerability assessment solution – in this case, [Qualys](https://www.qualys.com/) \(we will have additional VA solution partners in the future\).

Let’s click on that and see what shows up.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb584.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image697.png)

Looks like the Qualys solution is **Healthy** \(which means that it’s able to connect back to the Qualys site\). We also see that it’s identified two virtual machines that need looking into.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb585.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image698.png)

Qualys have found some issues that need addressing. Notice the entry below that says **Remediate vulnerabilities \(by Qualys\)**? That means that Qualys found this issue, not Azure Security Center – this is good! We’ll talk about why this is good in the next section.

Let’s drill down on the **Remediate vulnerabilities \(by Qualys\)** entry.

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb586.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image699.png)

Whoa! Lots of vulnerabilities discovered in the operating system of **vm1**. We get the **Vulnerability name**, **status** and **severity**, among other things**.** That’s a lot of known unknowns, or is that unknown knowns, unknown unknowns? ![Smile](https://msdnshared.blob.core.windows.net/media/2016/11/wlEmoticon-smile14.png)

[![image](https://msdnshared.blob.core.windows.net/media/2016/11/image_thumb587.png)](https://msdnshared.blob.core.windows.net/media/2016/11/image700.png)

### 10 Islands in the Stream \(disconnected log/audit silos\)

I don’t have a new screenshot for this section, but the one above will do. Notice the **Vendor** column? That column provide you information about where we got the data.

When you see alerts and recommendations in Azure Security Center, we actually connect data from a number of different sources to bring it into Azure Security Center. We then surface them into a single Azure Security Center console – so you don’t have to go poking around a dozen difference interfaces and systems. No information source is an [Island in the Stream](http://www.bing.com/videos/search?q=islands+in+the+stream&view=detail&mid=2E91A5AC948127745AB12E91A5AC948127745AB1&FORM=VIRE) of data ![Smile](https://msdnshared.blob.core.windows.net/media/2016/11/wlEmoticon-smile14.png). Siloed data is de-siloed and turned into useful information. The more security sources and devices you associate with Azure Security Center, the more we’ll bring those together in a single presentation to you.

And, if you want all this data we’ve collected and collated for you piped into your SIEM system \(whether that be on-premises or in the cloud\) – we’ve got you covered! Just check out our [Azure Log Integrator](https://docs.microsoft.com/en-us/azure/security/security-azure-log-integration-overview) feature. It’ll bring in the Azure Security Center information \(and more!\) into your SIEM.

