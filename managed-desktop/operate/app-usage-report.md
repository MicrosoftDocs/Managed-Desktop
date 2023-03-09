---
title: App usage report
description: How to use the app usage report
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
ms.author: tiaraquan
manager: dougeby
ms.topic: conceptual
ms.date: 12/06/2022
---

# App usage report

This report helps you understand how applications are being used across your Microsoft Managed Desktop devices. It can also act as a reference to help you assess any effect on your users when application issues are discovered.

**To view the App usage report:**

1. Go to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).
1. Select **Reports**.
1. Navigate to **Microsoft Managed Desktop** > **Managed devices**. Then, select the **Reports** tab.
1. Select **Application usage**.

## Report information

| Column name | Description |
| ------ | ------ |
| Application name | Applications with any amount of reported usage will appear in this list. |
| Foreground usage | Time spent interacting with the foreground application shown in hours. |
| Average weekday usage | Average usage per device excluding weekends.
| Device count | The number of reporting devices contributing to usage per application.
| % of reporting devices | The percentage of total reporting devices that have used this application.

> [!IMPORTANT]
> For devices to report data, they must be set to the Optional diagnostic data level. Learn more about [how Microsoft Managed Desktop uses Windows diagnostic data](../overview/privacy-personal-data.md).
