---
title: List tickets
description: Lists all support tickets.
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

# List tickets

## API description

Lists all support tickets.

Supported [OData V4 query](https://www.odata.org/documentation/) operators:

`$filter`

`$skip`

`$top`

`$orderby`

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | Not Applicable |
| Application | `MmdSupport.ReadWrite` |

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

## Example 1: List tickets

### List tickets request

Here is an HTTP example to list the first 50 tickets returned in descending order by the **createdDateTime** property.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tickets?$skip=0&$top=50&$orderby=createdDateTime desc
```

### List tickets response

Here is an example of the JSON response.

> [!NOTE]
> The response list shown here may be truncated for brevity. All tickets will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Tickets", 
    "value": [ 
        { 
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
            "id": "Ticket Number", 
            "severity": 4, 
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
        }, 
        { 
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
            "id": "Ticket Number", 
            "severity": 4, 
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
        }, 
        .... 
    ] 
}
```

## Example 2: List tickets filtered by title

### List tickets filtered by title request

Here is an HTTP example to list all tickets that contain `Test` in ticket title

```http
GET https://mmdls.microsoft.com/support/odata/v1/tickets?$filter=contains(title,'Test')
```

### List tickets filtered by title response

Here is an example of the JSON response.

> [!NOTE]
> The response list shown here may be truncated for brevity. All tickets will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Tickets", 
    "value": [ 
        { 
            "title": "Test ticket 1", 
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
            "id": "Ticket Number", 
            "severity": 4, 
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
        }, 
        { 
            "title": "Test ticket 2", 
            "description": "Description", 
            "isPartner": true, 
            "type": "Change Request", 
            "category": "Apps", 
            "subcategory": "Other ", 
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
            "id": "Ticket Number", 
            "severity": 4, 
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
        }, 
        .... 
    ] 
}
```

## Example 3: List tickets filtered by state and severity

### List tickets filtered by state and severity request

Here is an HTTP example to list all high severity tickets that are resolved.

```http
GET https://mmdls.microsoft.com/support/odata/v1/tickets?$filter=state eq 'resolved' and severity eq 2 
```

### List tickets filtered by state and severity response

Here is an example of the JSON response.

> [!NOTE]
> The response list shown here may be truncated for brevity. All tickets will be returned from an actual call.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Tickets", 
    "value": [ 
        { 
            "title": "Test ticket 1", 
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
            "id": "Ticket Number", 
            "severity": 2, 
            "state": "resolved", 
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
        }, 
        { 
            "title": "Test ticket 2", 
            "description": "Description", 
            "isPartner": true, 
            "type": "Change Request", 
            "category": "Apps", 
            "subcategory": "Other ", 
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
            "id": "Ticket Number", 
            "severity": 2, 
            "state": "resolved", 
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
        }, 
        .... 
    ] 
}
```
