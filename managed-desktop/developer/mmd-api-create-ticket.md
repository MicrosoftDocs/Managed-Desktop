---
title: Create ticket
description: Creates a new support ticket.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.localizationpriority: medium
ms.date: 04/26/2022
ms.collection: 
- M365-modern-desktop
- tier3
---

# Create ticket

## API description

Creates a new support ticket.

Adding attachments isn't currently supported via the API. To add a file to an existing support ticket, visit the **Service requests** page in the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

Viewing and adding contents to discussions isn't currently supported via the API.

## Prerequisites

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see Permissions.

| Permission type | Permissions |
| --- | --- |
| Delegated | Not Applicable |
| Application | `MmdSupport.ReadWrite` |

## HTTP request

```http
POST https://mmdls.microsoft.com/support/odata/v1/tickets
```

## Request headers

| Header | Value |
| --- | --- |
| Authorization | Bearer {token} **(Required)** |
| Accept | application/json |

## Request body

Don't supply a request body for this method.

| Property | Required | Type | Description |
| --- | --- | --- | --- |
| title | True | String | Brief description of question or issue. |
| description | True | String | Detailed description. |
| type | True | TicketType | Ticket type. |
| category | True | TicketCategory | Ticket category. |
| subcategory | True | String | Ticket subcategory. |
| usersOrDevicesImpacted |    | Int32  | Number of users/devices impacted. |
| businessImpact |    | String | Describe business impact |
| issueFirstNoticed  |    | String | Time when issue was first noticed. |
| issueReproduced |    | Boolean | Issue is reproducible on non-Microsoft Managed device. |
| endUserSupportEngaged  |    | Boolean   | End user support was engaged. |
| troubleshootingSteps   |    | String  | Description of performed remediation steps. |
| reproSteps |    | String  | Steps to reproduce issue. |
| severity | True | Severity Level | Ticket severity. |
| contact | True | CaseContact | Case contact object. |
| givenName | True | String | First name. |
| surname | True | String | Last name.m|
| email | True | String | Email address. |
| phoneNumber | True | String | Phone number. |

## Response

If successful, this method returns a 200 OK response code and a list of devices in the response body.

## Example 1: Create support ticket to request information

### Create a support ticket request

The following is an example of the HTTP request.

```http
POST https://mmdls.microsoft.com/support/odata/v1/tickets
```

The following is an example of the JSON request.

```json
{ 
    "title": "Title", 
    "description": "Description of ticket", 
    "type": "RequestForInformation", 
    "category": "Devices", 
    "subcategory": "Hardware", 
    "severity": 4, 
    "contact": { 
        "givenName": "John", 
        "surname": "Doe", 
        "email": "jd@contoso.com", 
        "phoneNumber": "phone number"
    } 
}
```

### Create support ticket response

The following is an example of the JSON response.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Tickets/$entity", 
    "title": "Title", 
    "description": "Description", 
    "isPartner": false, 
    "type": "RequestForInformation", 
    "category": "Devices", 
    "subcategory": "Hardware", 
    "compromiseIndicator": null, 
    "usersOrDevicesImpacted": null, 
    "relatedAlerts": null, 
    "businessImpact": null, 
    "issueFirstNoticed": null, 
    "issueReproduced": null, 
    "endUserSupportEngaged": null, 
    "troubleshootingSteps": null, 
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
}
```

## Example 2: Create a support ticket to request a change

### Request a change

The following is an example of the HTTP request.

```http
POST https://mmdls.microsoft.com/support/odata/v1/tickets
```

The following is an example of the JSON request.

```json
{ 
    "title": "Title", 
    "description": "Description of ticket", 
    "type": "ChangeRequest", 
    "category": "Devices", 
    "subcategory": " Deployment groups assignment", 
    "severity": 4, 
    "contact": { 
        "givenName": "John", 
        "surname": "Doe", 
        "email": "jd@contoso.com", 
        "phoneNumber": "phone number"
    } 
}
```

### Request a change response

The following is an example of the JSON response.

```json
{ 
    "@odata.context": "https://mmd-support-prod-nam.trafficmanager.net/odata/v1/$metadata#Tickets/$entity", 
    "title": "Title", 
    "description": "Description", 
    "isPartner": false, 
    "type": "ChangeRequest", 
    "category": "Devices", 
    "subcategory": " Deployment groups assignment", 
    "compromiseIndicator": null, 
    "usersOrDevicesImpacted": null, 
    "relatedAlerts": null, 
    "businessImpact": null, 
    "issueFirstNoticed": null, 
    "issueReproduced": null, 
    "endUserSupportEngaged": null, 
    "troubleshootingSteps": null, 
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
}
```

## Example 3: Create a support ticket for an incident

### Incident support ticket request

The following is an example of the HTTP request:

```http
POST https://mmdls.microsoft.com/support/odata/v1/tickets
```

The following is an example of the JSON request:

```json
{ 
    "title": "Title", 
    "description": "Description of ticket", 
    "type": "Incident", 
    "category": "Devices", 
    "subcategory": "Configuration/Policy", 
    "usersOrDevicesImpacted": 100, 
    "businessImpact": "Business Impact", 
    "issueFirstNoticed": "2021-10-06T07:00:00Z", 
    "issueReproduced": true, 
    "endUserSupportEngaged": true, 
    "troubleshootingSteps": "Describe any troubleshooting steps performed.", 
    "severity": 4, 
    "contact": { 
        "givenName": "John", 
        "surname": "Doe", 
        "email": "jd@contoso.com", 
        "phoneNumber": "+1 888" 
    } 
}
```

### Incident support ticket response

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
}
```
