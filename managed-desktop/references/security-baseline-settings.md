---
title: Security baseline settings
description: This article lists the security baseline settings used in Microsoft Managed Desktop
keywords: security, baseline, settings
ms.service: m365-md
ms.sitesec: library
author: tiaraquan
ms.topic: reference
audience: ITPro
manager: dougeby
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.article: whats-new
ms.localizationpriority: medium
ms.date: 05/02/2023
ms.collection: 
- M365-modern-desktop
- tier3
---

# Security baseline settings

The following are the security policy setting names, the policy paths, and the settings used in Microsoft Managed Desktop.

## PUAProtection

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Defender/PUAProtection`
- Setting: `1`

## SetDisablePauseUXAccess

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Update/SetDisablePauseUXAccess`
- Setting: `1`

## SvchostProcessMitigation

- Policy path: `./Device/Vendor/MSFT/Policy/Config/ServiceControlManager/SvchostProcessMitigation`
- Setting: `<Enabled/>`

## LetAppsActivateWithVoice

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Privacy/LetAppsActivateWithVoice`
- Setting: `2`

## ConfigureTelemetryOptinChangeNotification

- Policy path: `./Device/Vendor/MSFT/Policy/Config/System/ConfigureTelemetryOptinChangeNotification`
- Setting: `0`

## ConfigureTelemetryOptInSettingsUX

- Policy path: `./Device/Vendor/MSFT/Policy/Config/System/ConfigureTelemetryOptInSettingsUX`
- Setting: `0`

## DisableDeviceDelete

- Policy path: `./Device/Vendor/MSFT/Policy/Config/System/DisableDeviceDelete`
- Setting: `0`

## AllowMicrosoftAccountsToBeOptional

- Policy path: `./Device/Vendor/MSFT/Policy/Config/AppRuntime/AllowMicrosoftAccountsToBeOptional`
- Setting: `<Enabled/>`

## DisallowAutoplayForNonVolumeDevices

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Autoplay/DisallowAutoplayForNonVolumeDevices`
- Setting: `<Enabled/>`

## SetDefaultAutoRunBehavior

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Autoplay/SetDefaultAutoRunBehavior`
- Setting: `<Enabled/><Data id=""""NoAutorun_Dropdown"""" value=""""1""""/>`

## TurnOffAutoPlay

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Autoplay/TurnOffAutoPlay`
- Setting: `<Enabled/><Data id=""""Autorun_Box"""" value=""""255""""/>`

## HardenedUNCPaths

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Connectivity/HardenedUNCPaths` 
- Setting: `"<Enabled/><Data id=""Pol_HardenedPaths"" value=""\\*\SYSVOL&#xF000;RequireMutualAuthentication=1,RequireIntegrity=1&#xF000;\\*\NETLOGON&#xF000;RequireMutualAuthentication=1,RequireIntegrity=1""/>"`

## DisableDownloadingOfPrintDriversOverHTTP

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Connectivity/DisableDownloadingOfPrintDriversOverHTTP`
- Setting: `<Enabled/>`

## DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards

- Policy path:`./Device/Vendor/MSFT/Policy/Config/Connectivity/DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards`
- Setting: `<Enabled/>`

## DiablePrintingOverHTTP

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Connectivity/DiablePrintingOverHTTP`
- Setting: `<Disabled/>`

## AllowPINLogon

- Policy path: `./Device/Vendor/MSFT/Policy/Config/CredentialProviders/AllowPINLogon`
- Setting: `<Disabled/>`

## RemoteHostAllowsDelegationOfNonExportableCredentials

- Policy path: `./Device/Vendor/MSFT/Policy/Config/CredentialsDelegation/RemoteHostAllowsDelegationOfNonExportableCredentials`
- Setting: `<Enabled/>`

## EnumerateAdministrators

- Policy path: `./Device/Vendor/MSFT/Policy/Config/CredentialsUI/EnumerateAdministrators`
- Setting: `<Disabled/>`

## PreventInstallationOfMatchingDeviceSetupClasses

- Policy path: `./Device/Vendor/MSFT/Policy/Config/DeviceInstallation/PreventInstallationOfMatchingDeviceSetupClasses`
- Setting: `<Enabled/><Data id=""""DeviceInstall_Classes_Deny_List"""" value=""""1&#xF000;{d48179be-ec20-11d1-b6b8-00c04fa372a7}""""/><Data id=""""DeviceInstall_Classes_Deny_Retroactive"""" value=""""true""""/>`

## PreventLockScreenSlideShow

- Policy path: `./Device/Vendor/MSFT/Policy/Config/DeviceLock/PreventLockScreenSlideShow`
- Setting: `<Enabled/>`

## PreventEnablingLockScreenCamera

- Policy path: `./Device/Vendor/MSFT/Policy/Config/DeviceLock/PreventEnablingLockScreenCamera`
- Setting: `<Enabled/>`

## SpecifyMaximumFileSizeApplicationLog

- Policy path: `./Device/Vendor/MSFT/Policy/Config/EventLogService/SpecifyMaximumFileSizeApplicationLog`
- Setting: `<Enabled/><Data id=""""Channel_LogMaxSize"""" value=""""32768""""/>`

## SpecifyMaximumFileSizeSecurityLog

- Policy path: `./Device/Vendor/MSFT/Policy/Config/EventLogService/SpecifyMaximumFileSizeSecurityLog`
- Setting: `<Enabled/><Data id=""""Channel_LogMaxSize"""" value=""""196608""""/>`

## SpecifyMaximumFileSizeSystemLog

- Policy path: `./Device/Vendor/MSFT/Policy/Config/EventLogService/SpecifyMaximumFileSizeSystemLog`
- Setting: `<Enabled/><Data id=""""Channel_LogMaxSize"""" value=""""32768""""/>`

