---
title: Virtual device registration
description: Register virtual devices to be managed by Microsoft Managed Desktop
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: how-to
audience: Admin
---

# Virtual device registration

## Cloud PC - Windows 365 Enterprise Workloads

Microsoft Managed Desktop on Windows 365 workloads brings the management experience of your traditional Microsoft Managed Desktop workloads onto your Cloud PCs via Windows 365. With a streamlined admin management experience, enterprise admins can now automatically provision their Windows 365 workloads to be managed by Microsoft Managed Desktop with a single provisioning policy in their Windows 365 portal.

### Deploy Microsoft Managed Desktop on a Windows 365 Provisioning Policy

For general guidance, see [Create a Windows 365 Provisioning Policy](/windows-365/enterprise/create-provisioning-policy).

**To deploy Microsoft Managed Desktop on a Windows 365 Provisioning Policy:**

1. Go to the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) admin center.
1. In the left pane, select **Devices**.
1. Navigate to Provisioning > **Windows 365**.
1. Select Provisioning policies > **Create policy**.
1. Provide a policy name and select **Join Type**. For more information, see [Device join types](/windows-365/enterprise/identity-authentication#device-join-types).  
1. Select **Next**.
1. Choose the desired image and select **Next**.
1. Under the **Microsoft managed services** section, select **Microsoft Managed Desktop**. Then, select **Next**. Microsoft Managed Desktop isn't supported on Hybrid Azure AD workloads. If selected, the *Microsoft Managed Desktop is not currently supported with Hybrid Azure AD join. To change the join type, go to the General tab, then select Azure AD join* message appears.
1. Select your **Microsoft Managed Desktop profile**. Then, select **Next**.
1. Assign your policy accordingly and select **Next**.
1. Select **Create**. Now your newly provisioned Windows 365 Enterprise Cloud PCs will automatically be enrolled and managed by Microsoft Managed Desktop.

## Configurations which vary from the Microsoft Managed Desktop baseline

| Application | Explanation |
| ----- | ------ |
| Microsoft Teams | Deployment of Microsoft Teams by Microsoft Managed Desktop is excluded to allow for clients with native-optimized Teams. |

| Configuration | Explanation |
| ----- | ------ |
| BitLocker | No BitLocker enforcement. Windows 365 uses [Azure Storage server-side encryption (SSE)](/windows-365/enterprise/encryption). |
| Device compliance | Removed requirement for a Trusted Platform Module (TPM) from the Microsoft Managed Desktop managed device compliance policy as a TPM is not mandated on Cloud PC devices and hence may not always be available. |
| RDP settings | Enabled Remote Desktop Protocol (RDP) on virtual devices. |
| Firewall rules | Enable port 3389 in for Remote Desktop Protocol (RDP) access on virtual devices. |

## Contact support

Support is available either through Windows 365, or Microsoft Managed Desktop for update related incidents.

- For Windows 365 support, see [Get support](/mem/get-support).  
- For Microsoft Managed Desktop support, see [Submit a support request](../working-with-managed-desktop/admin-support.md).

## FAQ

| Question | Answer |
| ----- | ------ |
| Does Microsoft Managed Desktop on Windows 365 Cloud PCs have any feature differences from a physical device? | Some. With the nature of a Cloud PC, the baseline has been modified to optimize the experience on Windows 365. |
| Do my Cloud PCs appear any differently in the Microsoft Managed Desktop admin center? | Cloud PC displays the model as the license type you have provisioned. |
| Can I run Microsoft Managed Desktop on my Windows 365 Business Workloads? | No. Microsoft Managed Desktop is only available on enterprise workloads. |
