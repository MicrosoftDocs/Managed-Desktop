---
title: Elevation requests
description: Information about the methods and properties of elevation requests
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/26/2022
ms.collection: 
- M365-modern-desktop
- tier2
---

# Elevation Requests

## Methods

| Method | Return Type | Description  |
| --- | --- | --- |
| Get elevation request| Elevation request | Get details of an elevation request. |
| List elevation requests  | Collection of elevation requests | List all elevation requests. |
| Create elevation request | Elevation request | Creates a new elevation request.|
| Close elevation request  | Elevation request | Closes elevation request. |

## Properties

### ElevationRequest

| Property | Type | Description |
| --- | --- | --- |
| id | Guid | Elevation request id. |
| requestingAgentUpn | String | Upn of user requesting elevation. |
| partnerTicketId | String  | Ticket id of support ticket linked to elevation request. |
| deviceName | String  | Device name.|
| title | String | Title. |
| category | String | Request category. |
| subcategory | String | Request subcategory. |
| planOfAction | String | Plan of action to resolve case. |
| actionsTaken | String | Actions taken to resolve case. |
| closingAgentUpn | String | Upn of user closing elevation request. |
| requestCreationTime  | DateTimeOffset | Request creation time. |
| requestClosureTime  | DateTimeOffset | Request closure time.                                    |
| viewerUpns | Collection | List of user Upns that have viewed password. |
| passwordLastUpdatedTime | DateTimeOffset | Last time password was updated on device. |