## TurnOffDataExecutionPreventionForExplorer

- Policy path: `./Device/Vendor/MSFT/Policy/Config/FileExplorer/TurnOffDataExecutionPreventionForExplorer`
- Setting:`<Disabled/>`

## TurnOffHeapTerminationOnCorruption

- Policy path: `./Device/Vendor/MSFT/Policy/Config/FileExplorer/TurnOffHeapTerminationOnCorruption`
- Setting: `<Disabled/>`

## DoNotAllowUsersToAddSites

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DoNotAllowUsersToAddSites`
- Setting: `<Enabled/>`

## DoNotAllowUsersToChangePolicies

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DoNotAllowUsersToChangePolicies`
- Setting: `<Enabled/>`

## DisableEncryptionSupport

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableEncryptionSupport`
- Setting: `<Enabled/><Data id=""""Advanced_WinInetProtocolOptions"""" value=""""2688""""/>`

## AllowEnhancedProtectedMode

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/AllowEnhancedProtectedMode`
- Setting: `<Enabled/>`

## IncludeAllNetworkPaths

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/IncludeAllNetworkPaths`
- Setting: `<Disabled/>`

## InternetZoneAllowAccessToDataSources

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowAccessToDataSources`
- Setting: `<Enabled/><Data id=""""IZ_Partname1406"""" value=""""3""""/>`

## RestrictedSitesZoneAllowAccessToDataSources

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowAccessToDataSources`
- Setting: `<Enabled/><Data id=""""IZ_Partname1406"""" value=""""3""""/>`

## InternetZoneAllowScriptlets

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowScriptlets`
- Setting: `<Enabled/><Data id=""""IZ_Partname1209"""" value=""""3""""/>`

## RestrictedSitesZoneAllowScriptlets

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowScriptlets`
- Setting: `<Enabled/><Data id=""""IZ_Partname1209"""" value=""""3""""/>`

## InternetZoneAllowAutomaticPromptingForFileDownloads

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowAutomaticPromptingForFileDownloads
- Setting: `<Enabled/><Data id=""""IZ_Partname2200"""" value=""""3""""/>`

## RestrictedSitesZoneAllowAutomaticPromptingForFileDownloads

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowAutomaticPromptingForFileDownloads`
- Setting: `<Enabled/><Data id=""""IZ_Partname2200"""" value=""""3""""/>`

## InternetZoneInitializeAndScriptActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneInitializeAndScriptActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname1201"""" value=""""3""""/>`

## IntranetZoneInitializeAndScriptActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/IntranetZoneInitializeAndScriptActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname1201"""" value=""""3""""/>`

## TrustedSitesZoneInitializeAndScriptActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/TrustedSitesZoneInitializeAndScriptActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname1201"""" value=""""3""""/>`

## RestrictedSitesZoneInitializeAndScriptActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneInitializeAndScriptActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname1201"""" value=""""3""""/>`

## InternetZoneNavigateWindowsAndFrames

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneNavigateWindowsAndFrames`
- Setting: `<Enabled/><Data ID=""""IZ_Partname1607""" value=""""3""""/>`

## RestrictedSitesZoneNavigateWindowsAndFrames

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneNavigateWindowsAndFrames`
- Setting: `<Enabled/><Data id=""""IZ_Partname1607"""" value=""""3""""/>`

## InternetZoneAllowNETFrameworkReliantComponents`

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowNETFrameworkReliantComponents`
- Setting: `<Enabled/><Data id=""""IZ_Partname2004"""" value=""""3""""/>`

## RestrictedSitesZoneAllowNETFrameworkReliantComponents

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowNETFrameworkReliantComponents`
- Setting: `<Enabled/><Data id=""""IZ_Partname2004"""" value=""""3""""/>`

## InternetZoneAllowSmartScreenIE

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowSmartScreenIE`
- Setting: `<Enabled/><Data id=""""IZ_Partname2301"""" value=""""0""""/>`

## LockedDownInternetZoneAllowSmartScreenIE

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownInternetZoneAllowSmartScreenIE`
- Setting: `<Enabled/><Data id=""""IZ_Partname2301"""" value=""""0""""/>`

## RestrictedSitesZoneAllowSmartScreenIE

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowSmartScreenIE`
- Setting: `<Enabled/><Data id=""""IZ_Partname2301"""" value=""""0""""/>`

## LockedDownRestrictedSitesZoneAllowSmartScreenIE

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownRestrictedSitesZoneAllowSmartScreenIE`
- Setting: `<Enabled/><Data id=""""IZ_Partname2301"""" value=""""0""""/>`

## InternetZoneAllowUserDataPersistence

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowUserDataPersistence`
- Setting: `<Enabled/><Data id=""""IZ_Partname1606"""" value=""""3""""/>`

## RestrictedSitesZoneAllowUserDataPersistence

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowUserDataPersistence`
- Setting: `<Enabled/><Data id=""""IZ_Partname1606"""" value=""""3""""/>`

## InternetZoneAllowLessPrivilegedSites

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowLessPrivilegedSites`
- Setting: `<Enabled/><Data id=""""IZ_Partname2101"""" value=""""3""""/>`

## RestrictedSitesZoneAllowLessPrivilegedSites

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowLessPrivilegedSites`
- Setting: `<Enabled/><Data id=""""IZ_Partname2101"""" value=""""3""""/>`

## DoNotBlockOutdatedActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DoNotBlockOutdatedActiveXControls`
- Setting: `<Disabled/>`

