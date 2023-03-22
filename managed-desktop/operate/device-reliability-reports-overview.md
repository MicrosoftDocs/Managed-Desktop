---
title: Device reliability reports overview
description: Provides the necessary insights for IT admins to better understand the impact of operating system stop errors on managed devices
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
msreviewer: vigandhi
ms.date: 03/24/2023
---

# Device reliability reports overview (public preview)

> [!IMPORTANT]
> This feature is in **public preview**. The feature is being actively developed, and may not be complete. You can test and use these features in production environments and provide feedback.

The Device reliability reports provide the necessary insights for IT admins to better understand the impact of operating system stop errors on Microsoft Managed Desktop managed devices.

Microsoft Managed Desktop monitors operating system stop error codes on managed devices by using:

- A 97% stop error-free device threshold
- Anomaly detection over a 90-day period
    - Anomaly detection is used to detect unusual patterns in the daily total number of stop errors in each tenant.
        - Anomaly detection divides the data into trend and seasonality categories to predict the total number of stop errors in each customer's tenant. By comparing the predicted and actual stop errors that occur, the anomaly detection score is calculated and normalized.
        - The threshold that determines the Anomaly or Not Anomaly label is reviewed and adjusted periodically based on the observed failure impact data. Any anomaly detection scores with absolute scores above the threshold are considered anomalies and will be investigated.

Automated alerts raise a Service Raised Incident (SRI) which is assigned to the Microsoft Managed Desktop Service Engineering Team for investigation and troubleshooting. The Microsoft Managed Desktop Service Engineering Team will work to evaluate and remediate issues that are under Microsoft control.

If customer engagement is needed to remediate issues, the Microsoft Managed Desktop Service Engineering Team will reach out to [admin contacts](../prepare/add-admin-contacts.md) to expedite the remediation process.

> [!NOTE]
> Periodic updates are made to the threshold using a data-driven approach that optimizes the balance between the number of individual incidents addressed by Microsoft and the number of resolved failure cases. If appropriate, fixes for stop errors may be applied to the across all Microsoft Managed Desktop customers' tenants.

## View the Device reliability reports

**To view the Device reliability reports:**

1. Go to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Reports**.
3. Navigate to **Microsoft Managed Desktop** > **Device health**.
