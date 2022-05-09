---
title: Universal image
description:  Universal image requirements when ordering new devices or reusing existing devices
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
---

# Universal image

Microsoft Managed Desktop has created an image containing Windows Pro and Microsoft 365 Apps for Enterprise that you can use with Microsoft Managed Desktop.

However, it's best to use images appropriate to Microsoft Managed Desktop provided by the manufacturer whenever possible, even if that means an older Windows version must be updated once the user signs in. Using the Microsoft Managed Desktop Universal image should be the final option.

- We update the image with the latest Windows monthly quality updates every 30-60 days, and Microsoft 365 Apps for Enterprise updates at least twice a year.
- The image contains a recovery provisioning package to ensure Microsoft 365 Apps for Enterprise is restored following Windows recovery scenarios.
- You can deploy the image with USB drives.  
- You can provide model specific drivers which will be deployed via a scripted process to insert drivers for Windows, WinRE, and WinPE.
- You can modify the included scripts and folders with other customizations, such as adding specific cumulative updates, file copy code, or performing other checks.
- Drivers and quality updates are added to Windows during deployment from the USB drive.

> [!NOTE]
> It's your responsibility to add all necessary drivers, perform all testing, and ensure there are no issues with the final deployed image. We provide the universal image "as-is" but will provide technical guidance and answer questions. Contact MMDImage@microsoft.com.

Submit requests for the universal image by creating a change request in the [admin center](../working-with-managed-desktop/admin-support.md).

## Language support

The following are the images we support as part of the download script:

| Image type | Region | Language support |
| ----- | ------ | ----- |
| Regional universal image | EMEA | Supports regions and languages in Europe and the Middle East: <ul><li>Arabic</li><li>Bulgarian   </li><li>Croatian</li><li>Czech</li><li>Danish</li><li>Dutch</li><li>English (US, GB, AU, IN)</li><li>Estonian</li><li>Finnish</li><li>French (France)</li><li>German</li><li>Greek</li><li>Hebrew</li><li>Hungarian</li><li>Italian</li> <li>Latvian</li><li>Lithuanian</li><li>Norwegian (Bokmål)</li><li>Polish</li><li>Portuguese (Brazil)</li><li>Romanian</li><li>Russian</li><li>Serbian (Latin)</li><li>Slovak</li><li>Slovenian</li><li>Spanish (Spain)</li><li>Swedish</li><li>Turkish</li><li>Ukranian</li></ul> |
| Regional universal image | APAC | Supports regions and languages for Asia Pacific area: <ul><li>English (US, GB)</li><li>Japanese</li><li>Chinese (PRC)</li><li>Chinese (Taiwan)</li><li>Korean</li><li>Thai</li><li>Vietnamese (LiP)</li><li>Indonesian</li></ul> |
| Regional universal image | NA | Supports regions and languages for North America: <ul><li>English (US, GB)</li><li>Spanish (Mexico)</li><li>French (Canada)</li></ul> |
| Standard universal image | — | Supports English (US, GB) |
| EN-US universal Image | — | Supports English (US) |

## Multi-model driver support

> [!NOTE]
> This feature is in public preview. Please submit a request for information ticket in the [admin center](../working-with-managed-desktop/admin-support.md).

This feature allows customers to stage different model drivers in separate folder. Therefore, model-specific drivers are injected at the time of image deployment. The feature depends on:

- The `Sku_Folder.json` mapping file which contains the system SKU (displayed by SMBIOS System SKU).
- The corresponding driver folder (provided by you) where drivers (also provided by you) can be found for that model.

The feature supports driver injection to Windows, WinRE, and WinPE.

### Prerequisites

The following are the prerequisites are needed to deploy multi-model driver support. The prerequisites include system SKU, workstation, and model-specific drivers.

#### System SKU

Ths is the system SKU of the device that you want to inject drivers to.

Open `msinfo32` file on the exact model you are planning to deploy to and reference the system SKU (indicated in **bold** below). The `msinfo32` file provides the following information:

| Item | Value |
| ----- | ----- |
| OS Name | Microsoft Windows 10 Enterprise |
| Version | 10.0.19044 Build 19044 |
| Other OS Description | Not available |
| OS Manufacturer | Microsoft Corporation |
| System Name |
| System Manufacturer | Microsoft Corporation
| System Model | Surface Pro 4 |
| System Type | x-64-based PC |
| **System SKU** | **Surface_Pro_4** |
| Processor | Intel(R) Core(TM) i7-6650U CPU @ 2.20GHz, 2208 Mhz... |
| BIOS Version/Date | Microsoft Corporation 109.2748.78, Not Available |
| SMBIOS Version | 3.3 |
| Embedded Controller Version | 255.255 |
| BIOS Mode | UEFI |
| BaseBoard Manufacturer | Microsoft Corporation |

