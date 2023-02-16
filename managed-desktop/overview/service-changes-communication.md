---
title: Service changes and communication
description: How changes to the service occur and are communicated
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier2
manager: dougeby
ms.topic: how-to
audience: Admin
ms.date: 12/06/2022
---

# Service changes and communication

Sometimes, Microsoft might need to change details about the way Microsoft Managed Desktop works. Similarly, you might need to make changes that would affect the service as well. We handle such changes differently depending on how significant they are. This article defines:

- What changes are considered as major changes.
- How we handle them versus other changes.
- The types of communication channels we use to share information about these changes.

## Changes made by Microsoft

We'll give you notice at least 30 days ahead of time for any major change that requires action. We'll let you know by using the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) messaging system.

Major changes are those that might affect any of these areas:

- Changes affecting daily productivity.
- Changes to customized features and applications.
- Increase or decrease of visible capacity.
- Changes in product branding that might cause user confusion or change in helpdesk processes and reference material or URLs.
- Changes requiring permissions beyond those required by the service for daily operations, excluding actions that prevent or fix issues.
- Changes to where your data is stored.
- Adding a new component service or application to the scope of the service.
- Removal of a component service or application from the scope of the service.
- Adding new features to the service.

> [!NOTE]
> We might have to make changes to mitigate incidents or security issues that would be excluded from the 30-day notification policy.

We'll routinely make other changes to the service to improve user experience, security, reliability, and reporting. Some examples of these changes include:

- Installation of Windows and Office updates.
- Updates to the security baseline applied to devices.
- Supported devices. To see recommended devices, filter for Microsoft Managed Desktop on the [Shop Windows Pro business devices site](https://www.microsoft.com/windows/business/devices).

We'll communicate these changes by using the established [communication channels](#communication-channels). If you have any questions about any changes, contact the [Microsoft Managed Desktop Operations team](../operate/support-request.md). Changes to the service are also documented as needed in the What's new section).

Microsoft Managed Desktop changes and communications are governed by two Microsoft policies:

- [Modern Lifecycle Policy](/lifecycle/policies/modern)
- [Microsoft 365 Change Communication Policy](/microsoft-365/admin/manage/message-center?view=o365-worldwide&preserve-view=true)

## Changes you make

Some changes that you might make in your environment could affect Microsoft Managed Desktop.

For these major changes, we ask that you give us at least 30 days' notice by submitting a support request in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). For instructions, see [Admin support](../operate/support-request.md) for Microsoft Managed Desktop. This allows us adequate time to plan and prepare for the change to avoid disruptions.

Major changes are those that might affect any of the following areas:

- Identity systems and groups.
- Networking and network controls such as firewalls, proxy or caching, and VPN (virtual private networks) systems.
- Controls for accessing cloud services configurations.
- User or device certificates used for identity or securing of network services.
- Management systems that interact with the service.
- Security systems or agents that interact with the service.
- Configuration of any of the Microsoft 365 cloud services associated with, or used by, the service.

The following changes aren't likely to be disruptive, so you don't need to let us know about them ahead of time:

- Orphaned object cleanup.
- Adding or removing users from the service.
- Configuration of system that doesn't have a material impact on the delivery of the Microsoft Managed Desktop.
- Application version updates, except for VPN or proxy applications.

## Communication channels

Microsoft Managed Desktop will send general communications about the service for a variety of reasons, for example, service changes, new features, or feature deprecation.

Depending on the type of communications, we’ll either use the standard channels like the Message center and the Service health dashboard which is used by most products and services across Microsoft, or we may send a direct message to the Microsoft Managed Desktop admin contacts that you have registered in the admin center. For your convenience, we combine all these communications into a single blade in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) (**Tenant administration** > Microsoft Managed Desktop | **Messages**).

### Message center

This is the primary channel for official service announcements and feature changes. You can read these messages from Microsoft Managed Desktop alongside other services in the Microsoft 365 admin center, the admin mobile app, or receive a weekly digest in email. For more information, see this article on the [Message center](/microsoft-365/admin/manage/message-center?view=o365-worldwide&preserve-view=true). For admins that have access to Message center, any Microsoft Managed Desktop posts are also displayed in the Messages page in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

### Service health dashboard

You can view the health of your Microsoft services, including Microsoft Managed Desktop on the Service health page in the Microsoft 365 admin center.

If you’re experiencing problems with a cloud service, you can check the service health to determine whether this is a known incident with a resolution in progress before you engage support or spend time fixing the issue. For more information, see [how to check M365 service health](/microsoft-365/enterprise/view-service-health). For admins that have access to the Service health dashboard, Microsoft Managed Desktop posts are also displayed in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) > Service health dashboard > Messages page.

### Direct messages

For scenarios that fall outside the scope of the primary channels listed above, we may send direct messages to our customers. An example scenario is if our team needs to send a communication to a trial customer that doesn’t have access to the Message center. These messages are sent only to the admin contacts you’ve registered with our team, and the messages will only appear in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). To view these messages, navigate to **Tenant administration** on the Microsoft Managed Desktop | Messages page.

> [!NOTE]
> The Message center and Service health dashboard have different role requirements and permissions than the rest of Microsoft Managed Desktop. Most users who have been assigned any admin role in Microsoft 365, can view Message center posts. For admin roles that don’t have access to the Message center, see this [list](/microsoft-365/admin/manage/message-center?preserve-view=true&view=o365-worldwide#admin-roles-that-dont-have-access-to-the-message-center). You can also assign the Message center reader role to users who should be able to read and share Message center posts without having any other admin privileges.

### Managing email notifications

Communications may come over multiple channels. We recommend that, at a minimum, any administrators responsible for tracking changes with the service ensure they receive email notifications for all three of the channels.  

**To set up notification preferences for each communication channel:**

1. In the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), add yourself as an admin contact for Microsoft Managed Desktop.
1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), navigate to **Health > Message center**, and [setup your preferences](/microsoft-365/admin/manage/message-center?preserve-view=true&view=o365-worldwide#preferences) for notifications about new messages.
1. In the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), navigate to **Health > Service health**. Then, select **Customize** to turn on/off the **Send me email notifications about service health** option.
