![Microsoft Cloud Workshops](https://github.com/Microsoft/MCW-Template-Cloud-Workshop/raw/master/Media/ms-cloud-workshop.png "Microsoft Cloud Workshops")

<div class="MCWHeader1">
Windows Virtual Desktop
</div>

<div class="MCWHeader2">
Whiteboard design session student guide
</div>

<div class="MCWHeader3">
June 2020
</div>

Information in this document, including URLs and other Internet Web site references, is subject to change without notice. Unless otherwise noted, the example companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted herein are fictitious, and no association with any real company, organization, product, domain name, e-mail address, logo, person, place or event is intended or should be inferred. Complying with all applicable copyright laws is the responsibility of the user. Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.

Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.

The names of manufacturers, products, or URLs are provided for informational purposes only and Microsoft makes no representations and warranties, either expressed, implied, or statutory, regarding these manufacturers or the use of the products with any Microsoft technologies. The inclusion of a manufacturer or product does not imply endorsement of Microsoft of the manufacturer or product. Links may be provided to third party sites. Such sites are not under the control of Microsoft and Microsoft is not responsible for the contents of any linked site or any link contained in a linked site, or any changes or updates to such sites. Microsoft is not responsible for webcasting or any other form of transmission received from any linked site. Microsoft is providing these links to you only as a convenience, and the inclusion of any link does not imply endorsement of Microsoft of the site or the products contained therein.

© 2020 Microsoft Corporation. All rights reserved.

Microsoft and the trademarks listed at https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/Usage/General.aspx are trademarks of the Microsoft group of companies. All other trademarks are property of their respective owners.

**Contents**

<!-- TOC -->

- [Windows Virtual Desktop whiteboard design session student guide](#Windows-Virtual-Desktop-whiteboard-design-session-student-guide)
  - [Abstract](#abstract)
  - [Step 1: Review the customer case study](#step-1-review-the-customer-case-study)
    - [Customer situation](#customer-situation)
    - [Customer needs](#customer-needs)
    - [Customer objections](#customer-objections)
    - [Infographic for common scenarios](#infographic-for-common-scenarios)
  - [Step 2: Design a proof of concept solution](#step-2-design-a-proof-of-concept-solution)
  - [Step 3: Present the solution](#step-3-present-the-solution)
  - [Wrap-up](#wrap-up)
  - [Additional references](#additional-references)

<!-- /TOC -->

# Windows Virtual Desktop whiteboard design session student guide

## Abstract

In the Whiteboard Design Session (WDS), you will work in groups to design a Windows Virtual Desktop solution using Microsoft 365 and Azure technologies.  Your solution will consider the necessary Microsoft 365 subscription required for Windows 10 multi-user licensing, as well as the Azure Active Directory and security needs for a healthcare provider. You will need to determine how to connect Azure to the current VMware and Citrix on-premises infrastructure and the connections needed to connect this infrastructure to Azure for application access. Finally, you will need to design the Windows Virtual Desktop solution utilizing Azure virtual machines with availability and scalability to handle 24x7x365 operations without performance degradation.

At the end of the whiteboard design session, you will be better able to design a solution that leverages Microsoft 365 and Azure technologies together to build a secure and robust Windows Virtual Desktop infrastructure.

## Step 1: Review the customer case study

**Outcome**

Analyze your customer's needs.

Timeframe: 15 minutes

Directions: With all participants in the session, the facilitator/SME presents an overview of the customer case study along with technical tips.

1. Meet your table participants and trainer.

2. Read all of the directions for steps 1-3 in the student guide.

3. As a table team, review the following customer case study.

### Customer situation

Contoso Healthcare, headquartered in Detroit, Michigan, is a national healthcare provider with a network of affiliate hospitals and doctor’s offices located throughout North America. These locations continue to grow through acquisitions. The nature of their business requires a high level of security of personal health information (PHI) of patients, and personal identifiable information (PII) for their employees.

Contoso currently has approximately 500 workstations within their environment with a number of healthcare practice applications, insurance applications, and business applications. Contoso is currently supporting existing data centers in Detroit, MI and Dallas, Texas with VMware for the server control plane and a partial deployment of Citrix virtual desktop infrastructure.  These locations are connected with a private WAN connection and a backup VPN over broadband.  

Ken Greenwald, Contoso Healthcare CTO, has been evaluating the value of the public cloud and views Microsoft Azure as an excellent option to maintain availability and increase scalability of resources to the organization.  His team has also struggled with managing 500 workstations spread across the organization and needs an option to easily manage and maintain a standardized desktop image that gives users secure access to applications.  Ideally, these desktop images would not be maintained on local machines.  As Ken states, "Contoso Healthcare has continued to grow through the acquisition of doctor's offices and hospitals throughout North America, which has created an issue with our ability to standardize hardware at these locations.  The Board of Directors has been unwilling to increase capital expeditures for new equipment and we are forced as an IT organization to maximize our current infrastructure to deliver applications to users.  We need the ability to utilize what we have in place within our data centers and integrate Microsoft Azure technologies to facilite our ability to stardardize across the organization and quickly integrate a new office acquisition."

Contoso Healthcare's CISO, Laura Knight, has an additional list of objectives to address.  She is concerned with the threat of data exposure throughout the organization that is posed by the mulitple devices that they have acquired through their office acquisitions.  The continued increase in mobility of these devices raises concerns of PHI and PII being exposed to unauthorized individuals.  She also is responsible for the auditing of ISO/IEC 27001 and HIPAA controls.  Laura has said, "The growth of Contoso Healthcare has created an increased burden on my security and compliance organization.  It has become more difficult to monitor systems as they come online with variations of operating systems.  Some of these operating systems do not support mobile device management software to audit use and application access.  In addition, enforcing a centralized standard for security policies and access to confidential information has been challenging.  My organization needs to be able to maintain the security of our data and resources, and mitigate the prospect of data loss due to threat or unauthorized access to devices." 

Contoso Healthcare has completed an initial cloud assessment of their current infrastructure and applications, and they have divided the following areas that they feel that Microsoft 365 and Azure technologies can support:

**Security:** The business of healthcare has become more reliant on mobile devices to access patient health records, which has created a concern over theft and data exposure. Contoso would like to eliminate the possibility of any PHI or PII being located on a local device through use of a virtual desktop infrastructure. Security controls will need to audited, logged, and reviewed to ISO 27001 and HIPAA standards.

**Availability and Scalability:** Being a healthcare provider, Contoso has a requirement for applications to be accessible 24x7x365, so any infrastructure should be designed with high availability and scalability in mind. As Contoso Healthcare grows through acquisitions, they need to be able to scale out resources quickly for the addition of new users.

**Deployment Acceleration:** Contoso does not have a budget for additional capital expense required to upgrade current devices.  Therefore, they will need to utilize the current devices that are available to deliver a standard desktop image to users.   Contoso will be utilizing their current VMware and Citrix infrastructure for application delivery to user desktops.

### Customer needs

1. CH needs the ability to manage mobile device location and avoid access to patient health records when not on the Contoso Health network.

2. CH requires that any PHI and PII data is stored in a central encrypted storage account and not on local devices.

3. CH must be able to log activity and access, and be able to audit compliance to ISO 27001 and HIPAA controls.

4. CH requires 24x7x365 access to applications and the ability to scale resources as demand increases.

5. CH needs redundancy in network connections with low latency when accessing applications.

6. CH requires the ability to create and deploy a standardized desktop image to all users without the need to update and manage local devices.

7. CH needs to leverage the current application infrastructure in their current Detroit and Dallas datacenters.

### Customer objections

1. Contoso has made a substantial capital investment in their current data centers that they do not want to decommission. How can the infrastructure be architected to support the current data centers?

2. The CTO at Contoso does not want to invest in new workstations and mobile devices to support the standardized desktop image. Can these devices support the new image?

3. The CISO at Contoso needs to be convinced that data will not be exposed. How would Microsoft handle data protection?

4. Contoso must be able to log and audit all activity on the desktop image.  How will this be handled within the cloud and on-premises environments?

5. Connections between the cloud and existing data centers must be secure and reliable to support their requirements.  How will this be addressed and monitored?

### Infographic for common scenarios (Need to replace with WVD images)

![Azure Site Recovery Scenarios apply to multiple on-premises and cloud-based replication infrastructures, including Hyper-V to Hyper-V, Hyper-V to Azure, VMWare or physical to VMWare, VMWare or Physical to Azure, and Azure to Azure.](images/Whiteboarddesignsessiontrainerguide-Businesscontinuityanddisasterrecoveryimages/media/image2.png "Azure Site Recovery Scenarios ")

![Recovering Hyper-V VMs to Azure Architecture has the source as Hyper-V Hosts (Windows or Linux), an Azure Recovery Services agent, SCVMM with a Site Recovery DRA, Azure Site Recovery, and a Microsoft Azure cloud service. ](images/Whiteboarddesignsessiontrainerguide-Businesscontinuityanddisasterrecoveryimages/media/image3.png "Recover Hyper-V VMs to Azure Architecture")

![In this environment, the Source Environment (East US) has a storage account with two disks and a storage account cache asr with cache data. These interact with a VNet environment made up of an availability set of two Azure Virtual Machines, and a subnet. Data flows from here through the Cache data, and to the Target Environment (Central US) Storage account ASR disks. In the Target Environment, the VNet-asr is empty.](images/Whiteboarddesignsessiontrainerguide-Businesscontinuityanddisasterrecoveryimages/media/image4.png "Azure Site Recovery Region to Region Failover")

![Screenshot of the Azure Marketplace in the Azure Portal. Backup Exec 16 - Standard is called out.](images/Whiteboarddesignsessiontrainerguide-Businesscontinuityanddisasterrecoveryimages/media/image5.png "Azure Portal, Azure Marketplace")

![The Native Azure Backup Option one has an on-premises solution of one SharePoint and one SQL virtual machine that use an Azure backup server. On-premises uses the internet to upload to Azure Backup, which then downloads for App/Item-level restore. Option two has a solution of one SharePoint and one SQL virtual machine that use either a Commvault Simpana or VCC for Enterprise machine. This solution uses the internet to upload to Azure Storage (blob), which then downloads for App/Item-level restore.](images/Whiteboarddesignsessiontrainerguide-Businesscontinuityanddisasterrecoveryimages/media/image6.png "Azure Backup and third-party back solutions")

## Step 2: Design a proof of concept solution

**Outcome**

Design a solution and prepare to present the solution to the target customer audience in a 15-minute chalk-talk format.

Timeframe: 60 minutes

**Business needs**

Directions:  With all participants at your table, answer the following questions and list the answers on a flip chart:

1. Who should you present this solution to? Who is your target customer audience? Who are the decision makers?

2. What customer business needs do you need to address with your solution?

**Design**

Directions: With all participants at your table, respond to the following questions on a flip chart:

*Provide an overview of the technologies and the implementation at a high-level. How will you use Microsoft's M365, Windows Virtual Desktop, and Azure technologies to meet the Customer's needs?*

Design a Windows Virtual Desktop infrastructure that addresses the needs and requirements of the organization. At a high-level, provide details of your implementation. Make sure to document your design with a diagram along with addressing the questions.  Address the requirements in the following areas.

1. Microsoft 365

    - What Microsoft 365 subscription is required for Windows 10 multi-user licensing?

    - What subscription is required for Contoso's mobile device requirements?

    - What subscription is needed to classify and protect PHI and PII access?

    - What subscription is necessary to enforce device access on the local network only?

    - Why did you select the Microsoft 365 subscription(s)?

2. Security

    - What is required to audit, log, and monitor controls for ISO 27001 and HIPAA?

    - How will you address monitoring these controls in Azure and the on-premises data centers?

    - How will you avoid data exposure for data in-transit and data at-rest?

    - How will you maintain identity access management for the cloud and current Active Directory infrastructure, and how will they synchronize?

    - How will you address the secure and centralized file storage needs of the organization?

    - Describe the reasons for the specific security services selected.

3. Networking

    - What region or regions will you deploy resources and why?
    
    - How will you design the resource groups to support your design?
       
    - How will your virtual networks (VNETs) be configured for IP addresses and subnets?

    - How will you connect to Contoso Healthcare's data centers to minimize latency and maximize security?

    - How will you manage and balance network traffic to virtual desktops images?

    - What will you use to identify and monitor threats on the network?

    - How would you monitor network throughput and latency over the network?

4. Windows Virtual Desktop image

    - How will the standardized desktop image be created?

    - How will applications be delivered to the desktop image?

    - What are the connection options for users to access the Windows Virtual Desktop image?

    - What are the minimum system requirements for users to access the Windows Virtual Desktop image?   

5. Windows Virtual Desktop host pool
       
    - How many con-current sessions will be required to access the virtual desktop image?

    - How many virtual machines are required to support the number of con-current sessions?


**Customer Objections**

1. Provide details on how you will address each of the objections that were put forward by the client.

**Prepare**

Directions: With all participants at your table:

1. Identify any customer needs that are not addressed with the proposed solution.

2. Identify the benefits of your solution.

3. Determine how you will respond to the customer's objections.

Prepare a 15-minute chalk-talk style presentation to the customer.

## Step 3: Present the solution

**Outcome**

Present a solution to the target customer audience in a 15-minute chalk-talk format.

Timeframe: 30 minutes

**Presentation**

Directions:

1. Pair with another table.

2. One table is the Microsoft team and the other table is the customer.

3. The Microsoft team presents their proposed solution to the customer.

4. The customer makes one of the objections from the list of objections.

5. The Microsoft team responds to the objection.

6. The customer team gives feedback to the Microsoft team.

7. Tables switch roles and repeat Steps 2-6.

## Wrap-up

Timeframe: 15 minutes

Directions: Tables reconvene with the larger group to hear the facilitator/SME share the preferred solution for the case study.

## Additional references

|    |            |
|----------|:-------------:|
| **Description** | **Links** |
| Overview of Windows Virtual Desktop | <https://docs.microsoft.com/en-us/azure/virtual-desktop/overview> |
| Windows Virtual Desktop environment setup | <https://docs.microsoft.com/en-us/azure/virtual-desktop/environment-setup> |
| Create a virtual desktop host pool | <https://docs.microsoft.com/en-us/azure/virtual-desktop/create-host-pools-azure-marketplace> |
| Windows Virtual Desktop licensing requirements and pricing | <https://azure.microsoft.com/en-us/pricing/details/virtual-desktop/> |
| Prepare and customize a master VHD image | <https://docs.microsoft.com/en-us/azure/virtual-desktop/set-up-customize-master-image> |
| Azure Policy overview | <https://docs.microsoft.com/en-us/azure/governance/policy/overview> |
| Azure Security Center | <https://docs.microsoft.com/en-us/azure/security-center/> |
| Azure Active Directory | <https://docs.microsoft.com/en-us/azure/active-directory/> |
| File Storage in Windows Virtual Desktop | <https://docs.microsoft.com/en-us/azure/virtual-desktop/fslogix-containers-azure-files> |
| Connect WVD with a web client | <https://docs.microsoft.com/en-us/azure/virtual-desktop/connect-web> |
| WVD security best practices | <https://docs.microsoft.com/en-us/azure/virtual-desktop/security-guide> |
| Microsoft 365 enterprise plans | <https://www.microsoft.com/en-us/microsoft-365/compare-microsoft-365-enterprise-plans> |
| Microsoft 365 enterprise mobility + security plans | <https://www.microsoft.com/en-us/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing?rtc=1> |
| Virtual Desktop partners | <https://docs.microsoft.com/en-us/azure/virtual-desktop/partners> |


