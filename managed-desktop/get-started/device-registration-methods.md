---
title: Device registration in Microsoft Managed Desktop 
description:  Information on the device registration methods in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
msreviewer: andredm7
---

# Device registration

Microsoft Managed Desktop must register either existing or new devices into its service so it can fully manage devices on your behalf.

When you register your devices, the Microsoft Managed Desktop service will fully manage updates for those devices. Today Microsoft Managed Desktop supports two device registration methods:

- [Auto-registration](#auto-registration)
- [Manual registration from the Microsoft Managed Desktop devices blade](#manual-registration)

Whether you choose to use auto or manual registration, the overall device registration process is:

:::image type="content" source="../media/device-registration/device-registration-overview.png" alt-text="Overview of the device registration process" lightbox="../media/device-registration/device-registration-overview.png":::

1. Register devices by:
    1. Auto-registration:
        1. When using auto-registration, a partner uploads devices into the Windows Autopilot service on your behalf via either Partner Center or OEM APIs.
        2. You can also upload a .CSV file in the Windows Autopilot devices blade yourself, which is also considered an auto-registration method for Microsoft Managed Desktop as it’s outside its devices blade.
    2. Manual registration:
        1. When using manual registration, register devices into the Microsoft Managed Desktop Devices blade.
2. Assign devices into Microsoft Managed Desktop’s Windows Autopilot deployment profiles using the OrderID/Intune group tag.
3. Register devices to Microsoft Managed Desktop’s deployment group distribution.
4. Assign devices to the Microsoft Managed Desktop’s deployment groups.
5. Assign devices to the Microsoft Managed Desktop’s device configuration profiles.
6. Ship devices to end-users.
7. End-user logs in and starts their workday.

See the [Device registration workflow diagram](#device-registration-workflow-diagrams) section for more detail on what happens behind the scenes of the device registration process.

## Device registration prerequisites

See [device requirements](../service-description/device-requirements.md) to review both hardware and software-based requirements when registering devices with Microsoft Managed Desktop.

## Device name convention

Microsoft Managed Desktop applies a standardized naming convention format, `MMD-%RAND11`, when devices are registered into the service.

> [!IMPORTANT]
> If you must keep your own device naming convention, you can submit an exception request through the [admin center](../working-with-managed-desktop/admin-support.md) to disable both the Microsoft Managed Desktop device naming convention, and Microsoft Managed Desktop’s device rename function. The device rename function automatically renames devices when they don’t match the naming convention every four hours.

## Auto-registration

Any device registration that occurs outside the Microsoft Managed Desktop’s devices blade is considered an auto-registration method. There are also different ways to register devices with Microsoft Managed Desktop within the auto-registration method:

- [Partner center](partner-registration.md#register-devices-using-the-partner-center)
- [OEM API](partner-registration.md#register-devices-by-using-the-oem-api)
- [Registration in the Windows Autopilot devices blade](windows-autopilot-registration.md)

## Manual registration

Any device registration that originated from the Microsoft Managed Desktop's Devices blade is considered to be a manual registration method. This process is very similar to the Windows Autopilot’s manual registration process where you utilize a .CSV file containing the devices you want to register with the Microsoft Managed Desktop service.

The manual registration methods are:  

- [Manual registration for new devices](manual-registration.md)
- [Manual registration for existing devices](manual-registration-existing-devices.md)

## Device registration workflow diagrams

### Detailed auto-registration workflow diagram

See the following high-level overview workflow diagram. The diagram covers the auto-registration process in Microsoft Managed Desktop:

:::image type="content" source="../media/device-registration/auto-registration-high-level-workflow-diagram.png" alt-text="Detailed auto-registration workflow diagram" lightbox="../media/device-registration/auto-registration-high-level-workflow-diagram.png":::

#### Auto-registration workflow diagram steps

| Step | Description |
| ----- | ----- |
| **Step 1: Gather hardware hashes** | Partner, OEM, or IT admin gather hardware hashes for devices that need to be registered. |
| **Step 2: Build .CSV file** | Partner, OEM, or IT admin builds the .CSV file containing the following information:<ol><li>All hardware hashes for devices that need to be registered.</li><li>A Microsoft Managed Desktop-specific Intune group tag per device. The group tags are:</li><ol><li>**Microsoft365Managed_Standard**</li><li>**Microsoft365Managed_SensitiveData**</li><li>**Microsoft365Managed_PowerUser**</li></ol><li>The breakdown of the Intune group tag string in Microsoft Managed Desktop:</li><ol><li>The "**Microsoft365Managed**" section of the group tag string means the devices must be managed by the Microsoft Managed Desktop service.</li><li>The "**_Standard/SensitiveData/PowerUser**" section of the group tag string means the device must registered into Microsoft Managed Desktop using one of its default device configuration profiles (either Standard, SensitiveData, or Power User).</li><ol><li>Each registered device must be assigned to one of the Microsoft Managed Desktop's default device configuration profiles. **Adding multiple device configuration profiles as par of the Intune group tag string isn't supported.**</li></ol><li>**Optional**. You can also append **-Shared** to the end of the Intune group tag string when you want to register a [shared device](../service-description/shared-devices.md) with Microsoft Managed Desktop. For example, **Microsoft365Managed_Standard-Shared**, or **Microsoft365Managed_SensitiveData-Shared**). **The Power User device configuration profile isn't supported**.<ol><li>Two things happen when "**-Shared**" is appended to the end of the Intune group tag string:</li><ol><li>Microsoft Managed Desktop adds these devices into an Azure AD group that has the Windows Autopilot deployment profile with Shared devices assigned. Microsoft Managed Desktop applies the Windows Autopilot self-deploying mode settings when these devices go through the Windows Out-of-the-Box-Experience.</li><li>Microsoft Managed Desktop adds these devices into the Azure AD group that receives the Shared device mode configuration profile with the Shared device mode settings in Microsoft Endpoint Manager-Intune once users go through the Windows Out-of-the-Box-Experience.</li></ol></ol> |
| **Step 3: Upload the .CSV file** | Partner, OEM, or IT admin uploads the .CSV file into either via Partner center, using OEM APIs or through the Windows Autopilot Devices blade in the Microsoft Endpoint Manager portal. |
| **Step 4: Check for assigned devices** | Microsoft Managed Desktop has a function that checks for assigned devices in all three Microsoft Managed Desktop Windows Autopilot profiles every hour.<ol><li>The three Windows Autopilot Deployment profiles supported in Microsoft Managed Desktop are:</li><ol><li>**Modern Workplace Autopilot Profile**</li><li>**Modern Workplace Autopilot Profile Power User**</li><li>**Modern Workplace Autopilot Profile Shared**</li></ol><li>If there are newly added devices, these devices are added into the Microsoft Managed Desktop shipped device record database.</li><li>Microsoft Managed Desktop flags the device(s) with the status **Registration pending** in the **Devices** blade.</li></ol> |
| **Step 5: Compare device registration request records** | Another Microsoft Managed Desktop function compares device registration request records originating from its device blade against both its shipped, and managed device records in the Microsoft Managed Desktop database. This function runs every hour.<p>If there are devices that are part of the shipped device records but don’t have a device registration request record originating from its Devices blade, Microsoft Managed Desktop proceeds with registering this device in its service.</p> |
| **Step 6: Run device deployment group assignment algorithm** | Microsoft Managed Desktop runs its device deployment group assignment calculation algorithm to determine which deployment group to assign the devices to. For more information, see [Device deployment groups](/managed-desktop/service-description/deployment-groups). |
| **Step 7: Assign devices to deployment groups and other Azure AD groups to devices** | Microsoft Managed Desktop assigns the deployment group to devices and assigns other Azure AD groups to devices.<ol><li>Microsoft Managed Desktop deployment groups are made of four Azure AD groups that devices get assigned to during the device registration process:</li><ol><li>**Modern Workplace Devices-First**</li><li>**Modern Workplace Devices-Fast**</li><li>**Modern Workplace Devices-Broad**</li></ol><li>Other Azure AD groups that are assigned to devices in this step are:<ol><li>**Modern Workplace Devices-All**</li><li>**Modern Workplace Devices - Shared Device Mode** (this is in case the device was registered by Partner, OEM or, IT admin with -Shared appended one of the Intune group tags used by Microsoft Managed Desktop.</li></ol></ol> |
| **Step 8: Assign device configuration profiles to devices** | Microsoft Managed Desktop assigns the device configuration profiles to devices. For more information, see [Device profiles](/managed-desktop/service-description/profiles). The device configuration profiles are defined as:<ol><li>**Standard**</li><li>**Sensitive data**</li><li>**Power User**</li></ol> |
| **Step 9: Validate devices** | Microsoft Managed Desktop validates whether devices are part of the assigned devices in one of the Windows Autopilot Deployment profiles described in **step #4**.<p>If a device is part of one of the Windows Autopilot Deployment profiles created by Microsoft Managed Desktop in your tenant, Microsoft Managed Desktop flags the device as **Ready for User** in the Devices blade for the IT admin. Partners and OEM don’t have access to the Microsoft Managed Devices blade.</p> |
| **Step 10: Ship the device to the end-user** | Partners, OEM, or IT admin ship the device to the end-user. |
| **Step 11: End-user receives device** | The end-user receives the device and turns the device on and runs through the Windows Out-Of-Box-Experience. |
| **Step 12: End-user logs in** | Once the device runs through the Out-Of-Box-Experience steps, the end-user logs in with their corporate credentials. |
| **Step 13: Create Microsoft Endpoint Manager-Intune device record** | The Microsoft Endpoint Manager-Intune device record is created. |
| **Step 14: Deliver apps, configuration profiles and other settings** | Microsoft Endpoint Manager-Intune starts delivering apps, device configuration profiles and other settings Microsoft Managed Desktop applies to your devices.<p>The number of apps assigned is listed in the Windows Autopilot Enrollment Status Page. End-users can start using their devices because Intune installs apps and applies settings in the background. This is the end of the workflow for the end-user.</p> |
| **Step 15: Flag devices** | Microsoft Managed Desktop flags devices with the Active status in the **Devices** blade. |
| **Step 16: Confirm Active devices** | IT admin confirms that the devices now show up as **Active** in Microsoft Managed Desktop’s **Device** blade. |
| **Step 17: End of registration workflow** | This is the end of the auto-registration process. |

### Detailed manual registration workflow diagram

The following is the high-level overview workflow diagram that covers the manual device registration process in Microsoft Managed Desktop:

:::image type="content" source="../media/device-registration/manual-registration-high-level-workflow-diagram.png" alt-text="Detailed manual registration workflow diagram" lightbox="../media/device-registration/manual-registration-high-level-workflow-diagram.png":::

#### Manual registration workflow diagram steps

| Step | Description |
| ----- | ----- |
| **Step 1: Build .CSV file** | IT admin builds the .CSV file containing the following information. All hardware hashes for devices that need to be registered. |
| **Step 2: Log into the Microsoft Endpoint Manager portal** | IT admins log into the **Microsoft Endpoint Manager portal**.<ol><li>In the left pane, select **Devices**.</li><li>Navigate to **Microsoft Managed Desktop** section, then select **Devices**.</li><li>In the **Devices** blade, select **Register Devices** to upload the .CSV file containing hardware hashes for devices to be registered.</li><li>IT admins select the Microsoft Managed Desktop’s device configuration profiles:</li><ol><li>**Standard**</li><li>**Sensitive**</li><li>**Power user**</li></ol><li>**Optional**. You can use the toggle to switch to **[Shared device mode](../service-description/shared-devices.md)**. Then, select **Register devices** when you want to register a Shared device with Microsoft Managed Desktop. **The Power User device configuration profile isn't supported**.</li><ol><li>Two things happen when you turn on **Shared device mode**:</li><ol><li>Microsoft Managed Desktop adds these devices into an Azure AD group that has the Windows Autopilot deployment profile with Shared assigned. Microsoft Managed Desktop applies the Windows Autopilot self-deploying mode settings when these devices go through the Windows Out-of-the-Box-Experience.</li><li>Microsoft Managed Desktop adds these devices into the Azure AD group that receives the Shared device mode configuration profile with the Shared device mode settings in Microsoft Endpoint Manager-Intune once users go through the Windows Out-of-the-Box-Experience.</li></ol></ol> |
| **Step 3: Microsoft Managed Desktop API does the following:** |<ol><li>Reads all hardware hashes from the .CSV file.</li><li>Creates an Intune group tag based on the IT admin’s Microsoft Managed Desktop’s device configuration profile’s selection.</li><li>Sends a device registration request to the Microsoft Managed Desktop function app responsible for performing all the steps to register devices in the service.</li><li>Flags devices with **Registration pending** status in the Devices blade.</li></ol> |
| **Step 4: Function app makes Graph API call** | **Microsoft Managed Desktop’s function app is responsible for the device registration process**. The app makes an Intune Graph API call to register devices with the Windows Autopilot service. |
| **Step 5: Windows Autopilot creates device records** | The **Windows Autopilot service** creates device records in its database based on the .CSV list imported by IT admin in Microsoft Managed Desktop’s **Devices** blade. |
| **Step 6: Intune service makes Azure AD Graph API call** | The **Intune service** makes an Azure AD Graph API call to create Azure AD device records for devices being registered in Microsoft Managed Desktop. |
| **Step 7: Azure AD service creates Azure AD device records** | The **Azure AD service** creates the necessary Azure AD device records. |
| **Step 8: Azure AD service links device record** | The **Azure AD service** links its device record to the Windows Autopilot device records using its OrderID with the Intune group tag mapping. |
| **Step 9: Azure AD service returns device ID records** | The **Azure AD service** returns its respective device ID records to Intune. |
| **Step 10: Azure AD service assigns devices to Windows Autopilot deployment profile** | The **Azure AD service** also assigns devices to Windows Autopilot deployment profile based on the initial selection made by the IT admin when uploading devices into the Microsoft Managed Desktop’s **Devices** blade. |
| **Step 11: Intune service saves Azure AD device ID records** | The **Intune service** saves the Azure AD device ID records associated with its Windows Autopilot device records in its database. |
| **Step 12: Intune service sends device records** | The **Intune service** sends out both Windows Autopilot and Azure AD device records back to the **Microsoft Managed Desktop service**. |
| **Step 13: Run device deployment group assignment algorithm** | Microsoft Managed Desktop runs its device deployment group calculation algorithm to determine which deployment group to assign to devices to. For more information, see [Device deployment groups](/managed-desktop/service-description/deployment-groups). |
| **Step 14: Assign devices to deployment groups and other Azure AD groups to devices** | Assigns Microsoft Managed Desktop groups to devices and assigns other groups Azure AD groups to devices.<ol><li>Microsoft Managed Desktop deployment groups are made of four Azure AD groups which devices get assigned to during the device registration process:</li><ol><li>**Modern Workplace Devices-First**</li><li>**Modern Workplace Devices-Fast**</li><li>**Modern Workplace Devices-Broad**</li></ol><li>Other Azure AD groups that are assigned to devices in this step are:<ol><li>**Modern Workplace Devices-All**</li><li>**Modern Workplace Devices - Shared Device Mode** (this is in case the device was registered by Partner, OEM or, IT admin with **-Shared** appended one of the Intune group tags used by Microsoft Managed Desktop).</li></ol></ol> |
| **Step 15: Assign device configuration profiles to devices** | Microsoft Managed desktop assigns device configuration profiles to devices. For more information, see [Device profiles](/managed-desktop/service-description/profiles) for more details. The device configuration profiles are:<ol><li>**Standard**</li><li>**Sensitive data**</li><li>**Power User**</li></ol> |
| **Step 16: Validate devices** | Microsoft Managed Desktop validates whether devices are part of the assigned devices in one of the Windows Autopilot Deployment profiles.<ol><li>Microsoft Managed Desktop checks for assigned devices in all three Microsoft Managed Desktop Windows Autopilot profiles every hour.</li><li>The three Windows Autopilot Deployment profiles supported in Microsoft Managed Desktop are:<ol><li>**Modern Workplace Autopilot Profile**</li>**Modern Workplace Autopilot Profile Power User**</li><li>**Modern Workplace Autopilot Profile Shared**</li></ol><li>If there are newly added devices, these devices are added into the Microsoft Managed Desktop shipped device record database.</li></ol> |
| **Step 17: Flag device as Ready for User** | If a device is part of one of the Windows Autopilot Deployment profiles created by Microsoft Managed Desktop in your tenant, flags the device as **Ready for User** in the **Devices** blade for the IT admin. Partners and OEM don’t have access to the Microsoft Managed Devices blade. |
| **Step 18: Ship the device to the end-user** | IT admin ships the device to the end-user. |
| **Step 19: End-user receives device** | The end-user receives the device and turns the device on and runs through the Windows Out-Of-Box-Experience. |
| **Step 20: End-user logs in** | Once the device runs through the Out-Of-Box-Experience steps, the end-user logs in with their corporate credentials. |
| **Step 21: Create Microsoft Endpoint Manager-Intune device record** | The Microsoft Endpoint Manager-Intune device record is created. |
| **Step 22: Deliver apps, configuration profiles and other settings** | Microsoft Endpoint Manager-Intune starts delivering apps, device configuration profiles and other settings Microsoft Managed Desktop applies to your devices.<p>The number of apps assigned is listed in the Windows Autopilot Enrollment Status Page. End-users can start using their devices because Intune installs apps and applies settings in the background. This is the end of the workflow for the end-user.</p> |
| **Step 23: Flag devices** | Microsoft Managed Desktop flags devices with the Active status in the **Devices** blade. |
| **Step 24: Confirm Active devices** | IT admin confirms that the devices now show up as **Active** in Microsoft Managed Desktop’s **Device** blade. |
| **Step 25: End of registration workflow** | This is the end of the manual device registration process. |

## Steps to get started with Microsoft Managed Desktop

1. Access [admin portal](access-admin-portal.md).
1. [Add and verify admin contacts in the Admin portal](add-admin-contacts.md).
1. [Adjust settings after enrollment](conditional-access.md).
1. Deploy and assign the [Intune Company Portal](company-portal.md).
1. [Assign licenses](assign-licenses.md).
1. [Deploy apps](deploy-apps.md).
1. [Prepare devices](prepare-devices.md).
1. Set up [first-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).
1. [Turn on user support features](enable-support.md).
1. [Get your users ready to use devices](get-started-devices.md).
1. [Get started with app control](get-started-app-control.md).
