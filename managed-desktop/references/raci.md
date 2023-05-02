---
title: Microsoft Managed Desktop RACI matrix
description: This article lists the RACI matrix for Microsoft Managed Desktop
keywords: RACI, roles, responsibilities 
ms.service: m365-md
ms.sitesec: library
author: tiaraquan
ms.topic: reference
audience: ITPro
manager: dougeby
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.article: reference
ms.localizationpriority: medium
ms.date: 05/02/2023
ms.collection: 
- M365-modern-desktop
- tier3
---

# Microsoft Managed Desktop RACI matrix

## Product and service RACI matrix

### Azure Active Directory (AD)

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Directory management | R-A-C | I
| Group membership management | R-A-C-I | - |
| Deployment ring membership management | R-A-C-I | - |
| Deployment ring creation| C-I | R-A |
| Group creation | R-A-C | I |
| Group removal | R-A-C | I |
| Modern Workplace service account management | C-I | R-A |

### App Assure

The content of App Assure is restricted to only Microsoft Managed Desktop registered devices whenever they're impacted.

For global App Assure issues independent of Windows 10/11 Pro/Enterprise management (Microsoft Managed Desktop or otherwise), consult [App Assure with Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365/app-assure).

#### Microsoft

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Compatibility management | R-C-I | A |
| Issue investigation and remediation | C-I | R-A |

#### Independent software publisher

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Compatibility management | R-C-I | A
| Issue investigation and remediation | C-I | R-A |

#### Customer line of business

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Compatibility management | R-C-I | A
| Issue investigation and remediation | C-I | R-A |

### Driver management

#### Microsoft hardware

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Issue detection | R-C-I | A |
| Issue investigation | C-I | R-A |
| Remediation | C-I | R-A |

#### OEM hardware

Original Equipment Manufacturer (OEM) partner team remediates drivers as hardware is OEM owned. Microsoft offers drivers if published to Windows Update.

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Issue detection | R-C-I | A |
| Issue investigation | C-I | R-A |
| Remediation | R-A* | C-I |

### Exceptions

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Exception request creation| R-A-I | C |
| Exception approval | I | R-A-C |
| Solution definition | C-I | R-A |
| Enforcement | R-A | C-I |
| Deprecation | C-I | R-A |
| Approval revocation | A-C-I | R |

### Log collection

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Device availability | R-A | C-I |
| Analysis | C-I | R-A |
| [Personal data management](../overview/privacy-personal-data.md) | C-I | R-A |
| Data disposal and deletion | C-I | R-A |

### Microsoft Apps for enterprise

Microsoft 365 Apps for enterprise suite defined in the table: Word, Excel, PowerPoint, Outlook, OneNote, Access, Teams, and Publisher.

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Deployment | C-I | R-A |
| Enforcement | I | R-A-C |
| Deployment ring management | R-A-C-I | - |
| Issue detection | R-A | C-I |
| Troubleshooting and remediation| C-I | R-A |

### Microsoft Intune

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Platform management | R-A | C-I |
| Service availability | I | R-A-C |
| Service stability | I | R-A-C |
| Application deployment enforcement | C-I | R-A |
| Profile enforcement | C-I | R-A |

#### Security baseline management

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Enforcement | I | R-A-C |
| Remediation | C-I | R-A |

#### Device enrollment workflow

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Enforcement | R-A | C-I |
| Remediation | C-I | R-A |

#### Device retirement workflow

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Enforcement | R-A | C-I |
| Remediation | C-I | R-A |

### Windows 10/11

Supported areas for functionality, but not client data include:

- Windows Kernel
- Windows customizations enforced by Microsoft Managed Desktop
- Security Baseline
- Compliance
- BitLocker
- Performance Analysis Objects
- Microsoft Edge
- OneDrive
- Quick Assist

#### Platform experience

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Reliability, Stability| I | R-A-C |
| Accessibility | R-A-C | I |

#### Update management

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Enforcement | R-A | C-I |
| Remediation | C-I | R-A |

#### Platform security configuration

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Enforcement | R-A | C-I |
| Remediation | C-I | R-A |

### Microsoft Managed Desktop Windows image

For more information, see [Universal image](../prepare/universal-image.md).

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Customization | R-A | C-I |
| Hardware readiness | R-A | C-I |

#### Maintenance

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Issue reporting | R-A | C-I |
| Remediation | C-I | R-A |

### Workplace profiles

Workplace profiles mainly consist of Cloud printer addition/removal, network drives addition/removal and allow/block list profiles.

#### Cloud printer

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Request | R-A | C-I |
| Solution definition | C-I | R-A |
| Enforcement | R-A | C-I |
| Remediation | C-I | R-A |

#### Network drive

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Request | R-A | C-I |
| Solution definition | C-I | R-A |
| Enforcement | R-A | C-I |
| Remediation | C-I | R-A |

#### Allow/Blocklist

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Request | R-A | C-I |
| Solution definition | C-I | R-A |
| Enforcement | R-A | C-I |
| Remediation | C-I | R-A |

### Deployment scheduling

For more information, see [Software update management](../operate/updates.md).

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Planning | C-I | R-A |
| Communication | I | R-A-C |

### Monthly configuration and security baseline deployment

Microsoft Managed Desktop revises our service driven configuration on a monthly basis, as such certain settings and values will be included and changed.

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C
| Deployment | I | R-A-C |
| Communication | I | R-A-C |

