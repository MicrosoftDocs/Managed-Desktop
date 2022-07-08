---
title: Get elevation request details
description: Describes how to retrieve details of any open elevation request for a specific device.
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

# Get elevation request details

## API description

Retrieves details of any open elevation request for a specific device.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | Not Applicable |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/devices/{deviceName}/elevationDetails
```

## Request headers

| Header | Value |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| Accept | application/json |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a 200 OK response code and user details in the response body.

## Example

### Example request

Here is an example of the HTTP request.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/devices/MMD-03690457680/elevationDetails
```

### Example response

Here is an example of the JSON response.

```json
{ 
    "@odata.context": "https://mmd-support-preprod-nam.trafficmanager.net/odata/v1/$metadata#Microsoft.ManagedDesktop.DeviceElevationDetail", 
    "tenantId": "Tenant Id", 
    "deviceName": "MMD-03690457680", 
    "openedElevationRequestId": "Elevation Request Id", 
    "aadDeviceId": "Azure AD device Id", 
    "accountUpn": "accountUpn", 
    "password": "password", 
    "passwordLastUpdated": "2021-03-16T15:10:36.2066667Z", 
    "status": "PasswordSucceeded", 
    "isPasswordChanged": false, 
    "viewedBy": [ 
        "System" 
    ] 
}
```
