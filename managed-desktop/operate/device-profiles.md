---
title: Understand device profiles
description:  This article explains the various profiles that admins can assign to devices
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
ms.topic: conceptual
audience: Admin
ms.date: 12/06/2022
---

# Device profiles

You can think of device profiles as being part of a hierarchy of device configuration options.

:::image type="content" source="../media/mmd-profile-options-heirarchy.png" alt-text="Device configurations shown as a pyramid. Description follows.":::

| Device configuration options | Description
| ----- | ----- |
| Your configurations | At the top are your own configurations, such as network details or applications. A device can have any number of these configurations, which aren't managed or blocked by Microsoft Managed Desktop. |
| Customizations | The next higher level is more [customizations](../overview/exceptions-to-service-plan.md). Each device can have one or more (or no) customizations. The customizations can either:<ul><li>Modify a lower-level layer (device profiles or the foundational configuration) or</li><li>Be an entirely new request that's layered on top of the standard configuration.</li></ul> |
| Device profiles | Every Microsoft Managed Desktop device must have one, and only one, profile assigned. Admins can select which profile a device is assigned.<br><br>You can assign different pre-set profiles to devices. Each profile is optimized for the needs of specific types of users. Three device profiles are available:<ul><li>Standard</li><li>Sensitive Data</li><li>Power user</li><li>[Kiosk](kiosk-device-profile.md)</li></ul> |
| Foundation | Fundamentally, every Microsoft Managed Desktop device has a foundation that includes:<br><ul><li>Standard security baseline</li><li>Compliance policies</li><li>Windows Update settings</li><li>Groups</li></ul><br>To work with Microsoft Managed Desktop, every device must include all of these elements. These elements can't be changed by admins. You must submit a request to Microsoft Managed Desktop. |

## Device profile details

The following table summarizes the settings and their default values for each setting configured by device profiles. Behind the scenes, these settings are configured with OMA-URIs by using Custom Configuration Profiles in Microsoft Endpoint Manager.

<br>

****

| Feature | Sensitive Data | Power User | Standard | Kiosk |
| ----- | ----- | ----- | ----- | ----- |
|**Block External Storage**| Yes | Yes | No | Yes |
|**[Cloud Block Level](/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel)**| High | High | High | High |
|**Disable Microsoft Accounts**| Yes | Yes | No | Yes |
|**Disable personal OneDrive**| Yes | Yes | No | Yes |
|**[Switch to secure desktop for elevation](/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-useraccountcontrol-switchtothesecuredesktopwhenpromptingforelevation)**| No | Yes | No | No |
|**Microsoft Defender for Endpoint Device Tag**| M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard | M365Managed-Kiosk |
|**Admin on the device?**| No | Yes | No | No |
|**Autopilot Profile**| Modern Workplace Autopilot Profile | Modern Workplace Autopilot Profile Power User | Modern Workplace Autopilot Profile | [Modern Workplace Autopilot Profile Kiosk](kiosk-device-profile.md) |
|**AppLocker**| Yes | No | No | No |
|**Block Public Store**| Yes | Yes | No | Yes |

Each device profile also involves these items:

- A dynamic membership Azure Active Directory device group.
- A static membership Azure Active Directory device group.
- A Microsoft Endpoint Manager Configuration profile.

> [!IMPORTANT]
> Don't modify the membership of these groups directly. Use the interface as described in [Reassign profiles](../operate/change-device-profile.md).

## Limitations

You can request exceptions to the device profiles and their details as you would with any other policy.

You can only have one of each device profile in your Azure Active Directory organization ("tenant"). For example, you can't request that the Sensitive data device profile disables AppLocker for only some of your users. All devices with the sensitive data device profile must have the same configuration.

Each device can only have one profile. If a given device is used by more than one user, all users on that device will have the same configuration.

## Export admin CSV

Devices that are assigned the [Power user device profile](#device-profile-details) also include user(s) in the administrator group. As an IT admin, you can download and view all users and groups assigned to the local administrators group.  

**To export the CSV file:**

1. In [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), select **Devices** in the left pane.
2. In the **Microsoft Managed Desktop** section, select **Devices**.
3. Select the **Export** menu option and select **Export admins**. A CSV file is downloaded.

The CSV includes:

- Information retrieved from all devices that have been active in the last 28 days.
- Data that's refreshed once a day at midnight. The content is refreshed every 24 hours.
- The device profile names and can be filtered for Power user device profiles.
- Members of the local administrators' group that include Azure Active Directory groups, the group will include a (G) suffix. Disabled accounts will include a (D) suffix.
- Some data that will appear as GUIDs. Data that appears as GUIDs is because we're unable to determine the usernames. We only gather the usernames as displayed on the local device.
