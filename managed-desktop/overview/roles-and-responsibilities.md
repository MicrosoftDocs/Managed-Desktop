---
title: Microsoft Managed Desktop roles and responsibilities
description: This article describes the roles and responsibilities provided by Microsoft for Microsoft Managed Desktop. 
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.date: 03/10/2023
---

# Roles and responsibilities

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

When your organization is enrolled in Microsoft Managed Desktop (the service), what does Microsoft do for you? And what are your organization's responsibilities?

## Microsoft Managed Desktop's roles and responsibilities

Microsoft Managed Desktop (the service) provides these key roles and responsibilities:

| Role or responsibility | Description |
| ----- | ----- |
| Mobile Device Management (MDM) policy management | Microsoft will apply MDM policies according to [best practices](/mem/intune/protect/security-baselines) and consider requests for policy changes. We'll also make changes to your tenant as prescribed in [device policies](../operate/device-policies.md). |
| User support | We provide a mechanism for elevated access to devices and for issues to get escalated through a support request if necessary. For more information, see [User support](../operate/end-user-support.md).
| Microsoft Managed Desktop service support | Microsoft will provide support to your IT department through a [Microsoft Managed Desktop Operations Team](../overview/support-teams.md). The team will support technical remediation, change requests, and incident management for the customer's Microsoft Managed Desktop environment. For more information, see [submit a support request](../operate/support-request.md). |
| Change management | Microsoft will notify customers, in advance, when changes need to be made to their Microsoft Managed Desktop environment. For more information, see [service changes and communication](../overview/service-changes-communication.md). |
| Security monitoring | Microsoft will monitor your Microsoft Managed Desktop devices using Microsoft Defender for Endpoint. If the [Microsoft Managed Desktop Security Operations Center (SOC) team](../overview/support-teams.md#security-operations-center-team) detects a threat, we'll notify you, isolate the device, and rectify the issue remotely. For more information, see [Security](../overview/security-technologies.md). |
| Update monitoring and management | We actively monitor your Microsoft Managed Desktop devices to ensure that the latest quality and feature updates are installed for Microsoft Windows and Microsoft Office. For more information, see [how updates are handled](../operate/updates.md). |
| User and device grouping | [Microsoft Managed Desktop Operations Team](../overview/support-teams.md#service-engineering-team) will create and manage required device and user groups as part of IT operations. No membership or configuration changes are allowed for these groups. Altering these groups can lead to unexpected configuration of devices and loss of functionality. For any issues or questions around these groups once established, IT administrators can [submit a support request](../operate/support-request.md). |
| Microsoft 365 Apps for enterprise configuration and management | For [apps provided by Microsoft](../prepare/apps.md#apps-provided-by-microsoft) (Microsoft 365 Apps for enterprise comprising Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams, and OneNote), Microsoft will provide configuration for the deployment, update, and support. However, you must:<ul><li>Obtain and assign licenses for these apps</li><li>Add users to security groups</li><li>Manage end of life</li><li>Deploy any add-ons you need</li></ul><p>Microsoft will provide Microsoft Intune deployment tools to deliver the applications to remote clients.</p> |
| OneDrive | Microsoft is responsible for deployment and continued operation of OneDrive for Business clients. Information stored in key folders on the device is synchronized to OneDrive for Business. |

## Your roles and responsibilities

The following list of common roles and responsibilities is required for deployment, but aren't provided by Microsoft. It's not exhaustive but is applicable to most organizations. There are a few items that both you and Microsoft share responsibility for.

| Role or responsibility | Description |
| ----- | ----- |
| Change management | You must have your own change management process and [have a contact](../prepare/add-admin-contacts.md) established with Microsoft Managed Desktop Operations Team. You also must have resources to review and approve these changes. For more information, see [service changes and communication](../overview/service-changes-communication.md). |
| Identity management | You're responsible for creating user accounts, assigning users to groups, and keeping metadata up to date. |
| Microsoft 365 Apps for enterprise configuration and management | Microsoft is responsible for ensuring Office applications are deployed to users and those applications are kept up to date. <br><br> You're responsible for managing Microsoft 365 services and policies, including Exchange Online administration responsibilities:<br><ul><li>Email administration</li><li> Mailbox and rule configuration</li><li>Exchange on-premises management</li></ul><br>You're also responsible for collaboration tools, SharePoint server administration, domain management, and security and information policies that are set in the Microsoft 365 admin center. |
| User support | Provide all user support and technical assistance from first contact through to resolution for the user, either by you or through a designated support partner. You must either provide user support directly or work with a partner to provide support for these areas: <br><ul><li>On-site infrastructure: all network and internet connectivity, VPN infrastructure and client configuration, local conference room equipment, printers, proxy server and configuration, and firewalls.</li><li>Company-wide cloud resources: email, SharePoint, collaboration services, and other cloud infrastructure that relates to the company-wide technology footprint.</li><li>Line of business and any other company-specific applications.</li></ul> |
| Line of Business and third-party applications | [For apps you provide](../prepare/apps.md#apps-you-provide) (such as your line-of-business apps), whether you package them yourself or engage a non-Microsoft vendor to do so, you are responsible for the following:<ul><li>Identifying applications needed for targeted user groups</li><li>Creating and managing Azure AD groups for app deployment</li><li>Packaging apps to meet Microsoft Intune deployment standards</li>Uploading apps to Microsoft Intune</li><li>Testing apps in Microsoft Managed Desktop environment</li><li>Testing apps with your users</li><li>Managing and assigning users to applications</li><li>Identify and deploy application updates through Microsoft Intune</li><li>Uninstalling and removing applications when they've been retired</li><li>Procuring and assigning licenses</li><li>Providing user support for line-of-business apps</li><li>Managing app settings remotely</li></ul> |
| Security monitoring and response | You're responsible for investigating and resolving incidents for devices that aren't Microsoft Managed Desktop devices. |
| Operations support | You must provide a list of [preferred contacts and subject matter experts](../prepare/add-admin-contacts.md) in your organization. We need these contacts if there's an operational incident which requires Microsoft Managed Desktop Operations Team support or awareness. <br><br>You're also responsible for investigating and resolving incidents for devices and services that aren't in Microsoft Managed Desktop. You must ensure that the Microsoft Managed Desktop Operations Team is always informed of any issues that may impact on the Microsoft Managed Desktop service. |
| Network infrastructure, including VPN | You're responsible for setup, configuration, and management (including fixing and debugging) of all networking-related infrastructure and services. This also includes internet connectivity, network controls, proxy configuration, and remote connectivity infrastructure.<br><br>If a proxy is configured (in hardware or software), there's a collection of URLs that must be allowed by the proxy. You're responsible for fixing any conflicts or incompatibilities due to multiple proxies. For more information, see [Proxy configuration](../prepare/network.md). You can add network proxies specific to your organization using [configurable settings](../operate/config-setting-ref.md#proxy).<br><br>
| Printing | You're responsible for installing, maintaining, and administering printers and print queues. Cloud printing is a recommended solution, but it isn't required. |
| OneDrive | You're responsible for information that isn't synchronized with OneDrive for Business. |
