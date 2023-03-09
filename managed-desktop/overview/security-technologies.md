---
title: Security and access management technologies
description:  Technologies used for device security, identity and access management, network security, and information security
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.collection: 
- M365-modern-desktop
- tier2
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.date: 03/10/2023
---

# Security and access management technologies

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop uses several Microsoft technologies to help secure managed devices and data. In addition, the Microsoft Managed Desktop Security Operations Center uses various [processes](../overview/security-operations.md#processes) with these technologies.Specifically:

| Process | Description |
| ------ | ------ |
| [Device security](#device-security)| Security and protection on Microsoft Managed Desktop devices. |
| [Identity and Access Management](#identity-and-access-management) | Managing secure use of devices through Azure Active Directory identity services. |
| [Network security](#network-security)| VPN information and Microsoft Managed Desktop recommended solution and settings. |
| [Information security](#information-security)| Optional available services to further protect sensitive information. |

For information about data storage, usage, and security practices used by Microsoft Managed Desktop, see [our whitepaper](https://aka.ms/mmd-data).

## Device security

Microsoft Managed Desktop ensures managed devices are secured and protected, and detects threats as early as possible using the following services:

| Service | Description |
| ----- | ----- |
| Antivirus | [Microsoft Defender Antivirus](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows) is installed and configured<br>Microsoft Defender Antivirus definitions are up to date. |
| Full volume encryption | Microsoft Managed Desktop uses Windows BitLocker as the volume encryption solution.<br><br>We offer XTS AES 128 system drive encryption with allowed exceptions for 256. By default, PIN/KEY isn't required, but [you can request for an exception](../operate/support-request.md). Removable media is set to encrypt AES CBC 128.  |
| Monitoring | [Microsoft Defender for Endpoint](/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) is used for security threat monitoring across all Microsoft Managed Desktop devices. Defender for Endpoint allows enterprise customers to detect, investigate, and respond to advanced threats in their corporate network. |
| Operating system updates | Microsoft Managed Desktop devices are always secured with the latest security updates. For more information, see [software update management](../operate/updates.md). |
| Secure Device Configuration | Microsoft Managed Desktop implements the Microsoft Security Baseline. For more information, see [Windows security baselines.](/windows/security/threat-protection/windows-security-baselines)|

## Identity and access management

Identity and access management protects corporate assets and business-critical data. Microsoft Managed Desktop configures devices to ensure secure use with Azure Active Directory (AD) managed identities. It's the customer's responsibility to maintain accurate information in their Azure AD tenant.

| Service | Description |
| ----- | ----- |
| Biometric Authentication | Microsoft Managed Desktop offers the configuration option to ensure secure authentication powered by [Windows Hello for Business](/windows-hardware/design/device-experiences/windows-hello). Windows Hello for Business offers biometric security which is stronger than username and password-based authentication. Customers are responsible for implementing the necessary prerequisites for their on-premises Azure Active Directory to use this service in a hybrid configuration. |
| Device profiles | To protect the system and make it more secure, the end user will be assigned one of the following [device profiles](../operate/device-profiles.md):<ul><li>Standard User</li><li>Power User</li><li>Sensitive Data User</li><li>[Kiosk](../operate/kiosk-device-profile.md)</li></ul><p>Device profiles are assigned as part of the Windows Autopilot out-of-box experience. |

## Network security

Customers are responsible for network security.

| Service | Description |
| ----- | ----- |
| VPN | Customers own their VPN infrastructure to ensure limited corporate resources can be exposed outside the intranet.<p>Microsoft Managed Desktop requires:<ul><li>Windows 10 compatible and supported VPN solution</li><li>The device must support Windows 10 and be packaged and deployable through Intune</li></ul></p><p>Contact your software publisher for more information.</p><p>Recommendations:<br><ul><li> Microsoft recommends a modern VPN solution that could be easily deployed through Intune to push VPN profiles. This approach provides an always-on, seamless, reliable, and secure way to access corporate network. For more information, see [VPN settings in Intune](/intune/vpn-settings-configure).</li><li>Thick VPN clients, or older VPN clients, aren't recommended by Microsoft while using Microsoft Managed Desktop as it can affect the user environment.</li><li>Microsoft recommends that the outgoing web traffic goes directly to the Internet without going through the VPN to avoid any performance issues.</li><li>Ideally, Microsoft recommends the use of Azure Active Directory App Proxy instead of a VPN.</li></ul></p>|

## Information security

You can configure these optional services to help protect high-value corporate assets.

| Service | Description |
| ----- | ----- |
| Data recovery | Information stored in key folders on the device is backed up to [OneDrive for Business](/sharepoint/introduction). Microsoft Managed Desktop is responsible for the secure functionality of the OneDrive client and its data sync towards OneDrive For Business back end in Microsoft 365 Apps. However, the actual data being secured isn’t the responsibility of the Microsoft Managed Desktop support teams. You must contact OneDrive support. |
| Windows Information Protection | For companies that require high levels of information security, we recommend [Windows Information Protection](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) and [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection) |
