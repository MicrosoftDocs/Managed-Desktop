---
title: Users
description: Retrieves users assigned to Microsoft Managed Desktop devices.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/26/2022
ms.collection: 
- M365-modern-desktop
- tier2
---

# Users

Users assigned to Microsoft Managed Desktop devices.

## Methods

| Method | Return Type | Description |
| --- | --- | --- |
| Get user | Device | Get a single user object |
| List users | Device collection | List user and associated collections |

## Properties

| Property | Type | Description |
| --- | --- | --- |
| name | String  | Full name of the user. |
| upn | String | Username. |
| email | String | Email address. |
| devices  | devices collection | List of devices assigned to the user.  |
| groups  | configurations collection | List of groups the user is assigned to.|
