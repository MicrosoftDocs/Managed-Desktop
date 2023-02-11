---
title: Software update management overview
description: This article describes how updates are managed in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
ms.date: 12/06/2022
---

# Software update management overview

<!--This topic is the target for a "Learn more" link in the admin center (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure.

Keeping your devices up to date is a balance of speed and stability. Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure to manage updates on your behalf. We use update groups to ensure operating system updates and policies are rolled out in a safe manner. For more information, see the video [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Updates released by Microsoft are cumulative and are categorized as quality or feature updates. For more information, see [Windows Update for Business: Update types](/windows/deployment/update/waas-manage-updates-wufb#update-types).

## Software update workloads

| Software update workload | Description |
| ----- | ----- |
| Windows quality update | Microsoft Managed Desktop uses four deployment rings to manage Windows quality updates. For more detailed information, see [Windows quality updates](../operate/windows-quality-update-overview.md). |
| Anti-virus definition | Updated with each scan. |
| Microsoft 365 Apps for enterprise | For more information, see [Microsoft 365 Apps for enterprise](../operate/m365-apps.md). |
| Microsoft Edge | For more information, see [Microsoft Edge](../operate/edge-browser-app.md). |
| Microsoft Teams | For more information, see [Microsoft Teams](../operate/teams.md). |

## Microsoft Managed Desktop deployment rings

During the [tenant enrollment process](/prepare/enroll-your-tenant.md), Microsoft Managed Desktop creates four Azure AD assigned groups that are used to segment devices into its update groups:

| Ring | Description |
| ----- | ----- |
| **Modern Workplace Devices - Test** | Deployment ring for testing update deployments prior production rollout.<p>The Test group is exempt from any established service level agreements and user support. It's best to move just a few devices at first and then review the user experience. Microsoft Managed Desktop won't automatically assign devices to this group. This group will only contain devices you specify.</p>|
| **Modern Workplace Devices - First** | First production deployment ring for early adopters.|
| **Modern Workplace Devices - Fast** | Fast deployment ring for quick rollout and adoption. |
| **Modern Workplace Devices - Broad** | Final deployment ring for broad rollout into the organization. |
| Automatic | Select Automatic when you want Microsoft Managed Desktop to automatically assign devices to one of the other groups.<p>We won't automatically assign devices to Test. If you want to release a device that you've previously specified so it can be automatically assigned again, select this option.</p> |

Each deployment ring has a different set of update deployment policies to control the updates rollout.

> [!WARNING]
> Adding or importing devices into any of these groups directly is not supported and doing so might cause an unexpected impact on the Microsoft Managed Desktop service. To move devices between these groups, see [Move devices in between deployment rings](../operate/updates.md#move-devices-in-between-deployment-rings).

> [!IMPORTANT]
> Microsoft Managed Desktop device registration doesn't assign devices to its test deployment ring (**Modern Workplace Devices - Test**). This is intended to prevent devices that are essential to a business from being affected or devices that are used by executives from receiving early software update deployments.

Also, during the [device registration process](../prepare/device-registration-overview.md), Microsoft Managed Desktop assigns each device being registered to one of its deployment rings so that the service has the proper representation of the device diversity across the organization in each deployment ring. The deployment ring distribution is designed to release software update deployments to as few devices as possible to get the signals needed to make a quality evaluation of a given update deployment.

> [!NOTE]
> You can't create additional deployment rings or use your own for devices managed by the Microsoft Managed Desktop service.

### Labels

The Group assigned by column contains the following labels:

| Label | Description |
| ----- | ----- |
| Admin | The device is in a group you've specified. |
| Auto | Microsoft Managed Desktop assigned the group. |
| Pending | The device is in the process of moving to a group. |

The **Group** column always shows the group the device is currently in and only updates when a move is complete.

### Deployment ring calculation logic

The Microsoft Managed Desktop deployment ring calculation happens during the [device registration process](../prepare/device-registration-overview.md) and it works as follows:

- If the Microsoft Managed Desktop tenant's existing managed device size is **≤ 200**, the deployment ring assignment is First **(5%)**, Fast **(15%)**, remaining devices go to the Broad ring **(80%)**.
- If the Microsoft Managed Desktop tenant's existing managed device size is **>200**, the deployment ring assignment will be First **(1%)**, Fast **(9%)**, remaining devices go to the Broad ring **(90%)**.

| Deployment ring | Default device balancing percentage | Description |
| ----- | ----- | ----- |
| Test | **zero** | Microsoft Managed Desktop doesn't automatically add devices to this deployment ring. You must manually add devices to the Test ring following the required procedure. For more information on these procedures, see [Move devices in between deployment rings](#move-devices-in-between-deployment-rings). The recommended number of devices in this ring, based upon your environment size, is as follows:<br><ul><li>**0–500** devices: minimum **one** device.</li><li>**500–5000** devices: minimum **five** devices.</li><li>**5000+** devices: minimum **50** devices.</li></ul>Devices in this group are intended for your IT Administrators and testers since changes are released here first. This release schedule provides your organization the opportunity to validate updates prior to reaching production users. |
| First |  **1%** | The First ring is the first group of production users to receive a change.<p><p>This group is the first set of devices to send data to Microsoft Managed Desktop and are used to generate a health signal across all end-users. For example, Microsoft Managed Desktop can generate a statistically significant signal saying that critical errors are trending up in a specific release for all end-users, but can't be confident that it's doing so in your organization.<p><p>Since Microsoft Managed Desktop doesn't yet have sufficient data to inform a release decision, devices in this deployment ring might experience outages if there are scenarios that weren't covered during early testing in the Test ring.|
| Fast | **9%** | The Fast ring is the second group of production users to receive changes. The signals from the First ring are considered as a part of the release process to the Broad ring.<p><p>The goal with this deployment ring is to cross the **500**-device threshold needed to generate statistically significant analysis at the tenant level. These extra devices allow Microsoft Managed Desktop to consider the effect of a release on the rest of your devices and evaluate if a targeted action for your tenant is needed.</p> |
| Broad | Either **80%** or **90%** | The Broad ring is the last group of users to receive software update deployments. Since it contains most of the devices registered with Microsoft Managed Desktop, it favors stability over speed in a software update deployment.|

## Move devices in between deployment rings

If you want to move separate devices to different deployment rings, after Microsoft Managed Desktop's deployment ring assignment, you can repeat the following steps for one or more devices from the **Ready** tab.

> [!IMPORTANT]
> If you change the assignment, policies that are specific to that group will be applied to the device. The change might install the latest version of Windows 10 (including any new feature or quality updates). It's best to move just a few devices at first and then check the resulting user experience. Be aware that certain updates will restart the device. Double-check that you've selected the right devices to assign. It can take up to 24 hours for the assignment to take effect.

**To move devices in between deployment rings:**

1. In the [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Devices** in the left pane.
2. In the **Microsoft Managed Desktop** section, select **Devices**.
3. In the **Ready** tab, select one or more devices you want to assign. All selected devices will be assigned to the deployment ring you specify.
4. Select **Device actions** from the menu.
5. Select **Assign device to ring**. A fly-in opens.
6. Use the dropdown menu to select the deployment ring to move devices to, and then select **Save**. The **Ring assigned by** column will change to **Pending**.

When the assignment is complete, the **Ring assigned by** column changes to **Admin** (which indicates that you made the change) and the **Ring** column shows the new deployment ring assignment.

> [!NOTE]
> You can only move devices to other deployment rings when they're in an active state in the **Ready** tab.<p>If you don't see the **Ring assigned by column** change to **Pending** in Step 5, check to see whether the device exists in Microsoft Intune or not by searching for it in its device blade. For more information, see [Device details in Intune](/mem/intune/remote-actions/device-inventory).
  
> [!WARNING]
> Moving devices between deployment rings through directly changing Azure AD group membership isn't supported and may cause unintended configuration conflicts within the Microsoft Managed Desktop service. To avoid service interruption to devices, use the **Assign device to ring** action described previously to move devices between deployment rings.
  
## Automated deployment ring remediation functions

Microsoft Managed Desktop monitors device membership in its deployment rings, except for the **Modern Workplace Devices - Test** ring, to provide automated deployment ring remediation functions to mitigate the risk of not having its managed devices being part of one of its deployment rings. These automated functions help mitigate risk of potentially having devices in a vulnerable state, and exposed to security threats in case they're not receiving update deployments due to either:

- Changes performed by the IT admin on objects created by the Microsoft Managed Desktop tenant enrollment process, or
- An issue occurred which prevented devices from getting a deployment rings assigned during the [device registration process](../prepare/device-registration-overview.md).

There are two automated deployment ring remediation functions:

| Function | Description |
| ----- | ----- |
| **Check Device Deployment Ring Membership** | Every hour, Microsoft Managed Desktop checks to see if any of its managed devices aren't part of one of the deployment rings. If, for some reason, a device isn't part of a deployment ring, Microsoft Managed Desktop randomly assigns the device to one of its deployment rings (except for the **Modern Workplace Devices - Test** ring). |
| **Multi-deployment ring device remediator:**| Every hour, Microsoft Managed Desktop checks to see if any of its managed devices are part of multiple deployment rings (except for the **Modern Workplace Devices - Test** ring). If, for some reason, a device is part of multiple deployment rings, Microsoft Managed Desktop randomly removes device of one or more deployment rings until the device is only part of one deployment ring.|

> [!IMPORTANT]
> Microsoft Managed Desktop automated deployment ring functions doesn't assign or remove devices to or from the **Modern Workplace Devices - Test** ring.

## Windows Insider Program

Microsoft Managed Desktop doesn't support devices that are part of the Windows Insider program.

The Windows Insider program is used to validate pre-release Windows software. It's intended for devices that aren't mission critical. While it's an important Microsoft initiative, it's not intended for broad deployment in production environments.

Any devices found with Windows Insider builds might be put into the Test group. These devices will be exempt from update service level agreements and user support from Microsoft Managed Desktop.

## Bandwidth management

We use [Delivery Optimization](/windows/deployment/update/waas-delivery-optimization) for all operating system and driver updates. Delivery Optimization minimizes the download size from the Windows Update service by seeking updates from peers within the corporate network.
