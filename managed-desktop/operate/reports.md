---
title: Work with reports
description:  The various reports available in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier2
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.date: 12/06/2022
---

# Work with reports

The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor, and investigate issues with your Azure AD organization ("tenant") configuration and devices.

Microsoft Managed Desktop has a section in the **Reports** menu where you can find reports specific to Microsoft Managed Desktop's management of the registered devices. In several locations throughout Microsoft Endpoint Manager, you can filter reports from other product groups. You can include or exclude devices that are managed by Microsoft Managed Desktop.

## Managed devices reports

Microsoft Managed Desktop provides several reports and dashboards. IT admins, in your organization, can use these reports and dashboards to understand various aspects of your devices.

The following reports are available:

| Report | Description |
| ------ | ------ |
| [**Device inventory**](../operate/device-inventory-report.md) | Download a comma-delimited file of the devices' serial number, name, manufacturer, etc. |
| [**Application usage report**](../operate/app-usage-report.md) | This report provides information about typical app usage across your Microsoft Managed Desktop devices. For devices to provide data to this report, they must be set to the Optional diagnostic data level. |
| [**Service metrics report**](../operate/service-metrics-report.md) | This report provides straightforward summaries of key metrics for Microsoft Managed Desktop month over month. |

## Windows quality update reports

The Windows quality update reports provide you information about:

- Quality update device eligibility
- Device update health
- Device update trends  

Together, these reports provide insight into the quality update state and compliance of Windows devices that are enrolled into Microsoft Managed Desktop.  

The report types are organized into the following focus areas:

| Focus area | Description |
| ----- | ----- |
| Operational detail | <ul><li>[Summary dashboard](../operate/summary-dashboard.md): Provides the current update status summary for all devices.</li><li>[All devices report](../operate/all-devices-report.md): Provides the current update status of all devices at the device level.</li></ul> |
| Device trends | <ul><li>[All devices report–historical](../operate/all-devices-historical-report.md): Provides the update status trend of all devices over the last 90 days.</li><li>[Eligible devices report–historical](../operate/eligible-devices-historical-report.md): Provides the update status trend of all eligible devices to receive quality updates over the last 90 days.</li><li>[Ineligible devices report–historical](../operate/ineligible-devices-historical-report.md): Provides a trending view of why ineligible devices haven’t received quality updates over the last 90 days.</li></ul> |

### Who can access the reports?

Users with the following permissions can access the reports:

- Global Administrator
- Intune Service Administrator
- Administrators assigned to an Intune role with read permissions

### About data latency

