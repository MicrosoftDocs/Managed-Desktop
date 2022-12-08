---
title: Localize the user experience
description:  How to localize devices for users
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

# Localize the user experience

Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience"), or after completing the setup process.

## During setup (the "out of box experience")

During setup, users can select the language of their choice. This selection affects these attributes:

| Attribute | Description |
| ------ | ------ |
| Windows 10 language features | <ul><li>Display language</li><li>Keyboard language</li><li>Language-related Features on Demand</li><ul> |
| Microsoft 365 Apps for Enterprise language features | <ul><li>Display language</li><li>Proofing and authoring tools</li></ul> |

> [!NOTE]
> Users can only get language-related Features On Demand by selecting the language during the setup process.

## After completing setup

Users can select the language of their choice for Windows 10, and Microsoft 365 Apps for enterprise anytime after the setup process is complete. Specifically:

| Feature | Description |
| ------ | ------ |
| Windows 10 language features | <ul><li>Display language</li><li>Keyboard language</li><ul> |
| Microsoft 365 Apps for Enterprise language features | <ul><li>Display language</li><li>Proofing and authoring tools</li></ul> |

## Install more languages

> [!NOTE]
> In April 2022, Microsoft Managed Desktop allows standard users to install language accessory packs directly from their Microsoft Office apps by deploying this [policy](/deployoffice/overview-deploying-languages-microsoft-365-apps#allow-users-who-arent-admins-to-install-additional-languages). Users can now add languages directly by using the language settings found in any Office app by navigating to **Options > Language > Add a Language**.<p>Previously, Microsoft Office required users to be an admin and by adding devices to the custom Modern Workplace-Office-Language_Packs group that allowed users to add languages to Microsoft Office. This group is no longer needed and has been removed.

## Supported languages

For new devices, your manufacturer must provide device images that include the languages you require. If your manufacturer's image includes languages that aren't included in the supported languages list, the device is still supported by the service.

If you're reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images. For more information, see [Device images](../prepare/device-images.md).

The [universal image](../prepare/universal-image.md) provided by Microsoft Managed Desktop includes the supported languages and for Windows 10. For more information, see [language support](../prepare/universal-image.md#language-support).

> [!NOTE]
> Microsoft 365 Apps for enterprise might support a slightly different list.

If your users need a language other than the ones listed in [language support](../prepare/universal-image.md#language-support), submit a [support request](../operate/support-request.md) by using the [admin center](../prepare/access-admin-center.md).

## Languages for support and operations

### Admin support and operations

Microsoft Managed Desktop provides admin support only in English. This support includes the admin center and all communications with Microsoft Managed Desktop Operations. You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.
