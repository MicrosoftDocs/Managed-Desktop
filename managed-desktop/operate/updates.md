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
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
---

# Software update management overview

<!--This topic is the target for a "Learn more" link in the admin center (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop connects all devices to a modern cloud-based infrastructure.

Keeping Windows, Office, drivers, firmware, and Microsoft Store for Business applications up to date is a balance of speed and stability. We use update groups to ensure operating system updates and policies are rolled out in a safe manner. For more information, see the video [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Updates released by Microsoft are cumulative and are categorized as quality or feature updates. For more information, see [Windows Update for Business: Update types](/windows/deployment/update/waas-manage-updates-wufb#update-types).

## Update groups

Microsoft Managed Desktop uses four Azure AD groups to manage updates:

| Group | Description |
| ------ | ------ |
| Test | Used to validate Microsoft Managed Desktop policy changes, operating system updates, feature updates, and other changes pushed to the Azure AD organization ("tenant"). The Test group is: <br><ul><li>Best for testing or users who can provide early feedback.</li><li>Exempt from any established service level agreements and user support.</li><li>Available to validate compatibility of applications with new policy or operating system changes.</li></ul> |
| First | Contains early software adopters and devices that could be subject to pre-release updates. <br><br> Devices in this group might experience outages if there are scenarios that weren't covered during testing in the Test group. |
| Fast | Prioritizes speed over stability. The Fast group is: <br><ul><li>Useful for detecting quality issues before they're offered to the Broad group.</li> <li>The next layer of validation, and is typically more stable than the Test and First groups.</li></ul> |
| Broad | This group is the last group to have feature and quality updates available. <br><br> The Broad group contains most of users in the Azure AD organization, and therefore favors stability over speed in deployment. Testing of apps should be done with this group because the environment is the most stable. |

### Moving devices between update groups

You might want some devices to receive updates last and others that you want to go first. To move these devices into the appropriate update group, see [Assign devices to a deployment group](../operate/assign-deployment-group.md).

For more information on roles and responsibilities within these deployment groups, see [Microsoft Managed Desktop Roles and responsibilities](../overview/roles-and-responsibilities.md)

### Using Microsoft Managed Desktop update groups

There are parts of the service that you manage, like app deployment, where it might be necessary to target all managed devices.

## Update deployment

Below describes how update deployment works.

| Step | Description |
| ------ | ------ |
| Step 1 | Microsoft Managed Desktop deploys a new feature or quality update according to the schedule specified in the following [table](#deployment-settings).|
| Step 2 | During deployment, Microsoft Managed Desktop monitors for signs of failure, or disruption based on diagnostic data and the user support system. If any are detected, we immediately pause the deployment to all current and future groups.<p>For example, if an issue is discovered while deploying a quality update to the First group, the update deployments to First, Fast, and Broad groups will be paused until the issue is mitigated. For more information, see [Release management](#release-management).</p><p> You can report compatibility issues by [submitting a support request](support-request.md) in the Microsoft Managed Desktop admin center.</p><p>Feature and quality updates are paused independently. The pause is in effect for 35 days by default. However, it can be reduced or extended depending on whether the issue is mitigated.</p> |
| Step 3 | Once the groups are unpaused, deployment resumes according to the schedule in the following [table](#deployment-settings). |
| Step 4| Users are empowered to respond to restart notifications for a set period. This period is known as the deadline, and it's measured from the time the update is offered to the device. <br><br> During this time, the device will only automatically restart outside active hours. After this period expires, the deadline has been reached and the device will restart at the next available opportunity, regardless of active hours. <br><br> The deadline for quality updates is three days; for feature updates it's five days. |

> [!NOTE]
> This deployment process applies to both feature and quality updates, though the timeline varies for each.

## Deployment settings

Update deployment settings listed below:

| Update type | Test | First | Fast | Broad |
| ------ | ------ | ------ | ------ | ------ |
| Quality updates for operating system | Zero days | One day | Six days | Nine days |
| Feature updates for operating system | Zero days | 30 days | 60 days | 90 days |
| Drivers/firmware | Follows the schedule for quality updates. | Follows the schedule for quality updates. | Follows the schedule for quality updates. | Follows the schedule for quality updates. |
| Anti-virus definition | Updated with each scan. | Updated with each scan. | Updated with each scan. | Updated with each scan. |
| Microsoft 365 Apps for Enterprise | [Learn more](../operate/m365-apps.md#updates-to-microsoft-365-apps) | [Learn more](../operate/m365-apps.md#updates-to-microsoft-365-apps) | [Learn more](../operate/m365-apps.md#updates-to-microsoft-365-apps) | [Learn more](../operate/m365-apps.md#updates-to-microsoft-365-apps) |
| Microsoft Edge | [Learn more](../operate/edge-browser-app.md#updates-to-microsoft-edge) | [Learn more](../operate/edge-browser-app.md#updates-to-microsoft-edge) | [Learn more](../operate/edge-browser-app.md#updates-to-microsoft-edge) | [Learn more](../operate/edge-browser-app.md#updates-to-microsoft-edge) |
| Microsoft Teams | [Learn more](../operate/teams.md#updates) | [Learn more](../operate/teams.md#updates) | [Learn more](../operate/teams.md#updates) | [Learn more](../operate/teams.md#updates) |

>[!NOTE]
>These deferral periods are intentionally designed to ensure high security and performance standards for all users.<br><br> Based on data gathered across all Microsoft Managed Desktop devices and the varying scope and impact of updates, Microsoft Managed Desktop reserves flexibility to modify the length of the above deferral periods for any and all deployment groups on an ad hoc basis.
>
>Microsoft Managed Desktop conducts an independent assessment of each Windows feature release to evaluate its necessity and usefulness to its managed tenants. Consequently, Microsoft Managed Desktop might or might not deploy all Windows feature updates.

## Release management

In the Release management blade, you can:

1. Track the Windows quality update schedule for devices in the [four deployment groups](../operate/deployment-groups.md).
1. Review release announcements and knowledge based articles for regular and Out of Band (OOB) Windows quality updates.
1. Turn off expedited Windows quality updates.

### Release management tabs

The following tabs are available in the Release management blade.

| Tab | Description |
| ----- | ----- |
| Release schedule | For each [deployment group](../operate/deployment-groups.md), the Release schedule tab contains:<ul><li>The status of the update. Releases will appear as **Active**. The update schedule is based on the values of the [Windows 10 Update Ring policies](/mem/intune/protect/windows-update-for-business-configure), which have been configured on your behalf.</li><li>The date the update is available.</li><li>The target completion date of the update.</li></ul><p>In this tab, you can either **Pause** and/or **Resume** a Windows quality update release.</p><p>There are **two** types of paused quality updates, **Service Paused** and **Customer Paused**.<ul><li>**Service Paused**: If the Microsoft Managed Desktop service has paused an update, the release will have the **Service Paused** status. You must submit a [support request](../operate/support-request.md) to resume the update.</li><li>**Customer Paused**: If you've paused an update, the release will have the **Customer Paused** status. The Microsoft Managed Desktop service can't overwrite a customer-initiated pause. You must select **Resume** to resume the update.</li></ul>|
| Release announcements | View knowledge base (KB) articles corresponding to deployed out of band (OOB) and regular Windows quality updates.<br><p>**To view deployed Out of Band quality updates:**<ol><li>Go to [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) > **Devices** > **Microsoft Managed Desktop** > **Release management**.</li><li>Under the **Release Announcements** tab, you can view the knowledge base (KB) articles corresponding to deployed OOB and regular Windows quality updates.</li></ol></p><p>Announcements will be **removed** from the Release announcements tab when the next quality update is released. Further, if quality updates are paused for a deployment group, the OOB updates will also be paused.</p> |
| Release settings | Microsoft Managed Desktop assesses threat and vulnerability information on an ongoing basis throughout the release cycle.<p>By default, the service expedites quality updates as needed. For those organizations seeking greater control, you can disable expedited quality updates for Microsoft Managed Desktop-enrolled devices using Microsoft Intune.</p><p>**To turn off expedited quality updates:**</p><ol><li>Go to [**Endpoint Manager admin center**](https://endpoint.microsoft.com/#view/Microsoft_Intune_DeviceSettings/TenantAdminMenu/~/managedDesktopServiceRequests) > **Devices**.</li><li>Under **Microsoft Managed Desktop** > **Release management** > **Release settings** tab > Turn off the **Expedited Quality Updates** setting.</li></ol></p> |

## Windows Insider Program

Microsoft Managed Desktop doesn't support devices that are part of the Windows Insider program.

The Windows Insider program is used to validate pre-release Windows software. It's intended for devices that aren't mission critical. While it's an important Microsoft initiative, it's not intended for broad deployment in production environments.

Any devices found with Windows Insider builds might be put into the Test group. These devices will be exempt from update service level agreements and user support from Microsoft Managed Desktop.

## Bandwidth management

We use [Delivery Optimization](/windows/deployment/update/waas-delivery-optimization) for all operating system and driver updates. Delivery Optimization minimizes the download size from the Windows Update service by seeking updates from peers within the corporate network.