## DisableEnclosureDownloading

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableEnclosureDownloading`
- Setting: `<Enabled/>`

## DisableBypassOfSmartScreenWarnings

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableBypassOfSmartScreenWarnings`
- Setting: `<Enabled/>`

## DisableBypassOfSmartScreenWarningsAboutUncommonFiles

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableBypassOfSmartScreenWarningsAboutUncommonFiles`
- Setting: `<Enabled/>`

## RestrictedSitesZoneAllowActiveScripting

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowActiveScripting`
- Setting: `<Enabled/><Data id=""""IZ_Partname1400"""" value=""""3""""/>`

## RestrictedSitesZoneAllowBinaryAndScriptBehaviors

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowBinaryAndScriptBehaviors`
- Setting: `<Enabled/><Data id=""""IZ_Partname2000"""" value=""""3""""/>`

## InternetZoneAllowCopyPasteViaScript

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowCopyPasteViaScript`
- Setting: `<Enabled/><Data id=""""IZ_Partname1407"""" value=""""3""""/>`

## RestrictedSitesZoneAllowCopyPasteViaScript

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowCopyPasteViaScript`
- Setting: `<Enabled/><Data id=""""IZ_Partname1407"""" value=""""3""""/>`

## InternetZoneAllowDragAndDropCopyAndPasteFiles

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowDragAndDropCopyAndPasteFiles`
- Setting: `<Enabled/><Data id=""""IZ_Partname1802"""" value=""""3""""/>`

## RestrictedSitesZoneAllowDragAndDropCopyAndPasteFiles

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowDragAndDropCopyAndPasteFiles`
- Setting: `<Enabled/><Data id=""""IZ_Partname1802"""" value=""""3""""/>`

## AllowFallbackToSSL3

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/AllowFallbackToSSL3`
- Setting: `<Enabled/><Data id=""""Advanced_EnableSSL3FallbackOptions"""" value=""""0""""/>`

## RestrictedSitesZoneAllowFileDownloads

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowFileDownloads`
- Setting: `<Enabled/><Data id=""""IZ_Partname1803"""" value=""""3""""/>`

## InternetZoneAllowLoadingOfXAMLFiles

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowLoadingOfXAMLFiles`
- Setting: `<Enabled/><Data id=""""IZ_Partname2402"""" value=""""3""""/>`

## RestrictedSitesZoneAllowLoadingOfXAMLFiles

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowLoadingOfXAMLFiles`
- Setting: `<Enabled/><Data id=""""IZ_Partname2402"""" value=""""3""""/>`

## RestrictedSitesZoneAllowMETAREFRESH

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowMETAREFRESH`
- Setting: `<Enabled/><Data id=""""IZ_Partname1608"""" value=""""3""""/>`

## InternetZoneAllowOnlyApprovedDomainsToUseActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowOnlyApprovedDomainsToUseActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname120b"""" value=""""3""""/>`

## RestrictedSitesZoneAllowOnlyApprovedDomainsToUseActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowOnlyApprovedDomainsToUseActiveXControls`
- Setting:`<Enabled/><Data id=""""IZ_Partname120b"""" value=""""3""""/>`

## InternetZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl`
- Setting: `<Enabled/><Data id=""""IZ_Partname120c"""" value=""""3""""/>`

## RestrictedSitesZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl`
- Setting: `<Enabled/><Data id=""""IZ_Partname120c"""" value=""""3""""/>`

## InternetZoneAllowScriptingOfInternetExplorerWebBrowserControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowScriptingOfInternetExplorerWebBrowserControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname1206"""" value=""""3""""/>`

## RestrictedSitesZoneAllowScriptingOfInternetExplorerWebBrowserControls`

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowScriptingOfInternetExplorerWebBrowserControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname1206"""" value=""""3""""/>`

## InternetZoneAllowScriptInitiatedWindows

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowScriptInitiatedWindows`
- Setting: `<Enabled/><Data id=""""IZ_Partname2102"""" value=""""3""""/>`

## RestrictedSitesZoneAllowScriptInitiatedWindows

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowScriptInitiatedWindows`
- Setting: `<Enabled/><Data id=""""IZ_Partname2102"""" value=""""3""""/>`

## AllowSoftwareWhenSignatureIsInvalid

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/AllowSoftwareWhenSignatureIsInvalid`
- Setting: `<Disabled/>`

## InternetZoneAllowUpdatesToStatusBarViaScript

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowUpdatesToStatusBarViaScript`
- Setting: `<Enabled/><Data id=""""IZ_Partname2103"""" value=""""3""""/>`

## RestrictedSitesZoneAllowUpdatesToStatusBarViaScript

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowUpdatesToStatusBarViaScript`
- Setting: `<Enabled/><Data id=""""IZ_Partname2103"""" value=""""3""""/>`

## CheckServerCertificateRevocation

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/CheckServerCertificateRevocation`
- Setting: `<Enabled/>`

## CheckSignaturesOnDownloadedPrograms

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/CheckSignaturesOnDownloadedPrograms`
- Setting: `<Enabled/>`

## DoNotAllowActiveXControlsInProtectedMode

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DoNotAllowActiveXControlsInProtectedMode`
- Setting: `<Enabled/>`

## InternetZoneDoNotRunAntimalwareAgainstActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneDoNotRunAntimalwareAgainstActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname270C"""" value=""""0""""/>`

## IntranetZoneDoNotRunAntimalwareAgainstActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/IntranetZoneDoNotRunAntimalwareAgainstActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname270C"""" value=""""0""""/>`

