---
title: Adjust settings after enrollment
description:  How to exclude certain Microsoft accounts
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier2
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.date: 12/06/2022
---

# Adjust settings after enrollment

After you've completed enrollment in Microsoft Managed Desktop, some management settings might need to be adjusted. To check and adjust if needed, follow these steps:

1. Review the Microsoft Intune and Azure Active Directory settings described in the next section.
2. If any of the items apply to your environment, make the adjustments as described.

> [!NOTE]
> As your operations continue in following months, if you make changes after enrollment to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365 that affect Microsoft Managed Desktop, it's possible that Microsoft Managed Desktop could stop operating properly. To avoid problems with the service, check the specific settings described in [Fix issues found by the readiness assessment tool](../prepare/readiness-assessment-fix.md) before you change the policies listed there.

## Microsoft Intune settings

| Setting | Description |
| ------ | ------ |
| Autopilot deployment profile | If you use any Autopilot policies, update each one to exclude the **Modern Workplace Devices -All** Azure AD group. <br><br> **To update the Autopilot policies:** <br><br> Under **Assignments**, in the **Excluded groups**, select the **Modern Workplace Devices -All** Azure AD group that was created during Microsoft Managed Desktop enrollment. <br><br> Microsoft Managed Desktop will also have created an Autopilot profile, which will have "Modern Workplace" in the name (the **Modern Workplace Autopilot Profile**). When you update your own Autopilot profiles, ensure that you *don't* exclude the **Modern Workplace Devices -All** Azure AD group from the **Modern Workplace Autopilot Profile** that was created by Microsoft Managed Desktop. |
| Conditional Access policies | If you create any new conditional access policies related to Azure AD, Microsoft Intune, or Microsoft Defender XDR for Endpoint after Microsoft Managed Desktop enrollment, exclude the **Modern Workplace Service Accounts** Azure AD group from them. For more information, see [Conditional Access: Users and groups](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop maintains separate conditional access policies to restrict access to these accounts. <br><br> **To review the Microsoft Managed Desktop conditional access policy (Modern Workplace – Secure Workstation):** <br><br> Go to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and navigate to **Conditional Access** in **Endpoint Security**. Don't modify any Azure AD conditional access policies created by Microsoft Managed Desktop that have "Modern Workplace" in the name. |
| Multi-factor authentication | If you create any new multi-factor authentication requirements in conditional access policies related to Azure AD, Intune, or Microsoft Defender XDR for Endpoint after Microsoft Managed Desktop enrollment, exclude the **Modern Workplace Service Accounts** Azure AD group from them. For more information, see [Conditional Access: Users and groups](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop maintains separate conditional access policies to restrict access to members of this group. <br><br> **To review the Microsoft Managed Desktop conditional access policy (Modern Workplace -):** <br><br> Go to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and navigate to **Conditional Access** in **Endpoint Security**.
| Windows 10 update ring | For any Windows 10 update ring policies you've created, exclude the **Modern Workplace Devices -All** Azure AD group from each policy. For more information, see [Create and assign update rings](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings). <br><br> Microsoft Managed Desktop will also have created some update ring policies, all of which will have "Modern Workplace" in the name. For example: <ul><li>Modern Workplace Update Policy [Broad]</li><li>Modern Workplace Update Policy [Fast]</li><li>Modern Workplace Update Policy [First]</li><li>Modern Workplace Update Policy [Test]</li></ul> <br>When you update your own policies, ensure that you *don't* exclude the **Modern Workplace Devices -All** Azure AD group from those that Microsoft Managed Desktop created. |

## Azure Active Directory settings

Self-service password reset: if you use self-service password reset for all users, adjust the assignment to exclude Microsoft Managed Desktop service accounts.

**To adjust this assignment:**

1. Create an Azure AD dynamic group for all users *except* Microsoft Managed Desktop service accounts
1. Use that group for assignment instead of "all users."

To help you find and exclude the service accounts, here's an example of a dynamic query you can use:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

In this query, replace `@TENANT` with your tenant domain name.
