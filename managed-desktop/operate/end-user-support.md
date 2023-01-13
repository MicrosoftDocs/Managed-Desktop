---
title: Get user support
description:  Explains the options for customer-led and partner-led support.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
---

# Get user support

Your Microsoft Managed Desktop users can get support either from your organization ("customer-led" support) or from a selected partner ("partner-led" support).

We aim to provide a consistent experience for users while keeping devices secure with both support options. No matter which option you choose, these same principles apply:

- Flexible integration of Microsoft Managed Desktop devices with your existing support processes.
- Clear roles and responsibilities between the support provider, IT admins, and Microsoft Managed Desktop.
- [Defined escalation paths](#escalation-paths).
- Documentation provided by Microsoft Managed Desktop, along with a portal, where you can request elevated device access and escalation to our support staff, if needed.
- Threat monitoring and mitigation provided by Microsoft Managed Desktop all day every day.

## Roles and responsibilities

To ensure the quality of service without compromising security, the support provider, IT admins, and Microsoft Managed Desktop have different roles and responsibilities.

| Role | Responsibilities |
| ------ | ------ |
| Support provider | Whoever provides support (either you for customer-led support or a partner for partner-led) is responsible for these items: <ul><li>Provide all user support and technical assistance from first contact through to resolution for the user.</li><li>Fulfill all service-level agreements for user support established by your organization, or in partnership with your chosen support provider.</li><li>Perform specific remediation actions, such as requesting elevated device privileges as described in [Elevation requests](../operate/end-user-support.md#submit-an-elevation-request).</li><li>Remediate user problems including: <ul><li>Operating system (Windows)</li><li>Microsoft Apps for enterprise</li><li>Browser features</li><li>Device problems</li><li>Problems with infrastructure, such as printers, drivers, and VPNs</li><li>Line-of-business applications</li></ul></ul> |
| IT admin | Your IT admin is responsible for these items: <ul><li>Work with the support provider to set and manage service level agreements for user support</li><li>Manage elevated access privileges for approved support staff. For more information, see [Turn on user support features](../deploy/enable-user-support-features.md).</li><li>If there are device issues affecting users, escalate the issues by using the Microsoft Managed Desktop admin support process. For more information, see [Admin support for Microsoft Managed Desktop](../operate/support-request.md).</li><li>Route hardware-related issues to the appropriate vendor or supplier.</li><li>Maintain and protect device security policy settings on Microsoft Managed Desktop devices. Don't change the policies we set. </li></ul> |
| Microsoft Managed Desktop |As the service provider, we're responsible for these items: <ul><li>Provide the means for elevated device access and issue escalation including documentation.</li><li>Keep this information about the roles and responsibilities current.</li><li>Respond to admin support requests in accordance with the severity definitions.</li><li>Provide threat monitoring and mitigation for all enrolled devices all day every day.</li></ul> |

## Escalation paths

Whether support is customer-led or partner-led, the flow of activity for a user support request follows this path:

:::image type="content" source="../media/mmd-support-flow.png" alt-text="When a user contacts support, they'll work through your tiered staff system as you've designed. It's important to designate a group of support staff that will be given the abilities for elevation and escalation, known as the support escalation team. For specific Microsoft Managed Desktop issues, they can escalate to our Operations team. Or for other Microsoft issues, they can route to your existing support channel, Unified or Premier. Hardware issues should always be routed to your established provider or supplier":::

Integrating your existing processes with this workflow for Microsoft Managed Desktop devices is flexible, so the details could be different. Typically, the support provider follows an existing tier-based or handoff approach. The support provider designates specific users, who have the ability to elevate permissions or escalate issues, to Microsoft Managed Desktop Operations. It's best to keep this group smaller than the broader support team.

If an issue must be escalated to Microsoft Managed Desktop, it's helpful to identify which team the issue should be directed to. We can transfer cases appropriately, but it saves time to route them to the right place from the start.

| Problem | Contact this team |
| ------ | ------ |
| Problems specific to Microsoft Managed Desktop | For example, a policy or setting that's deployed by the service itself. Escalate directly to the Operations team by creating a new support request. For more information, see [escalation request](../operate/end-user-support.md#submit-an-escalation-request).
| Hardware problems | Direct to your hardware supplier or vendor.
| Other problems| Escalate through existing support channels, whether that's a Unified or Premier subscription.

## Support framework

>[!NOTE]
>These support options are not available for devices in the Test group.

### Elevation portal

Since Microsoft Managed Desktop devices run on standard user by default, some tasks require elevation of privileges. For more information about user account control, see [User account control](/windows/security/identity-protection/user-account-control/user-account-control-overview). In order for support staff to be able to [perform tasks](../operate/end-user-support.md#submit-an-elevation-request) while fixing issues for users, we provide "just-in-time" access to an admin account. This password is accessed securely by only users you designate, and rotates every couple of hours.  

For steps on how to set up users to access to this portal, see [Turn on user support features](../deploy/enable-user-support-features.md).

For steps on submitting an elevation request, see [Elevation requests](../operate/end-user-support.md#submit-an-elevation-request).

### Escalation portal

If an issue requires escalation to the Microsoft Managed Desktop Operations team, designated support staff might direct similar to an IT admin support request.  

> [!NOTE]
> Only Sev C support requests can be filed in this manner. For an issue matching the description of other severities, it's recommended to contact the appropriate IT admin to file. For more info, see [Support request severity definitions](../operate/support-request.md#support-request-severity-definitions).

For steps on how to set up users for access to this portal, see [Turn on user support features](../deploy/enable-user-support-features.md).

For steps on submitting an escalation request, see [Escalation requests](../operate/end-user-support.md#submit-an-escalation-request).

## Submit an elevation or escalation request

> [!IMPORTANT]
> Ensure you've [set up user support](../deploy/enable-user-support-features.md) before you submit an elevation or escalation request.

If you've reached the point in the [escalation path](../operate/end-user-support.md) where you need to request elevated device access or escalation to Microsoft, use the following steps:

### Submit an elevation request

Before you request elevated access to a device, it's best to review which actions are best suited.

| Actions | Examples |
| ------ | ------ |
| **Typical actions** are intended for the elevation request process. It's performed routinely when fixing problems with Microsoft Managed Desktop devices. | <ul><li>Elevating built-in system fixes, the command prompt, or Windows PowerShell Troubleshooting line-of-business applications.</li><li>Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating).</li><li>Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes.</li></ul>
| **Actions that aren't recommended** | <ul><li>Installing software or browsers.</li><li>Installing drivers outside of Windows settings, including drivers for peripherals.</li><li>Installing .msi or .exe files.</li><li>Installing Windows features.</li></ul>
| **Actions that aren't supported** | <ul><li>Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations.</li><li>Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker.</li><li>Modifying settings managed by your organization.</li><ul>

**To request elevation:**

1. Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Devices** menu.
1. In the **Microsoft Managed Desktop** section, select **Devices**, which contains two tabs: the **Devices** tab and the **Elevation requests** tab.
1. To create a new elevation request on the **Device** tab, select a single device that you want to elevate.
1. From the Device actions dropdown menu, select **Request elevation**. A new elevation request fly-in will appear with the device’s name pre-populated in that field.
1. Instead, to create a new elevation request in the **Elevations requests** tab, select **+New elevation request.**
1. Provide these details:
    - **Support ticket ID**: This is from your own support ticketing system.
    - **Device name**: This is only when creating request from the **Elevation requests** tab. Enter the device serial number and then select the device from the menu.
    - **Category**: Select the category that best fits your issue. If no option seems close, then select **Other**. It's best to select a category if at all possible.
    - **Title**: Provide a short description of the issue on the device.
    - **Plan of action**: Provide the remediation steps you plan to take once elevation is granted.
1. Select **Submit**.
1. The list and details of all active and closed requests can be seen on the **Elevation requests** tab.

## Submit an escalation request

**To [escalate](../operate/end-user-support.md#escalation-portal) an issue to Microsoft:**

1. Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) and navigate to the **Tenant administration** menu.
2. In the Microsoft Managed Desktop section, select **Service requests**.
3. In the **Service requests** section, select **+ New support request**.
4. Provide a brief description in the **Title** field. Then, set the **Request type** to **Incident**.
5. Select the **Category** and **Sub-category** that best fits your issue. Then, select **Next**.
6. In the **Details** section, provide the following information:
    - **Description**: Add any extra details that could help our team understand the problem. If you need to attach files, you can do that by coming back to the request after you submit it.
    - **Primary contact information**: Provide information about how to contact the main person responsible for working with our team.
7. Select the **Severity** level. For more information, see [Support request severity definitions](../operate/support-request.md#support-request-severity-definitions).
8. Provide as much information about the request as possible to help the team respond quickly. Depending on the type of request, you may be required to provide different details.
9. Review all the information you provided for accuracy.
10. When you're ready, select **Create**.
