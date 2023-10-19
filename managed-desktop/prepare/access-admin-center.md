---
title: Access the admin center
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
description: How to find and use the admin center, including controlling access to it.
ms.service: m365-md
ms.author: tiaraquan
author: tiaraquan
ms.topic: how-to
audience: ITPro
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
manager: dougeby
ms.date: 12/06/2022
---

# Access the admin center

Your gateway to the Microsoft Managed Desktop service is the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). If you're unfamiliar with the capabilities of the admin center for device management, see the [Microsoft Intune documentation](/mem/).

> [!NOTE]
> In the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) the following browsers are supported:

> - Microsoft Edge (latest version)
> - Safari (latest version, Mac only)
> - Chrome (latest version)
> - Firefox (latest version)

Your administrative account will need specific permissions in order to access the Microsoft Managed Desktop administrative features in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

You can manage admin access to these features within your organization by using role-based access control. Several Microsoft Entra administrator roles, and built-in Microsoft Managed Desktop roles are available to provide more granular control to different features within the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). For more information about Microsoft Entra roles, see [Microsoft Entra built-in roles](/azure/active-directory/roles/permissions-reference).

Unlike Microsoft Entra administrator roles that apply to various Microsoft products and services, the built-in roles are specific to Microsoft Managed Desktop and will only guarantee access to the Admin features for this service. Admins can assign built-in roles to users individually, or in combination with Microsoft Entra administrator roles to add Microsoft Managed Desktop permissions to existing admin accounts.

<a name='azure-active-directory-roles-with-microsoft-managed-desktop-access'></a>

## Microsoft Entra roles with Microsoft Managed Desktop access

| Microsoft Entra role | Microsoft Managed Desktop permissions |
| ----- | ----- |
| Global Administrator | Admins with this role will have **read and write permissions to all features** in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). |
| Global Reader | Admins with this role will have **read-only permissions to all features** in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). |
| Intune Service Administrator | Admins with this role will have **read and write permissions to features not related to security** in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). |
| Service Support Administrator | Admins with this role will have **read-only permissions to features not related to security** and **write permissions to manage support requests including escalation requests** in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). |
| Security Admin | Admins with this role will have **read-only permissions to all features** and **write permissions for security related features** in Microsoft Managed Desktop in the admin center. |
| Security Reader |Admins with this role will have **read-only permissions to all features** in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). |

If you need help with assigning Microsoft Entra roles, see [Microsoft Entra built-in roles](/azure/active-directory/roles/permissions-reference).

> [!IMPORTANT]
> Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop. Be aware that Microsoft Entra roles will give user accounts privileges across a variety of Microsoft services. After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.

## Built-in roles provided by Microsoft Managed Desktop

The following are the built-in roles provided by Microsoft Managed Desktop:

| Built-in role | Microsoft Managed Desktop permissions |
| ----- | ----- |
| Microsoft Managed Desktop Service Administrator | When assigned to a user, this role gives the admin **read and write permissions to Microsoft Managed Desktop features not related to security** in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). |
| Microsoft Managed Desktop Service Reader | When assigned to a user, this role gives the admin **read-only permissions to Microsoft Managed Desktop features not related to security** in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). |
| Microsoft Managed Desktop Security Manager | When assigned to a user, this role gives that admin **read and write permissions only for security related features** in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). |
| Microsoft Managed Desktop Support Partner |When assigned to a user, this role gives the admin **read and write permissions only for creating and managing elevation requests and support partner engaged escalation requests** in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431). |

> [!NOTE]
> Security features include security-related communications, management of security contacts, management of security-related support requests, and access to security related reports.

### Assigning built-in roles to user

For easy management of built-in roles, there's a security group for each custom role with the name "Modern Workplace Roles - **Role Name**". For example, “Modern Workplace Roles – **Security Manager**”).

**To assign users to one of these security groups:**

1. Go to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. In the left pane, select **Groups**.
3. Search for **Modern Workplace Roles**, and then select the group associated with the role you want to assign.
4. Select **Members** on the left side, and then select **+ Add members** in the command bar.
5. Enter the email of the person being added. If they're a guest, you must invite them before you can assign the group.
6. Select **Select** at the bottom.

> [!NOTE]
> Nesting security groups for role assignment is not currently supported.

### Assigning built-in roles to groups

**To assign one or more of the built-in roles to a existing group:**

1. Go to [portal.azure.com](https://portal.azure.com/).
2. Search for and open **Enterprise applications**.
3. Change the **Application type** filter to **Microsoft Applications** and, then select **Apply**.
4. Search for and select **Modern Workplace Customer APIs**.
5. Select **Users and groups** from the pane on the left side, and then select **+ Add user/group**.
6. Search for the group you want from **Users and groups**.
7. Search for the applicable role from **Select a role**, and then select it.
8. Select **Assign**.