## LocalMachineZoneDoNotRunAntimalwareAgainstActiveXControls

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LocalMachineZoneDoNotRunAntimalwareAgainstActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname270C"""" value=""""0""""/>`

## RestrictedSitesZoneDoNotRunAntimalwareAgainstActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneDoNotRunAntimalwareAgainstActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname270C"""" value=""""0""""/>`

## TrustedSitesZoneDoNotRunAntimalwareAgainstActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/TrustedSitesZoneDoNotRunAntimalwareAgainstActiveXControls`
- Setting `<Enabled/><Data id=""""IZ_Partname270C"""" value=""""0""""/>`

## PreventManagingSmartScreenFilter

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/PreventManagingSmartScreenFilter`
- Setting: `<Enabled/><Data id=""""IE9SafetyFilterOptions"""" value=""""1""""/>`

## InternetZoneDownloadSignedActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneDownloadSignedActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname1001"""" value=""""3""""/>`

## RestrictedSitesZoneDownloadSignedActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneDownloadSignedActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname1001"""" value=""""3""""/>`

## InternetZoneDownloadUnsignedActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneDownloadUnsignedActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname1004"""" value=""""3""""/>`

## RestrictedSitesZoneDownloadUnsignedActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneDownloadUnsignedActiveXControls`
- Setting: `<Enabled/><Data id=""""IZ_Partname1004"""" value=""""3""""/>`

## InternetZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows`
- Setting: `<Enabled/><Data id=""""IZ_Partname2709"""" value=""""3""""/>`

## RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows`
- Setting: `<Enabled/><Data id=""""IZ_Partname2709"""" value=""""3""""/>`

## InternetZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows`
- Setting `<Enabled/><Data id=""""IZ_Partname2708"""" value=""""3""""/>`

## RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows`
- Setting: `<Enabled/><Data id=""""IZ_Partname2708"""" value=""""3""""/>`

## InternetZoneIncludeLocalPathWhenUploadingFilesToServer

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneIncludeLocalPathWhenUploadingFilesToServer`
- Setting: `<Enabled/><Data id=""""IZ_Partname160A"""" value=""""3""""/>`

## RestrictedSitesZoneIncludeLocalPathWhenUploadingFilesToServer

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneIncludeLocalPathWhenUploadingFilesToServer`
- Setting: `<Enabled/><Data id=""""IZ_Partname160A"""" value=""""3""""/>`

## ConsistentMimeHandlingInternetExplorerProcesses

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/ConsistentMimeHandlingInternetExplorerProcesses`
- Setting:  `<Enabled/>`

## MimeSniffingSafetyFeatureInternetExplorerProcesses

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/MimeSniffingSafetyFeatureInternetExplorerProcesses`
- Setting: `<Enabled/>`

## MKProtocolSecurityRestrictionInternetExplorerProcesses

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/MKProtocolSecurityRestrictionInternetExplorerProcesses`
- Setting: `<Enabled/>`

## NotificationBarInternetExplorerProcesses

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/NotificationBarInternetExplorerProcesses`
- Setting: `<Enabled/>`

## ProtectionFromZoneElevationInternetExplorerProcesses

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/ProtectionFromZoneElevationInternetExplorerProcesses`
- Setting: `<Enabled/>`

## RestrictActiveXInstallInternetExplorerProcesses

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictActiveXInstallInternetExplorerProcesses`
- Setting: `<Enabled/>`

## RestrictFileDownloadInternetExplorerProcesses

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictFileDownloadInternetExplorerProcesses`
- Setting: `<Enabled/>`

## ScriptedWindowSecurityRestrictionsInternetExplorerProcesses

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/ScriptedWindowSecurityRestrictionsInternetExplorerProcesses`
- Setting: `<Enabled/>`

## InternetZoneJavaPermissions

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneJavaPermissions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>`

## IntranetZoneJavaPermissions

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/IntranetZoneJavaPermissions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""65536""""/>`

## LocalMachineZoneJavaPermissions

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LocalMachineZoneJavaPermissions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>`

## LockedDownLocalMachineZoneJavaPermissions

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownLocalMachineZoneJavaPermissions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>`

## LockedDownRestrictedSitesZoneJavaPermissions

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownRestrictedSitesZoneJavaPermissions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>`

## LockedDownTrustedSitesZoneJavaPermissions

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownTrustedSitesZoneJavaPermissions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>`

## RestrictedSitesZoneJavaPermissions

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneJavaPermissions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>`

## TrustedSitesZoneJavaPermissions

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/TrustedSitesZoneJavaPermissions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""65536""""/>`

## InternetZoneLaunchingApplicationsAndFilesInIFRAME

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneLaunchingApplicationsAndFilesInIFRAME`
- Setting: `<Enabled/><Data id=""""IZ_Partname1804"""" value=""""3""""/>`

## RestrictedSitesZoneLaunchingApplicationsAndFilesInIFRAME

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneLaunchingApplicationsAndFilesInIFRAME`
- Setting: `<Enabled/><Data id=""""IZ_Partname1804"""" value=""""3""""/>`

## InternetZoneLogonOptions

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneLogonOptions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1A00"""" value=""""65536""""/>`

## RestrictedSitesZoneLogonOptions

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneLogonOptions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1A00"""" value=""""196608""""/>`

## DisableIgnoringCertificateErrors

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableIgnoringCertificateErrors`
- Setting: `<Enabled/>`

## PreventPerUserInstallationOfActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/PreventPerUserInstallationOfActiveXControls`
- Setting: `<Enabled/>`

## RemoveRunThisTimeButtonForOutdatedActiveXControls

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RemoveRunThisTimeButtonForOutdatedActiveXControls`
- Setting: `<Enabled/>`

## InternetZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode`
- Setting: `<Enabled/><Data id=""""IZ_Partname2001"""" value=""""3""""/>` |

## RestrictedSitesZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode`
- Setting: `<Enabled/><Data id=""""IZ_Partname2001"""" value=""""3""""/>`

## RestrictedSitesZoneRunActiveXControlsAndPlugins

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneRunActiveXControlsAndPlugins`
- Setting: `<Enabled/><Data id=""""IZ_Partname1200"""" value=""""3""""/>`

## RestrictedSitesZoneScriptActiveXControlsMarkedSafeForScripting

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneScriptActiveXControlsMarkedSafeForScripting`
- Setting: `<Enabled/><Data id=""""IZ_Partname1405"""" value=""""3""""/>`

## RestrictedSitesZoneScriptingOfJavaApplets

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneScriptingOfJavaApplets`
- Setting: `<Enabled/><Data id=""""IZ_Partname1402"""" value=""""3""""/>`

## SecurityZonesUseOnlyMachineSettings

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/SecurityZonesUseOnlyMachineSettings`
- Setting: `<Enabled/>`

## InternetZoneShowSecurityWarningForPotentiallyUnsafeFiles

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneShowSecurityWarningForPotentiallyUnsafeFiles`
- Setting: `<Enabled/><Data id=""""IZ_Partname1806"""" value=""""1""""/>`

## RestrictedSitesZoneShowSecurityWarningForPotentiallyUnsafeFiles

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneShowSecurityWarningForPotentiallyUnsafeFiles`
- Setting: `<Enabled/><Data id=""""IZ_Partname1806"""" value=""""3""""/>`

## SpecifyUseOfActiveXInstallerService

- Policy path:`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/SpecifyUseOfActiveXInstallerService`
- Setting: `<Enabled/>`

## DisableCrashDetection

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableCrashDetection`
- Setting: `<Enabled/>`

## DisableSecuritySettingsCheck

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableSecuritySettingsCheck`
- Setting: `<Disabled/>`

## DisableProcessesInEnhancedProtectedMode

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableProcessesInEnhancedProtectedMode`
- Setting: `<Enabled/>`

## AllowCertificateAddressMismatchWarning

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/AllowCertificateAddressMismatchWarning`
- Setting: `<Enabled/>`

## InternetZoneEnableCrossSiteScriptingFilter

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneEnableCrossSiteScriptingFilter`
- Setting: `<Enabled/><Data id=""""IZ_Partname1409"""" value=""""0""""/>`

## RestrictedSitesZoneEnableCrossSiteScriptingFilter

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneEnableCrossSiteScriptingFilter`
- Setting: `<Enabled/><Data id=""""IZ_Partname1409"""" value=""""0""""/>`

## InternetZoneEnableProtectedMode

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneEnableProtectedMode`
- Setting" `<Enabled/><Data id=""""IZ_Partname2500"""" value=""""0""""/>`

## RestrictedSitesZoneTurnOnProtectedMode

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneTurnOnProtectedMode`
- Setting: `<Enabled/><Data id=""""IZ_Partname2500"""" value=""""0""""/>`

## InternetZoneUsePopupBlocker

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneUsePopupBlocker`
- Setting: `<Enabled/><Data id=""""IZ_Partname1809"""" value=""""0""""/>`

## RestrictedSitesZoneUsePopupBlocker

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneUsePopupBlocker`
- Setting: `<Enabled/><Data id=""""IZ_Partname1809"""" value=""""0""""/>`

## InternetZoneAllowVBScriptToRunInInternetExplorer

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowVBScriptToRunInInternetExplorer`
- Setting: `<Enabled/><Data id=""""IZ_Partname140C"""" value=""""3""""/>`

## LockedDownIntranetJavaPermissions

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownIntranetJavaPermissions`
- Setting: `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>`

## RestrictedSitesZoneAllowVBScriptToRunInInternetExplorer

- Policy path: `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowVBScriptToRunInInternetExplorer`
- Setting: `<Enabled/><Data id=""""IZ_Partname140C"""" value=""""3""""/>`

## ApplyUACRestrictionsToLocalAccountsOnNetworkLogon

- Policy path: `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/ApplyUACRestrictionsToLocalAccountsOnNetworkLogon`
- Setting: `<Enabled/>`

## ConfigureSMBV1Server

- Policy path: `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/ConfigureSMBV1Server`
- Setting: `<Disabled/>`

## ConfigureSMBV1ClientDriver

- Policy path: `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/ConfigureSMBV1ClientDriver`
- Setting: `<Enabled/><Data id=""""Pol_SecGuide_SMB1ClientDriver"""" value=""""4""""/>`

## EnableStructuredExceptionHandlingOverwriteProtection

- Policy path: `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/EnableStructuredExceptionHandlingOverwriteProtection`
- Setting: `<Enabled/>`

## WDigestAuthentication

- Policy path: `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/WDigestAuthentication`
- Setting: `<Disabled/>`

## TurnOnWindowsDefenderProtectionAgainstPotentiallyUnwantedApplications

- Policy path: `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/TurnOnWindowsDefenderProtectionAgainstPotentiallyUnwantedApplications`
- Setting: `<Enabled/>`

## IPv6SourceRoutingProtectionLevel

- Policy path: `./Device/Vendor/MSFT/Policy/Config/MSSLegacy/IPv6SourceRoutingProtectionLevel`
- Setting: `<Enabled/><Data id=""""DisableIPSourceRoutingIPv6"""" value=""""2""""/>`

## IPSourceRoutingProtectionLevel

- Policy path: `./Device/Vendor/MSFT/Policy/Config/MSSLegacy/IPSourceRoutingProtectionLevel`
- Setting: `<Enabled/><Data id=""""DisableIPSourceRouting"""" value=""""2""""/>`

