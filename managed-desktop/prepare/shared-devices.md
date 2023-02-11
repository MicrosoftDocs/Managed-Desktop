---
title: Register devices in shared device mode
description:  How and when to use shared device mode
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
ms.date: 12/06/2022
---

# Register devices in shared device mode

Microsoft Managed Desktop allows you to register devices in "shared device mode," similar to the shared device mode offered by [Microsoft Intune](/mem/intune/configuration/shared-user-device-settings). Shared device mode can be turned on when you select a device profile during the [device registration process](#turn-on-shared-device-mode).

Devices in this mode are optimized for situations where users aren't tied down to a single desk and are frequently changing devices. For example, frontline workers such as bank tellers or nursing staff. You can apply the Microsoft Managed Desktop [profiles](../operate/device-profiles.md) to devices in this mode. Devices registered in this mode have some important differences:

- [Device storage](#device-storage) is optimized for shared users.
- [Inactive accounts](#deletion-of-inactive-accounts) are deleted.
- [Guest accounts](#guest-accounts) aren't supported by default.
- [Microsoft 365 Applications](#microsoft-365-apps-for-enterprise) for enterprise licensing is optimized for shared devices.

Because you make the choice to use shared device mode at the point of registration in Microsoft Managed Desktop, if you want to change out of this mode later, you must deregister it and register it again.

## When to use shared device mode

Use shared device mode in situations where users are frequently changing devices.

For example, bank tellers might be in one location managing deposits, but move to a back office to help customers with a mortgage. In each of those locations, the device runs different applications and is optimized for those tasks, though they're used by multiple people.

Nursing staff typically move between rooms and offices as they interact with patients. They can sign into a workstation in an office, but connect to their remote desktop and take notes, and repeat this process in a different room with a different patient.

## When not to use shared device mode

Shared device mode isn't a good choice in these situations:

- When a user's files need to be stored locally rather than in the cloud.
- If the user experience needs to be different for different users on the device.
- If the set of applications each user needs differs greatly.

## Turn on shared device mode

There are three ways to turn on shared device mode when registering devices:

1. [Partner registration](../prepare/partner-registration.md)
1. [Manual registration for new devices](../prepare/manual-registration.md)
1. [Windows Autopilot registration from Microsoft Endpoint Manager](../prepare/windows-autopilot-registration.md)

## Consequences of shared device mode

### Device storage

Users of shared devices must have their data backed up onto the cloud so it can follow them to other devices. Once you've registered devices in shared device mode, be sure to enable OneDrive's [Files On-Demand](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e#:~:text=%20Turn%20on%20Files%20On-Demand%20%201%20Make,files%20as%20you%20use%20them%20box.%20More%20) and [known-folder redirection](/onedrive/redirect-known-folders) features. This approach minimizes the effect that each user profile has on device storage. Devices in shared device mode automatically delete user profiles if the free disk space drops below 25%. This activity is scheduled for midnight at the device's local time, unless storage becomes critically limited.

Microsoft Managed Desktop uses the [SharedPC](/mem/intune/configuration/shared-user-device-settings-windows) CSP to do these operations, so make sure you don't use those CSPs yourself.

> [!IMPORTANT]
> Train your users that after they have downloaded a large file they should confirm that they see the green check icon on the file before they sign out. If their account gets deleted as part of the cleanup operations and the file isn't completely uploaded in OneDrive, the file will be permanently lost.

### Deletion of inactive accounts

Shared device mode removes any accounts that haven't been signed into for more than 30 days.

### Guest accounts

Devices in shared device mode only allow accounts that are joined to a domain. If you need guest accounts on a device, you can file a [change request](../operate/support-request.md) to request them to be enabled.

### Microsoft 365 Apps for enterprise

[Microsoft 365 Apps for enterprise](../operate/m365-apps.md) typically allows a given user to install those apps on only five devices at the same time. In shared device mode, the apps don't count against the limit, so they can use them while roaming between devices. Deployment and updates of Microsoft 365 Apps for enterprise work as usual.

### Device profiles

In shared device mode, you can have only one [device profile](../operate/device-profiles.md) on a given device. Also, the Power user device profile isn't currently supported in shared device mode.

### Apps and policies assigned to users

On shared devices, you should assign any apps or policies that you're managing yourself to *device groups*, not user groups. Assigning to device groups ensures that each user has a more consistent experience. The exception is [Company Portal](#deploying-apps-with-company-portal).

## Limitations of shared device mode

### Windows Hello

Windows Hello uses smart card emulation to securely [cache user PINs](/windows/security/identity-protection/hello-for-business/hello-faq), minimizing the number of times users have to authenticate. However, Windows only allows 10 smart cards at a time on a given device. When an 11th user signs in for the first time, one of the existing accounts will lose their smart card. They'll be able to sign in, but their PIN won't be cached.

### Universal print

When Universal print installs a printer for a single user on a shared device that printer becomes available to all users of that device. There's no way to isolate printers between users on shared devices.

### Deploying apps with Company Portal

Some apps probably don't need to be present on all devices, so you might prefer that users only install those apps when they need them from [Company Portal](/mem/intune/user-help/install-apps-cpapp-windows).

Microsoft Managed Desktop disables Company Portal by default for devices in shared device mode. If you want the Company Portal enabled, you can file a [change request](../operate/support-request.md). However, you should be aware of some limitations in this feature:

- To make an app available to users in Company Portal, [assign a user group](/mem/intune/apps/apps-deploy) to that app in Intune and then add each user to that user group.
- To uninstall an app that a user installed through Company Portal, you must uninstall the app from all users on that device.

> [!CAUTION]
> Company Portal doesn't support applications assigned to device groups as available.

### Redeployment of Microsoft 365 Apps for Enterprise

If Microsoft 365 Apps must be redeployed, users must contact their local support staff to request an agent elevate and reinstall Microsoft 365 Apps for enterprise on that device.

### Microsoft Teams

When a user starts Teams for the first time, they'll be prompted to update the app before they can use it. Once they allow the update, Teams will keep itself updated in the background.
