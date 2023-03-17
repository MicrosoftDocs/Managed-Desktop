---
title: Add and deploy apps to devices
description: Information for adding and deploying apps to Microsoft Managed Desktop devices.  
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, apps, line-of-business apps, LOB apps
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.date: 03/17/2023
---

# Add and deploy apps to devices

Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices. Use the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add and deploy your apps.

> [!TIP]
> If you already have [co-management for Windows devices](/mem/configmgr/comanage/overview) turned on and want to combine the benefits of Microsoft Intune for all workload management, you can configure devices and deploy apps using [Autopilot into co-management](../prepare/autopilot-co-management.md). Client applications will continue to be managed by Configuration Manager.

The overall process looks like this:

1. [Add apps to the Microsoft Intune admin center](#step-1-add-apps-to-the-microsoft-intune-admin-center).
2. [Assign apps to your users](#step-2-assign-and-deploy-apps-to-your-users).

> [!TIP]
> If you'd like to restrict the execution of code on client devices, you must turn on [app control](../prepare/app-control.md). To turn on app control, you must [submit a request](../operate/support-request.md).

## Step 1: Add apps to the Microsoft Intune admin center

Before you can configure, assign, protect, or monitor apps, you must [add the apps to Microsoft Intune](/mem/intune/apps/apps-add).

## Step 2: Assign and deploy apps to your users

After you've added apps to Microsoft Intune, you must [assign](/mem/intune/apps/apps-deploy#assign-an-app) and [deploy apps to devices](/mem/intune/apps/apps-windows-10-app-deploy).  

After assigning and deploying apps to devices, you can [monitor app information and assignments with Microsoft Intune](/mem/intune/apps/apps-monitor).

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the admin center (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
