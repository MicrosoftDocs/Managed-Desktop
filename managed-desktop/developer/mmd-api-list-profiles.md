---
title: List all device profiles
description: List all device profiles in the tenant.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 12/06/2022
ms.collection: 
- M365-modern-desktop
- tier2
---

# List all device profiles

## API description

Lists all the available profiles in the tenant.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | `MWaaSDevice.Read` |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/profiles  
```

## Request headers

| Header | Value  |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |

## Response

If successful, this method returns a 200 OK response code and a list of profiles in the response body.

```json
200 OK
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Profile", 
    "value": [ 
        { 
            "id": "SensitiveData", 
            "status": "Enabled" 
        }, 
        { 
            "id": "Standard", 
            "status": "Enabled" 
        }, 
        { 
            "id": "PowerUser", 
            "status": "Enabled" 
        } 
    ] 
} 
```
