---
title: List devices
description: Retrieves a list of devices managed by Microsoft Managed Desktop.
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

# List devices

## API description

Retrieves a list of devices managed by Microsoft Managed Desktop.

Supported [OData V4 query](https://www.odata.org/documentation/) operators:

`searchText on name, serialNumber, globalDeviceId, userUpn, userEmail`

`$skip`

`$top`

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | `MWaaSDevice.Read` |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

Here is an example of an HTTP request.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/devices

```

## Request headers

| Header | Value |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| Accept | application/json |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a 200 OK response code and a list of devices in the response body.

## Example 1: List all devices

### List all devices request

Here is an example of the HTTP request.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/devices
```

### List all devices response

Here is an example of the JSON response.

> [!NOTE]
> The response list shown here may be truncated for brevity. All devices will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Devices", 
    "value": [ 
        { 
            "name": "Device name value", 
            "intuneId": "Intune Id Value", 
            "manufacturer": "Microsoft Corporation", 
            "model": "Surface Laptop", 
            "serialNumber": "Serial number value", 
            "globalDeviceId": "g:value", 
            "enrolledIntoIntuneDateTimeUtc": "2021-11-11T15:01:07.5381567Z", 
            "tenantId": "Tenant Id value", 
            "tenantName": null, 
            "assignedUser": "firstName lastName", 
            "userUpn": "username@contoso.onmicrosoft.com", 
            "userEmail": "username@contoso.onmicrosoft.com", 
            "complianceState": "Compliant", 
            "osVersion": "10.0.19043.1586", 
            "primaryUpdateRing": "Broad", 
            "lastIntuneSyncDateTimeUtc": "2021-04-13T09:19:06.6991927Z", 
            "ageInMonths": 13.978561, 
            "planType": "Premium", 
            "persona": "Standard", 
            "aadDeviceId": "aadDevice Id value", 
            "managementAgent": "Intune", 
            "operatingSystemEdition": "Enterprise", 
            "profileAssignmentStatus": "Successful", 
            "groups": [], 
            "configurations": [] 
        }, 
        { 
            "name": "Device name value", 
            "intuneId": "Intune Id Value", 
            "manufacturer": "Microsoft Corporation", 
            "model": "Virtual Machine", 
            "serialNumber": "Serial number value", 
            "globalDeviceId": "g:value", 
            "enrolledIntoIntuneDateTimeUtc": "2021-02-25T07:42:07Z", 
            "tenantId": "Tenant Id value", 
            "tenantName": null, 
            "assignedUser": "firstName lastName", 
            "userUpn": "username@contoso.onmicrosoft.com", 
            "userEmail": "username@contoso.onmicrosoft.com", 
            "complianceState": "Compliant", 
            "osVersion": "10.0.19043.1586", 
            "primaryUpdateRing": "First", 
            "lastIntuneSyncDateTimeUtc": "2021-03-16T11:10:04Z", 
            "ageInMonths": 1.5491623, 
            "planType": "Premium", 
            "persona": "Standard", 
            "aadDeviceId": "aadDevice Id value", 
            "managementAgent": "Intune", 
            "operatingSystemEdition": "Enterprise", 
            "profileAssignmentStatus": "Successful", 
            "groups": [], 
            "configurations": [] 
        }, 
        { 
            "name": "", 
            "intuneId": null, 
            "manufacturer": "Microsoft Corporation", 
            "model": "Surface Pro 4", 
            "serialNumber": "Serial number value", 
            "globalDeviceId": null, 
            "enrolledIntoIntuneDateTimeUtc": null, 
            "tenantId": "Tenant Id value", 
            "tenantName": null, 
            "assignedUser": null, 
            "userUpn": null, 
            "userEmail": null, 
            "complianceState": "Unknown", 
            "osVersion": null, 
            "primaryUpdateRing": "Test", 
            "lastIntuneSyncDateTimeUtc": null, 
            "ageInMonths": 11.417163, 
            "planType": "Premium", 
            "persona": "Standard", 
            "aadDeviceId": "aadDevice Id value", 
            "managementAgent": null, 
            "operatingSystemEdition": null, 
            "profileAssignmentStatus": "Successful", 
            "groups": [], 
            "configurations": [] 
        } 
    ] 
}
```

## Example 2: List devices with filters

### List devices with filters request

Here is an HTTP example to skip the first record and list the next top two records.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/devices?skip=1&top=2
```

