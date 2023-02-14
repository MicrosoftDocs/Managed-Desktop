---
title: Kiosk device profile
description:  This article explains how to assign the Kiosk device profile on device
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
manager: dougeby
ms.topic: how-to
audience: Admin
ms.date: 11/18/2022
---

# Kiosk device profile

Microsoft Managed Desktop allows you to configure devices as kiosk devices that restrict Windows to run either:

- A single application (single-app) that runs full screen.
- Multiple, pre-defined applications (multi-app) that appear as start screen tiles on the desktop.

> [!IMPORTANT]
> Currently, multi-app kiosk is only supported on Windows 10. [Multi-app kiosk isn't supported on Windows 11](/windows/configuration/lock-down-windows-10-to-specific-apps).

Single-app kiosks are ideal for purpose-specific devices such as digital or interactive signage. Multi-app kiosks are appropriate for devices shared by multiple people and with few applications. You can have combinations of multiple single-app and multi-app Kiosk device profiles within your environment.

Kiosk devices are configured using the [AssignedAccess CSP configuration service provider](/windows/client-management/mdm/assignedaccess-csp). The policies are enforced system-wide when the assigned access kiosk configuration is applied on the device.

> [!NOTE]
> You'll need to [wipe a device](../operate/reset-devices-factory.md) or [reassign the device profile](../operate/change-device-profile.md) to remove all settings before a device is reassigned to a different user and/or assigned a different device profile. For more information, visit [Policies enforced on kiosk devices (Windows 10/11)](/windows/configuration/kiosk-policies).

The following high-level activities must be completed to enable kiosks for device management in Microsoft Managed Desktop. Administrators must:

1. Create kiosk configuration profiles that meet their operational and user experience needs.
1. Register or tag devices as kiosks with the service.
1. Assign devices with the newly created profiles.  

Microsoft Managed Desktop and the associated profile and tags will ensure that devices are kept up to date while respecting service windows and the lack of traditional interactive users and identities.  

## Step 1: Create kiosk configuration profiles in Microsoft Endpoint Manager  

Microsoft Endpoint Manager includes a kiosk configuration as a template to help you create and modify these single-app or multi-app kiosk configurations for your business needs. You can configure them with the following steps:

**To create the kiosk configuration profiles:**

1. Go to [Microsoft Endpoint Manager](https://endpoint.microsoft.com).
1. Go to Devices > Configuration Profiles > **+ Create Profile**.
    1. For the **Platform**, select **Windows 10 and Later**.
    2. For the **Profile Type**, select **Templates** and **Kiosk**.
    3. Select **Create**.
1. In the **Basic Settings** tab, enter the following information:
    1. **Name**: Provide a suitable profile name
    2. **Description**: Provide a suitable profile name
1. Select **Next**.
1. Select one of the following options:
    1. Single-app, full-screen kiosk
    2. Multi-app kiosk
1. Complete the required and desired configuration options based on the kiosk mode selected. For more information, see [kiosk settings for Windows 10/11 in Microsoft Intune](/mem/intune/configuration/kiosk-settings-windows).  
1. Select **Next**.
1. Assign the desired device groups to each configuration profile you created. Your kiosk device(s) registered with Microsoft Managed Desktop must also be a member of one of the device groups for each profile.

## Step 2: Register devices as kiosks in Microsoft Managed Desktop

For Microsoft Managed Desktop to fully manage devices, the devices must be registered. Microsoft Managed Desktop supports two device registration methods:

- [Manual registration for existing devices](../prepare/device-registration-overview.md#manual-registration) from the Microsoft Managed Desktop Devices blade.
- [Auto-registration](../prepare/device-registration-overview.md#auto-registration) using the kiosk Autopilot group tag.

| Device profile | Autopilot group tag (standard mode) |
| ----- | ----- |
| Kiosk device profile | Microsoft365Managed_Kiosk |

Microsoft Managed Desktop applies a standardized naming convention format, `Kiosk-%RAND:9%`, when devices are registered into the service. A [self-deploying Autopilot profile](/mem/autopilot/self-deploying) is assigned to all kiosk devices. The device will be automatically enrolled into Intune and joined to Azure Active Directory as part of the device registration process.

> [!NOTE]
> You'll need to [wipe a device](../operate/reset-devices-factory.md) or [reassign the device profile](../operate/change-device-profile.md) to remove all settings before a device is reassigned to a different user and/or assigned a different device profile. For more information, visit [Policies enforced on kiosk devices (Windows 10/11)](/windows/configuration/kiosk-policies).

## Step 3: Assign kiosk configuration profiles to devices or device groups

Once kiosk configuration profiles have been created and devices are assigned with the Kiosk device profile in Microsoft Managed Desktop, the Kiosk device profile must be assigned to devices or device groups.  

**To reassign the kiosk device profile:**

1. Go to [Microsoft Endpoint Manager](https://endpoint.microsoft.com).
1. Navigate to Devices > Microsoft Managed Desktop > **Devices**.
1. Find and select on the desired device(s).
1. In **Devices action**, select **Device Actions**.
1. For the **New device profile**, select **Kiosk Device Profile**.
1. Select **Change Profile**, and then select **Reset device**.

## Step 4: Optional. Create local users for Kiosk device profiles

If the user LogonType is Autologon, a local account is automatically created. This applies to each kiosk device where the user account will authenticate or sign into. The following instructions use OMA-URI and the [Accounts CSP](/windows/client-management/mdm/accounts-csp). Consult your security and IT architecture team for guidance.

> [!NOTE]
> Using the OMA-URI to configure a local account will store the password in the Azure portal as plain text.

**To create local users for kiosk device profiles:**

1. Go to [Microsoft Endpoint Manager](https://endpoint.microsoft.com).
1. Go to Devices > Configuration Profiles > **Create Profile**.
1. For the **Platform**, select **Windows 10 and Later**.
1. For the **Profile Type**, select **Templates and Custom**.
1. Select **Create**.
1. In the **Basic Settings** tab, enter the following information:
    1. **Name**: Provide a suitable profile name
    2. **Description**: Provide a suitable profile name
1. Select **Next**.
1. In the **Configuration settings** tab, select **Add**. Then, enter the following information:
    1. **Name***: Enter your username
    2. **Description**: Provide a suitable row description
    3. **OMA-URI***: `./Device/Vendor/MSFT/Accounts/Users/TestUser/Password`. `TestUser` is your username.
    4. **Data Type***: String
    5. **Value***: Any valid or preferred password
1. Select **Save**.
1. In the **Scope Tags** section, select **Next**.
1. In the **Assignment Tags** section, select **Next**.
1. In the **Applicability Rules** section, select **Next**.
1. In **Review + Create**, select **Create**.

## Add apps to the Enrollment Status Page

If there are applications you need for the full kiosk experience, you may add them to the [Modern Workplace Kiosk device profile Enrollment Status Page](../deploy/esp-first-run.md#enrollment-status-page-settings ) to meet your business needs.

For more information about best practices, see [Selecting required apps for your Enrollment Status Page](https://techcommunity.microsoft.com/t5/intune-customer-success/selecting-required-apps-for-your-enrollment-status-page/ba-p/2200381) to block only apps that are required for the full kiosk experience.

> [!IMPORTANT]
> Don't remove any Microsoft Managed Desktop applications included in the ESP (enrollment status page) configuration.

## Known issues

| Known issue | Description |
| ----- | ----- |
| Multi-app kiosk is only supported on Windows 10 | For more information, see Kiosks aren't supported on Windows 11](/windows/configuration/lock-down-windows-10-to-specific-apps). |
| Multiple monitors | The use of multiple monitors isn't supported for multi-app kiosk mode. |
| Unable to save the kiosk configuration profile, when the user logon type is Azure AD user or group. | This issue occurs when the selected Azure Active Directory user group has multiple users, and the application type is NOT the Microsoft Edge browser. The error **Unable to save due to invalid data. Update your data then try again. Single Fullscreen UWP app configuration accepts only one user or type Autologon, local user or Azure AD user** is displayed. |
| The configuration profile will report as "Error" when viewing within [Microsoft Endpoint Manager](https://endpoint.microsoft.com) | When using the [Accounts CSP](/windows/client-management/mdm/accounts-csp) to configure a local account on the device, the configuration profile will report as "Error" when viewing within [Microsoft Endpoint Manager](https://endpoint.microsoft.com), even when configured successfully and the account is created on the device. |
| Single-app kiosk and multi-app profiles may not apply accurately | Single-app kiosk and multi-app profiles may not apply accurately, or CSP displays errors when the User Logon Type is Azure AD Group, and the Azure AD group has multiple users. As a workaround, add **Select Logon type** as the **Azure AD user** or group, and add individual accounts to the list. |
| Microsoft Office apps don't launch in kiosk mode. | This issue occurs when there's a mismatch in the Application Model User ID(AUMID). Use the **Add Win 32 apps** option to configure apps. For more information on how to find the AUMID, see [Find the Application User Model ID of an installed app](/windows/configuration/find-the-application-user-model-id-of-an-installed-app). |

## Best practices

To add the latest Microsoft Edge browser to the multi-app kiosk configuration, Microsoft Edge must be included using the **Add Win32 app** option. Selecting the **Add Microsoft Edge** button will install the legacy Microsoft Edge browser.

## Fix Kiosk mode issues

| Issue | Workaround and/or information |
| ----- | ----- |
| General tips | For more information about general tips, see [Troubleshoot kiosk mode issues (Windows 10/11)](/windows/configuration/kiosk-troubleshoot). |
| Users are automatically signed out or can't sign into Windows 10 computers with the multi-app profile assigned | For more information, see [Users can't log on to Windows 10 computers with multi-app Kiosk device profile assigned](/troubleshoot/mem/intune/users-cannot-logon-windows-multi-app-kiosk). |