## AllowICMPRedirectsToOverrideOSPFGeneratedRoutes

- Policy path: `./Device/Vendor/MSFT/Policy/Config/MSSLegacy/AllowICMPRedirectsToOverrideOSPFGeneratedRoutes`
- Setting: `<Disabled/>`

## AllowTheComputerToIgnoreNetBIOSNameReleaseRequestsExceptFromWINSServers

- Policy path: `./Device/Vendor/MSFT/Policy/Config/MSSLegacy/AllowTheComputerToIgnoreNetBIOSNameReleaseRequestsExceptFromWINSServers`
- Setting: `<Enabled/>`

## AllowStandbyWhenSleepingPluggedIn

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Power/AllowStandbyWhenSleepingPluggedIn`
- Setting: `<Disabled/>`

## RequirePasswordWhenComputerWakesOnBattery

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Power/RequirePasswordWhenComputerWakesOnBattery`
- Setting: `<Enabled/>`

## RequirePasswordWhenComputerWakesPluggedIn

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Power/RequirePasswordWhenComputerWakesPluggedIn`
- Setting: `<Enabled/>`

## AllowStandbyStatesWhenSleepingOnBattery

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Power/AllowStandbyStatesWhenSleepingOnBattery`
- Setting: `<Disabled/>`

## SolicitedRemoteAssistance

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteAssistance/SolicitedRemoteAssistance`
- Setting: `<Disabled/>`

## DoNotAllowPasswordSaving

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteDesktopServices/DoNotAllowPasswordSaving`
- Setting: `<Enabled/>`

## DoNotAllowDriveRedirection

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteDesktopServices/DoNotAllowDriveRedirection`
- Setting: `<Enabled/>`

## PromptForPasswordUponConnection

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteDesktopServices/PromptForPasswordUponConnection`
- Setting: `<Enabled/>`

## RequireSecureRPCCommunication

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteDesktopServices/RequireSecureRPCCommunication`
- Setting: `<Enabled/>`

## ClientConnectionEncryptionLevel

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteDesktopServices/ClientConnectionEncryptionLevel`
- Setting: `<Enabled/><Data id=""""TS_ENCRYPTION_LEVEL"""" value=""""3""""/>`

## AllowBasicAuthentication_Client

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/AllowBasicAuthentication_Client`
- Setting: `<Disabled/>`

## AllowBasicAuthentication_Service

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/AllowBasicAuthentication_Service`
- Setting: `<Disabled/>`

## AllowUnencryptedTraffic_Client

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/AllowUnencryptedTraffic_Client`
- Setting: `<Disabled/>`

## AllowUnencryptedTraffic_Service

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/AllowUnencryptedTraffic_Service`
- Setting: `<Disabled/>`

## DisallowDigestAuthentication

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/DisallowDigestAuthentication`
- Setting: `<Enabled/>`

## DisallowStoringOfRunAsCredentials

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/DisallowStoringOfRunAsCredentials`
- Setting: `<Enabled/>`

## RestrictUnauthenticatedRPCClients

- Policy path: `./Device/Vendor/MSFT/Policy/Config/RemoteProcedureCall/RestrictUnauthenticatedRPCClients`
- Setting: `<Enabled/><Data id=""""RpcRestrictRemoteClientsList"""" value=""""1""""/>` |

## BootStartDriverInitialization

- Policy path: `./Device/Vendor/MSFT/Policy/Config/System/BootStartDriverInitialization`
- Setting: `<Enabled/><Data id=""""SelectDriverLoadPolicy"""" value=""""3""""/>`

## ProhitConnectionToNonDomainNetworksWhenConnectedToDomainAuthenticatedNetwork

- Policy path: `./Device/Vendor/MSFT/Policy/Config/WindowsConnectionManager/ProhitConnectionToNonDomainNetworksWhenConnectedToDomainAuthenticatedNetwork`
- Setting: `<Enabled/>`

## EnumerateLocalUsersOnDomainJoinedComputers

- Policy path: `./Device/Vendor/MSFT/Policy/Config/WindowsLogon/EnumerateLocalUsersOnDomainJoinedComputers`
- Setting: `<Disabled/>`

## AllowAutomaticRestartSignOn

- Policy path: `./Device/Vendor/MSFT/Policy/Config/WindowsLogon/AllowAutomaticRestartSignOn`
- Setting: `<Disabled/>`

## TurnOnPowerShellScriptBlockLogging

- Policy path: `./Device/Vendor/MSFT/Policy/Config/WindowsPowerShell/TurnOnPowerShellScriptBlockLogging`
- Setting: `<Enabled/><Data id=""""EnableScriptBlockInvocationLogging"""" value=""""true""""/>`

## AllowAutoComplete

- Policy path: `./User/Vendor/MSFT/Policy/Config/InternetExplorer/AllowAutoComplete`
- Setting: `<Disabled/>`

## AllowGameDVR

- Policy path: `./Device/Vendor/MSFT/Policy/Config/ApplicationManagement/AllowGameDVR`
- Setting: `0`

## MSIAlwaysInstallWithElevatedPrivileges

- Policy path: `./Device/Vendor/MSFT/Policy/Config/ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges`
- Setting: `0`

## MSIAllowUserControlOverInstall

- Policy path: `./Device/Vendor/MSFT/Policy/Config/ApplicationManagement/MSIAllowUserControlOverInstall`
- Setting: `0`

## AllowPasswordManager

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager`
- Setting: `0`

## AllowSmartScreen

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen`
- Setting: `1`

