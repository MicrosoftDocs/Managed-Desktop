---
title: Reset devices with a factory reset
description:  This article explains how to reset your devices with a factory reset
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
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
ms.topic: article
ms.date: 12/06/2022
---

# Reset devices with a factory reset

The Microsoft Managed Desktop Operations team can perform a factory reset of devices enrolled in the service when required. Resetting is helpful if you need to give a device to a different employee, or if an employee leaves your company.

There are a few requirements:

- Your global administrator must submit a [support request](../operate/support-request.md).
- Include the device's computer name in the request.
- The user account must be in Azure AD before we reset the device.

Managed Desktop Operations team will:

- Look up the device name in Intune.
- Send the factory reset command to the device.

> [!NOTE]
> Do not remove the user account from Azure AD before the device is reset. If the user isn't in Azure AD, Intune can't send the factory reset command to the device.

The device will boot into the "out of box experience," and all preinstalled applications and settings will be applied again. The user of the device needs to provide initial setup information again.

When the device has been reset, you can give it to a different person in your organization. None of the previous user's data or enterprise data will be on the device. The next user will go through the same process that the previous person did with a new Microsoft Managed Desktop device.

BitLocker is a key component of data security in this process. With BitLocker encryption on Microsoft Managed Desktop devices, data on the drive remains secure even after the device has been factory-reset. Any data that was on the drive won't be available to the next user of the device. For more information, see [BitLocker overview](/windows/security/information-protection/bitlocker/bitlocker-overview).

For more information, see [Factory reset a device](/intune/remote-actions/devices-wipe#factory-reset-a-device).
