---
title: Windows Autopilot registration from the Microsoft Endpoint Manager portal
description:  This article describes how to register devices using the Windows Autopilot deployment profile in the Microsoft Endpoint Manager portal
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
---

# Windows Autopilot registration from the Microsoft Endpoint Manager portal

Whether you or a partner are handling device registration, you can choose to use the [Windows Autopilot self-deploying mode](/mem/autopilot/self-deploying) profile in Microsoft Managed Desktop.

## Before you begin

Review the Windows Autopilot self-deploying mode requirements:

> [!IMPORTANT]
> You cannot automatically re-enroll a device through Autopilot after an initial deployment in self-deploying mode. Instead, delete the device record in the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431). To delete the device record from the admin center, select **Devices** > **All devices** > select the devices you want to delete > **Delete**.  For more information, see [Updates to the Windows Autopilot sign-in and deployment experience](https://techcommunity.microsoft.com/t5/intune-customer-success/updates-to-the-windows-autopilot-sign-in-and-deployment/ba-p/2848452).

### Trusted Platform Module

Self-deploying mode uses a device's TPM 2.0 hardware to authenticate the device into an organization's Azure Active Directory tenant. Therefore, devices without TPM 2.0 can't use this mode. Devices must also support TPM device attestation. All new Windows devices should meet these requirements. The TPM attestation process also requires access to a set of HTTPS URLs that are unique for each TPM provider. For more information, see the entry for Autopilot self-deploying mode and Autopilot pre-provisioning in [Networking requirements](/mem/autopilot/self-deploying#requirements). For more information about Windows Autopilot software requirements, see [Windows Autopilot software requirements](/mem/autopilot/software-requirements).

> [!TIP]
> If you attempt to deploy self-deploying mode on a device that doesn't have TPM 2.0 support or it's on a virtual machine, the process will fail when verifying the device with the following error: 0x800705B4 timeout error (Hyper-V virtual TPMs are not supported). Also note that Windows 10 version 1903 or later is required to use self-deploying mode due to issues with TPM device attestation in Windows 10 version 1809. Since Windows 10 Enterprise 2019 LTSC is based on Windows 10 version 1809, self-deploying mode is also not supported on Windows 10 Enterprise 2019 LTSC.
>
> For more information about other known issues and review solutions, see [Windows Autopilot known issues](/mem/autopilot/known-issues) and [Troubleshoot Autopilot device import and enrollment](/mem/autopilot/troubleshoot-device-enrollment).

## Steps to register devices using the Windows Autopilot self-deploying mode profile

If you're registering devices yourself, you must import new devices into the Windows Autopilot Devices blade.

**To import new devices into the Windows Autopilot Devices blade:**

1. Collect the [hardware hash](../get-started/manual-registration.md#obtain-the-hardware-hash) for new devices you want to assign the Windows Autopilot Self-deployment mode profile to.
2. Go to the [Microsoft Endpoint Manager portal](https://endpoint.microsoft.com).
3. Select **Devices** from the left navigation menu.
4. In the **By platform** section, select **Windows**. Then, select **Windows Enrollment**.
5. In the **Windows Autopilot Deployment Program** section, select **Devices**.
6. [Import](../get-started/manual-registration.md#register-devices-by-using-the-admin-portal) the .CSV file containing all hardware hashes collected in step #1.
7. After you've uploaded the Windows Autopilot devices, you must edit the imported devices' group tag attribute so Microsoft Managed Desktop can register them using the Windows Autopilot self-deploying mode profile. See below for the group tag attributes. You must append **-Shared** to the group tag, as shown in the following table:

| Device profile | Autopilot group tag (standard mode) | Group tag (shared device mode) |
| ----- | ----- | ----- |
| Sensitive data | Microsoft365Managed_SensitiveData |  Microsoft365Managed_SensitiveData-Shared |
| Power user | Microsoft365Managed_PowerUser | Not supported |
| Standard  | Microsoft365Managed_Standard | Microsoft365Managed_Standard-Shared |

**To manually register devices from the Microsoft Managed Desktop devices blade:**

1. Collect the [hardware hash](../get-started/manual-registration.md#obtain-the-hardware-hash) for new devices.
2. Go to the [Microsoft Endpoint Manager portal](https://endpoint.microsoft.com) and select **Devices** in the left navigation pane.
3. In the **Microsoft Managed Desktop** section, select **Devices**.
4. In the **Microsoft Managed Desktop Devices** workspace, select **+ Register devices**. A fly-in menu opens to register new devices.
5. In the **File upload** box, provide the path to the CSV file you created previously.
6. Select a **[device profile](../service-description/profiles.md)** from the dropdown menu and turn on the **Shared device** toggle.
7. Select **Register devices**. The system will add the devices to your list of devices. If successful, the device will show as **Ready for user** meaning it's ready and waiting for a user to start using. For more information on see [Manual registration](../get-started/manual-registration.md).
8. The **Shared Device** column will be marked with **Yes**.

If you have a partner that enrolls devices, follow the steps in [Partner registration](../get-started/partner-registration.md), but append **-Shared** to the group tag, as shown in the preceding table.

> [!WARNING]
> Don't try to edit the group tab attribute by appending **-Shared** to devices previously imported to Windows Autopilot. Devices already imported into Windows Autopilot, using one of the Microsoft Managed Desktop group tags starting with **Microsoft365Managed_**, but without **-Shared** initially appended, are already part of a different Azure Active Directory group. This Azure Active Directory group doesn't have the Windows Autopilot self-deploying mode profile assigned to it. If you must re-purpose an existing device to be a shared device, you must delete and reregister the device into Windows Autopilot again.