## PreventSmartScreenPromptOverride

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Browser/PreventSmartScreenPromptOverride`
- Setting: `1`

## PreventSmartScreenPromptOverrideForFiles

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Browser/PreventSmartScreenPromptOverrideForFiles`
- Setting: `1`

## AllowBehaviorMonitoring

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring`
- Setting: `1`

## AllowCloudProtection

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection`
- Setting: `1`

## AllowEmailScanning

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning`
- Setting: `1`

## AllowFullScanRemovableDriveScanning

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning`
- Setting: `1`

## EnableNetworkProtection

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection`
- Setting `1`

## SubmitSamplesConsent

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent`
- Setting: `1`

## DisallowExploitProtectionOverride

- Policy path: `./Device/Vendor/MSFT/Policy/Config/WindowsDefenderSecurityCenter/DisallowExploitProtectionOverride`
- Setting: `1`

## EnableVirtualizationBasedSecurity

- Policy path: `./Device/Vendor/MSFT/Policy/Config/DeviceGuard/EnableVirtualizationBasedSecurity`
- Setting: `1`

## RequirePlatformSecurityFeatures

- Policy path: `./Device/Vendor/MSFT/Policy/Config/DeviceGuard/RequirePlatformSecurityFeatures`
- Setting: `3`

## LsaCfgFlags

- Policy path: `./Device/Vendor/MSFT/Policy/Config/DeviceGuard/LsaCfgFlags`
- Setting: `1`

## AllowThirdPartySuggestionsInWindowsSpotlight

- Policy path: `./User/Vendor/MSFT/Policy/Config/Experience/AllowThirdPartySuggestionsInWindowsSpotlight`
- Setting: `0`

## AllowWindowsConsumerFeatures

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Experience/AllowWindowsConsumerFeatures`
- Setting: `1`

## EnableInsecureGuestLogons

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LanmanWorkstation/EnableInsecureGuestLogons`
- Setting: `0`

## AllowIndexingEncryptedStoresOrItems

Policy path: `./Device/Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems`
Setting: `0`

## EnableSmartScreenInShell

- Policy path: `./Device/Vendor/MSFT/Policy/Config/SmartScreen/EnableSmartScreenInShell`
- Setting: `1`

## PreventOverrideForFilesInShell

- Policy path: `./Device/Vendor/MSFT/Policy/Config/SmartScreen/PreventOverrideForFilesInShell`
- Setting: `1`

## AllowAutoConnectToWiFiSenseHotspots

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Wifi/AllowAutoConnectToWiFiSenseHotspots`
- Setting: `0`

## AllowInternetSharing

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Wifi/AllowInternetSharing`
- Setting: `0`

## AllowWindowsInkWorkspace

- Policy path: `./Device/Vendor/MSFT/Policy/Config/WindowsInkWorkspace/AllowWindowsInkWorkspace`
- Setting: `1`

## InteractiveLogon_SmartCardRemovalBehavior

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/InteractiveLogon_SmartCardRemovalBehavior`
- Setting: `1`

## NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM`
- Setting: `O:BAG:BAD:(A;;RC;;;BA)`

## Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly`
- Setting: `1`

## InteractiveLogon_MachineInactivityLimit

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/InteractiveLogon_MachineInactivityLimit`
- Setting: `900`

## MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers`
- Setting: `0`

## MicrosoftNetworkServer_DigitallySignCommunicationsAlways

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/MicrosoftNetworkServer_DigitallySignCommunicationsAlways`
- Setting: `1`

## NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts`
- Setting: `1`

## NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares`

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares`
- Setting: `1`

## NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares`
- Setting: `1`

## NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange`
- Setting: `1`

## NetworkSecurity_LANManagerAuthenticationLevel

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkSecurity_LANManagerAuthenticationLevel`
- Setting: `5`

## NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers`
- Setting: `537395200`

## UserAccountControl_UseAdminApprovalMode

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_UseAdminApprovalMode`
- Setting: `1`

## UserAccountControl_BehaviorOfTheElevationPromptForAdministrators

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_BehaviorOfTheElevationPromptForAdministrators`
- Setting: `2`

## UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers

- Policy path:`./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers`
- Setting: `3`

## UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations`
- Setting: `1`

## UserAccountControl_RunAllAdministratorsInAdminApprovalMode

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_RunAllAdministratorsInAdminApprovalMode`
- Setting: `1`

## UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations`
- Setting: `1`

## UserAccountControl_DetectApplicationInstallationsAndPromptForElevation

- Policy path: `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_DetectApplicationInstallationsAndPromptForElevation`
- Setting: `1`

## MinimumPasswordAge

- Policy path: `./Device/Vendor/MSFT/Policy/Config/DeviceLock/MinimumPasswordAge`
- Setting: `1`

## BackupFilesAndDirectories

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/BackupFilesAndDirectories`
- Setting: `*S-1-5-32-544`

## CreatePageFile

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/CreatePageFile`
- Setting: `*S-1-5-32-544`

## CreateSymbolicLinks

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/CreateSymbolicLinks`
- Setting: `*S-1-5-32-544`

## DebugPrograms

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/DebugPrograms`
- Setting: `*S-1-5-32-544`

## DenyLocalLogOn

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/DenyLocalLogOn`
- Setting: `*S-1-5-32-546`

## RemoteShutdown

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/RemoteShutdown`
- Setting: `*S-1-5-32-544`

## LoadUnloadDeviceDrivers

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/LoadUnloadDeviceDrivers`
- Setting: `*S-1-5-32-544`

## ManageAuditingAndSecurityLog

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/ManageAuditingAndSecurityLog`
- Setting: `*S-1-5-32-544`

