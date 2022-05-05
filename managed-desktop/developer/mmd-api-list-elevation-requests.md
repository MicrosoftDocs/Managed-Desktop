---
title: List elevation requests
description: Describes how to list all elevation requests
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

# List elevation requests

## API description

Lists all elevation requests.

Supported [OData V4 query](https://www.odata.org/documentation/) operators:

`$filter`

`$skip`

`$top`

## Prerequisites

One of the following permissions is required to call this API.

| Permission type | Permissions |
| --- | --- |
| Delegated | `MWaaSDevice.Read` |
| Accept | `MmdSupport.ReadWrite` |

## HTTP request

```http
GET https://mmdls.microsoft.com/support/odata/v1/tickets
```

## Request headers

| Header | Value |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| Accept | application/json |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a 200 OK response code and a list of tickets in the response body.

## Example 1: List elevation requests

### List elevation request

Here is an HTTP example to list the first two elevation requests.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tickets?$skip=0&$top=2
```

### List elevation response

Here is an example of the JSON response.

> [!NOTE]
> The response list shown here may be truncated for brevity. All elevation requests will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#ElevationRequests", 
    "value": [ 
        { 
            "id": "Elevation Request Id", 
            "tenantId": "Tenant Id", 
            "partnerId": "Tenant Id", 
            "requestingAgentUpn": "user UPN email", 
            "partnerTicketId": "Support Ticket Id", 
            "deviceName": "Device Name", 
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
        }, 
        { 
            "id": "Elevation Request Id", 
            "tenantId": "Tenant Id", 
            "partnerId": "Tenant Id", 
            "requestingAgentUpn": "user UPN email", 
            "partnerTicketId": "Support Ticket Id", 
            "deviceName": "Device Name", 
            "title": "Elevation request title", 
            "category": "Hardware", 
            "subcategory": "Device", 
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
        }, 
        .... 
    ] 
}
```

## Example 2: List elevation requests for a device

### List elevation requests for a device request

Here is an HTTP example to list all elevation requests for a specific device.

```http
GET https://mmdls.microsoft.com/support/odata /v1/tenants/{tenantId}/elevationRequests?$filter=deviceName eq ' MMD-03690457680'
```

### List elevation requests for a device response

Here is an example of the JSON response.

> [!NOTE]
> The response list shown here may be truncated for brevity. All elevation requests will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#ElevationRequests", 
    "value": [ 
        { 
            "id": "Elevation Request Id", 
            "tenantId": "Tenant Id", 
            "partnerId": "Tenant Id", 
            "requestingAgentUpn": "user UPN email", 
            "partnerTicketId": "Support Ticket Id", 
            "deviceName": "MMD-03690457680", 
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
        }, 
        { 
            "id": "Elevation Request Id", 
            "tenantId": "Tenant Id", 
            "partnerId": "Tenant Id", 
            "requestingAgentUpn": "user UPN email", 
            "partnerTicketId": "Support Ticket Id", 
            "deviceName": "MMD-03690457680", 
            "title": "Elevation request title", 
            "category": "Hardware", 
            "subcategory": "Device", 
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
        }, 
        .... 
    ] 
}
```

## Example 3: List elevation requests filtered by category

### List elevation requests filtered by category request

Here is an HTTP example to list all elevation requests with category of ‘Office’.

```http
GET https://mmd-support-preprod-nam.trafficmanager.net/odata/v1/tenants/{tenantId}/elevationRequests?$filter=contains(category,'Office')
```

### List elevation requests filtered by category response

Here is an example of the JSON response.

> [!NOTE]
> The response list shown here may be truncated for brevity. All tickets will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#ElevationRequests", 
    "value": [ 
        { 
            "id": "Elevation Request Id", 
            "tenantId": "Tenant Id", 
            "partnerId": "Tenant Id", 
            "requestingAgentUpn": "user UPN email", 
            "partnerTicketId": "Support Ticket Id", 
            "deviceName": "MMD-03690457680", 
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
        }, 
        { 
            "id": "Elevation Request Id", 
            "tenantId": "Tenant Id", 
            "partnerId": "Tenant Id", 
            "requestingAgentUpn": "user UPN email", 
            "partnerTicketId": "Support Ticket Id", 
            "deviceName": "MMD-03690457680", 
            "title": "Elevation request title", 
            "category": "Office", 
            "subcategory": "Word", 
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
        }, 
        .... 
    ] 
}
```
