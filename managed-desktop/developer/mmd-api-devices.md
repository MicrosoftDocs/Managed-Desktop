---
title: Devices
description: Information about devices registered and managed by Microsoft Managed Desktop.
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

# API Schema

## Devices

Devices registered and managed by Microsoft Managed Desktop.

### Methods

| Method | Return Type | Description |
| --- | --- | --- |
| Get device  | Device | Get a single device object |
| List devices | Device collection | List device collection |

### Properties

| Property | Type | Description   |
| --- | --- | --- |
| name  | String | Name of the device. |
| intuneId | String | Intune identifier for the device. |
| manufacturer | String  | Manufacturer of the device. |
| model | String | Model of the device. |
| serialNumber | String | Serial number of the device. |
| globalDeviceId | String | Unique identifier of the device. |
| enrolledIntoIntuneDateTimeUtc | DateTimeOffset | Enrollment time of the device. |
| tenantId  | Guid | The tenant’s Azure Active Directory Id. |
| assignedUser | String | User assigned to the device. |
| userUpn | String | Username of the assigned user. |
| userEmail | String | Email address of the assigned user. |
| complianceState | String | Compliance state of the device. |
| osVersion | String  | OS version. |
| primaryUpdateRing | String | Primary update ring of the device. Possible values are: `Test`, `First`, `Fast`, `Broad`. |
| lastIntuneSyncDateTimeUtc | DateTimeOffset | The date and time that the device last completed a successful sync with Intune. |
| ageInMonths | Single | Age of device since enrollment. |
| planType | String |  |
| persona  | String | Device profile. Possible values are: `Standard`, `SensitiveData`, `PowerUser`, `Kiosk`, `Starter`. |
| aadDeviceId | Guid | The device’s Azure Active Directory Id. |
| managementAgent | String  | Management channel of the device. |
| operatingSystemEdition | String | Operating system edition. |
| profileAssignmentStatus | String | Status of profile assignment. |
| groups | group collection | List of groups device is assigned to. |
| configurations | configuration collection | List of configuration policies assigned to device. |