The data source for these reports is the [Windows diagnostic data](../references/privacy-personal-data.md#microsoft-windows-1011-diagnostic-data). The data typically uploads from enrolled devices once per day. Then, the data is processed in batches before being made available in Microsoft Managed Desktop. The maximum end-to-end latency is approximately 24 hours.

### Windows quality update statuses

The following statuses are used throughout the Microsoft Managed Desktop reporting suite to describe the quality update status for devices:  

- [Healthy devices](#healthy-devices)
- [Not Up to Date (Microsoft Action)](#not-up-to-date-microsoft-action)
- [Ineligible Devices (Customer Action)](#ineligible-devices-customer-action)

Each status has its own set of sub statuses to further describe the status.

#### Healthy devices

Healthy devices are devices that meet all of the following prerequisites:

- [Prerequisites](../prepare/prerequisites.md)
- [Device requirements](../prepare/device-requirements.md)

> [!NOTE]
> Healthy devices will remain with the **In Progress** status for the 21-day service level objective period. Devices which are **Paused** are also considered healthy.

| Sub status | Description |
| ----- | ----- |
| Up to Date | Devices are up to date with the latest quality update deployed through the [Microsoft Managed Desktop release schedule](../operate/windows-quality-update-overview.md#windows-quality-update-releases) |
| In Progress | Devices are currently installing the latest quality update deployed through the [Microsoft Managed Desktop release schedule](../operate/windows-quality-update-overview.md#windows-quality-update-releases) |
| Paused | Devices that are currently paused due to a Microsoft Managed Desktop pause. For more information, see [update deployment](../operate/windows-quality-update-overview.md#pausing-and-resuming-a-release). |

#### Not Up to Date (Microsoft Action)

Not Up to Date means a device isn’t up to date when the:

- Quality update is more than a month out of date, or the device is on last month’s quality update  
- Device is more than 21 days overdue from the last release.

> [!NOTE]
> Microsoft Action refers to the responsibility of the Microsoft Managed Desktop Operations Team to carry out the appropriate action to resolve the reported device state. Microsoft Managed Desktop aims to keep at least 95% of eligible devices on the latest Windows quality update 21 days after release.

| Sub status | Description |
| ----- | ----- |
| No Heartbeat | The Windows Update service hasn’t been able to connect to this device. The service can’t offer the update to that device. |
| Not Offered | The Windows Update service hasn’t offered the update to that device. |
| Policy Blocking Update | This device has a policy that is blocking the update, such as a deferral or pause policy. Devices are only in this state after the 21-day threshold. |
| In Progress—Stuck | This device has downloaded the update but is getting stuck in a loop during the install process. The update isn’t complete. |
| Other | This device isn't up to date and isn’t reporting back data from the client. |

#### Ineligible Devices (Customer Action)

Customer Action refers to the responsibility of the designated customer IT administrator to carry out the appropriate action to resolve the reported device sub status.  

Within each 24-hour reporting period, devices that are ineligible are updated with one of the following sub statuses.

| Sub status | Description |
| ----- | ----- |
| Insufficient Usage | Devices must have at least six hours of usage, with at least two hours being continuous. |
| Low Connectivity | Devices must have a steady internet connection, and access to [Windows update endpoints](../prepare/network.md). |
| Out of Disk Space | Devices must have more than one GB (GigaBytes) of free storage space. |
| Not Deployed | Microsoft Managed Desktop doesn't update devices that haven't yet been deployed. |
| Not On Supported on Windows Edition | Devices must be on a Windows edition supported by Microsoft Managed Desktop. For more information, see [prerequisites](../prepare/prerequisites.md). |
| Not On Supported Windows Build | Devices must be on a Windows build supported by Microsoft Managed Desktop. For more information, see [prerequisites](../prepare/prerequisites.md). |
| Intune Sync Older Than 5 Days | Devices must have checked with Intune within the last five days. |

## Data export

Select **Export devices** to export data for each report type.  

> [!NOTE]
> You can’t export Microsoft Managed Desktop report data using Microsoft Graph RESTful web API.

## Endpoint analytics

Microsoft Managed Desktop is now integrated with [Endpoint analytics](/mem/analytics/overview). These reports give you insights for measuring how your organization is working and the quality of the experience delivered to your users. You can find Endpoint analytics in the **Reports** menu of [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). To pivot a score to only include devices being managed by Microsoft Managed Desktop, go to any report, select the **Filter** dropdown, and then select **Microsoft Managed Desktop devices**.

If Endpoint analytics weren't automatically configured for your Azure AD organization ("tenant") during enrollment, you can do that yourself. For more information, see [Onboard in the Endpoint analytics portal](/mem/analytics/enroll-intune#bkmk_onboard). You can enroll all of your devices, or, if you want to include only Microsoft Managed Desktop devices, select the **modern workplace device** groups for Test, First, Fast, and Broad. These reports might require different permissions. For more information, see [Permissions](/mem/analytics/overview#permissions) to ensure you have roles appropriately assigned.

> [!NOTE]
> To better respect user privacy, there must be more than 10 Microsoft Managed Desktop devices enrolled with Endpoint analytics to use this filter.

## Intune reports

Microsoft Intune is one of the services we use to manage devices on your behalf.

In some cases, it can be helpful to use Intune reports to specifically monitor administration of your Microsoft Managed Desktop devices. You can exclude the devices we manage from the report you use to manage other devices. The following reports let you filter capability to include or exclude Microsoft Managed Desktop devices.

- [All devices](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [Device compliance](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [Noncompliant devices](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports. To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).

## Microsoft Managed Desktop inventory data

In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop. In Microsoft Endpoint Manager, navigate to the **Devices** section, under Microsoft Managed Desktop, select **Devices** and use the **Export all** tab to [download a detailed inventory report](../operate/device-inventory-report.md).