### List devices with filters response

Here is an example of the JSON response.

> [!NOTE]
> The response list shown here may be truncated for brevity. All devices will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Devices", 
    "value": [ 
        { 
            "name": "Device name value", 
            "intuneId": "Intune Id Value", 
            "manufacturer": "Microsoft Corporation", 
            "model": "Virtual Machine", 
            "serialNumber": "Serial number value", 
            "globalDeviceId": "g:value", 
            "enrolledIntoIntuneDateTimeUtc": "2021-02-25T07:42:07Z", 
            "tenantId": "Tenant Id value", 
            "tenantName": null, 
            "assignedUser": "firstName lastName", 
            "userUpn": "username@contoso.onmicrosoft.com", 
            "userEmail": "username@contoso.onmicrosoft.com", 
            "complianceState": "Compliant", 
            "osVersion": "10.0.19043.1586", 
            "primaryUpdateRing": "First", 
            "lastIntuneSyncDateTimeUtc": "2021-03-16T11:10:04Z", 
            "ageInMonths": 1.5491623, 
            "planType": "Premium", 
            "persona": "Standard", 
            "aadDeviceId": "aadDevice Id value", 
            "managementAgent": "Intune", 
            "operatingSystemEdition": "Enterprise", 
            "profileAssignmentStatus": "Successful", 
            "groups": [], 
            "configurations": [] 
        }, 
        { 
            "name": "", 
            "intuneId": null, 
            "manufacturer": "Microsoft Corporation", 
            "model": "Surface Pro 4", 
            "serialNumber": "Serial number value", 
            "globalDeviceId": null, 
            "enrolledIntoIntuneDateTimeUtc": null, 
            "tenantId": "Tenant Id value", 
            "tenantName": null, 
            "assignedUser": null, 
            "userUpn": null, 
            "userEmail": null, 
            "complianceState": "Unknown", 
            "osVersion": null, 
            "primaryUpdateRing": "Test", 
            "lastIntuneSyncDateTimeUtc": null, 
            "ageInMonths": 11.417163, 
            "planType": "Premium", 
            "persona": "Standard", 
            "aadDeviceId": "aadDevice Id value", 
            "managementAgent": null, 
            "operatingSystemEdition": null, 
            "profileAssignmentStatus": "Successful", 
            "groups": [], 
            "configurations": [] 
        } 
    ] 
}
```

## Example 3: List devices with userUpn

### List devices with userUpn request

Here is an HTTP example that returns list of devices based on search of user’s UPN.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/devices?searchText=jdoe@contoso.onmicrosoft.com
```

### List devices with userUpn response

Here is an example of the JSON response.

> [!NOTE]
> The response list shown here may be truncated for brevity. All devices will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Devices", 
    "value": [ 
        { 
            "name": "Device name value", 
            "intuneId": "Intune Id Value", 
            "manufacturer": "Microsoft Corporation", 
            "model": "Virtual Machine", 
            "serialNumber": "Serial number value", 
            "globalDeviceId": "g:value", 
            "enrolledIntoIntuneDateTimeUtc": "2021-02-25T07:42:07Z", 
            "tenantId": "Tenant Id value", 
            "tenantName": null, 
            "assignedUser": "John Doe", 
            "userUpn": "jdoe@contoso.onmicrosoft.com", 
            "userEmail": "jdoe@contoso.onmicrosoft.com", 
            "complianceState": "Compliant", 
            "osVersion": "10.0.19043.1586", 
            "primaryUpdateRing": "First", 
            "lastIntuneSyncDateTimeUtc": "2021-03-16T11:10:04Z", 
            "ageInMonths": 1.5491623, 
            "planType": "Premium", 
            "persona": "Standard", 
            "aadDeviceId": "aadDevice Id value", 
            "managementAgent": "Intune", 
            "operatingSystemEdition": "Enterprise", 
            "profileAssignmentStatus": "Successful", 
            "groups": [], 
            "configurations": [] 
        } 
    ] 
}
```
