---
title: Configure ServiceNow for Microsoft Managed Desktop API
description: Describes how to configure your ServiceNow environment to use the Microsoft Managed Desktop API.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: how-to
ms.localizationpriority: medium
ms.date: 04/26/2022
ms.collection: 
- M365-modern-desktop
- tier3
---

# Configure ServiceNow for Microsoft Managed Desktop API

This article describes how to configure your ServiceNow environment to use the Microsoft Managed Desktop API.

## Before you begin

The scenario outlined in this article assumes that you already have the following prerequisites:

- A ServiceNow instance with Integration Hub subscription.
- A user account with the admin role in ServiceNow.
- Your organization’s ServiceNow instance URL typically looks like `https://\<your-organization-domain\>.service-now.com`.

<a name='create-an-azure-ad-app'></a>

### Create a Microsoft Entra app

**To create a Microsoft Entra app:**

1. Register and configure an application in Microsoft Entra ID with [application context](mmd-api-access-app-context.md) or [user context](mmd-api-access-user-context.md).
2. In **Redirect URI**, enter your ServiceNow instance URL in this format: `https://\<Instance-Name\>.service-now.com/oauth_redirect.do`.
3. Note the following values:
    1. The client (application) ID assigned by the Azure app registration portal.
    2. The client (application) secret.
4. Add necessary API permissions:

    | Permission | Type |
    | --- | --- |
    | offline_access | Delegated |
    | openid | Delegated |
    | MWaaSDevice.Read | Delegated |

<a name='register-azure-ad-as-the-oauth-provider'></a>

### Register Microsoft Entra ID as the OAuth provider

**To register Microsoft Entra ID as the 0Auth provider:**

1. Register and configure an application in Microsoft Entra ID with application context or user context.
2. Navigate to **All** \> **System OAuth** \> **Application Registry**.
3. Select **New**.
4. The system displays the message **What kind of OAuth application?** Select **Connect to a third party OAuth Provider**.
5. Enter the following values:

    | Field | Value |
    | --- | --- |
    | Name | Enter any name to uniquely identify the record. For example, enter `MMD API OAuth`. |
    | Client Id | Enter the client (application) ID assigned by the Azure app registration portal. |
    | Client Secret | Enter the client (application) secret. |
    | Default Grant type | Select: <ul><li>Client Credentials for application context.</li><li>Authorization Code for user context.</li></ul>  |
    | Authorization URL | Enter `https://login.microsoftonline.com/{tenantId}/oauth2/v2.0/authorize`. Replace `{tenantId}` with your Microsoft Entra directory ID. |
    | Token URL | Enter `https://login.microsoftonline.com/{tenantId}/oauth2/v2.0/token`. Replace `{tenantId}` with your Microsoft Entra directory ID. |
    | Redirect URL | Enter `https://.service-now.com/oauth_redirect.do` |
6. In the **OAuth Entity Scopes** related list, create these entries:

    | Name | OAuth Scope |
    | --- | --- |
    | Enter a unique name for the record, such as `mmd_offlineaccess` | Enter `offline_access` |
    | Enter a unique name for the record, such as `mmd_openid` | Enter `openid`|
    | Enter a unique name for the record, such as `mmd_api_user` (For user context) | Enter `https://mwaas-services-customerapi-prod.azurewebsites.net/MmdSupport.ReadWrite` |
    | Enter a unique name for the record, such as `mmd_api_app` (For application context) | Enter `https://mwaas-services-customerapi-prod.azurewebsites.net/.Default` |
7. In the **OAuth Entity Profiles** related list, open the default profile record.
8. Add the entity scopes created based on grant type.

### Create credential records

**To create credential records for the custom app registration you created:**

1. Navigate to **All** \> **System OAuth** \> **Application Registry.**
2. Navigate to **All** \> **Connections & Credentials** \> **Credentials.**
3. Select **New**.
4. The system displays the message **What type of Credentials would you like to create?** Select **OAuth 2.0 Credentials**.
5. Enter the following values:

    | Field  | Value |
    | --- | --- |
    | Name | Enter any name to uniquely identify the record. For example, enter `MMD API Credentials`. |
    | Active  | Checked |
    | OAuth Entity Profile | Select the OAuth profile you created when you registered the custom Microsoft Entra application as an OAuth provider. For example, select **MMD API OAuth default_profile**. |
6. Select **Submit**.
7. Optional: If you require both the **Authorization Code** and **Client Credentials** grant types to perform certain actions, create a child alias.

### Create connection records

**To create connection records for your Microsoft Entra application:**

1. Navigate to **All** \> **Connections & Credentials** \> **Connection**.
2. Select the **New** button in the Connections related list.
3. Enter these values:

    | Field | Value |
    | --- | --- |
    | Name | Enter any name to uniquely identify the record. For example, enter `MMD API Connection`. |
    | Credential | Select the Credential record you created for Microsoft Entra ID. For example, select **MMD API Credentials**. |
    | Connection URL | Enter `https://mmdls.microsoft.com/support/odata/v1/` |
4. Select **Submit**.

#### Example: Create an action using Microsoft Managed Desktop API

1. Navigate to **Process Automation** \> **Flow Designer**.
2. Select the **New** button and select **Action**.
3. Fill in the **Action Properties** (example GET MMD device details) and select **Submit**.
4. Define action inputs by selecting **+ Create Input** and enter the following values:

    | Label | Name | Type | Mandatory |
    | ----- | ----- | ----- | ----- |
    | Tenant id | tenant_id | String | Turn on |
    | Device name | device_name | String | Turn on |

5. Add an action step after Inputs and select **REST** (Perform a REST web service request).
6. Under **Connection Details**:
    1. **Connection**: Use Connection Alias
    2. **Connection Alias**: Select the connection alias you’ve previously set up. For example, select MMD API Connection.
    3. Confirm **Base URL** auto-populates with `https://mmdls.microsoft.com/support/odata/v1/`.
7. Under **Request Details**:
    1. **Build Request**: Manually
    2. **Resource Path**: `tenants/{tenant_Id data pill}/*devices/{device_name data pill}`**Note**: drag and drop the data pills of the input variables you created in the previous step.
    3. **HTTP Method**: GET
    4. **Headers**:
        1. Name: Authorization
        1. Value: Bearer `{Credential Value data pill}`
![Request details screen](../media/api/request-details.png)
8. Select **Save** to save a draft of your action.
9. Select **Test** to test and validate your new action:
10. Enter your Microsoft Entra directory ID.
11. Enter a valid Microsoft Managed Desktop device name.
12. Select **Run Test**.
13. After Flow Designer is done processing test action, select **Your test has finished running. View the action execution details**, to validate the response.
14. In the **Execution Details** tab that opens, navigate to **ACTION \>**Expand Steps**\>Step Output Data**.
15. Confirm the **200 Status code** and the JSON in **Response Body** if action was successful.
