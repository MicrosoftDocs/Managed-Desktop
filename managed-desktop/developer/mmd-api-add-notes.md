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
ms.date: 10/25/2022
ms.collection: M365-modern-desktop
---

# Add notes to a ticket

## API description

Adds notes to specific ticket.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | Not Applicable |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
POST https://mmdls.microsoft.com/support/odata/v1/tickets('TicketId')/addNote
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
POST https://mmdls.microsoft.com/support/odata/v1/tickets('TicketId')/addNote 
```

Here is an example of the JSON request:

```json
{     

    "text": "Note to add to ticket" 

}
```
