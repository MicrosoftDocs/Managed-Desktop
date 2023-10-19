---
title: Guest account prerequisites
description:  Configuration guidelines for guest accounts and how to adjust them
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
audience: Admin
ms.date: 03/10/2023
---

# Guest account prerequisites

Microsoft Managed Desktop requires the following settings in your Azure Active Directory (AD) organization for guest account access. You can adjust these settings in the Azure portal under **External Identities / External collaboration**:

- Admins and users with the guest inviter role can set invite to **Yes**.
- For Collaboration restrictions, choose any of the following options:
    - If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration is required.
    - If you select **Deny invitations to the specified domains**, make sure that Microsoft.com is not listed in the target domains.
    - If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com is listed in the target domains.

## Role and group creation during enrollment

When your tenant is enrolled into the service, Microsoft creates one group per role in your Azure AD organization.

### Example of the guest account access process

1. Alert notification is received by the Microsoft Managed Desktop Secure Operations Centers (SOC) team.
2. A SOC engineer submits a one-time access request for the security admin role.
3. Depending on the task requirement, the team might need to request one-time access with approval or auto-approval.  
    1. Once the role-specific request has been completed, the SOC service engineer signs into the tenant’s [Microsoft Defender portal](https://security.microsoft.com) and investigates the alert. Primary investigative actions during a typical alert investigation could include items such as:  
        1. Review of the alert specific details populated by Defender.
        2. Classify, set the state, or comment on the incident or alert.  
        3. Review of device timeline and incident page details.
        4. Approve or deny remedial actions.
        5. Start automated investigations.
    2. Use [Advanced Hunt](/microsoft-365/security/defender/advanced-hunting-overview) capabilities.
4. When these actions are completed, the SOC engineer signs out of the tenant and closes the request.

## External collaboration settings

Microsoft Managed Desktop recommends the following configuration in your Azure AD organization for guest account access. You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration settings**:

| Setting | Description |
| ------ | ------ |
| Guest access | Guests have limited access to properties and memberships of directory objects. |
| Guest invite settings | Member users and users assigned to specific admin roles can invite guests including guests with member permissions |

Microsoft Managed Desktop requires the following configuration in your Azure AD organization for guest account access. You can adjust this setting at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration settings**:

| Setting | Option |
| ------ | ------ |
| Collaboration restrictions | Select any of these options: <ul><li>If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</li><li>If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn't listed in the target domains.</li><li>If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</li><ul>

If you set restrictions that interact with these settings, ensure to exclude the Azure Active Directory **Modern Workplace Service Accounts**. For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.

For more information, see [Enable B2B external collaboration and manage who can invite guests](/azure/active-directory/external-identities/delegate-invitations#to-configure-external-collaboration-settings).

## Unlicensed Intune admin

The **Allow access to unlicensed admins** setting must be enabled. Without this setting enabled, errors can occur when we try to access your Azure AD organization for service. You can safely enable this setting without worrying about security implications. The scope of access is defined by the roles assigned to users, including our operations staff.

**To enable this setting:**

1. Go to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Navigate to **Tenant administration**, select **Roles**. Then, select **Administrator licensing**.
3. In the **Allow access to unlicensed admins** section, select **Yes**.

> [!IMPORTANT]
> You cannot undo this setting after you select **Yes**.

For more information, see [Unlicensed admins in Microsoft Intune](/mem/intune/fundamentals/unlicensed-admins).
