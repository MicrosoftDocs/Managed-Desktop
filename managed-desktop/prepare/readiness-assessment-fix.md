---
title: Fix issues found by the readiness assessment tool
description:  Detailed actions to take for each issue the tool finds
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
audience: Admin
ms.date: 03/17/2023
---

# Fix issues found by the readiness assessment tool

For each check, the tool will report one of four possible results:

| Result  | Meaning |
| ----- | ----- |
| Ready | No action is required before completing enrollment. |
| Advisory | Follow the steps in the tool or this article for the best experience with enrollment and for users. <br><br> You *can* complete enrollment, but you must fix these issues before you deploy your first device. |
| Not ready | **Enrollment will fail if you don't fix these issues.** <br><br> Follow the steps in the tool or this article to resolve them. |
| Error | The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check or your tenant isn't properly licensed for Microsoft Intune. |

> [!NOTE]
> The results reported by this tool reflect the status of your settings only at the time that you ran it. If you make changes later to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready." To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you add or change any policies.

## Microsoft Intune settings

Access the Intune settings in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

### Autopilot deployment profile

You shouldn't have any existing Autopilot profiles that include or target-assigned or dynamic groups with Microsoft Managed Desktop devices. Microsoft Managed Desktop uses Autopilot to configure new devices. If you have an existing Autopilot deployment profile, the **Convert all targeted devices to Autopilot** setting must be set to **No** for the Microsoft Managed Desktop Autopilot readiness test to succeed.

| Result  | Meaning |
| ----- | ----- |
| Not ready | You have an Autopilot profile that is assigned to all devices. <br><br> For more information, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot). After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices - All** Azure AD group.
| Advisory | Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices. <br><br> For more information, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot). After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices - All** Azure AD group. |

### Certificate connectors

If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors shouldn't have any errors. Only one of the following advisories will apply to your situation. Check the advisories carefully.

| Result  | Meaning |
| ----- | ----- |
| Advisory | No certificate connectors are present. It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices. <br><br> For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](../prepare/certs-wifi-lan.md). |
| Advisory | At least one certificate connector has an error. If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error. <br><br> For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](../prepare/certs-wifi-lan.md). |
| Advisory | You have at least one certificate connector, and no errors are reported. However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices. <br><br> For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](../prepare/certs-wifi-lan.md). |

### Company Portal

Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.

| Result  | Meaning |
| ----- | ----- |
| Advisory | You don’t have the Company Portal application available in your tenant. Microsoft Managed Desktop will add it to your tenant when enrolling into the service, or [you can get the Company Portal from Intune using the Microsoft Store Integration](/mem/intune/apps/store-apps-microsoft). |

### Conditional Access policies

Conditional Access policies can't prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.

| Result  | Meaning |
| ----- | ----- |
| Not ready | You have at least one Conditional Access policy that targets all users. <br><br> During enrollment, we'll attempt to exclude Microsoft Managed Desktop service accounts from relevant Conditional Access policies and apply new Conditional Access policies to restrict access to these accounts. However, if we're unsuccessful, this can cause errors during your enrollment experience. For best practice, create an assignment that targets a specific Azure AD group that doesn't include Microsoft Managed Desktop service accounts. <br><br> After enrollment, you can review the Microsoft Managed Desktop Conditional Access policy in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). For more about these service accounts, see [Standard operating procedures](../overview/standard-operating-procedures.md). |
| Advisory | You have Conditional Access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service. <br><br> During enrollment, we'll exclude Microsoft Managed Desktop service accounts from relevant Conditional Access policies and apply new Conditional Access policies to restrict access to these accounts. <br><br> For more information about these service accounts, see [Standard operating procedures](../overview/standard-operating-procedures.md). |
| Error | The Intune Administrator role doesn't have sufficient permissions for this check. You'll also need to have these Azure AD roles assigned to run this check: <ul><li>Security Reader</li><li>Security Administrator</li><li>Conditional Access Administrator</li><li>Global Reader</li><li>Devices Administrator</li></ul>

### Device Compliance policies

Intune Device Compliance policies in your Azure AD organization might affect Microsoft Managed Desktop devices.

| Result  | Meaning |
| ----- | ----- |
| Advisory | You have at least one compliance policy that applies to all users. Microsoft Managed Desktop also includes compliance policies that will apply to your Microsoft Managed Desktop devices. Review all of the compliance policies created by your organization that apply to Microsoft Managed Desktop devices to ensure there are no conflicts. <br><br> For more information, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy). |

### Device Configuration profiles

Intune Device Configuration profiles in your Azure AD organization can't target any Microsoft Manage Desktop devices or users.

