---
title: Close an elevation request
description: Describes how to close elevation requests
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

# Close an elevation request

## API description

Close an elevation request.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | `MWaaSDevice.Read` |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
PATCH https://mmdls.microsoft.com/support/odata/v1 /tenants/{tenantId}/elevationRequests/{elevationRequestId}
```

## Request headers

| Header | Value |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| Accept | application/json |

## Request body

| Property | Type | Description |
| --- | --- | --- |
| ActionsTaken | String | Actions taken to resolve case. |

## Response

If successful, this method returns a 204 No Content response code.

## Example

### Example request

Here is an example of the HTTP request.

```http
PATCH https://mmdls.microsoft.com/support/odata/v1/tenants/{tenantId}/elevationRequests/{elevationRequestId}
```

Here is an example of the JSON request.

```json
{ 
    "ActionsTaken" : "Actions taken to resolve case." 
}
```

### Example response

Here is an example of a successful response.

| Response |
| --- |
| 204 No Content |

### Failed responses

Here are examples of failed responses.

#### Example one

Here is an example of a failed JSON response.

```json
{ 
    "error": { 
        "code": "400", 
        "message": "This elevation request was already closed." 
    } 
}
```

#### Example two

Here is an example of a failed JSON response.

```json
{ 
    "error": { 
        "code": "404", 
        "message": "This elevation request does not exist." 
    } 
}
```
