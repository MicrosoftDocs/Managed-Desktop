---
title: Get user by userUpn
description: Retrieves specific user by userUpn.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/26/2022
ms.collection: M365-modern-desktop
---

# Get user by userUpn

## API description

Retrieves specific user by userUpn.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | `MWaaSDevice.Read`  |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/users/{userUpn}
```

## Request headers

| Header | Value |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| Accept  | application/json |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a 200 OK response code and user details in the response body.

## Example

### Example request

The following is an example of the HTTP request.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/devices/jdoe@contoso.onmicrosoft.com
```

### Example response

The following is an example of the JSON response.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Users", 
    "value": [ 
        { 
            "name": "John Doe", 
            "upn": "jdoe@contoso.onmicrosoft.com", 
            "email": "jdoe@contoso.onmicrosoft.com", 
            "groups": [ 
                { 
                    "id": "00000000-0000-0000-0000-000000000000", 
                    "displayName": "Group display name", 
                    "description": "Group description", 
                    "countMembers": null 
                } 
                ... 
            ], 
            "devices": [ 
                { 
                    "serialNumber": "Serial number value", 
                    "name": "Device Name value", 
                    "model": "Virtual Machine", 
                    "ring": "First", 
                    "lastIntuneSyncTime": "2021-03-16T11:10:04Z" 
                } 
                ... 
            ] 
        } 
    ] 
}
```
