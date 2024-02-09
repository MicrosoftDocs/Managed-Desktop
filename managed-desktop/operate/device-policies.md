---
title: Device policies 
description: Learn about the default policies applied to Microsoft Managed Desktop devices.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
- essentials-manage
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.date: 12/06/2022
---

# Device policies

<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

When a new Microsoft Managed Desktop device is being set up, we ensure that the configuration is optimized Microsoft Managed Desktop.

The configuration includes a set of default policies that are set as part of the onboarding process. These policies are delivered using Mobile Device Management (MDM) whenever possible. For more information, see [Mobile Device Management](/windows/client-management/mdm/).

>[!NOTE]
>To avoid conflicts, do not alter these policies.

Devices will arrive with a signature image, and then join the Microsoft Entra domain when the first user signs in. The device will automatically install required policies and applications without any intervention from your IT personnel.

## Default policies

This table highlights the default policies that are applied to all Microsoft Managed Desktop devices during device provisioning. All detected changes to objects not approved by Microsoft Managed Desktop Operations Team and managed by Microsoft Managed Desktop will be reverted.

| Policy | Description
| ----- | ----- |
| Security baseline | [Microsoft security baseline](/windows/device-security/windows-security-baselines) for mobile device management is configured for all Microsoft Managed Desktop devices. This baseline is the industry-standard configuration. It's publicly released, well tested, and reviewed by Microsoft security experts to keep Microsoft Managed Desktop devices, and apps secure in the modern workplace. <br><br>To mitigate threats in the constantly evolving security threat landscape, the Microsoft security baseline will be updated, and deployed to Microsoft Managed Desktop devices with each Windows 10 feature update.<br><br>For more information, see [Windows security baselines](/windows/security/threat-protection/windows-security-baselines).
| Microsoft Managed Desktop recommended security template | This template is a set of recommended changes to the security baseline that optimizes the user experience. These changes are documented in [the Security Addendum](#security-addendum). Updates to the policy addendum occur on an as needed basis.  
| Update deployment | Use Windows Update for Business to perform gradual deployment of software updates. IT admins can't modify settings for the deployment group policies. For more information on group-based deployment, see [How updates are handled in Microsoft Managed Desktop](../operate/updates.md).
| Metered connections | By default, updates over metered connections (such as LTE networks) are turned off. Though, each user can independently turn on this setting by navigating to **Settings, then Updates, then to Advanced options**. <br><br>If you want to allow all users to enable updates over metered connections, [submit a change request](../operate/support-request.md), which will turn on this setting for all devices.
| Device compliance | These policies are configured for all Microsoft Managed Desktop devices. A device is reported as non-compliant when it drifts from our required security configuration.

## Windows diagnostic data

 Devices will be set to provide enhanced diagnostic data to Microsoft under a known commercial identifier. As part of Microsoft Managed Desktop, IT admins can't change these settings.

For customers in General Data Protection Regulation (GDPR) regions, users can reduce the level of diagnostic data that is provided, but there will be a reduction in service. For example, Microsoft Managed Desktop will be unable to collect the data necessary to iterate on settings and policies to best serve performance and security needs. For more information, see [Configure Windows diagnostic data in your organization.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## Security addendum

 This section outlines the policies that will be deployed in addition to the standard Microsoft Managed Desktop policies listed in [Default policies](#default-policies). This configuration is designed with financial services and highly regulated industries in mind, and optimized for the highest security while maintaining user productivity.

### Additional security policies

 These policies are added to increase security for highly regulated industries:

| Policy | Description |
| ----- | ----- |
|Security monitoring | Microsoft will monitor devices using [Microsoft Defender for Endpoint](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). If a threat is detected, Microsoft will notify the customer, isolate the device, and rectify the issue remotely. |
 | Disable PowerShell V2 | Microsoft removed PowerShell V2 in August 2017.<br><br>This feature has been disabled on all Microsoft Managed Desktop devices. For more information on this change, see [Windows PowerShell 2.0 Deprecation](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/). |