| Result  | Meaning |
| ----- | ----- |
| Not ready | You have at least one configuration profile that applies to all users, all devices, or both. Reset the profile to apply to a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices. <br><br> For more information, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure). |
| Advisory | Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users. <br><br> For more information, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure). |

### Device type restrictions

Microsoft Managed Desktop devices must be allowed to enroll in Intune.

| Result  | Meaning |
| ----- | ----- |
| Not ready | You currently have **at least** one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune. <br><br> Follow the steps in [Set enrollment restrictions](/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**. You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**. |

### Enrollment Status Page

You currently have the Enrollment Status Page (ESP) enabled. If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item. For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../deploy/esp-first-run.md).

| Result  | Meaning |
| ----- | ----- |
| Not ready | You have the ESP default profile set to **Show app and profile configuration progress**. <br><br> Disable this setting or ensure that assignments to any Azure AD group don't include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status). |
| Advisory | Make sure that any profiles that has the **Show app and profile configuration progress** setting aren't assigned to any Azure AD group that includes Microsoft Managed Desktop devices. <br><br> For more information, see [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status). |

### Multi-factor authentication

Multi-factor authentication shouldn't prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.

| Result  | Meaning |
| ----- | ----- |
| Not ready | You have some multi-factor authentication policies set as **required** for Conditional Access policies that are assigned to all users. <br><br> During enrollment, we'll exclude Microsoft Managed Desktop service accounts from relevant Conditional Access policies and apply new Conditional Access policies to restrict access to these accounts. <br><br> For more information about these service accounts, see [Standard operating procedures](../overview/standard-operating-procedures.md). |
| Advisory | You have multi-factor authentication required on Conditional Access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service. <br><br> During enrollment, we'll exclude Microsoft Managed Desktop service accounts from relevant Conditional Access policies and apply new Conditional Access policies to restrict access to these accounts. For more information about these service accounts, see [Standard operating procedures](../overview/standard-operating-procedures.md). |
| Error | The user running the readiness assessment doesn't have sufficient permissions for this check. You must have the following Azure AD roles assigned to run this check: <ul><li>Security Reader</li><li>Security Administrator</li><li>Conditional Access Administrator</li><li>Global Reader</li><li>Devices Administrator</li></ul>

### PowerShell scripts

Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.

| Result  | Meaning |
| ----- | ----- |
| Advisory | Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users. Don't assign a PowerShell script to target all users, all devices, or both. Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users. <br><br> For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension). |

### Region

Your region must be supported by Microsoft Managed Desktop.

| Result  | Meaning |
| ----- | ----- |
| Not ready | Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop. <br><br> For more information, see [Microsoft Managed Desktop supported regions and languages](../overview/regions-languages.md). |
| Advisory | One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop. <br><br> For more information, see [Microsoft Managed Desktop supported regions and languages](../overview/regions-languages.md). |

### Security baselines

Security baseline policies shouldn't target any Microsoft Managed Desktop devices.

| Result  | Meaning |
| ----- | ----- |
| Not ready | You have a security baseline profile that targets all users, all devices, or both. Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices. <br><br> For more information, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines). During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices. After enrollment, you can review the Microsoft Managed Desktop security baseline policy in the **Configuration policy** area of the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). |
| Advisory | Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices. For more information, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines). <br><br> During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices. The **Modern Workplace Devices - All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop. You'll have to come back to exclude this group after enrollment. |

### Unlicensed admins

This setting must be enabled to avoid a "lack of permissions" error when we interact with your Azure AD organization.

| Result  | Meaning |
| ----- | ----- |
| Not ready | **Allow access to unlicensed admins** should be enabled. For more information, see [Prerequisites for guest accounts](../prepare/guest-accounts.md). |

### Windows apps

Review apps you want your Microsoft Managed Desktop users to have.

| Result  | Meaning |
| ----- | ----- |
| Advisory | You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have. Since these apps must be deployed by Intune, evaluate reusing existing Intune apps. Consider using Company Portal (see [Install the Intune Company Portal on devices](../prepare/company-portal.md) and Enrollment Status Page (ESP) to distribute apps to your users. <br><br> For more information, see [Apps in Microsoft Managed Desktop](../prepare/apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](../deploy/esp-first-run.md). <br><br> You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment. |

### Windows Hello for Business

Microsoft Managed Desktop requires Windows Hello for Business to be enabled.

| Result  | Meaning |
| ----- | ----- |
| Advisory | Windows Hello for Business is either disabled or not set up. Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy). |

### Windows 10 and later update rings

Your Windows 10 and later update ring policy in Intune must not target any Microsoft Managed Desktop devices.

