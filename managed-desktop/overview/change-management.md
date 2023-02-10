---
title: Change management
description:  Who does what for various change processes
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier2
manager: dougeby
ms.topic: conceptual
ms.date: 12/06/2022
---

# Change management

In the service offering, the balance of responsibility for hardware maintenance and security updates shifts to the service provider (Microsoft) instead of the customer (you). However, you must still ensure that non-Microsoft and custom software continues to function as expected when updates are rolled out.

For on-premises products, your organization assumes all responsibility for managing change.

## Balance of responsibility

| Responsibility | Microsoft Managed Desktop service | Microsoft 365 client software | On-premises clients and servers | Non-Microsoft and custom software
| ----- | ----- | ----- | ----- | ----- |
| Provide new functionality | Microsoft | Microsoft | Both | Customer
| Test new features for quality assurance |  Microsoft | Microsoft | Both | Customer
| Communicate about new features | Both | Both | Both | Customer
| Integrate custom software | Both | Both | Customer | Customer
| Apply security updates | Microsoft | Microsoft | Customer | Customer
| Maintain system software | Microsoft | Microsoft | Customer | Customer
| Package for deployment | Microsoft | Microsoft | Customer | Customer

## Change process overview

Below is a summary of how the change process is shared between Microsoft and customers:

| Scenario | Microsoft's role | Customer's role |
| ----- | ----- | ----- |
| Before a change | <ul><li>Set expectations for service changes.</li><li>Notify customers 5 days in advance for changes that require administrator action.</li><li>For emergency changes, apply a mitigation prior to notifying.</li></ul> | <ul><li>Understand what to expect for changes and communications.</li><li>Read Microsoft Managed Desktop Message Center regularly.</li><li>Review and update internal change management processes.</li><li>Understand, and check compliance with Microsoft Managed Desktop requirements. </li><li>Acknowledge and approve, when required.</li></ul>
| During a change | <ul><li>Release and deploy monthly security and non-security updates for Windows 10 and Office 365 clients.</li><li>Monitor data signals and support queues for impact.</li></ul> | <ul><li>Check the Microsoft Managed Desktop Message Center and review any additional information.</li><li>Take any action required, if applicable, and test applications.</li><li>If a break/fix scenario is experienced, create a support request.</li></ul> |
| After a change | <ul><li>Collect customer feedback to improve rollout of future changes.</li><li>Monitor data signals and support queues for impact.</li></ul> | <ul><li>Work with people in your organization to adopt the change.</li><li>Review change and adoption management processes for opportunities to gain efficiencies.</li><li>Provide general feedback and specific feedback in the admin feedback tool.</li><li>Train users to provide app-specific feedback using the Windows Feedback Hub and the Smile button in Office apps.</li></ul> |

## Change types

There are several types of changes that we make to the service regularly. The communication channel for those changes and the actions you're responsible for vary.

Not all changes have the same effect on your users or require action. Some are planned and some are unplanned. For example, non-security updates and security updates aren't usually planned.

Depending on the type of change, the communication channel may vary. The following table lists the types of changes you can expect for the Microsoft Managed Desktop service.

|  | Functionality | Non-security updates | Security |
| ----- | ----- | ----- | ----- |
| **Type of change** | <ul><li>Feature updates</li><li>New features or applications</li><li>Deprecated features</li></ul> | Client hotfixes for issues | Security updates |
**Advance notice** | Five days notice for changes that require action | No such changes are included in the monthly release | No changes are included in the monthly release |
**Communication channel** | <ul><li>Message Center</li><li>Email alert</li></ul> | <ul><li>Message Center</li><li>Email alert</li></ul> | <ul><li>Message Center</li><li>Email alert</li></ul> |
**Requires global admin action** | Sometimes | Rarely | Rarely |
**Type of action** | Change settings | Communicate changes to users | Change admin settings |
**Requires testing** | Check business applications including remote access services | Sometimes; testing the fix against processes or customizations | Rarely |
**Examples of change** | <ul><li>Feature updates: IT Admin Portal simplified support ticket submission and review</li><li>New features or applications: Semi-Annual release of a Windows 10 feature update</li></ul> | Hotfixes based on customer reported bugs |
