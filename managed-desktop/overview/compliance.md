---
title: Compliance
description:  This article lists the compliance standards relevant to Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
- essentials-compliance
ms.author: tiaraquan
manager: dougeby
ms.topic: conceptual
ms.date: 03/10/2023
---

# Compliance and security controls

This article helps you to understand how your organization complies with the various compliance requirements and security standards.

## Compliance

### Compliance coverage

Microsoft Managed Desktop has achieved the following compliance certifications:

- [ISO 27001 Information Security Management Standards (ISMS)](/compliance/regulatory/offering-ISO-27001)
- [ISO 27701 Privacy Information Management System (PIMS)](/compliance/regulatory/offering-iso-27701)
- [ISO 27017 Code of Practice for Information Security Controls](/compliance/regulatory/offering-ISO-27017)
- [ISO 27018 Code of Practice for Protecting Personal Data in the Cloud](/compliance/regulatory/offering-ISO-27018)
- [ISO 9001 Quality Management Systems Standards](/compliance/regulatory/offering-ISO-9001)
- [ISO 20000-1 Information Technology Service Management](/compliance/regulatory/offering-ISO-20000-1-2011)
- [ISO 22301 Business Continuity Management Standard](/compliance/regulatory/offering-ISO-22301)
- [Cloud Security Alliance (CSA) STAR attestation](/compliance/regulatory/offering-CSA-STAR-Attestation)
- [Cloud Security Alliance (CSA) STAR certification](/compliance/regulatory/offering-CSA-Star-Certification)
- [Service Organization Controls (SOC) 1, 2, 3](/compliance/regulatory/offering-SOC)
- [Information Security Registered Assessor Program (IRAP)](/compliance/regulatory/offering-ccsl-irap-australia)
- [Payment Card Industry (PCI) Data Security Standard (DSS)](/compliance/regulatory/offering-PCI-DSS)
- [Health Insurance Portability and Accountability Act (HIPAA)](/compliance/regulatory/offering-hipaa-hitech)
- [Health Information Trust Alliance (HITRUST) Common Security Framework (CSF)](/compliance/regulatory/offering-hitrust)

### Auditor reports and compliance certificates

You can find relevant information, including control and technical requirements, in the [Service Trust Portal (STP)](https://servicetrust.microsoft.com/). This portal is the central repository for information about Microsoft Cloud Service offerings. You can download auditor reports, compliance certificates, and more from the [Audit Reports](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide) section of STP.

> [!NOTE]
> Because Microsoft Managed Desktop runs on Azure, relevant documents usually have file names such as "Microsoft Azure, Dynamics 365, and other Online Services". In those documents, you can usually find Microsoft Managed Desktop under the category "Microsoft Online Services" or "Monitoring + Management".

## Security controls

### Device control

All Microsoft Managed Desktop personnel use approved devices for managing the service and accessing managed tenants. These devices are dedicated to production operations and require multi-factor authentication, have their own specialized identity, monitoring, and hardening. Additionally, these special-use devices have controls to prevent devices from being shared by engineers.  

### People control

Microsoft Managed Desktop maintains and updates a record of authorized personnel access to Microsoft systems containing customer data. All service engineers must comply with standard Microsoft security policies and practices. These include regular mandatory training (security, identity, privacy, and compliance) and recurring background and security checks.

Engineers don't retain continued access to production systems or customer data. All-access is time limited and must be renewed by the individual, with mandatory management review and approval. All entitlements are subject to a quarterly access review.

Microsoft Managed Desktop has processes with the assigned owners that we use to grant, alter, and cancel access authorization to data and resources. For instance, if a Microsoft Managed Desktop staff member leaves the team, their credentials are revoked in a timely manner.

Access to any of the interactive service accounts is restricted to the context of a support request and is limited to service engineers using these devices. Requests and usage of these accounts can only originate from a Microsoft secure access workstation.

### Privileged access management control

While handling a support request, it's possible that service engineers may need to access your tenant. To do so, access to a specific directory role must be requested. If approved, a guest account is granted those permissions for a maximum of eight hours. This approach enables the association of specific users with all actions taken within a tenant.

### Service account control

All Microsoft Managed Desktop service account credentials are stored in a secured Azure Key Vault. The credentials are randomly generated and rotate every 13 days, or 30 mins if used in the interim period. You can [request the audit log through Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md). All “Just-In-Time” use is audited, and the audit log contains the details of the service requests by the Microsoft Managed Desktop Service Engineering team and is stored for 365 days in Azure.

For more information, see the **Microsoft Managed Desktop – data storage, usage, and security practices** document in the [Service Trust Portal (STP)](https://servicetrust.microsoft.com/).
