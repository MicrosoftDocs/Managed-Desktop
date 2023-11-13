---
title: Microsoft Managed Desktop API
description: Information about Microsoft Managed Desktop APIs
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.localizationpriority: medium
ms.date: 04/26/2022
ms.collection: 
- M365-modern-desktop
- tier3
---

# Microsoft Managed Desktop API

## Overview

The Microsoft Managed Desktop API enables data and capabilities through a set of programmatic APIs that will allow you to automate workflows using your preferred tools.

The API enables you to view and manage devices, support tickets, and elevation requests details as you would through [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431)).

Using the API, you can:

- Get a list of devices managed within your tenant and detailed information about each device.
- Get a list of users with their managed devices.
- Create and manage support tickets.
- Create and manage elevation requests.

## Before you begin

In general, you’ll need to take the following steps to use the APIs:

1. Create and register [a Microsoft Entra application](/graph/auth-register-app-v2).
1. Configure permissions for Microsoft Managed Desktop on your app.
1. Get administrator consent or user credential.
1. Get an access token.
1. Use the token to access Microsoft Managed Desktop API.

For more information, see Get access to API with [application context](mmd-api-access-app-context.md) or [user context](mmd-api-access-user-context.md).
