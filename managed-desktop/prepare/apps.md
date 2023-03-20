---
title: Apps in Microsoft Managed Desktop 
description:  Explains how apps are handled, including how to package, deploy, and support them.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
ms.author: tiaraquan
manager: dougeby
ms.topic: conceptual
audience: Admin
ms.date: 03/17/2023
---

# Apps in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the admin center (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->

## Apps generally

Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop. However, even though we provide these apps, you still have certain responsibilities and actions to complete.

You can also deploy additional non-Microsoft apps to your users via self-service through the Company Portal, or a required background installation using Microsoft Intune's deployment pipeline.

## Apps provided by Microsoft

Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams, and OneNote).

Click-to-Run versions of Microsoft Project and Visio *aren't* included by default, but you can [submit a change request](../operate/support-request.md) for them to be added. For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../operate/project-visio.md).

### What Microsoft does to support the apps we provide

Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps. Click-to-Run versions of Microsoft Project and Visio *aren't* included by default. However, Microsoft Managed Desktop will provide deployment groups to allow your IT administrator to manage licenses, and deploy these applications appropriately for your organization. Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.

> [!IMPORTANT]
> Microsoft Visio and Project licenses must be from Office 365 subscriptions. Microsoft Managed Desktop doesn’t support volume license keys (VLKs).

### What you need to do to support the apps we provide

There are still certain things you need to do with these apps:

| Task | Description |
| ------ | ------ |
| Assign licenses | You're responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise. |
| Add users to security groups | If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for reclaiming licenses from those users if they leave the company. |
| [Deploy Microsoft 365 Add-ons](/microsoft-365/admin/manage/manage-deployment-of-add-ins) | If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app. |

## Apps you provide

You probably have other apps you need for your business operations. These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune's deployment pipeline. For more information about application deployment, follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../deploy/deploy-apps.md).

### Preparing your own apps for inclusion in Microsoft Managed Desktop

Review your apps, checking:

- None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../prepare/app-requirements.md).
- Apps must be ready for management
    - For **Intune** tenants, see the following articles: Microsoft Intune.
        - [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy)
        - [Add apps to Microsoft Intune](/intune/apps-add).
    - If you **already have [Autopilot into co-management](../prepare/autopilot-co-management.md)**, you can [deploy apps using Configuration Manager](../prepare/autopilot-co-management.md#step-2-deploy-applications-in-configuration-manager).
- Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.

## Default Windows apps

There are different types of apps that can run on your Windows client devices. Some end user facing apps may be available and installed as part of the default Windows apps, for example, Windows Media Player, game apps, etc. You can uninstall these apps from your environment without submitting a support request or a request for an exception.
