---
title: Get device by device name
description: Retrieves a device by its device name.
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

# Get device by device name

## API description

Retrieves a device by its device name.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | `MWaaSDevice.Read` |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/devices/{devicename}
```

## Request headers

| Header | Value  |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| Accept | application/json |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a 200 OK response code and a list of devices in the response body.

## Example

### Example request

Here is an example of the HTTP request.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/devices/MMD-123456789
```

### Example response

Here is an example of the JSON response.

> [!NOTE]
> The response list shown here may be truncated for brevity. All devices will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Devices/$entity", 
    "name": "MMD-123456789", 
    "intuneId": "Intune Id value", 
    "manufacturer": "Microsoft Corporation", 
    "model": "Virtual Machine", 
    "serialNumber": "Serial number value", 
    "globalDeviceId": "g:value", 
    "enrolledIntoIntuneDateTimeUtc": "2021-07-05T09:22:13.729238Z", 
    "tenantId": "Tenant Id value", 
    "tenantName": null, 
    "assignedUser": "firstName lastName", 
    "userUpn": "username@contoso.onmicrosoft.com", 
    "userEmail": "username@contoso.onmicrosoft.com", 
    "complianceState": "NonCompliant", 
    "osVersion": "10.0.19043.1586", 
    "primaryUpdateRing": "Test", 
    "lastIntuneSyncDateTimeUtc": "2021-04-13T04:37:09.6615599Z", 
    "ageInMonths": 9.274547, 
    "planType": "Premium", 
    "persona": "Standard", 
    "aadDeviceId": "aadDeviceId", 
    "managementAgent": "Intune", 
    "operatingSystemEdition": "Enterprise", 
    "profileAssignmentStatus": "Successful", 
    "groups": [ 
        { 
            "id": "46bde30a-9113-4f1e-b169-d9e178f41fa7", 
            "displayName": "Modern Workplace Devices-Test", 
            "description": "Immediate ring for device rollout", 
            "countMembers": null 
        }, 
        { 
            "id": "58834fcf-e369-463f-9405-e856e8de60f6", 
            "displayName": "Modern Workplace Device Profiles - Standard", 
            "description": "Devices with a secure experience", 
            "countMembers": null 
        } 
        ... 
    ], 
    "configurations": [ 
        { 
            "id": "57dc3bb4-7b7f-4052-b9af-0a9c31586e9e", 
            "type": "Policy", 
            "name": "Modern Workplace - Standard Device Profile Configuration", 
            "version": "1", 
            "createdUtc": "2021-06-22T01:29:53.4328287Z", 
            "lastModifiedUtc": "2021-06-22T01:29:53.4328287Z", 
            "deploymentStatus": "Compliant", 
            "lastReportedStatusUtc": "2021-02-09T07:44:52.6201692Z" 
        }, 
        { 
            "id": "1d576a6f-d0b9-4df7-ba3c-1216965caa3d", 
            "type": "Policy", 
            "name": "Modern Workplace - Edge Update Policy [Test]", 
            "version": "2", 
            "createdUtc": "2021-11-09T00:57:00.2017126Z", 
            "lastModifiedUtc": "2021-12-22T20:38:39.5457039Z", 
            "deploymentStatus": "Compliant", 
            "lastReportedStatusUtc": "2021-02-09T07:44:52.6201692Z" 
        }, 
        { 
            "id": "f0cb96d3-527f-4532-8675-1518f7aa813f", 
            "type": "Script", 
            "name": "Modern Workplace - Configure AppV", 
            "version": "0", 
            "createdUtc": "2021-07-21T02:00:31.1331001Z", 
            "lastModifiedUtc": "2021-07-21T02:00:31.1331001Z", 
            "deploymentStatus": "Success", 
            "lastReportedStatusUtc": "2021-02-09T07:51:06Z" 
        }, 
        { 
            "id": "ba8215d7-1aed-4a77-8546-62b1e1a5a981", 
            "type": "App", 
            "name": "Modern Workplace - Teams Machine Wide Installer x32", 
            "version": "", 
            "createdUtc": "2021-02-05T19:26:46.6049199Z", 
            "lastModifiedUtc": "2021-10-20T17:28:49.654275Z", 
            "deploymentStatus": "NotApplicable", 
            "lastReportedStatusUtc": "0001-01-01T00:00:00Z" 
        } 
        ... 
    ] 
}
```
