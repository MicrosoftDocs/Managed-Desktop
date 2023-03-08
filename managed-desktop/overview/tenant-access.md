---
title: Tenant access and service accounts
description: This article describes how Microsoft Managed Desktop uses service and/or guest accounts to access your tenant
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
ms.author: tiaraquan
manager: dougeby
ms.topic: conceptual
ms.date: 03/10/2023
---

# Tenant access and service accounts

To successfully use the Microsoft Managed Desktop service, we require a service account and a temporary guest account to be created in your “tenant”. The Microsoft Managed Desktop service personnel will request one-time access to your tenant to operate the Microsoft Managed Desktop service and help you secure your tenant. This article explains how Microsoft Managed Desktop accesses your tenant to operate the service.

## Service account access

Microsoft Managed Desktop creates different service accounts during the enrollment process. These accounts remain active while using the service. Microsoft Managed Desktop service engineers exclusively use interactive and non-interactive accounts to perform the service, together with mandatory controls.  

### Examples of how Microsoft Managed Desktop uses service accounts

- The [Microsoft Managed Desktop Service Engineering team](../overview/support-teams.md#service-engineering-team) accesses the interactive account through the Microsoft Intune admin center and uses it to change the security policy setting.  
- The [Microsoft Managed Desktop Secure Operations Centers (SOC) team](../overview/support-teams.md#security-operations-center-team) will use an interactive account to access the Microsoft 365 Defender security portal to perform auditing needs with read-only privilege.
- The Microsoft Managed Desktop service uses non-interactive accounts to make automated changes. One example would be when a service engineer needs to update a deployment or configuration or perform other changes through a partner API.

## Guest account access

Microsoft Managed Desktop uses guest account access during two types of events in your Azure Active Directory (AD) organization:

- During enrollment, the required groups are created by the service software.
- When access to your Azure AD organization is required, a service engineer’s operational account is elevated from being a user in the Microsoft.com tenant to one of the role groups in your tenant.

Guest account access is temporary and requires Two-Key completion, whereby anyone on the Microsoft Managed Desktop Service Engineering or SOC teams are allowed to approve the request.

We’ll send an email to the Microsoft Managed Desktop Service Engineering team alias to request a second person to approve the request. Once approved, an approval notification email is sent to the requester. For more information, see [Guest account prerequisites](../prepare/guest-accounts.md).