## ModifyFirmwareEnvironment`

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/ModifyFirmwareEnvironment`
- Setting: `*S-1-5-32-544`

## ManageVolume

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/ManageVolume`
- Setting: `*S-1-5-32-544`

## ProfileSingleProcess

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/ProfileSingleProcess`
- Setting: `*S-1-5-32-544`

## RestoreFilesAndDirectories

- Policy path:`./Device/Vendor/MSFT/Policy/Config/UserRights/RestoreFilesAndDirectories`
- Setting: `*S-1-5-32-544`

## TakeOwnership

- Policy path: `./Device/Vendor/MSFT/Policy/Config/UserRights/TakeOwnership`
- Setting: `*S-1-5-32-544`

## AllowToasts

- Policy path: `./Device/Vendor/MSFT/Policy/Config/AboveLock/AllowToasts`
- Setting: `0`

## AllowDirectMemoryAccess`

- Policy path: `./Device/Vendor/MSFT/Policy/Config/DataProtection/AllowDirectMemoryAccess`
- Setting: `0`

## AttackSurfaceReductionRules

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`
- Setting:
    - `75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84=2|3b576869-a4ec-4529-8536-b80a7769e899=2|`
    - `d4f940ab-401b-4efc-aadc-ad5f3c50688a=2|92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B=2|`
    - `5beb7efe-fd9a-4556-801d-275e5ffc04cc=2|d3e037e1-3eb8-44c8-a917-57927947596d=2|`
    - `be9ba2d9-53ea-4cdc-84e5-9b1eeee46550=2|9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2=2|`
    - `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4=2|7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c=2|`

## FacialFeaturesUseEnhancedAntiSpoofing

- Policy path: `./Device/Vendor/MSFT/PassportForWork/Biometrics/FacialFeaturesUseEnhancedAntiSpoofing`
- Setting: `TRUE`

## EnableFirewall

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/DomainProfile/EnableFirewall`
- Setting: `TRUE`

## DefaultInboundAction

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/DomainProfile/DefaultInboundAction`
- Setting: `1`

## DefaultOutboundAction

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/DomainProfile/DefaultOutboundAction`
- Setting: `0`

## DisableInboundNotifications

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/DomainProfile/DisableInboundNotifications`
- Setting: `TRUE`

## EnableFirewall (privae profile)

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/PrivateProfile/EnableFirewall`
- Setting: `TRUE`

## DefaultInboundAction (private profile)

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/PrivateProfile/DefaultInboundAction`
- Setting: `1`

## DefaultOutboundAction (private profile)

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/PrivateProfile/DefaultOutboundAction`
- Setting: `0`

## DisableInboundNotifications (private profile)

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/PrivateProfile/DisableInboundNotifications`
- Setting: `TRUE`

## EnableFirewall (public profile)

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/EnableFirewall`
- Setting: `TRUE`

## DefaultInboundAction (public profile)

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/DefaultInboundAction`
- Setting: `1`

## DefaultOutboundAction (public profile)

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/DefaultOutboundAction`
- Setting: `0`

## DisableInboundNotifications (public profile)

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/DisableInboundNotifications`
- Setting: `TRUE`

## AllowLocalPolicyMerge

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/AllowLocalPolicyMerge`
- Setting: `FALSE`

## AllowLocalIpsecPolicyMerge

- Policy path: `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/AllowLocalIpsecPolicyMerge`
- Setting: `FALSE`

## ExploitProtectionSettings

- Policy path: `./Device/Vendor/MSFT/Policy/Config/ExploitGuard/ExploitProtectionSettings`
- Setting:

```xml
<?xml version=""""1.0"""" encoding=""""UTF-8""""?><MitigationPolicy><AppConfig Executable=""""ONEDRIVE.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><ImageLoad BlockRemoteImageLoads=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""firefox.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR ForceRelocateImages=""""true"""" RequireInfo=""""false"""" BottomUp=""""true"""" HighEntropy=""""false"""" /></AppConfig><AppConfig Executable=""""fltldr.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ImageLoad BlockRemoteImageLoads=""""true"""" /><ChildProcess DisallowChildProcessCreation=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""GROOVE.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><ImageLoad BlockRemoteImageLoads=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /><ChildProcess DisallowChildProcessCreation=""""true"""" /></AppConfig><AppConfig Executable=""""Acrobat.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR ForceRelocateImages=""""true"""" RequireInfo=""""false"""" BottomUp=""""true"""" HighEntropy=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""AcroRd32.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR ForceRelocateImages=""""true"""" RequireInfo=""""false"""" BottomUp=""""true"""" HighEntropy=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""chrome.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /></AppConfig><AppConfig Executable=""""EXCEL.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""iexplore.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR ForceRelocateImages=""""true"""" RequireInfo=""""false"""" BottomUp=""""true"""" HighEntropy=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""INFOPATH.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""java.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""javaw.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""javaws.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""LYNC.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""MSACCESS.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""MSPUB.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""OIS.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""OUTLOOK.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""plugin-container.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""POWERPNT.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""PPTVIEW.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""VISIO.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""VPREVIEW.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""WINWORD.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""wmplayer.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""wordpad.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig></MitigationPolicy>
```

## BlockPicturePassword

- Policy path: `./Device/Vendor/MSFT/Policy/Config/CredentialProviders/BlockPicturePassword`
- Setting: `<Enabled/>`

## DontDisplayNetworkSelectionUI

- Policy path: `.Device/Vendor/MSFT/Policy/Config/WindowsLogon/DontDisplayNetworkSelectionUI`
- Setting: `<Disabled/>`

## CloudExtendedTimeout

- Policy path: `./Device/Vendor/MSFT/Policy/Config/Defender/CloudExtendedTimeout`
- Setting: `10`
