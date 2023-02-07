---
title: List users
description: Retrieves a list of users that are assigned devices managed by Microsoft Managed Desktop.
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

# List users

## API description

Retrieves a list of users that are assigned devices managed by Microsoft Managed Desktop.

Supported [OData V4 query](https://www.odata.org/documentation/) operators:

`searchText on name, upn, email, serialNumber, devices name`

`$skip`

`$top`

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | `MWaaSDevice.Read` |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/users
```

## Request headers

| Header | Value |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| Accept  | application/json |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a 200 OK response code and a list of devices in the response body.

## Example 1:  List all users

### List all users request

The following is an example of the HTTP request.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/users
```

### List all users request response

Here's an example of the JSON response.

> [!NOTE]
> The response list shown may be truncated for brevity. All users will be returned from an actual call.

```json
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Users",</p>
    "value": [
        {
            "name": "User Name",
            "upn": "username@contoso.onmicrosoft.com",
            "email": "username@contoso.onmicrosoft.com",
            "groups": [],
            "devices": [
                {
                    "serialNumber": "Serial number value",
                    "name": "Device Name value",
                    "model": "Surface Laptop",
                    "ring": "Broad",
                    "lastIntuneSyncTime": "2021-04-13T09:19:06.6991927Z"
                }
            ]
        },
        {
            "name": "User Name",
            "upn": "username@contoso.onmicrosoft.com",
            "email": "username@contoso.onmicrosoft.com",
            "groups": [],
            "devices": [
                {
                    "serialNumber": "Serial number value",
                    "name": "Device Name value",
                    "model": "Virtual Machine",
                    "ring": "First",
                    "lastIntuneSyncTime": "2021-03-16T11:10:04Z"
                }
            ]
        },
        {
            "name": "User Name",
            "upn": "username@contoso.onmicrosoft.com",
            "email": "username@contoso.onmicrosoft.com",
            "groups": [],
            "devices": [
                {
                    "serialNumber": "Serial number value",
                    "name": "Device Name value",
                    "model": "Virtual Machine",
                    "ring": "Test",
                    "lastIntuneSyncTime": "2021-04-13T12:14:02.968959Z"
                },
                {
                    "serialNumber": "Serial number value",
                    "name": "Device Name value",
                    "model": "Virtual Machine",
                    "ring": "Test",
                    "lastIntuneSyncTime": "2021-03-17T17:52:04.8631737Z"
                },
                {
                    "serialNumber": "Serial number value",
                    "name": "Device Name value",
                    "model": "Virtual Machine",
                    "ring": "First",
                    "lastIntuneSyncTime": "2021-03-09T07:10:26Z"
                }
            ]
        }
    ]
}

```

## Example 2: List users with filters

### List users with filters request

The following is an HTTP example to skip the first record and list the next top two records.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/users?$skip=1&$top=2
```

### List users with filters response

The following is an example of the JSON response.

> [!NOTE]
> The response list shown may be truncated for brevity. All users will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Users", 
    "value": [ 
        { 
            "name": "User Name", 
            "upn": "username@contoso.onmicrosoft.com", 
            "email": "username@contoso.onmicrosoft.com", 
            "groups": [], 
            "devices": [ 
                { 
                    "serialNumber": "Serial number value", 
                    "name": "Device Name value", 
                    "model": "Virtual Machine", 
                    "ring": "First", 
                    "lastIntuneSyncTime": "2021-03-16T11:10:04Z" 
                } 
            ] 
        }, 
        { 
            "name": "User Name", 
            "upn": "username@contoso.onmicrosoft.com", 
            "email": "username@contoso.onmicrosoft.com", 
            "groups": [], 
            "devices": [ 
                { 
                    "serialNumber": "Serial number value", 
                    "name": "Device Name value", 
                    "model": "Virtual Machine", 
                    "ring": "Test", 
                    "lastIntuneSyncTime": "2021-04-13T12:14:02.968959Z" 
                }, 
                { 
                    "serialNumber": "Serial number value", 
                    "name": "Device Name value", 
                    "model": "Virtual Machine", 
                    "ring": "Test", 
                    "lastIntuneSyncTime": "2021-03-17T17:52:04.8631737Z" 
                }, 
                { 
                    "serialNumber": "Serial number value", 
                    "name": "Device Name value", 
                    "model": "Virtual Machine", 
                    "ring": "First", 
                    "lastIntuneSyncTime": "2021-03-09T07:10:26Z" 
                } 
            ] 
        } 
        ... 
    ] 
}
```

## Example 3: List users by searchText

### List users by searchText request

The following is an HTTP example to list users with assigned device based on device name.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/users?$searchText={deviceName}
```

### List users by searchText response

The following is an example of the JSON response.

> [!NOTE]
> The response list shown may be truncated for brevity. All users will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Users", 
    "value": [ 
        { 
            "name": "User Name", 
            "upn": "username@contoso.onmicrosoft.com", 
            "email": "username@contoso.onmicrosoft.com", 
            "groups": [], 
            "devices": [ 
                { 
                    "serialNumber": "Serial number value", 
                    "name": "Device Name value", 
                    "model": "Virtual Machine", 
                    "ring": "First", 
                    "lastIntuneSyncTime": "2021-03-16T11:10:04Z" 
                } 
            ] 
        } 
    ] 
}
```
