---
title: Enable Enterprise State Roaming
description:  This article describes how to enable enterprise state roaming
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

# Enable Enterprise State Roaming

[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) lets users securely synchronize user and application settings data to the cloud. This means they'll have the same experience no matter which Windows device they sign into. For example, if you replace one of their Microsoft Managed Desktop devices with a new device, it will look and behave exactly the same as the last one.

Enterprise State Roaming is an optional feature for the Microsoft Managed Desktop service that you can configure for your users. It isn't included or managed as part of Microsoft Managed Desktop.

To enable Enterprise State Roaming, follow the steps in [Enable Enterprise State Roaming in Microsoft Entra ID](/azure/active-directory/devices/enterprise-state-roaming-enable).

>[!NOTE]
>If you enable Enterprise State Roaming, your preferred language list will overwrite the language selected during device setup. Although users can fix this easily, it could cause an inconsistent localization experience initially. Determine if Enterprise State Roaming is right for your users before setting up devices.
