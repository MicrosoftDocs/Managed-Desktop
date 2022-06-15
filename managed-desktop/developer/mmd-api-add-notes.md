---
title: Add notes to a ticket
description: Describes how to add notes to specific ticket.
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

# Add notes to a ticket

## API description

Adds notes to specific ticket.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | `MWaaSDevice.Read` |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
POST https://mmdls.microsoft.com/support/odata/v1/tickets('{TicketId}')/addNote
```

## Request headers

| Header  | Value |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| Accept | application/json |

## Request body

| Property | Required | Type | Description  |
| --- | --- | --- | --- |
| text | True | String | Note to add to ticket for support engineer. |

## Response

If successful, this method returns a 204 response code and there is no content in response body.

## Example

### Example request

Here is an HTTP example of a request to add notes to a specific ticket and a second request to retrieve all ticket notes.

Here is an example of the HTTP request:

```http
POST https://mmdls.microsoft.com/support/odata/v1/tickets('{MMD-1465058-R5V8P}')/addNote 

GET https://mmdls.microsoft.com/support/odata/v1/tickets('{MMD-1465058-R5V8P}')/notes
```

Here is an example of the JSON request:

```json
{     

    "text": "Note to add to ticket" 

}
```

### Example response

Here is an example of the JSON response.

204 No content

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
            "text": "This is the test note 1 to add", 
            "sender": "Sender Id" 
        }, 
        { 
            "id": 1, 
            "type": "post", 
            "renderType": "html", 
            "createdDateTime": "2021-12-14T04:28:18Z", 
            "modifiedDateTime": "2021-12-14T04:28:18Z", 
            "text": "Note to add to ticket", 
            "sender": "Sender Id" 
        } 
    ] 
}
```
