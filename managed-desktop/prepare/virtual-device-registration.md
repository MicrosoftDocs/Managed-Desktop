---
title: Virtual device registration
description: Register virtual devices to be managed by Microsoft Managed Desktop
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier1
manager: dougeby
ms.topic: how-to
audience: Admin
ms.date: 12/06/2022
---

# Virtual device registration

## Cloud PC - Windows 365 Enterprise Workloads

Microsoft Managed Desktop on Windows 365 workloads brings the management experience of your traditional Microsoft Managed Desktop workloads onto your Cloud PCs via Windows 365. Enterprise admins can automatically provision their Windows 365 workloads to be managed by Microsoft Managed Desktop with a single provisioning policy in their Windows 365 portal.

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
1. Under the **Microsoft managed services** section, select **Microsoft Managed Desktop**. Then, select **Next**. Microsoft Managed Desktop isn't supported on Hybrid Azure AD workloads. If selected, the *Microsoft Managed Desktop isn't currently supported with Hybrid Azure AD join. To change the join type, go to the General tab, then select Azure AD join* message appears.
1. Select your **Microsoft Managed Desktop profile**. Then, select **Next**.
1. Assign your policy accordingly and select **Next**.
1. Select **Create**. Now your newly provisioned Windows 365 Enterprise Cloud PCs will automatically be enrolled and managed by Microsoft Managed Desktop.

### Cloud PC - Windows 365 FAQ

| Question | Answer |
| ----- | ------ |
| Does Microsoft Managed Desktop on Windows 365 Cloud PCs have any feature differences from a physical device? | Some. With the nature of a Cloud PC, the baseline has been modified to optimize the experience on Windows 365. |
| Do my Cloud PCs appear any differently in the Microsoft Managed Desktop admin center? | Cloud PC displays the model as the license type you've provisioned. |
| Can I run Microsoft Managed Desktop on my Windows 365 Business Workloads? | No. Microsoft Managed Desktop is only available on enterprise workloads. |

## Azure Virtual Desktop workloads

Azure Virtual Desktop virtual machines can be provisioned and brought onto your Microsoft Managed Desktop-enabled tenant using the [enrollment API](#azure-virtual-desktop-enrollment-api). The enrollment API can be adapted to meet your provisioning preference.

Microsoft Managed Desktop provides the same scope of service with virtual machines as it does with [physical devices](../overview/device-services.md). However, Microsoft Managed Desktop defers any Azure Virtual Desktop specific support to Azure support unless otherwise specified.

### Prerequisites

Microsoft Managed Desktop for Azure Virtual Desktop follows the same [prerequisites](../prepare/prerequisites.md) as Microsoft Managed Desktop, and the [Azure Virtual Desktop prerequisites](/azure/virtual-desktop/prerequisites).  

The service supports:

- Personal persistent virtual machines (pooled non-multi-session hosts)

The following Azure Virtual Desktop features aren’t supported:

- Multi-session hosts
- Pooled non persistent virtual machines
- Remote app streaming

### Onboard your workloads

Microsoft Managed Desktop onboards newly provisioned session hosts through the [enrollment API](#azure-virtual-desktop-enrollment-api). The API is executed after the device has been Azure AD joined and Intune Registered. The API requires the Azure AD Device ID of the virtual machine.

### Azure Virtual Desktop enrollment API

> [!NOTE]
> Shared device mode isn't supported on AVD workloads via API.

The following PowerShell script provides IT teams with the ability to manually register Azure Virtual Desktop virtual machines with the Microsoft Managed Desktop service using the enrollment API. The script can be incorporated into existing provisioning or deployment pipelines for automation.  

For more information on how to use Microsoft Managed Desktop APIs, see [Microsoft Managed Desktop API](../developer/mmd-api-overview.md).  

#### Dependencies

The script uses the [Az.Accounts Module](/powershell/module/az.accounts) and should be executed with [Intune administrator permissions](/mem/intune/fundamentals/users-add#types-of-administrators) for the tenant because the scripts will collect a Token for the takeover action.

Save and execute the `New-MMDAVDEnrollment.ps1` PowerShell script locally.

#### PowerShell script example

The PowerShell script provides the parameters for your Azure AD device ID. The following PowerShell script is an example of the Azure AD device ID parameters:

```powershell
$Global:aadDeviceID = "Azure AD Device ID" 
$Global:CusmPartnerAPIUrl = "https://mmdls.microsoft.com/api/v1.0/devices/register/takeover" 

# Define the required parameters for takeover 
$deviceList = @" 
{ 
  "deviceList": [ 
    { 
      "aadDeviceId": "$aadDeviceID", 
      "plan": "Premium", 
      "persona": "All" 
    } 
  ] 
} 
"@ 

function PostRegisterRequest([string]$uri) 
{ 
    Write-Host Importing Az.Accounts 
    Import-Module Az.Accounts -Force 

    # Connect to Az account! 
    Write-Host Login with Intune Admin to get the token to post by custom API 
    Connect-AzAccount

    # Get token for API 
    $token = Get-AzAccessToken -ResourceUrl "c9d36ed4-91b3-4c87-b8d7-68d92826c96c" 

    # Construct the auth header 
    $header = @{ 
        'Content-Type' = 'application/json' 
        'Authorization' = "Bearer"+ " " + "$($token.token)" 
    } 

    # Use Customer API to add device to autopilot 
    $APIResponse = Invoke-RestMethod -Uri $uri -Method POST -Headers $header -Body $deviceList 

    return  $APIResponse 
} 

#Main method 
PostRegisterRequest $Global:CusmPartnerAPIUrl 
```

> [!IMPORTANT]
> This script is provided as is. Microsoft Managed Desktop will not provide any support customizing its contents or configuring it to any other workflows.

### Azure Virtual Desktop FAQ

| Question | Answer |
| ----- | ----- |
| Does Microsoft Managed Desktop on Azure Virtual Desktop Virtual Machines have any feature differences from a physical device? | Some. With the nature of an Azure Virtual Desktop, the baseline has been modified to optimize the experience on virtual machines.|
| Do my virtual machines appear any differently in the Microsoft Managed Desktop admin center? | Virtual machines are displayed as ‘virtual machines’. |

## Configurations that vary from the Microsoft Managed Desktop baseline

| Application | Explanation |
| ----- | ------ |
| Microsoft Teams | Deployment of Microsoft Teams by Microsoft Managed Desktop is excluded to allow for clients with native-optimized Teams. |

| Configuration | Explanation |
| ----- | ------ |
| BitLocker | No BitLocker enforcement. Windows 365 uses [Azure Storage server-side encryption (SSE)](/windows-365/enterprise/encryption). |
| Device compliance | Removed requirement for a Trusted Platform Module (TPM) from the Microsoft Managed Desktop managed device compliance policy as a TPM isn't mandated on Cloud PC devices and hence may not always be available. |
| RDP settings | Enabled Remote Desktop Protocol (RDP) on virtual devices. |
| Firewall rules | Enable port 3389 in for Remote Desktop Protocol (RDP) access on virtual devices. |

## Contact support

Support is available either through Windows 365, Azure, or Microsoft Managed Desktop for update related incidents.

- For Windows 365 support, see [Get support](/mem/get-support).
- For Azure Virtual Desktop support, see  [Get support](https://azure.microsoft.com/support/create-ticket/).
- For Microsoft Managed Desktop support, see [Submit a support request](../operate/support-request.md).
