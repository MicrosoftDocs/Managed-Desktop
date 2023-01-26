---
title: Device names and request device name changes
description: How Microsoft Managed Desktop manages device names
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.date: 12/06/2022
---

# Device names

Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.

For these services to work together seamlessly, devices need consistent, standardized names. Microsoft Managed Desktop applies the following standardized name formats when devices are enrolled:

- `MMD-%RAND:11`
- `[Kiosk-%RAND:9%](profiles.md#device-profile-details)`(for devices with the [Kiosk device profile](../operate/kiosk-device-profile.md) assigned)

Windows Autopilot assigns these names. For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../deploy/esp-first-run.md).

## Automated name changes

If a device is renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format. This process occurs every four hours. The name change takes place the next time the user restarts the device.

## Request device name change

> [!IMPORTANT]
> If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.

If you must keep the name dependency, you can submit a request through the [admin center](../operate/support-request.md) to disable the renaming function and use your desired name format.
