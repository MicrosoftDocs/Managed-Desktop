---
title: Maintain the Microsoft Managed Desktop environment
description: This article details how to maintain the Microsoft Managed Desktop environment
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.localizationpriority: medium
ms.date: 03/31/2023
ms.collection: 
- M365-modern-desktop
- tier1
---

# Maintain the Microsoft Managed Desktop environment

## Microsoft Managed Desktop tenant actions

The Tenant management blade is used to alert IT admins of any actions that are required to maintain overall service health.  

The Tenant management blade can be found by navigating to **Tenant administration** > **Microsoft Managed Desktop** > **Tenant management**.

> [!IMPORTANT]
> Microsoft Managed Desktop will now manage your tenant with our [enterprise applications](../overview/privacy-personal-data.md#tenant-access). If your tenant is still using the [Microsoft Managed Desktop service accounts](../prepare/readiness-assessment-fix.md#microsoft-managed-desktop-service-accounts), your Global admin must go to the Tenant management blade to approve the configuration change.

The type of banner that appears depends on the severity of the action. Currently, only critical actions are listed.

### Tenant action severity types

| Severity | Description |
| ----- | ----- |
| Critical | You must take action, as soon as possible. If no action is taken, the Microsoft Managed Desktop service may be affected. |

### Critical actions in Microsoft Managed Desktop

| Action type | Severity | Description |
| ----- | ----- | ----- |
| Maintain tenant access | Critical | Address tenant access issues. Reasons for tenant access issues:<ul><li>You haven't yet migrated to the new Microsoft Managed Desktop enterprise application. Microsoft Managed Desktop uses this  enterprise application to run the service.</li><li>You have migrated to the new enterprise application but still need to clean up the old service accounts created by the service.</li></ul><p>Take action by consenting to allow Microsoft Managed Desktop to make the appropriate changes on your behalf. You must be a Global Administrator to approve this action. Once you provide consent, Microsoft Managed Desktop will take action and remediate this critical action for you. For more information, see [Microsoft Managed Desktop privacy](../overview/privacy-personal-data.md).</p> |

If you need more assistance, please [submit a support request](../operate/support-request.md).