### Windows 10/11 conditional access authentication failures and deviations

Microsoft Managed Desktop monitors spikes of un-approved authentications attempts from Microsoft Managed Desktop devices.

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Monitoring definition | - | R-A-C-I |
| Remediation | I | R-A-C |

### Windows 10/11 device health signals

Health signals include kernel crashes.

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Monitoring definition | - | R-A-C-I |
| Automated remediation| I | R-A-C |
| Customer driven remediation | R-I | A-C |
| Verbose data collection/disposal | C-I | R-A |

### Windows 10/11 storage encryption status

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Monitoring definition | - | R-A-C-I |
| Remediation| I | R-A-C |

### Windows 10/11 update health signals

| Microsoft Managed Desktop reactive operations | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Monitoring definition | - | R-A-C-I |
| Remediation| I | R-A-C |

## Service RACI matrix

### Device profiles

For more information, see [Device profiles](../operate/device-profiles.md).

#### Sensitive device profile

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Enforcement | I | R-A-C |
| Device allocation to profile | R-A-C-I | - |

#### Standard device profile

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Enforcement | I | R-A-C |
| Device allocation to profile | R-A-C-I | - |

#### Power user device profile

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Enforcement | I | R-A-C |
| Device allocation to profile | R-A-C-I | - |

#### Kiosk device profile

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Enforcement | I | R-A-C |
| Device allocation to profile | R-A-C-I | - |

#### Shared device profile

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Definition | I | R-A-C |
| Enforcement | I | R-A-C |
| Device allocation to profile | R-A-C-I | - |

### Exceptions management

Microsoft Managed Desktop assesses and decides if active exceptions are compliant to our monthly baseline or if they conflict with our service offering security standards. For more information, see [Exceptions to the service plan](../overview/exceptions-to-service-plan.md).

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Planning | - | R-A-C |
| Decision management | I | R-A-C |
| Deprecation communication | I | R-A |
| Deprecation enforcement | R-A-C | I |

### Incident management

For more information, see [Submit a support request](../operate/support-request.md).

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Incident creation | R-A | C-I |
| Management and resolution of incidents | C-I | R-A |
| Admin contact(s) maintenance | R-A | C-I |
| Incident management/resolution through collaboration with other Microsoft technology teams | C-I | R-A |
| Major Incident Management and Post Incident Review (PIR) | C-I | R-A |

### Change and release management

For more information, see [Change management](../overview/change-management.md).

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Planning | I | R-A-C |
| Risk assessment | I | R-A-C |
| Deployment | I | R-A-C |
| Control | I | R-A-C |
| Service component changes | I | R-A-C |
| Customer environment changes | R-A | C-I |
| Windows image modernization | I | R-A-C |

### Event management

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| [Monitoring](../overview/privacy-personal-data.md) and [diagnostic data collection](../references/diagnostic-logs.md) | I | R-A-C |
| [Device health reporting](../operate/device-reliability-reports-overview.md) | I | R-A-C |
| Remediation of device health | R-C-I | R-A |

### Device onboarding/off-boarding to/from service

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Autopilot registration | R-A-C-I | - |
| Device enrollment | R-A-C-I | - |
| Device off-boarding | R-A-C-I | - |
| Device administration | R-A-C-I | - |

### Tenant onboarding/off-boarding

| Microsoft Managed Desktop ongoing solution administration/maintenance | You | Microsoft Managed Desktop IT Ops |
| ----- | ----- | ----- |
| Solution definition | - | R-A-C-I |
| Service improvement | - | R-A-C-I |

## Microsoft Managed Desktop Security Operations

| Microsoft Managed Desktop Security Operations | You | Monitoring | Premier support, App Assure, Fast Track |
| ----- | ----- | ----- | ----- |
| [Ensure Microsoft Endpoints for Security Services are accessible](../prepare/readiness-assessment-online.md) | R-A | C-I | - |
| [Configure, manage, and deploy the Microsoft Managed Desktop device security baseline](../operate/config-setting-overview.md) | I | R-A | - |
| [Analyze threat intelligence, monitor and triage endpoint alerts](../overview/security-operations.md) | C-A | R | - |
| [Develop and execute on endpoint mitigation and remediation for detected device incidents](../overview/security-operations.md) | C- I | R-A | - |
| [Request for Information (RFI), Change Request (CR), or other issues that might affect the service](../overview/change-management.md) | R-A | C-I | - |
| [Keep security admin contact list updated](../overview/change-management.md)| R-A | I | - |
| [Microsoft Managed Desktop Service Delivery Kickoff (SDK) - Service awareness training](../prepare/readiness-assessment-online.md) | I | R-A | - |
| [Microsoft Managed Desktop Service awareness and training for security admin contacts](../prepare/readiness-assessment-online.md) | R-A | - | - |
| [Microsoft Managed Desktop provided Service Delivery Metrics and Reporting](../operate/service-metrics-report.md) | I |R-A | I |
| [Microsoft Managed Desktop provided Service Delivery Review sessions (for eligible customers)](../operate/service-metrics-report.md)| I | R-A | I |
| Knowledge management - Microsoft Managed Desktop Docs and Guides | I | R-A | I |
| [Transfer of Microsoft Managed Desktop RFI & CR to other Microsoft Teams](../operate/support-request.md) | C-I |R-A | I |
| [Requesting an exception to the Microsoft Managed Desktop service including justification](../overview/exceptions-to-service-plan.md) | A | R-C | - |
