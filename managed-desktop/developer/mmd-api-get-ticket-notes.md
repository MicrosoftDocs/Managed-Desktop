---
title: Get ticket notes
description: Retrieves all ticket notes created by customer for a specific ticket.
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

# Get ticket notes

## API description

Retrieves all ticket notes created by customer for a specific ticket.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | Not Applicable |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
GET https://mmdls.microsoft.com/support/odata/v1/tickets('TicketId')/notes
```

## Request headers

| Header  | Value |
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
GET https://mmdls.microsoft.com/support/odata/v1/tickets('TicketId')/notes
```

### Example response

The following is an example of the JSON response.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Tickets('MMD-1465058-R5V8P')/notes", 
    "value": [ 
        { 
            "id": 0, 
            "type": "post", 
            "renderType": "html", 
            "createdDateTime": "2021-12-14T04:28:18Z", 
            "modifiedDateTime": "2021-12-14T04:28:18Z", 
            "text": "This is the test note to add", 
            "sender": "Sender Id" 
        } 
    ] 
}
```
