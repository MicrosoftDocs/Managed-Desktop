---
title: Exceptions to the service plan
description: How to request exceptions to the standard service plan
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.date: 03/10/2023
---

# Exceptions to the service plan

Microsoft Managed Desktop provides [device requirements](../prepare/device-requirements.md), [standard device policies](../operate/device-policies.md), [application requirements](../prepare/app-requirements.md), and certain [configurable settings](../operate/config-setting-overview.md)—all designed to provide a secure, productive, and pleasant experience for users.  

It's best to always stay with the service as provided. However, we recognize that some details of the service might not fit exactly with your organization's needs. If you feel you need to alter the service in some way, it's important that you understand the following processes to request those changes:

- [Exception acceptance criteria](#exception-acceptance-criteria)
- [Exception types](#exception-types)
- [Request an exception](#request-an-exception)
- [Exception request evaluation process](#exception-request-evaluation-process)
- [Revoking approval for an exception](#revoking-approval-for-an-exception)

## Exception acceptance criteria

The service team will review exceptions to ensure exceptions don’t violate any of the following conditions or criteria:  

- Exceptions can’t adversely affect or reduce system security.
- Exception maintenance and management can’t incur a significant cost for Microsoft Managed Desktop operations or support.
- Exceptions can’t affect system stability or reliability. For example, exceptions can’t cause the kernel mode to crash or stop responding.
- Exceptions can’t restrict Microsoft Managed Desktop from operating the service or conflict with core [Microsoft Managed Desktop technologies](../overview/operating-system.md).
- Exceptions can't involve personalizing the user experience, such as changing the Start menu or Taskbar.

Exception acceptance criteria could change in the future. If such changes occur, 30 days' notice will be provided prior to those conditions coming into effect. If Microsoft Managed Desktop delivers an alternative way to meet an approved exception, Microsoft Managed Desktop will notify you should Microsoft Managed Desktop alter the way it supports the exception.

## Exception types

An exception is any addition or change to the Microsoft Managed Desktop base configuration. Examples range from USB port configuration to deploying a new device driver.

| Exception types | Description |
| ----- | ----- |
| Productivity software | Foreground software needed by users, restricted by the [application requirements](../prepare/app-requirements.md). |
| Security agents | Software used to secure, monitor, or change the behavior of the device or network, for example, third-party antivirus agents. |
| Digital experience monitoring | Software used to track data on an end user's device to report to IT. For more information about our data platform and privacy compliance, see [privacy](../overview/privacy-personal-data.md).|
| Policies | <ul><li>Windows 10</li><li>Windows 11</li><li>Microsoft 365 Apps for enterprise settings on a managed device. For more information on Microsoft 365 Apps for enterprise settings, see [settings managed by Microsoft Managed Desktop](../operate/m365-apps.md#settings-managed-by-microsoft-managed-desktop) and [settings you manage](../operate/m365-apps.md#settings-you-manage).</li></ul> |

## Request an exception

You can submit an exception request through the Intune admin center by [creating a Change request](../operate/support-request.md). Be sure to include the following details:

| Change request detail | Description |
| ----- | ----- |
| Exception type | Which type of exception is it? For more  information, see the [exception types](#exception-types). |
| Requirement | What is the specific business requirement for the exception? |
| Proposal | Which solution is your business requesting? |
| Timeline | How long do you want this exception to last? |

## Exception request evaluation process

When we review exception requests, we assess the following factors in this order:  

1. Some applications and policies which Microsoft Managed Desktop deploys to all devices aren't negotiable. Your request must not affect those applications and policies. For more information, see [device configuration](../operate/device-policies.md).  
2. Restricted productivity software required by a user to do their job will be considered along with the [exception acceptance criteria](#exception-acceptance-criteria).  
3. If we can't meet your requirement using Microsoft technology, your request will be considered alongside the [exception acceptance criteria](#exception-acceptance-criteria).  

The previous principles ensure that Microsoft Managed Desktop can always meet your needs while tracking deviations from our standard template.  

## Revoking approval for an exception

We reserve the right to revoke any exceptions. After a requested exception is approved and deployed, it's possible we might discover problems that violate the [acceptance criteria](#exception-acceptance-criteria) that weren't clear when we initially approved the exception. In this situation, we might have to revoke approval for the exception.  

If we must revoke approval for the exception, we'll notify you by using the Microsoft Intune admin center. From the first time we notify you, you have 90 days to remove the exception before the devices with the exception are no longer bound by Microsoft Managed Desktop service level agreements.  

We'll send you several notifications according to the following timeline. However, a severe incident or threat might require us to change the timeline of our decisions about an exception. We won't remove an exception without your consent. However, any device, with a revoked exception that is deployed and enforced, will no longer be bound by our service level agreement.

The following table is the timeline of notifications we'll send you:

| Notice type | Days | Description |
| ----- | ----- | ----- |
| First notice | - | We’ll provide the following information in the first notice:<br><ul><li>Information about why we're revoking it</li><li>The actions we recommend that you take</li><li>The deadline for those actions</li><li>Steps to follow if you want to appeal the decision</li></ul><p>This notice occurs 90 days in advance before the exception must be removed from all devices.</p> |
| Second notice (30 days later) | 30 days later | We’ll provide a second notice, including the same information provided in the first notice. |
| Third notice (60 days after the first notice) | 60 days after the first notice | We’ll provide a third notice, including the same information provided in the first notice. |
| Final notice (One week before the 90-day deadline) | One week before the 90-day deadline | We’ll provide a fourth notice, including the same information provided in the first notice. |
| 90 days after the first notice | - | Microsoft Managed Desktop service level agreements no longer apply to any devices that have the revoked exception. At any time, you can challenge the decision and provide more information for consideration, including upgrade, configuration changes, or change of software. |