#### Workstation

Run Windows 10 or higher with administrative rights. You'll use this to edit the JSON file, create folders on the USB, and copy over drivers to the USB.  

> [!NOTE]
> You must use a local administrator account. Elevating to admin or using the ‘Run as admin’ option on a standard user device will fail during the scripting process when downloading the USB files.

#### Model specific drivers

OEMs have allowed customers to download all the drivers needed for their models. Please work with your OEM to locate the drivers for your specific device. There will be two types of drivers you should plan to stage on the USB:

| Driver | Description |
| ------ | ----- |
| Windows drivers | Typical Windows drivers include (but are not limited to): <ul><li>Chipset</li><li>Graphics</li><li>Network</li><li>Audio</li><li>Keyboard/Trackpad</li><li>Storage Controller</li></ul> |
| WinPE/WinRE drivers | Typical WinPE/WinRE drivers (critical drivers only): <ul><li>Keyboard/Trackpad</li><li>Storage Controller</li><li>Network</li></ul>

##### Where to find OEM Drivers

| OEM | Link |
| ----- | ------ |
| Dell | [Drivers & Downloads](https://www.dell.com/support/home/en-us?app=drivers) |
| HP | [Official HP® Drivers and Software Download](https://support.hp.com/drivers) |
| Lenovo | [Lenovo Drivers and Updates](https://support.lenovo.com/us/en/) |
| Surface | [Download drivers and firmware for Surface](/surface/download-drivers-and-firmware-for-surface-09bb2e09-2a4b-cb69-0951-078a7739e120) |

### Add system SKU specific drivers

Use the following steps to add system SKU specific drivers.

#### Step 1: Prepare the USB key

Follow this process to edit the JSON file and create driver folders once you have downloaded Universal Image to a USB key.

There are two partitions on the USB as created by the Microsoft Managed Desktop script:

- WinPE (E:)
- Images (F:)

The JSON file (`SKU_Folder.json`) is located on the WinPE partition in the `<USB WinPE Partition>:\Scripts` folder. For example, the USB WinPE partition is in the "`E:\Scripts`" volume.

#### Step 2: Edit the JSON file

1. Locate the JSON file in the WinPE\Scripts folder, and add entries to map the driver folders to the correct device model (System SKU).
1. Insert an entry for `"SystemSKU": “name of System SKU”`. The name should exactly match the System SKU found in the prerequisite section.  
1. Insert an entry for the `“Folder”: “name of folder containing drivers”`. The name should exactly match the driver folder name you created on the USB key with the drivers. The path for drivers is based on `<USB Images partition>:\Images\Drivers`. You don't need a full path, just the name of the folder within that location.
1. You don't need to include `_OS`, `_WinPE`, `_WinRE` in the folder name in the JSON file. We'll automatically look for your folder name to contain those extensions.

The following is an example of a JSON file filled out for several HP and Surface devices. The HP device is the same model, but for two different regions

In this example, we know the drivers are the same for the HP device (even though it's in two different regions). Therefore, we have one driver folder to be applied for two regions (America and UK – HP has SKU MODELS where region is after the #). Similar logic, using multiple SystemSku entries mapping to the same Folder name, can be used any time you want a folder to be applied to multiple models.

```json
[
    {
        "SystemSKU": "Surface_Pro_6_1976_Commercial",
        "Folder": "Pro6"
    },
    {
        "SystemSKU": "Surface_Laptop_4_1950:1951",
        "Folder": "SL4_Intel"
    },
    {
        "SystemSKU": "46Z55UP#ABA",
        "Folder": "HP Elitebook 830 G5"
    },
    {
        "SystemSKU": "46Z55UP#ABU",
        "Folder": "HP Elitebook 830 G5"
    }
]
```

In each example above, the SystemSKU is exactly what is listed for ‘System SKU’ in the `msinfo32` file.

#### Step 3: Create driver folders

You choose the name of each folder that you're placing the drivers into on the USB key.

All driver folders you create will be on the Images partition in the `<USB Image Partition>:\Images\Drivers` folder.

We support three folder name extensions to determine specific driver locations for a SystemSKU.

| Folder name extension | Description
| ----- | ----- |
| `_OS` | Drivers in this folder will only be applied to full Windows (not WinPE or WinRE). |
| `_WinRE` | Drivers in this folder will only be applied to WinRE. |
| `_WinPE` | Drivers in this folder will be online injected into the running instance of WinPE. |

> [!NOTE]
> Some drivers are built in such a way that they don't support online injection without performing a reboot. For those cases, we recommend you inject the driver into WinPE offline (`<USB WinPE Partition>\Sources\Boot.wim`). Utilize the first option outlined in [Method for making drivers available to WinPE](/troubleshoot/windows-client/deployment/limitations-dollar-sign-winpedriver-dollar-sign?msclkid=e4628b43a60a11eca8fafc2b766ea9f9#methods-for-making-drivers-available-to-winpe).

If you want to create driver folders applicable to ALL models, we support the following folder locations:

- OS
- WinRE
- WinPE

> [!NOTE]
> If you place drivers in these folders, we'll load those drivers in addition to any SKU model-specific driver folders that are applicable.

Below is an example of SKU-specific driver folders for HP and SurfacePro7, and generic driver folders in `F:\Images\Drivers`.

| SKU specific driver folder | Folder names |
| ----- | ----- |
| HP | HP-specifc driver folders include: <ul><li>HP_Driver_OS</li><li>HP_Driver_WinPE</li><li>HP_Driver_WinRe</li></ul> |
| SurfacePro7 | SurfacePro7-specific driver folders include: <ul><li>SurfacePro7_OS</li><li>SurfacePro7_WinPE</li><li>SurfacePro7_WinRe</li></ul> |
| Generic driver folders | Generic driver folders include: <ul><li>OS</li><li>WinPE</li><li>WinRe</li></ul> |

For the previous example, the JSON file contains:

```json
[
    {
        "SystemSKU": "Surface_Pro_7_1866",
        "Folder": "SurfacePro7"
    },
    {
        "SystemSKU": "46Z55UP#ABA",
        "Folder": "HP_Driver"
    }
]
```

Based on this example, this is the behavior of the driver injection on a Surface Pro 7 device where the SKU model is reported as `Surface_Pro_7_1866`:  

- Drivers in the `<USB Images partition>:\Images\Drivers\SurfacePro7_OS folder` will have all drivers in it applied to the device as well as any drivers in the `<USB Images partition>:\Images\Drivers\OS folder`.
- Drivers in the `SurfacePro7_WinRE` folder and drivers in the WinRE folder will be applied to the `Winre.wim` file during deployment.
- Drivers in the `SurfacePro7_WinPE` folder and drivers in the WinPE folder will be loaded online once WinPE has started from the USB key.  
- All drivers in other folders will **NOT** be loaded for the Surface Pro 7. If any applicable folders are blank, those folders are ignored.

#### Step 4: Deploy the image

Start up your device from the USB key. Example instructions of starting a Surface device device from a USB key can be found [here](/surface/boot-surface-from-a-usb-device-fe7a7323-8d1d-823d-be17-9aec89c4f9f5#WindowsVersion=Windows_11).

## FAQ

| Question | Answer |
| ----- | ----- |
| Where can I get the universal image? | Please submit a request via the [admin center](../working-with-managed-desktop/admin-support.md) to the Microsoft Managed Desktop team. |
| My drivers for WinPE are not working, what could be wrong? | Some drivers injected in WinPE may require a restart. In which case, they must be inserted by injecting them into the `boot.wim` file offline using Deployment Image Servicing and Management (DISM) commands. For more information, see [Add and Remove Drivers to an Offline Windows Image](/windows-hardware/manufacture/desktop/add-and-remove-drivers-to-an-offline-windows-image?view=windows-11). |
| What is the size of WinPE partition? | The default WinPE partition created on the USB is 4GB in size. Adding WinPE drivers should be limited to only those drivers needed in WinPE to reduce the risk of exceeding the 4GB size limitation. |
| Can I use my model specific drivers on other models? | It's recommended to only use drivers that OEMs have targeted for specific models. Utilizing drivers across multiple models (applying model specific drivers to different models) can result in errors within Windows. |
| How much hard drive space do I need when downloading the universal image? | In general, please ensure that your device has 30 GB of open space when downloading the universal image. |
| How can I identify the Microsoft Managed Desktop image version in devices already deployed? | All the universal images released after March-2021 onwards set the following registry keys to identify the image, build version, UI version, and region.<br><ul><li>`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Managed365/Original Image Build Version`</li><li>`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Managed365/UI Version`</li><li>`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Managed365/Region`</li></ul><p>Images released before March-2021 should have a file ‘`VersionTracking`’ with version details. That file can be found in the directory: `Windows\System32\ImageVersionTracking`.</p> |
| Can I run the PowerShell installation script using “Run as different user” that has admin rights? | No. The scripts need local administrator rights. It's recommended to run the PowerShell installation script as a local administrator account on the device. |
| Will 32GB USB drives be sufficient for the universal image? | It's recommended to use a 64GB USB for the universal image, especially, for our larger images that contain many languages such as the regional the universal image for EMEA. |
| Why am I getting a “Can’t validate argument” message when running the PowerShell installation script? | This error usually occurs because the account running the script has insufficient permissions. We highly recommend you use a local administrator account. Don't run this script as “Run as a different user”. |
