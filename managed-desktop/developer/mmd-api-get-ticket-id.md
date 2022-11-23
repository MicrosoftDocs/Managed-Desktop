---
title: Get ticket by ID
description: Retrieves specific ticket by its ID.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/25/2022
ms.collection: M365-modern-desktop
---

# Get ticket by ID

## API description

Retrieves specific ticket by its ID.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | Not Applicable |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
GET https://mmdls.microsoft.com/support/odata/v1/tickets('TicketId')
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

The following is an example of the HTTP request.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tickets('TicketId')
```

### Example response

The following is an example of the JSON response.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Tickets/$entity", 
    "title": "Title", 
    "description": "Description", 
    "isPartner": true, 
    "type": "Incident", 
    "category": "Devices", 
    "subcategory": "Configuration/Policy", 
    "compromiseIndicator": null, 
    "usersOrDevicesImpacted": 100, 
    "relatedAlerts": null, 
    "businessImpact": "Business Impact", 
    "issueFirstNoticed": "2021-10-06T07:00:00Z", 
    "issueReproduced": true, 
    "endUserSupportEngaged": true, 
    "troubleshootingSteps": "Describe any troubleshooting steps performed.", 
    "nextActionOwner": "Microsoft", 
    "nextActionTime": null, 
    "reproSteps": null, 
    "id": "MMD-1465058-R5V8P", 
    "severity": 2, 
    "state": "active", 
    "createdDateTime": "2021-12-14T04:28:18Z", 
    "resolvedDateTime": null, 
    "contact": { 
        "id": "Unique Id", 
        "givenName": "John", 
        "surname": "Doe", 
        "email": "jd@contoso.com", 
        "phoneNumber": "phone number", 
        "preferredLanguageId": "" 
    }, 
    "emails": [], 
    "attachments": [], 
    "notes": [] 
}
```
