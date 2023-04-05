---
title: Proactive monitoring
description:  Explains how Microsoft Managed Desktop proactively monitors devices for potential issues
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
ms.date: 04/05/2023
---

# Proactive monitoring

Microsoft Managed Desktop monitors, automatically raises Service Raised Incidents (SRI), and remediates issues related to the following issues:

- [Stop errors](#stop-errors)
- [Microsoft Defender Firewall](#microsoft-defender-firewall)
- [BitLocker](#bitlocker)

## Eligible devices

Eligible devices are:

- Devices that must have checked in and synced with Microsoft Intune in the last 24 hours.  
- Evaluated during the observation window. The observation window is every 24 hours.  

## Stop errors

Microsoft Managed Desktop monitors operating system stop errors (displayed as a blue screen) codes on managed devices by using:

- A 97% stop error-free device threshold
- Anomaly detection over a 90-day period
    - Anomaly detection is used to detect unusual patterns in the daily total number of stop errors in each tenant.
    - Anomaly detection divides the data into trend and seasonality categories to predict the total number of stop errors in each customer's tenant. By comparing the predicted and actual stop errors that occur, the anomaly detection score is calculated and normalized.
    - The threshold that determines the Anomaly or Not Anomaly label is reviewed and adjusted periodically based on the observed failure impact data. Any anomaly detection scores with absolute scores above the threshold are considered anomalies and will be investigated.

For more insights about the impact of operating system stop errors on Microsoft Managed Desktop managed devices, see [Device reliability reports](../operate/reports.md#device-health-reports).

## Microsoft Defender Firewall

Microsoft Managed Desktop monitors managed devices that have Microsoft Defender Firewall enabled by using a 95% Firewall Enabled device threshold.

## BitLocker

Microsoft Managed Desktop monitors managed devices with BitLocker enabled by using a 95% BitLocker enabled device threshold.

## Service Raised Incidents (SRIs)

Automated alerts raise a Service Raised Incident (SRI) which is assigned to the Microsoft Managed Desktop Service Engineering Team for investigation and troubleshooting. The Microsoft Managed Desktop Service Engineering Team will work to evaluate and remediate issues that are under Microsoft's control. If your engagement is needed to remediate issues, the Microsoft Managed Desktop Service Engineering Team will reach out to [admin contacts](../prepare/add-admin-contacts.md) to expedite the remediation process.

> [!NOTE]
> Periodic updates are made to the threshold using a data-driven approach that optimizes the balance between the number of individual incidents addressed by Microsoft and the number of resolved failure cases. If appropriate, fixes might be applied across all Microsoft Managed Desktop customers' tenants.

| Question | Answer |
| ----- | ----- |
| When will a Service Raised Incident be created and investigated? | Microsoft Managed Desktop will:<ul><li>Automatically create an internal (non-customer visible) Service Raised Incident (SRI) if the number of devices in your tenant drops below the threshold during each observation window.</li><li>Assign a service engineer to work toward a resolution.</li></ul> |
| What action will Microsoft Managed Desktop drive as part of the investigation? | <ul><li>Engineers will triage, debug, and isolate the failures (hardware or policy) that are most impactful to the devices in your tenant and those that are contributing most to your tenant falling below the threshold.</li><li>Microsoft Managed Desktop service engineers might collaborate with the appropriate Microsoft and/or non-Microsoft partners (if applicable) to advocate on your behalf to provide a solution. The details will be shared with you, including any appropriate actions you must take.</li></ul> |

## Roles and responsibilities

| Microsoft Managed Desktop responsibilities | Your responsibilities |
| ----- | ----- |
| <ul><li>Microsoft Managed Desktop will monitor and create an internally raised case for all devices dropping below the threshold</li><li>Microsoft Managed Desktop will obtain [logs](../references/diagnostic-logs.md) and investigate to determine the scope of failures (hardware or policy) and work to resolve the issues.</li><li>If the failed module is Microsoft owned, or on a Microsoft device, Microsoft Managed Desktop will drive troubleshooting and remediation.</li><li>If the failure is caused by the third-party vendors, Microsoft Managed Desktop will work with you and the software/hardware vendor to assist with troubleshooting and remediation. Microsoft Managed Desktop will support you through this effort and might engage the [Microsoft App Assure team](/windows/compatibility/app-assure), if necessary, for troubleshooting and remediation of third-party applications.</li></ul> | To obtain and deploy a fix, it’s recommended to work with Microsoft Managed Desktop as needed. This might include but isn’t necessarily limited to:<br><ul><li>Working with Microsoft Managed Desktop (on a case-by-case basis) to obtain required information from affected devices.</li><li>Working with Microsoft Managed Desktop and/or non-Microsoft partners to deploy and test solutions provided for affected hardware and software.</li><li>If you need more assistance or need to report an incident, [submit a support request](../operate/support-request.md).</li></ul> |
