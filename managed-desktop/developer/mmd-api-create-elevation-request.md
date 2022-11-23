---
title: Create an elevation request
description: Describes how to create an elevation request for a specific device
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

# Create an elevation request

## API description

Create an elevation request for a specific device.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | Not Applicable |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
POST https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/elevationRequests
```

## Request headers

| Header | Value |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| Accept | application/json |

## Request body

| Property | Type | Description |
| --- | --- | --- |
| partnerTicketId | String | Ticket ID of support ticket linked to elevation request. |
| deviceName | String | Device name. |
| title  | String | Title. |
| category | String | Request category.  |
| subcategory | String | Request subcategory. |
| planOfAction | String | Plan of action to resolve case. |

## Response

If successful, this method returns a 201 Created response code and a list of devices in the response body.

## Example

### Example request

The following is an example of the HTTP request.

```http
POST https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/elevationRequests
```

The following is an example of the JSON request.

```json
{ 
    "PartnerTicketId": "Support Ticket Id", 
    "DeviceName": "DeviceName", 
    "Title": "Elevation request title", 
    "Category": "Office", 
    "Subcategory": "Excel", 
    "PlanOfAction": "Plan of action using elevation." 
}
```

### Example response

The following is an example of the JSON response.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#ElevationRequests/$entity", 
    "id": "Elevation Request Id", 
    "tenantId": "Tenant Id", 
    "partnerId": "Tenant Id", 
    "requestingAgentUpn": "user UPN email", 
    "partnerTicketId": "Support Ticket Id", 
    "deviceName": "DeviceName", 
    "title": "Elevation request title", 
    "category": "Office", 
    "subcategory": "Excel", 
    "planOfAction": "Plan of action using elevation.", 
    "actionsTaken": "", 
    "closingAgentUpn": "", 
    "requestCreationTime": "2021-12-14T14:06:25.0338102Z", 
    "requestClosureTime": null, 
    "requestRenewTime": null, 
    "isSuccessfulRequest": true, 
    "viewerUpns": [], 
    "passwordLastUpdatedTime": "2021-03-16T15:10:36.2066667Z", 
    "isDeleted": false, 
    "ttl": 7776000, 
    "eTag": null 
}
```

### Failed responses

The following are examples of failed responses.

#### Example one

The following is an example of a failed JSON response.

```json
{ 
    "error": { 
        "code": "403", 
        "message": "This device has too many open elevation requests." 
    } 
}
```

#### Example two

The following is an example of a failed JSON response.

```json
{ 
    "error": { 
        "code": "404", 
        "message": "This device does not exist." 
    } 
}
```
