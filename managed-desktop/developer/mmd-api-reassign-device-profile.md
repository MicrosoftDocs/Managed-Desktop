---
title: Reassign device profile
description: Reassign a device's profile or devices' profiles in bulk.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.localizationpriority: medium
ms.date: 12/06/2022
ms.collection: 
- M365-modern-desktop
- tier3
---

# Reassign device profile

## API description

Reassign a device's profile or devices' profiles in bulk.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | Not applicable |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
PATCH https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/profiles/reassignProfile?persona={persona} &wipe={wipe} 
```

## Request headers

| Header | Value  |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| ContentType | application/json |

## Request body

```json
[ 
    "{aadDeviceId1}", 
    "{aadDeviceId2}", 
    "{aadDeviceId3}" 
] 
```

## Example response

The following is an example of a successful response.

```json
200 OK
Successfully start reassigning devices to profile Kiosk
```

### Failed responses

#### Example 1: 400 Bad request: Kiosk not enabled for tenant

```json
{ 
    "errorCode": "400", 
    "message": "Kiosk not enabled for tenant {tenantId}, only SensitiveData,Standard,PowerUser are enabled", 
    "instanceAnnotations": [] 
} 
```

The target profile not enabled for this tenant. Use available profiles in the response or use the [List Profiles](mmd-api-list-profiles.md) API to check the status of each profile.

### Example 2: 400 Bad request: Persona not supported

```json
{ 
    "errorCode": "400", 
    "message": "This persona is not supported.", 
    "instanceAnnotations": [] 
} 
```

The target profile is incorrect or no profile available for this tenant.
