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
msreviewer: andredm7
---

# Manual Windows Autopilot device registration outside the Microsoft Managed Desktop Devices blade

You can also register devices with Microsoft Managed Desktop by manually registering devices with the Windows Autopilot service either in the Microsoft Endpoint Manager portal (Windows Autopilot devices blade) or using the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.

When you register a device with Microsoft Managed Desktop outside its device blade, this device registration method is considered an auto device registration method since the device registration request wasn't originated in Microsoft Managed Desktop's device blade.

## Before you begin

Review the [Windows Autopilot software requirements](/mem/autopilot/software-requirements).

Whether you or a partner are handling device registration, you can choose to use the [Windows Autopilot self-deploying mode](/mem/autopilot/self-deploying) profile in Microsoft Managed Desktop. If planning to use the Windows Autopilot self-deploying mode, review the self-deploying mode requirements:

### Trusted Platform Module

Self-deploying mode uses a device's TPM 2.0 hardware to authenticate the device into an organization's Azure Active Directory tenant. Therefore, devices without TPM 2.0 can't use this mode. Devices must also support TPM device attestation. All new Windows devices should meet these requirements. The TPM attestation process also requires access to a set of HTTPS URLs that are unique for each TPM provider. For more information, see the entry for Autopilot self-deploying mode and Autopilot pre-provisioning in [Networking requirements](/mem/autopilot/self-deploying#requirements). For more information about Windows Autopilot software requirements, see [Windows Autopilot software requirements](/mem/autopilot/software-requirements).

> [!TIP]
> If you attempt to deploy self-deploying mode on a device that doesn't have TPM 2.0 support or it's on a virtual machine, the process will fail when verifying the device with the following error: 0x800705B4 timeout error (Hyper-V virtual TPMs are not supported). Also note that Windows 10 version 1903 or later is required to use self-deploying mode due to issues with TPM device attestation in Windows 10 version 1809. Since Windows 10 Enterprise 2019 LTSC is based on Windows 10 version 1809, self-deploying mode is also not supported on Windows 10 Enterprise 2019 LTSC.
>
> For more information about other known issues and review solutions, see [Windows Autopilot known issues](/mem/autopilot/known-issues) and [Troubleshoot Autopilot device import and enrollment](/mem/autopilot/troubleshoot-device-enrollment).

## Steps to register devices in the Microsoft Endpoint Manager-Intune portal

When registering devices yourself, you must import new devices into the Windows Autopilot Devices blade.

**To import new devices into the Windows Autopilot Devices blade:**

1. Collect the [hardware hash](../get-started/manual-registration.md#obtain-the-hardware-hash) for new devices you want to assign the Windows Autopilot Self-deployment mode profile to.
2. Go to the [Microsoft Endpoint Manager portal](https://endpoint.microsoft.com).
3. Select **Devices** from the left navigation menu.
4. In the **By platform** section, select **Windows**. Then, select **Windows Enrollment**.
5. In the **Windows Autopilot Deployment Program** section, select **Devices**.
6. [Import](../get-started/manual-registration.md#manually-register-devices-in-the-microsoft-managed-desktop-devices-blade) the .CSV file containing all hardware hashes collected in step #1.
7. If not adding the group tag column in the .CSV file, after you've uploaded the Windows Autopilot devices, you must edit the imported devices' group tag attribute so Microsoft Managed Desktop can register them in its service.

See the following table for the group tag attributes. If you're planning on deploying Shared mode devices, you must append **[-Shared](../service-description/shared-devices.md)** to the group tag, as shown in the following table:

| Device profile | Autopilot group tag (standard mode) | Group tag (shared device mode) |
| ----- | ----- | ----- |
| Sensitive data | Microsoft365Managed_SensitiveData |  Microsoft365Managed_SensitiveData-Shared |
| Power user | Microsoft365Managed_PowerUser | Not supported |
| Standard  | Microsoft365Managed_Standard | Microsoft365Managed_Standard-Shared |

If you have a partner that enrolls devices, follow the steps in [Partner registration](../get-started/partner-registration.md).

> [!WARNING]
> When registering Shared devices, don't try to edit the group tab attribute by appending **-Shared** to devices previously imported to Windows Autopilot. Devices already imported into Windows Autopilot, using one of the Microsoft Managed Desktop group tags starting with **Microsoft365Managed_**, but without **-Shared** initially appended, are already part of a different Azure Active Directory group. This Azure Active Directory group doesn't have the Windows Autopilot self-deploying mode profile assigned to it. If you must re-purpose an existing device to be a shared device, you must delete and reregister the device into Windows Autopilot again.

## Register devices with Windows Autopilot service using PowerShell script

You can also register devices with Microsoft Managed Desktop when you register devices with the Windows Autopilot service using the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.

### Get-WindowsAutoPilotInfo parameters

The following parameters can be used:

| Parameter | Description |
| ----- | ----- |
| -Name | The names of the computers. These can be provided via the pipeline such as the property name or one of the available aliases, DNSHostName, ComputerName, and Computer). |
| -OutputFile |The name of the .CSV file to be created with the details for the computers. If not specified, the details will be returned to the PowerShell pipeline. |
| -Append | Switch to specify that new computer details should be appended to the specified output file, instead of overwriting the existing file. |
| -Credential | Credentials that should be used when connecting to a remote computer (not supported when gathering details from the local computer). |
| -Partner | Switch to specify that the created .CSV file should use the schema for the Partner Center (using serial number, make, and model). |
| -GroupTag | An optional tag value that should be included in the .CSV file that is intended to be uploaded via Intune (not supported by the Partner Center or Microsoft Store for Business). |
| -AssignedUser | An optional value specifying the UPN of the user to be assigned to the device. This can only be specified for Intune (not supported by the Partner Center or Microsoft Store for Business). |
| -Online | Add computers to Windows Autopilot via the Intune Graph API. |
| -AssignedComputerName | An optional value that specifies the computer name to be assigned to the device. This can only be specified with the **-Online** switch and only works with Azure AD join scenarios. |
| -AddToGroup | Specifies the name of the Azure AD group that the new device should be added to. |
| -Assign | Wait for the Autopilot profile assignment. This can take a while for dynamic groups. |
| -Reboot | Restart the device after the Autopilot profile has been assigned. If specified, it's necessary to download the profile and apply the computer name. |

### Using Get-WindowsAutopilotInfo.ps1

1. Open a Windows PowerShell prompt with administrative rights.
2. You must install the PowerShell script, run the following command: `Install-script -name Get-WindowsAutoPilotInfo`, then accept all changes.
3. Once script is installed, you must set the PowerShell script execution policy, run the following command: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned`.
4. Run `Get-WindowsAutopilotInfo.ps1` with the parameters you need to use from the list described in the [Get-WindowsAutoPilotInfo parameters](#get-windowsautopilotinfo-parameters) section. You must run the script from the folder it was installed in (step #2).
5. You must sign into your **Azure Global Administrator** account and accept permission requests when assigning users, adding devices, and adding devices to groups.

Example:

`.\Get-WindowsAutopilotInfo.ps1 -AssignedUser user@contoso.com -GroupTag Microsoft365Managed_SensitiveData -Online`

> [!IMPORTANT]
> You must have a device rename exception request with the Microsoft Managed Desktop Service Engineering team if you plan on using the **-AssignedComputerName** parameter. For more information, see [Admin support for Microsoft Managed Desktop](/managed-desktop/working-with-managed-desktop/admin-support).