| Result  | Meaning |
| ----- | ----- |
| Not ready | You have an "update ring" policy that targets all devices, all users, or both. Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices. <br><br> For more information, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure). |
| Advisory | Make sure that any update ring policies you have exclude the **Modern Workplace Devices - All** Azure AD group. If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace - All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group). <br><br> For more information, see [Manage Windows 10 and 11 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure). Both the **Modern Workplace Devices - All** and **Modern Workplace - All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop. You'll have to come back to exclude this group after enrollment. |

## Azure Active Directory settings

You can access Azure Active Directory settings in the [Azure portal](https://portal.azure.com).

### Intune enrollment

Windows 10 and later devices in your Azure AD organization must be able to automatically enroll in Intune.

| Result  | Meaning |
| ----- | ----- |
| Advisory | Make sure the **MDM User scope** is set to **Some** or **All**, not **None**. <br><br> If you choose **Some**, come back after enrollment and select the **Modern Workplace - All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users. <br><br> For more information, see [Set up enrollment for Windows devices using Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment). |

### Ad-hoc subscriptions

Advises how to check a setting that, if set to "false", might prevent Enterprise State Roaming from working correctly.

| Result  | Meaning |
| ----- | ----- |
| Advisory | Ensure that **AllowAdHocSubscriptions** is set to **True**. Otherwise, Enterprise State Roaming might not work. <br><br> For more information, see [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings). |

### Enterprise State Roaming

Enterprise State Roaming should be enabled.

| Result  | Meaning |
| ----- | ----- |
| Advisory | Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups. <br><br> For more information, see [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable). |

### Guest Invitation settings

Microsoft Managed Desktop recommends adjusting Guest Invitation settings, since the default setting allows all users and guests in your directory to invite guests.

| Result  | Meaning |
| ----- | ----- |
| Advisory | **Member users and users assigned to specific admin roles can invite guest including guests with member permissions** should be enabled. <br><br> For more information, see [Prerequisites for guest accounts](../prepare/guest-accounts.md). |

### Guest User access

Microsoft Managed Desktop recommends adjusting guest access, since the default setting allows all guest in your directory to have the same access as members.

| Result  | Meaning |
| ----- | ----- |
| Advisory | **Guest Users have limited access to properties and memberships of directory objects** should be enabled. <br><br> For more information, see [Prerequisites for guest accounts](guest-accounts.md). |

### Licenses

Many licenses are required to use Microsoft Managed Desktop.

| Result  | Meaning |
| ----- | ----- |
| Not Ready | Valid and sufficent licenses are required to operate, configure and consume Microsoft Managed Desktop services.<br><br>For more information, see [Microsoft Managed Desktop technologies](../overview/operating-system.md) and [More about licenses](../prepare/prerequisites.md#more-about-licenses). |

### Microsoft Managed Desktop service accounts

Existing account names could conflict with account names created by Microsoft Managed Desktop to manage the Microsoft Managed Desktop service.

| Result  | Meaning |
| ----- | ----- |
| Not ready | You have at least one account name that will conflict with account names created by Microsoft Managed Desktop. Work with your Microsoft account representative to exclude these account names. We don't list the account names publicly to minimize security risk.

### Security administrator roles

Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.

| Result  | Meaning |
| ----- | ----- |
| Advisory | If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint. Otherwise, administrators with these roles won't be able to access the admin center. <ul><li>Security Operator</li><li>Global Reader</li></ul> <br> For more information, see [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).

### Security default

Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.

| Result  | Meaning |
| ----- | ----- |
| Not ready | You have Security defaults turned on. Turn off Security defaults and set up Conditional Access policies. <br><br> For more information, see [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common). |

### Self-service Password Reset

Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts. <br><br> For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](/azure/active-directory/authentication/tutorial-enable-sspr).

| Result  | Meaning |
| ----- | ----- |
| Advisory | Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users, but excludes Microsoft Managed Desktop service accounts. Microsoft Managed Desktop service accounts can't work as expected when SSPR is enabled. |

### Standard user role

By default, Microsoft Managed Desktop users will be "standard users" without local administrator privileges. Users will be effectively assigned a standard user role via the Microsoft Managed Desktop Standard User Device Profile upon successful enrollment.

| Result  | Meaning |
| ----- | ----- |
| Advisory | Microsoft Managed Desktop users won't have local administrator privileges on their Microsoft Managed Desktop devices after enrolling. |

## Microsoft 365 Apps for enterprise

### OneDrive

The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop. You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).

| Result  | Meaning |
| ----- | ----- |
| Advisory | You're using the **Allow syncing only on PCs joined to specific domains** setting. This setting won't work with Microsoft Managed Desktop. Disable this setting. Instead, set up OneDrive to use a Conditional Access policy. <br><br> For more information, see [Plan a Conditional Access deployment](/azure/active-directory/conditional-access/plan-conditional-access) for help. |
