---
title: Core applications
description:  This article lists the core apps used in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier2
ms.author: tiaraquan
manager: dougeby
ms.topic: conceptual
ms.date: 12/06/2022
---

# Core applications

## Office 365 E3 or E5

The following apps are included in Microsoft Managed Desktop

| Product | Information |
| ----- | ----- |
| Microsoft 365 Apps for enterprise (64-bit) | The following Office applications will be shipped with the device:<br><ul><li>Word</li><li>Excel</li><li>PowerPoint</li><li>Outlook</li><li>Publisher</li><li>Access</li><li>Skype for Business</li><li>OneNote</li></ul><br>The 64-bit full versions of Microsoft Project and Microsoft Visio aren't included. However, since the installation of these applications depends on the Microsoft 365 Apps for Enterprise installation, Microsoft Managed Desktop created default Microsoft Intune deployments, and security groups that you can use to deploy these applications to licensed users. For more information, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../operate/project-visio.md). |
| OneDrive | Azure Active Directory Single Sign On is enabled for users when they first sign in to OneDrive.<br><br>Known Folder Redirection for Desktop, Document, and Pictures folders are included. These folders are enabled and configured by Microsoft Managed Desktop. |
| Store Apps | Microsoft Sway and Power BI aren't shipped with the device. These apps are available for download from Microsoft Store. |
| Win32 Applications | Teams isn't shipped with the device, but it's packaged and provided by Microsoft for Microsoft Managed Desktop devices. Azure Information Protection Client isn't shipped with the device, but you can have it packaged for deployment. |
| Web Applications | The following web applications aren't shipped with the device: <ul><li>Yammer</li><li>Office in a browser</li><li>Delve</li><li>Flow</li><li>StaffHub</li><li>Power Apps</li><li>Planner</li></ul> <br>Users can access the web version of these applications with a browser. |
