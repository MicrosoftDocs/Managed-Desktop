---
title: Autopilot into co-management
description:  This article explains how to combine the benefits of Microsoft Intune for workload management but continue to have client applications managed by Configuration Manager
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: 
- M365-modern-desktop
- tier2
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.date: 08/19/2022
---

# Autopilot into co-management

Microsoft Managed Desktop allows you to configure devices using [Autopilot into co-management](/mem/configmgr/comanage/autopilot-enrollment), where the device is co-managed. The device can be registered as detailed in the [device registration overview article](device-registration-overview.md) and delivered to users. When the device goes through the  [first run experience](../deploy/esp-first-run.md), the device joins Azure Active Directory.

The feature is optimal for organizations that already have [co-management for Windows devices](/mem/configmgr/comanage/overview) turned on and want to combine the benefits of Microsoft Intune for all workload management, except for client applications. Client applications can continue to be managed using Configuration Manager.

## Common scenarios

The following are common scenarios where you may want to use Autopilot into co-management:

- You use Microsoft Intune for all workload management, except client apps, for all devices in your organization.
- All Microsoft Managed Desktop devices in the tenant will be co-managed once this setting is enabled. It’s recommended to configure the co-management settings soon after completing tenant enrollment into Microsoft Managed Desktop, and prior to registering devices for the service. This will ensure that all devices in Microsoft Managed Desktop are in the co-managed state.
- If you already have existing Microsoft Managed Desktop devices, configuring this setting will affect all these existing devices, by installing and enabling the Configuration Manager client, not just new devices running Autopilot. Devices will be in a co-managed state as soon as the co-managed policy is received by the device.

> [!WARNING]
> Do **not** change the co-management policy authority after device provisioning. Because of the timing of the policy synchronization, the behavior of the policy change is non-deterministic. For more information, see [How to enroll with Autopilot](/mem/configmgr/comanage/autopilot-enrollment#advanced-settings).

> [!IMPORTANT]
> You no longer need to create and assign an Intune app to install the Configuration Manager client. The [co-management policy](/mem/configmgr/comanage/autopilot-enrollment) automatically installs the Configuration Manager client as a first-party app during [Autopilot Enrollment Status page](/mem/intune/enrollment/windows-enrollment-status) (ESP) phase of the first run experience.

## Before you begin

Autopilot into co-management currently supports:

- Azure Active Directory joined only
- User-driven Autopilot scenarios only

Currently, the following aren't supported:

- Hybrid Azure AD-joined devices
- Autopilot self-deployment mode
- Autopilot pre-provisioning
- Co-management workloads set to **Pilot Intune**. This functionality is dependent upon collection evaluation, which doesn't happen until **after** the client is installed and registered. Since the client won't get the correct policy until later in the Autopilot process, it can cause indeterminate behaviors.

### Prerequisites

For Microsoft Managed Desktop devices, the following settings must be met:

1. Configure and assign only one co-management policy.  
2. Configure the Configuration Manager client installation properties without a task sequence to prevent conflicts with applications that are included in the Microsoft Managed Desktop first run experience. For more information, see [How to enroll with Autopilot](/mem/configmgr/comanage/autopilot-enrollment#recommendations).
3. The co-management policy must be set to use Intune for all workloads. Even when Intune is the device authority for the Client apps workload, a co-managed device can get apps from Configuration Manager and Intune.
4. Before setting up the co-management policy, you must meet the [prerequisites for Autopilot into co-management](/mem/configmgr/comanage/autopilot-enrollment#requirements).
5. Then, you can [configure co-management settings](#step-1-configure-co-management-settings).  

### Step 1: Configure co-management settings

**To configure the co-management settings:**

1. Go to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/).
2. Select the **Devices** menu, select **Enroll devices**, and then select **Windows enrollment**.
3. Select **Co-management settings**, and then select **Create**.
4. In the **Basics** page, **specify a name** for the policy, and an optional description.
5. In the **Settings** page, select **Yes** to the **Automatically install the Configuration Manager agent** setting.
:::image type="content" source="../media/mmd-autopilot-co-management.png" alt-text="Configure the co-management settings":::
6. Specify the client installation command-line parameters. You can copy these parameters from the **Enablement** tab of the cloud attach properties in the Configuration Manager console. For more information and specific command-line parameters, see [Get the command line from Configuration Manager](/mem/configmgr/comanage/how-to-prepare-win10#get-the-command-line-from-configuration-manager).
7. Expand the **Advanced** settings, for **Override co-management policy and use Intune for all workloads** option and select **Yes**. Even when Intune is the authority for the Client apps workload, a co-managed device can still get apps from Configuration Manager. For more information, see [Workloads: Client apps](/mem/configmgr/comanage/workloads#client-apps) and Use the [Company Portal app on co-managed devices](/mem/configmgr/comanage/company-portal).
8. In the **Assignments** page, select the **Modern Workplace Devices-All** group.
9. In the **Review + create** page, review the settings, and create the policy.

> [!NOTE]
> To provide a consistent user experience and unified application delivery on all devices, configure co-managed devices to also use the Company Portal. This will also ensure that users receive notifications only from the Company Portal. For more information, see [Apps in the Company Portal](/mem/configmgr/comanage/company-portal#configuration-manager-client-settings).

### Step 2: Deploy applications in Configuration Manager

**To deploy applications in Configuration Manager:**

1. In the Configuration Manager console, Microsoft Managed Desktop devices are listed as **Workgroup** clients.  
2. Add the **Domain** column in the **Devices** node to identify **Workgroup** clients. When using this column to help identify Microsoft Managed Desktop clients, workgroup clients will be included.  
3. Create a [device collection](/mem/configmgr/core/clients/manage/collections/create-collections) for the Microsoft Managed Desktop devices.  
4. Deploy the application to the device collection for the Microsoft Managed Desktop devices. For more information, see [Create and deploy an application with Configuration Manager](/mem/configmgr/apps/get-started/create-and-deploy-an-application).

### Step 3: Register your devices

For Microsoft to manage your devices in Microsoft Managed Desktop, you must have devices registered with the service. Follow the registration methods described in [device registration overview article](device-registration-overview.md).

- For new devices, once registered, deliver the new device to users to complete device enrollment.  
- If you reuse an existing device, the device must be wiped and reset. For more information, see [device wipe with factory reset](../operate/reset-devices-factory.md).

Once complete, your user can start up the device and proceed through the Windows setup experience.  

## Known Issues

A co-managed device in Microsoft Managed Desktop **can't** be a shared device.  

A shared device in Microsoft Managed Desktop will be assigned an Autopilot profile that will deploy in the self-deployment mode. Autopilot into co-management supports User-driven mode only.
