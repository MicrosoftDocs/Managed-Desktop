---
title: Standard operating procedures
description:  Details the standard operating procedures in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: conceptual
ms.date: 12/06/2022
---

# Standard operating procedures

The Microsoft Managed Desktop service is implemented and operated by Microsoft in your Microsoft cloud instance where you might conduct other administrative activities. Microsoft is solely responsible for Microsoft Managed Desktop-specific setup, configuration, and operation.

For on-premises products, your organization takes on all the responsibility for managing setup, and configuration and operational activities.

| Categories | Microsoft will | Customer will |
| ----- | ----- | ----- |
| Network (proxy, packet inspection, VPN) | Advise and plan with customers to minimize risk to business users. | <ul><li>Create a support request requesting information for a planned configuration change. Include the configuration details, scope, timeline, and other pertinent details for Microsoft to review.</li><li>Only apply a change once Microsoft Managed Desktop Operations has assessed and advised.</li></ul> |
Service accounts | <ul><li>Implement, securely store, and manage the credentials.</li><li>Communicate unauthorized access or use of these credentials to your Security Operations team.</li></ul> | <ul><li>Create a support request requesting information for a planned configuration change. Include configuration details, scope, timeline, and other pertinent details for Microsoft to review.</li><li>Only apply a change once Microsoft Managed Desktop Operations has assessed and advised.</li><li>Not assign policy, multi-factor authentication, conditional access, or application deployment to the Microsoft Managed Desktop Service Accounts.</li><li>Not reset the password or use the credentials.</li><li>Open a Sev C support request to Microsoft Managed Desktop Operations if suspicious activity is observed in Intune or Azure audit logs, related to these service accounts.</li></ul>
| Device Groups | <li> Implement and assign the membership of devices within Microsoft Managed Desktop groups.</li><li>Use the Microsoft Managed Desktop groups to manage the assignment and release of configuration and updates to devices.</li></ul> | <ul><li>Create a support request requesting information for a planned configuration change. Include configuration details, scope, timeline, and other pertinent details for Microsoft to review.</li><li>Only apply a change once Microsoft Managed Desktop Operations has assessed and advised.</li><li>Only assign devices to any Microsoft Managed Desktop group following the steps described in [Assign devices to a deployment group](../operate/assign-deployment-group.md).</li><li>Only use the groups to assign corporate certificates for services such as VPN, Windows Hello for Business or email encryption, or corporate wifi profile configuration.</li><li>Where co-management exists, explicitly exclude all Microsoft Managed Desktop groups when deploying the Configuration Manager client.</li></ul>
| Policies | <ul><li>Implement and manage the Microsoft Managed Desktop policies that govern the configuration state of devices within service.</li><li> Deploy updates, to policy or Windows, incrementally using Device Groups.</li><li>Explicitly exclude targeting non-Microsoft Managed Desktop groups.</li></ul> | <ul><li>Create a support request requesting information for a planned configuration change. Include configuration details, scope, timeline, and other pertinent details for Microsoft to review.</li><li>Only apply a change once Microsoft Managed Desktop Operations has assessed and advised.</li><li>Not edit or assign Microsoft Managed Desktop policies to devices or users not managed by the Microsoft Managed Desktop service.
Microsoft 365 Defender for Endpoint.</li></ul> | Monitor and investigate devices within the scope of the Microsoft Managed Desktop service. | <ul><li>Create a support request requesting information for a planned configuration change. Include configuration details, scope, timeline, and other pertinent details for Microsoft to review.</li><li>Only apply a change once Microsoft Managed Desktop Operations has assessed and advised.</li></ul>
| Microsoft Store for Business | Configure and maintain the Windows Autopilot profile for the Microsoft Managed Desktop service. | <ul><li>Create a support request requesting information for a planned configuration change. Include configuration details, scope, timeline, and other pertinent details for Microsoft to review.</li><li>Only apply a change once Microsoft Managed Desktop Operations has assessed and advised.</li><li>Not modify the configuration of the Microsoft Managed Desktop Windows Autopilot profile or add/remove assigned devices.</li></ul>
| Certificates | | <ul><li>Create a support request 60 days prior to a certificate expiring, requesting information for a planned configuration change. Include configuration details, scope, timeline, and other pertinent details for Microsoft to review.</li><li>Only apply a change once Microsoft Managed Desktop Operations has assessed and advised.</li><li>Update all certificates that are required to configure certificate profiles, VPN profiles, and Wi-Fi profiles.</li></ul>|
