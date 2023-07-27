---
title: What is Microsoft Managed Desktop?
description:  Information about the service is and shortcuts to articles
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
audience: ITpro
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
ms.custom: intro-overview
ms.author: tiaraquan
manager: dougeby
ms.topic: conceptual
ms.date: 03/10/2023
---

# What is Microsoft Managed Desktop?

> [!IMPORTANT]
> As we enter a new growth phase for managed services at Microsoft, **Microsoft Managed Desktop will transition to end-of-life (EOL) on July 31, 2024**. We're committed to working closely with each customer to provide support and guidance to make the transition as smooth as possible. If you have any questions, concerns, or need assistance, [submit support request](../operate/support-request.md).

Microsoft Managed Desktop is a cloud-based device management service that brings together Microsoft 365 Enterprise (including Windows 10/11 Enterprise, and Office apps) and delivers the following functionalities:  

- Device provisioning  
- Device configuration and management
- IT service management (ITSM) and operations  
- Security monitoring and response

## Key features and services

- Implement and maintain a [four deployment ring, staged and sequenced device management solution](../operate/updates.md#microsoft-managed-desktop-deployment-rings)
- Devices are kept up to date with the latest monthly Windows quality updates for Windows 10 and Windows 11
- Users will enjoy the latest versions of Windows 10, Windows 11, and Microsoft 365 Apps for enterprise
- Monitor managed devices 24 hours a day, seven days a week for security issues

## Features, capabilities and services

Microsoft Managed Desktop provides the following services, features, and capabilities:

- Vendor-registered devices. New OEM-supplied devices can directly be shipped to end users and managed by the service without customer IT involvement.
- Security baseline to keep users and devices secure according to Microsoft’s best practices.
- Modern device provisioning through Windows Autopilot to provide:
    - A seamless and curated user experience with minimal downtime  
    - Integrated device configuration and management via Microsoft Endpoint Manager, Azure Active Directory, Autopilot, and Intune
    - Device naming
    - Device configuration
- Service management and operational support by a dedicated team of [service engineers and delivery managers](../overview/support-teams.md#service-engineering-team)
- Device security monitoring and remediation services through a [dedicated team of security specialists](../overview/support-teams.md#security-operations-center-team)
- Proactive management of the most secure and stable versions of Windows 10/11 and Microsoft 365 Apps for enterprise  
- Service integration with the Microsoft App Assurance program to diagnose and remediate application compatibility issues

## Benefits

- Technical and operational support from Microsoft experts  
- Reduced resource requirements to administer and manage Windows updates and security configurations  
- Visibility into device and app performance
- Early warning of security issues from the service

## Service plan description

For details about the specific services included with Microsoft Managed Desktop, see the following articles:

| Service | Description|
| ----- | ----- |
| [Supported regions and languages](../overview/regions-languages.md)| Explains which regions and languages are supported with the service. |
| [Device requirements](../prepare/device-requirements.md) | Instead of your IT department researching and figuring out if a device is compatible with the service, we've provided specific hardware and software requirements, tools, and processes so you can choose devices, or work with a partner, with confidence.<p>You can find recommended devices by filtering for Microsoft Managed Desktop on the [Shop Windows Pro business devices site](https://www.microsoft.com/windows/business/devices). You can either obtain devices yourself, work with a partner, or reuse devices you already have. Registering devices is easy and straightforward. Before they're deployed, you can also customize certain aspects of the device experience for your users.</p><p>For more information, also see:<ul><li>[Device images](../prepare/device-images.md)</li><li>[Request device name changes](../operate/request-device-name-change.md)</li></ul> |
| [Device images](../prepare/device-images.md) | We provide universal images for [reimaging](../operate/recover-devices.md#reimage-the-device), [break and fix](../operate/recover-devices.md#break-and-fix), and other scenarios. Driver management and injection are your responsibilities.<ul><li>[Universal image](../prepare/universal-image.md)</li><li>VHDX image<ul><li>To enable rapid testing and validation of the Microsoft Managed Desktop platform in your Hyper-V environment, you'll need a VHDX file. To obtain the VHDX file, [submit a support request](../operate/support-request.md).</li></ul></li><li>[Recover devices](../operate/recover-devices.md)</li></ul> |
| [Device services](../overview/device-services.md)| Specifies the device-related services that Microsoft will provide to subscribers. |
| [Device configuration](../operate/device-policies.md) | Clarifies the default and security-related Mobile Device Management policies that the service will apply to enrolled devices. |
| [Security](../overview/security-technologies.md) | Specifies the following:<ul><li>Data collected from enrolled devices</li><li>The features and policies related to device security, identity and access management, network security, and information security.</li></ul> |
| [Updates](../operate/updates.md) | Describes the various [deployment rings](../operate/updates.md#microsoft-managed-desktop-deployment-rings) that Microsoft Managed Desktop uses to roll out updates to your devices.<p>Microsoft Managed Desktop sets up and manages all aspects of [deployment rings](../operate/updates.md#microsoft-managed-desktop-deployment-rings) for Windows 10/Windows 11 quality and feature updates, anti-virus definitions, and Microsoft 365 Apps for enterprise updates.</p><p>We use deployment rings to ensure operating system updates and policies are rolled out in a safe manner. During deployment, Microsoft Managed Desktop monitors for signs of failure, or disruption based on diagnostic data and the user support system to assure that registered devices are always up to date, minimizing disruptions, and freeing your IT department from that ongoing task.</p> |
| [Application requirements](../prepare/app-requirements.md) | Describes the types of apps and behaviors allowed in Microsoft Managed Desktop, and the division of roles and responsibilities for app deployment and management.<p>As part of Microsoft 365 Enterprise, Microsoft provides and manages several key Microsoft apps for you.</p><p>However, you may also have other apps that you need for your business. Instead of your IT department having to test, package, and deploy those apps, Microsoft helps you deploy them through the [FastTrack program](https://www.microsoft.com/FastTrack).</p><p>Additionally, [Microsoft's App Assure program](/fasttrack/products-and-capabilities#app-assuree) can help remediate any app compatibility issues that arise when migrating to the latest versions of our products.</p><p>For more information about apps, see:<ul><li>[Prepare apps](../prepare/apps.md)</li><li>[Deploy apps to devices](../deploy/deploy-apps.md)</li><li>[Autopilot into co-management](../prepare/autopilot-co-management.md)</li></ul> |
| Device monitoring | We help maintain the security of your devices with a dedicated security operations center that monitors your devices and uses data from the unique threats that Microsoft analyzes each month. These security features are built in instead of added on later.<p>We also monitor device health and provide you with insights about device performance.</p>|
| [Change management](../overview/change-management.md) | Explains how change management works with Microsoft Managed Desktop and includes standard procedures for requesting and preparing for changes in the deployment. |
| [Proactive monitoring](../operate/proactive-monitoring.md) | Explains how Microsoft Managed Desktop proactively monitors and remediates issues related to stop errors, Microsoft Defender Firewall, and BitLocker. |
| [Support requests and management](../operate/support-request.md) | Clarifies the support Microsoft provides for your organization and users. |

If you're ready to come on board, contact your local account team.

## More information

For more information about the value of Microsoft Managed Desktop, including customer stories, see the following resources:

- [Microsoft Managed Desktop homepage](https://aka.ms/mmd)
- [Microsoft Managed Desktop blog](https://techcommunity.microsoft.com/t5/microsoft-managed-desktop-blog/bg-p/MicrosoftManagedDesktop)
- [Roadmap](https://aka.ms/AA6jiam)
- [Forrester Total Economic Impact case study](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/intro/downloads/forrester-tei-study.pdf)
- Downloadable [one-page summary](https://aka.ms/AA6ob3h)

| Information | Description |
| ----- | ----- |
| Overview | The articles in this section, but not limited to, detail the division of roles and responsibilities between your organization and Microsoft, technologies used in Microsoft Managed Desktop, and how the service fits into a broader strategy as part of the ITIL framework.<br><ul><li>[Privacy](../overview/privacy-personal-data.md)</li><li>[Compliance](../overview/compliance.md)</li><li>[Microsoft Managed Desktop roles and responsibilities](../overview/roles-and-responsibilities.md)</li><li>[Microsoft Managed Desktop technologies](../overview/operating-system.md)</li><li>[Microsoft Managed Desktop and ITIL](../overview/MMD-and-ITSM.md)</li></ul> |
| Prepare | The articles in this section describe the mandatory steps to enroll your tenant in Microsoft Managed Desktop, including, but not limited to:<ul><li>[Infrastructure requirements](../prepare/prerequisites.md)</li><li>[Device requirements](../prepare/device-requirements.md)</li><li>[Prepare your network](../prepare/on-premise-resources.md)</li><li>[Enroll your tenant](../prepare/enroll-your-tenant.md)</li><li>[Access the admin center](../prepare/access-admin-center.md)</li></ul> |
| Deploy | Once your tenant is enrolled in Microsoft Managed Desktop, this section includes, but not limited to, the following articles:<ul><li>[First-run experience with Autopilot and the Enrollment Status Page](../deploy/esp-first-run.md)</li><li>[Assign and communicate how to use the Company Portal](../prepare/adjust-management-settings.md)</li><li>[Get your users ready to use devices](../deploy/get-started-devices.md)</li><li>[Deploy apps to devices](../deploy/deploy-apps.md)</li></ul> |
| Operate | This section includes the following, but not limited to, articles about operating with the Microsoft Managed Desktop service: <ul><li>[Software update management overview](../operate/updates.md)<li>[Move devices in between deployment rings](../operate/updates.md#move-devices-in-between-deployment-rings)</li><li>[Change device profiles](../operate/change-device-profile.md)</li><li>[Work with reports](../operate/reports.md)</li>[Recover devices](../operate/recover-devices.md)</li><li>[Get end user support](../operate/end-user-support.md)</li><li>[Submit a support request](../operate/support-request.md)</li></ul>|
| What's new | To keep up with what's new in Microsoft Managed Desktop, see the What's new section. |
