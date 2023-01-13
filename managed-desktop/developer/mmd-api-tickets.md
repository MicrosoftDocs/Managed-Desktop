---
title: Tickets
description: Information about Microsoft Managed Desktop ticket APIs
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

# Tickets

## Methods

| Method  | Return Type | Description |
| --- | --- | --- |
| Get ticket | CustomerTicket | Get details of support ticket. |
| List tickets | CustomerTicket collection | List all support tickets. |
| Create ticket | CustomerTicket | Creates a new support ticket. |

## Properties

### CustomerTicket

| Property | Type | Description |
| --- | --- | --- |
| title | String | Name of the device. |
| description | String | Detailed description of question or issue. |
| isPartner | Boolean | Is a support partner ticket. |
| type | TicketType | Ticket type. |
| category | TicketCategory | Ticket category. |
| subcategory | String  | Ticket subcategory. |
| usersOrDevicesImpacted | Int32 | Number of users/devices impacted. |
| businessImpact | String | Describe business impact |
| issueFirstNoticed  | DateTimeOffset | Time when issue was first noticed. |
| issueReproduced | Boolean | Issue is reproduced on non-Microsoft Managed device. |
| endUserSupportEngaged | Boolean  | End user support was engaged. |
| troubleshootingSteps  | String  | Description of the performed remediation steps. |
| reproSteps | String | Steps to reproduce issue. |
| ID  | String | Ticket ID. |
| severity | Severity Level | Ticket severity. |
| state | Ticket State | Ticket State. |
| createdDateTime | DateTimeOffset | Time of ticket creation. |
| resolvedDateTime | DateTimeOffset | Time of ticket resolution. |
| contact | CaseContact | Case contact object. |
| emails | email collection | List of emails. |
| attachments | attachment collection | List of attachments. |
| notes  | notes collection | List of notes. |

### CaseContact

| Property | Type | Description |
| --- | --- | --- |
| ID | Guid | Unique identifier. |
| givenName | String | First name. |
| surname | String | Last name. |
| email | String | Email address. |
| phoneNumber | String | Phone number. |
