---
title: Prepare printing resources
description:  Important steps to make sure printing work smoothly
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier2
manager: dougeby
ms.topic: how-to
audience: Admin
ms.date: 12/06/2022
---

# Prepare printing resources

As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment. You have three options:

| Option | Description |
| ------ | ------ |
| Deploy the Microsoft Universal Print solution | The Microsoft Universal Print solution to make it easy for Microsoft Managed Desktop devices to discover printers. For more information, see [What is Universal Print](/universal-print/fundamentals/universal-print-whatis). |
| Deploy printers directly by using a custom PowerShell script | Follow the steps in the [Set up local printers](#set-up-local-printers) section. |
| Use a non-Microsoft cloud printing solution | Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices and joined to a Microsoft Entra domain. The solution must meet the software requirements for Microsoft Managed Desktop. For more information, see [Microsoft Managed Desktop app requirements](../prepare/app-requirements.md). |

In all the above options, if the printer drivers aren't available from Microsoft Update or the Microsoft Store, you must obtain them yourself, and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune. For more, see [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)

## Set up local printers

The following instructions assume you've prepared the printing resources and decided to deploy printers using a custom PowerShell script.

**To deploy printers using a custom PowerShell script:**

1. Navigate to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).
1. Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the admin center.
1. Provide the following details:
    - All UNC paths to shared printer locations that must be deployed for Microsoft Managed Desktop devices.
    - User groups that require access to these shared printers.
1. Using the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431), we'll let you know when the request has been completed. Initially we'll only deploy the configuration to devices in the Test deployment group.
1. Test and confirm whether the configuration works as you expect.
1. Reply by using the **Discussion** tab in the support request to let us know when you've completed your testing.
1. We'll then deploy the configuration to the other deployment groups.
