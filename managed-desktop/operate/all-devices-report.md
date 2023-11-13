---
title: All devices report
description: Provides a summary view of the current update status for all devices enrolled into Microsoft Managed Desktop. Used to be called Device status report
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
msreviewer: adnich
ms.date: 12/06/2022
---

# All devices report

The All devices report provides a per device view of the current update status for all Microsoft Managed Desktop enrolled devices.

**To view the All devices report:**

1. Go to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).
1. Navigate to **Reports** > **Microsoft Managed Desktop** > **Windows Quality Updates**.
1. Select the **Reports** tab.
1. Select **All devices report**.

:::image type="content" source="../media/reports/all-devices-report.png" alt-text="All devices report" lightbox="../media/reports/all-devices-report.png":::

> [!NOTE]
> The data in this report is refreshed every 24 hours. The last refreshed on date/time can be seen at the top of the page.

## Report information

The following information is available in the All devices report:

| Column name | Description |
| ----- | ----- |
| Device name | The name of the device. |
| Microsoft Entra device ID | The current Microsoft Entra ID recorded device ID for the device. |
| Serial number | The current Intune recorded serial number for the device. |
| Deployment ring | The currently assigned Microsoft Managed Desktop deployment ring for the device. |
| Update status | The current update status for the device (see [Windows quality update status](../operate/reports.md#windows-quality-update-statuses). |
| Update sub status | The current update sub status for the device (see [Windows quality update status](../operate/reports.md#windows-quality-update-statuses). |
| OS version | The current version of Windows installed on the device. |
| OS revision | The current revision of Windows installed on the device. |
| Intune last check in time | The last time the device checked in to Intune. |

## Report options

The following options are available:

| Option | Description |
| ----- | ----- |
| Search | Use to search by device name, Microsoft Entra device ID or serial number |
| Sort | Select the **column headings** to sort the report data in ascending and descending order. |
| Export | Select **Export devices** at the top of the page to export data from this report into a CSV file. |
| Filter | Select either the **Update status** or **Deployment rings** filters at the top of the report to filter the results. Then, select **Generate report**. |
