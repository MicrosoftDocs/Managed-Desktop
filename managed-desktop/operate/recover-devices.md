---
title: Recover devices
description:  This article explains how to use Windows Recovery to recover devices
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier2
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.date: 12/06/2022
---

# Recover devices

This article covers two primary scenarios for Windows Recovery in Microsoft Managed Desktop:

- [Break and fix](#break-and-fix)
- [Reuse the device](#reuse-the-device)

The key factor in the two options is to ensure that devices don't have their mobile device management (MDM) enrollment data removed. Keeping the MDM enrollment data ensures device specific settings, related to upgrade and migration used in our Windows Update for Business service, are kept and features like [Max OS Version](/mem/intune/protect/compliance-policy-create-windows#device-properties) are honored post [Windows Recovery](/windows-hardware/manufacture/desktop/windows-recovery-environment--windows-re--technical-reference?view=windows-11&preserve-view=true).

## Break and fix

For scenarios where service desk teams have decided that the fastest way to resolve the issue is through a device reset, Microsoft Managed Desktop recommends the **Microsoft Endpoint Manager device wipe action** and selecting the **Retain enrollment state and user account** setting. This action uses Windows recovery on the client device. Performing Windows recovery can place the system back into a known good state and address issues like Windows file corruption, reset to default settings, etc. For more information about Windows recovery (also known as push-button reset), see [Push-button reset feature settings](/windows-hardware/manufacture/desktop/how-push-button-reset-features-work?view=windows-11#settings&preserve-view=true).

### What to expect with the Wipe action and retaining enrollment state

The following table describes:

- The information and files that are kept after the wipe.
- The information and files that aren't kept after the wipe.

| Kept after wipe | Not kept after wipe |
| ----- | ----- |
| User accounts associated with the device | User files |
| Machine state (domain join, Azure AD-joined) | User-installed apps (store and Win32 apps) |
| Mobile device management (MDM) enrollment | Non-default device settings |
| OEM pre-installed apps (store and Win32 apps) | |
| User profile and some [user configured settings](/windows-hardware/manufacture/desktop/how-push-button-reset-features-work?view=windows-11#settings&preserve-view=true)  | |
| User data outside of the user profile  | |
| User autologin settings | |

> [!NOTE]
> Performing the device wipe:<ul><li>Does NOT format the drive, erase user data outside of the user profile, or clear the Trusted Platform Module (TPM).</li><li>The experience is different from the [Out of Box Experience](/windows-hardware/customize/desktop/customize-oobe) (OOBE) when users first turn on a new device. Since user profiles are maintained, the user is automatically presented with a Windows logon screen once Windows Recovery has been completed.</li></ul>

## Reuse the device

The preferred method when handing an existing device from one user to another is to reimage the device (by USB key or other deployment method). Reimaging ensures all user data from the previous user is removed and provides the new user with a clean Microsoft Managed Desktop enrollment experience.

There are two options for device reuse scenarios available to IT admins in Microsoft Managed Desktop:

- [Reimage the device](#reimage-the-device) (preferred)
- [Autopilot Reset](#autopilot-reset)

### Reimage the device

For imaging options, it’s best to utilize a [OEM image](../prepare/device-images.md) whenever possible for this scenario but for some cases where a non-OEM image is needed, the Microsoft Managed Desktop [universal image](../prepare/universal-image.md) may be an option.  

### Autopilot Reset

An alternative to reimaging a device is to use [Autopilot Reset](/mem/autopilot/windows-autopilot-reset).  

However, this option isn’t preferred to reimage the device because OEM pre-installed applications (for example, Microsoft 365 Apps for enterprise) aren't restored. Microsoft Office will need to be reinstalled post Windows Recovery using the Company Portal or Intune Application installation.

The following table describes:

- The information and files that are kept after Autopilot Reset.
- The information and files that aren't kept after Autopilot Reset.

| Kept after Autopilot Reset | Not kept after Autopilot Reset |
| ----- | ----- |
| User accounts associated with the device | User profiles |
| Machine state (domain join, Azure AD-joined) | User-installed apps (store and Win32 apps) |
| Mobile device management (MDM) enrollment | Non-default device settings |
| OEM pre-installed apps (store) | OEM pre-installed apps (Win32 apps) |

> [!IMPORTANT]
> BitLocker is a key component of data security in this process. With BitLocker encryption on Microsoft Managed Desktop devices, data on the drive remains secure even after the device has been factory-reset. Any data that was on the drive won't be available to the next user of the device. For more information, see [BitLocker overview](/windows/security/information-protection/bitlocker/bitlocker-overview).
