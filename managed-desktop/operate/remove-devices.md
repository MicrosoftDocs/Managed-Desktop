---
title: Remove devices
description: Remove devices from Microsoft Managed Desktop management
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
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

# Remove devices

You can remove devices from Microsoft Managed Desktop management by using the admin center. This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [manual registration steps](../prepare/manual-registration.md).

When you remove a device, all of the following occur:

- We remove the device from Autopilot.
- We remove the device from  all "Modern Workplace" device groups.
- We remove the device from the **Devices** blade in the admin center.

When you remove a device, you can also remove it from Microsoft Entra ID and Microsoft Intune.
  
> [!CAUTION]
> Removing the objects related to a device from Microsoft Entra ID and Microsoft Intune is permanent. If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals. The devices won't be able to access their company's corporate resources. Company data might be deleted from them if the devices try to sign in after they're deleted.

**To remove a device:**

1. In the **[Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431)**, select **Devices** in the left navigation pane.
2. In the **Microsoft Managed Desktop** section, select **Devices**.
3. In the **Microsoft Managed Desktop Devices workspace**, select the devices you want to delete.
4. Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.
5. In the fly-in, review the selected devices and then select **Remove devices**. If you want to also remove the Microsoft Entra ID and Intune objects at the same time, select the checkbox. Device removal can take a few minutes to complete.

> [!NOTE]
> You can't remove devices that are in a **pending** registration state.
