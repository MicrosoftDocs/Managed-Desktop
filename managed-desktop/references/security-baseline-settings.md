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

The following table lists the security baseline settings used in Microsoft Managed Desktop.

| Policy setting name | Policy path | Settings |
| ----- | ----- | ----- |
| `PUAProtection` | `./Device/Vendor/MSFT/Policy/Config/Defender/PUAProtection` | 1 |
| `SetDisablePauseUXAccess` | `./Device/Vendor/MSFT/Policy/Config/Update/SetDisablePauseUXAccess` | 1 |
| `SvchostProcessMitigation` | `./Device/Vendor/MSFT/Policy/Config/ServiceControlManager/SvchostProcessMitigation` | `<Enabled/>` |
| `LetAppsActivateWithVoice` | `./Device/Vendor/MSFT/Policy/Config/Privacy/LetAppsActivateWithVoice` | 2 |
| `ConfigureTelemetryOptinChangeNotification` | `./Device/Vendor/MSFT/Policy/Config/System/ConfigureTelemetryOptinChangeNotification` | 0 |
| `ConfigureTelemetryOptInSettingsUX` | `./Device/Vendor/MSFT/Policy/Config/System/ConfigureTelemetryOptInSettingsUX` |	0 |
| `DisableDeviceDelete` | `./Device/Vendor/MSFT/Policy/Config/System/DisableDeviceDelete` |	0 |
| `AllowMicrosoftAccountsToBeOptional` | `./Device/Vendor/MSFT/Policy/Config/AppRuntime/AllowMicrosoftAccountsToBeOptional`| `<Enabled/>` |
| `DisallowAutoplayForNonVolumeDevices` | `./Device/Vendor/MSFT/Policy/Config/Autoplay/DisallowAutoplayForNonVolumeDevices`| `<Enabled/>` |
| `SetDefaultAutoRunBehavior` | `./Device/Vendor/MSFT/Policy/Config/Autoplay/SetDefaultAutoRunBehavior` | `<Enabled/><Data id=""""NoAutorun_Dropdown"""" value=""""1""""/>` |
| `TurnOffAutoPlay`| `./Device/Vendor/MSFT/Policy/Config/Autoplay/TurnOffAutoPlay` | `<Enabled/><Data id=""""Autorun_Box"""" value=""""255""""/>` |
| `HardenedUNCPaths` | `./Device/Vendor/MSFT/Policy/Config/Connectivity/HardenedUNCPaths` |	`"<Enabled/><Data id=""Pol_HardenedPaths"" value=""\\*\SYSVOL&#xF000;RequireMutualAuthentication=1,RequireIntegrity=1&#xF000;\\*\NETLOGON&#xF000;RequireMutualAuthentication=1,RequireIntegrity=1""/>"` |
| `DisableDownloadingOfPrintDriversOverHTTP` | `./Device/Vendor/MSFT/Policy/Config/Connectivity/DisableDownloadingOfPrintDriversOverHTTP` | `<Enabled/>` |
| `DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards` | `./Device/Vendor/MSFT/Policy/Config/Connectivity/DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards` | `<Enabled/>` |
| `DiablePrintingOverHTTP` | `./Device/Vendor/MSFT/Policy/Config/Connectivity/DiablePrintingOverHTTP` |	`<Disabled/>` |
| `AllowPINLogon` | `./Device/Vendor/MSFT/Policy/Config/CredentialProviders/AllowPINLogon` | `<Disabled/>` |
| `RemoteHostAllowsDelegationOfNonExportableCredentials` | `./Device/Vendor/MSFT/Policy/Config/CredentialsDelegation/RemoteHostAllowsDelegationOfNonExportableCredentials` | `<Enabled/>` |
| `EnumerateAdministrators` | `./Device/Vendor/MSFT/Policy/Config/CredentialsUI/EnumerateAdministrators` | `<Disabled/>` |
| `PreventInstallationOfMatchingDeviceSetupClasses`	| `./Device/Vendor/MSFT/Policy/Config/DeviceInstallation/PreventInstallationOfMatchingDeviceSetupClasses` | `<Enabled/><Data id=""""DeviceInstall_Classes_Deny_List"""" value=""""1&#xF000;{d48179be-ec20-11d1-b6b8-00c04fa372a7}""""/><Data id=""""DeviceInstall_Classes_Deny_Retroactive"""" value=""""true""""/>`|
| `PreventLockScreenSlideShow` | `./Device/Vendor/MSFT/Policy/Config/DeviceLock/PreventLockScreenSlideShow` | `<Enabled/>` |
| `PreventEnablingLockScreenCamera` | `./Device/Vendor/MSFT/Policy/Config/DeviceLock/PreventEnablingLockScreenCamera` |	`<Enabled/>` |
| `SpecifyMaximumFileSizeApplicationLog` | `./Device/Vendor/MSFT/Policy/Config/EventLogService/SpecifyMaximumFileSizeApplicationLog` |`<Enabled/><Data id=""""Channel_LogMaxSize"""" value=""""32768""""/>` |
| `SpecifyMaximumFileSizeSecurityLog` | `./Device/Vendor/MSFT/Policy/Config/EventLogService/SpecifyMaximumFileSizeSecurityLog` | `<Enabled/><Data id=""""Channel_LogMaxSize"""" value=""""196608""""/>` |
| `SpecifyMaximumFileSizeSystemLog` | `./Device/Vendor/MSFT/Policy/Config/EventLogService/SpecifyMaximumFileSizeSystemLog` | `<Enabled/><Data id=""""Channel_LogMaxSize"""" value=""""32768""""/>` |
| `TurnOffDataExecutionPreventionForExplorer` | `./Device/Vendor/MSFT/Policy/Config/FileExplorer/TurnOffDataExecutionPreventionForExplorer` | `<Disabled/>` |
|`TurnOffHeapTerminationOnCorruption` | `./Device/Vendor/MSFT/Policy/Config/FileExplorer/TurnOffHeapTerminationOnCorruption` | `<Disabled/>` |
| `DoNotAllowUsersToAddSites` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DoNotAllowUsersToAddSites` | `<Enabled/>` |
| `DoNotAllowUsersToChangePolicies` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DoNotAllowUsersToChangePolicies` | `<Enabled/>` |
| `DisableEncryptionSupport` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableEncryptionSupport` | `<Enabled/><Data id=""""Advanced_WinInetProtocolOptions"""" value=""""2688""""/>` |
| `AllowEnhancedProtectedMode` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/AllowEnhancedProtectedMode` | `<Enabled/>` |
| `IncludeAllNetworkPaths` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/IncludeAllNetworkPaths` |	`<Disabled/>` |
| `InternetZoneAllowAccessToDataSources` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowAccessToDataSources` |`<Enabled/><Data id=""""IZ_Partname1406"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowAccessToDataSources` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowAccessToDataSources` | `<Enabled/><Data id=""""IZ_Partname1406"""" value=""""3""""/>` |
| `InternetZoneAllowScriptlets`	| `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowScriptlets` | `<Enabled/><Data id=""""IZ_Partname1209"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowScriptlets` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowScriptlets` |	`<Enabled/><Data id=""""IZ_Partname1209"""" value=""""3""""/>`|
| `InternetZoneAllowAutomaticPromptingForFileDownloads` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowAutomaticPromptingForFileDownloads`| `<Enabled/><Data id=""""IZ_Partname2200"""" value=""""3""""/>`|
| `RestrictedSitesZoneAllowAutomaticPromptingForFileDownloads` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowAutomaticPromptingForFileDownloads` | `<Enabled/><Data id=""""IZ_Partname2200"""" value=""""3""""/>` |
| `InternetZoneInitializeAndScriptActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneInitializeAndScriptActiveXControls` | `<Enabled/><Data id=""""IZ_Partname1201"""" value=""""3""""/>` |
| `IntranetZoneInitializeAndScriptActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/IntranetZoneInitializeAndScriptActiveXControls` | `<Enabled/><Data id=""""IZ_Partname1201"""" value=""""3""""/>` |
| `TrustedSitesZoneInitializeAndScriptActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/TrustedSitesZoneInitializeAndScriptActiveXControls` | `<Enabled/><Data id=""""IZ_Partname1201"""" value=""""3""""/>` |
| `RestrictedSitesZoneInitializeAndScriptActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneInitializeAndScriptActiveXControls` | `<Enabled/><Data id=""""IZ_Partname1201"""" value=""""3""""/>` |
| `InternetZoneNavigateWindowsAndFrames` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneNavigateWindowsAndFrames` | `<Enabled/><Data ID=""""IZ_Partname1607""" value=""""3""""/>` |
| `RestrictedSitesZoneNavigateWindowsAndFrames` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneNavigateWindowsAndFrames` | `<Enabled/><Data id=""""IZ_Partname1607"""" value=""""3""""/>` |
| `InternetZoneAllowNETFrameworkReliantComponents` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowNETFrameworkReliantComponents` | `<Enabled/><Data id=""""IZ_Partname2004"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowNETFrameworkReliantComponents` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowNETFrameworkReliantComponents` | `<Enabled/><Data id=""""IZ_Partname2004"""" value=""""3""""/>` |
| `InternetZoneAllowSmartScreenIE` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowSmartScreenIE` |`<Enabled/><Data id=""""IZ_Partname2301"""" value=""""0""""/>`|
| `LockedDownInternetZoneAllowSmartScreenIE` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownInternetZoneAllowSmartScreenIE` | `<Enabled/><Data id=""""IZ_Partname2301"""" value=""""0""""/>` |
| `RestrictedSitesZoneAllowSmartScreenIE` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowSmartScreenIE` | `<Enabled/><Data id=""""IZ_Partname2301"""" value=""""0""""/>` |
| `LockedDownRestrictedSitesZoneAllowSmartScreenIE` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownRestrictedSitesZoneAllowSmartScreenIE` | `<Enabled/><Data id=""""IZ_Partname2301"""" value=""""0""""/>` |
| `InternetZoneAllowUserDataPersistence` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowUserDataPersistence` | `<Enabled/><Data id=""""IZ_Partname1606"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowUserDataPersistence` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowUserDataPersistence` | `<Enabled/><Data id=""""IZ_Partname1606"""" value=""""3""""/>` |
| `InternetZoneAllowLessPrivilegedSites` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowLessPrivilegedSites` |`<Enabled/><Data id=""""IZ_Partname2101"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowLessPrivilegedSites` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowLessPrivilegedSites` | `<Enabled/><Data id=""""IZ_Partname2101"""" value=""""3""""/>` |
| `DoNotBlockOutdatedActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DoNotBlockOutdatedActiveXControls` | `<Disabled/>` |
| `DisableEnclosureDownloading` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableEnclosureDownloading` |`<Enabled/>` |
| `DisableBypassOfSmartScreenWarnings` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableBypassOfSmartScreenWarnings` |	`<Enabled/>`|
| `DisableBypassOfSmartScreenWarningsAboutUncommonFiles` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableBypassOfSmartScreenWarningsAboutUncommonFiles` | `<Enabled/>` |
| `RestrictedSitesZoneAllowActiveScripting` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowActiveScripting` | `<Enabled/><Data id=""""IZ_Partname1400"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowBinaryAndScriptBehaviors` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowBinaryAndScriptBehaviors` | `<Enabled/><Data id=""""IZ_Partname2000"""" value=""""3""""/>` |
| `InternetZoneAllowCopyPasteViaScript` |`./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowCopyPasteViaScript` | `<Enabled/><Data id=""""IZ_Partname1407"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowCopyPasteViaScript` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowCopyPasteViaScript` | `<Enabled/><Data id=""""IZ_Partname1407"""" value=""""3""""/>` |
| `InternetZoneAllowDragAndDropCopyAndPasteFiles` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowDragAndDropCopyAndPasteFiles` | `<Enabled/><Data id=""""IZ_Partname1802"""" value=""""3""""/>`|
| `estrictedSitesZoneAllowDragAndDropCopyAndPasteFiles` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowDragAndDropCopyAndPasteFiles` | `<Enabled/><Data id=""""IZ_Partname1802"""" value=""""3""""/>` |
| `AllowFallbackToSSL3` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/AllowFallbackToSSL3` | `<Enabled/><Data id=""""Advanced_EnableSSL3FallbackOptions"""" value=""""0""""/>` |
| `RestrictedSitesZoneAllowFileDownloads` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowFileDownloads` | `<Enabled/><Data id=""""IZ_Partname1803"""" value=""""3""""/>` |
| `InternetZoneAllowLoadingOfXAMLFiles` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowLoadingOfXAMLFiles` | `<Enabled/><Data id=""""IZ_Partname2402"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowLoadingOfXAMLFiles` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowLoadingOfXAMLFiles` | `<Enabled/><Data id=""""IZ_Partname2402"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowMETAREFRESH` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowMETAREFRESH` | `<Enabled/><Data id=""""IZ_Partname1608"""" value=""""3""""/>` |
| `InternetZoneAllowOnlyApprovedDomainsToUseActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowOnlyApprovedDomainsToUseActiveXControls` | `<Enabled/><Data id=""""IZ_Partname120b"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowOnlyApprovedDomainsToUseActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowOnlyApprovedDomainsToUseActiveXControls` | `<Enabled/><Data id=""""IZ_Partname120b"""" value=""""3""""/>` |
| `InternetZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl` | `<Enabled/><Data id=""""IZ_Partname120c"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl` | `<Enabled/><Data id=""""IZ_Partname120c"""" value=""""3""""/>` |
| `InternetZoneAllowScriptingOfInternetExplorerWebBrowserControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowScriptingOfInternetExplorerWebBrowserControls` | `<Enabled/><Data id=""""IZ_Partname1206"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowScriptingOfInternetExplorerWebBrowserControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowScriptingOfInternetExplorerWebBrowserControls` | `<Enabled/><Data id=""""IZ_Partname1206"""" value=""""3""""/>` |
| `InternetZoneAllowScriptInitiatedWindows` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowScriptInitiatedWindows` | `<Enabled/><Data id=""""IZ_Partname2102"""" value=""""3""""/>` |
| `-RestrictedSitesZoneAllowScriptInitiatedWindows` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowScriptInitiatedWindows` | `<Enabled/><Data id=""""IZ_Partname2102"""" value=""""3""""/>` |
| `AllowSoftwareWhenSignatureIsInvalid` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/AllowSoftwareWhenSignatureIsInvalid` |`<Disabled/>` |
| `InternetZoneAllowUpdatesToStatusBarViaScript` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowUpdatesToStatusBarViaScript` | `<Enabled/><Data id=""""IZ_Partname2103"""" value=""""3""""/>` |
| `RestrictedSitesZoneAllowUpdatesToStatusBarViaScript` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowUpdatesToStatusBarViaScript` | `<Enabled/><Data id=""""IZ_Partname2103"""" value=""""3""""/>`|
| `CheckServerCertificateRevocation` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/CheckServerCertificateRevocation` | `<Enabled/>` |
| `CheckSignaturesOnDownloadedPrograms` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/CheckSignaturesOnDownloadedPrograms` |`<Enabled/>` |
| `DoNotAllowActiveXControlsInProtectedMode` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DoNotAllowActiveXControlsInProtectedMode` | `<Enabled/>` |
| `InternetZoneDoNotRunAntimalwareAgainstActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneDoNotRunAntimalwareAgainstActiveXControls` | `<Enabled/><Data id=""""IZ_Partname270C"""" value=""""0""""/>` |
| `IntranetZoneDoNotRunAntimalwareAgainstActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/IntranetZoneDoNotRunAntimalwareAgainstActiveXControls` | `<Enabled/><Data id=""""IZ_Partname270C"""" value=""""0""""/>` |
| `LocalMachineZoneDoNotRunAntimalwareAgainstActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LocalMachineZoneDoNotRunAntimalwareAgainstActiveXControls` | `<Enabled/><Data id=""""IZ_Partname270C"""" value=""""0""""/>` |
| `RestrictedSitesZoneDoNotRunAntimalwareAgainstActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneDoNotRunAntimalwareAgainstActiveXControls` | `<Enabled/><Data id=""""IZ_Partname270C"""" value=""""0""""/>` |
| `TrustedSitesZoneDoNotRunAntimalwareAgainstActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/TrustedSitesZoneDoNotRunAntimalwareAgainstActiveXControls` | `<Enabled/><Data id=""""IZ_Partname270C"""" value=""""0""""/>` |
| `PreventManagingSmartScreenFilter` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/PreventManagingSmartScreenFilter` | `<Enabled/><Data id=""""IE9SafetyFilterOptions"""" value=""""1""""/>` |
| `InternetZoneDownloadSignedActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneDownloadSignedActiveXControls` | `<Enabled/><Data id=""""IZ_Partname1001"""" value=""""3""""/>` |
| `RestrictedSitesZoneDownloadSignedActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneDownloadSignedActiveXControls` | `<Enabled/><Data id=""""IZ_Partname1001"""" value=""""3""""/>` |
| `InternetZoneDownloadUnsignedActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneDownloadUnsignedActiveXControls` | `<Enabled/><Data id=""""IZ_Partname1004"""" value=""""3""""/>` |
| `RestrictedSitesZoneDownloadUnsignedActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneDownloadUnsignedActiveXControls` | `<Enabled/><Data id=""""IZ_Partname1004"""" value=""""3""""/>` |
| `InternetZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows`| `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows`|  `<Enabled/><Data id=""""IZ_Partname2709"""" value=""""3""""/>` |
| `RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows` | `<Enabled/><Data id=""""IZ_Partname2709"""" value=""""3""""/>` |
| `InternetZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows`| `<Enabled/><Data id=""""IZ_Partname2708"""" value=""""3""""/>` |
| `RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows` | `<Enabled/><Data id=""""IZ_Partname2708"""" value=""""3""""/>` |
| `InternetZoneIncludeLocalPathWhenUploadingFilesToServer` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneIncludeLocalPathWhenUploadingFilesToServer` | `<Enabled/><Data id=""""IZ_Partname160A"""" value=""""3""""/>` |
| `RestrictedSitesZoneIncludeLocalPathWhenUploadingFilesToServer` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneIncludeLocalPathWhenUploadingFilesToServer`| `<Enabled/><Data id=""""IZ_Partname160A"""" value=""""3""""/>`|
| `ConsistentMimeHandlingInternetExplorerProcesses` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/ConsistentMimeHandlingInternetExplorerProcesses` | `<Enabled/>` |
| `MimeSniffingSafetyFeatureInternetExplorerProcesses` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/MimeSniffingSafetyFeatureInternetExplorerProcesses` | `<Enabled/>` |
| `MKProtocolSecurityRestrictionInternetExplorerProcesses` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/MKProtocolSecurityRestrictionInternetExplorerProcesses` | `<Enabled/>` |
| `NotificationBarInternetExplorerProcesses` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/NotificationBarInternetExplorerProcesses` | `<Enabled/>` |
| `ProtectionFromZoneElevationInternetExplorerProcesses` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/ProtectionFromZoneElevationInternetExplorerProcesses` | `<Enabled/>` |
| `RestrictActiveXInstallInternetExplorerProcesses` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictActiveXInstallInternetExplorerProcesses` | `<Enabled/>` |
| `RestrictFileDownloadInternetExplorerProcesses` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictFileDownloadInternetExplorerProcesses` | `<Enabled/>` |
| `ScriptedWindowSecurityRestrictionsInternetExplorerProcesses` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/ScriptedWindowSecurityRestrictionsInternetExplorerProcesses` | `<Enabled/>` |
| `InternetZoneJavaPermissions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneJavaPermissions` | `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>` |
| `IntranetZoneJavaPermissions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/IntranetZoneJavaPermissions` | `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""65536""""/>` |
| `LocalMachineZoneJavaPermissions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LocalMachineZoneJavaPermissions` | `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>` |
| `LockedDownLocalMachineZoneJavaPermissions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownLocalMachineZoneJavaPermissions` | `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>` |
| `LockedDownRestrictedSitesZoneJavaPermissions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownRestrictedSitesZoneJavaPermissions` | `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>` |
| `LockedDownTrustedSitesZoneJavaPermissions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownTrustedSitesZoneJavaPermissions` | `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>` |
| `RestrictedSitesZoneJavaPermissions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneJavaPermissions` |`<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>` |
| `TrustedSitesZoneJavaPermissions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/TrustedSitesZoneJavaPermissions` | `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""65536""""/>` |
| `InternetZoneLaunchingApplicationsAndFilesInIFRAME` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneLaunchingApplicationsAndFilesInIFRAME` | `<Enabled/><Data id=""""IZ_Partname1804"""" value=""""3""""/>` |
| `RestrictedSitesZoneLaunchingApplicationsAndFilesInIFRAME` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneLaunchingApplicationsAndFilesInIFRAME` | `<Enabled/><Data id=""""IZ_Partname1804"""" value=""""3""""/>` |
| `InternetZoneLogonOptions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneLogonOptions` | `<Enabled/><Data id=""""IZ_Partname1A00"""" value=""""65536""""/>` |
| `RestrictedSitesZoneLogonOptions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneLogonOptions` | `<Enabled/><Data id=""""IZ_Partname1A00"""" value=""""196608""""/>` |
| `DisableIgnoringCertificateErrors` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableIgnoringCertificateErrors` | `<Enabled/>` |
| `PreventPerUserInstallationOfActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/PreventPerUserInstallationOfActiveXControls` | `<Enabled/>` |
| `RemoveRunThisTimeButtonForOutdatedActiveXControls` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RemoveRunThisTimeButtonForOutdatedActiveXControls` | `<Enabled/>` |
| `InternetZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode` | `<Enabled/><Data id=""""IZ_Partname2001"""" value=""""3""""/>` |
| `RestrictedSitesZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneRunNETFrameworkReliantComponentsSignedWithAuthenticode` | `<Enabled/><Data id=""""IZ_Partname2001"""" value=""""3""""/>` |
| `RestrictedSitesZoneRunActiveXControlsAndPlugins` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneRunActiveXControlsAndPlugins` | `<Enabled/><Data id=""""IZ_Partname1200"""" value=""""3""""/>` |
| `RestrictedSitesZoneScriptActiveXControlsMarkedSafeForScripting` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneScriptActiveXControlsMarkedSafeForScripting` | `<Enabled/><Data id=""""IZ_Partname1405"""" value=""""3""""/>` |
| `RestrictedSitesZoneScriptingOfJavaApplets` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneScriptingOfJavaApplets` | `<Enabled/><Data id=""""IZ_Partname1402"""" value=""""3""""/>` |
| `SecurityZonesUseOnlyMachineSettings` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/SecurityZonesUseOnlyMachineSettings` | `<Enabled/>` |
| `InternetZoneShowSecurityWarningForPotentiallyUnsafeFiles` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneShowSecurityWarningForPotentiallyUnsafeFiles` | `<Enabled/><Data id=""""IZ_Partname1806"""" value=""""1""""/>` |
| `RestrictedSitesZoneShowSecurityWarningForPotentiallyUnsafeFiles`| `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneShowSecurityWarningForPotentiallyUnsafeFiles` | `<Enabled/><Data id=""""IZ_Partname1806"""" value=""""3""""/>` |
| `SpecifyUseOfActiveXInstallerService` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/SpecifyUseOfActiveXInstallerService` | `<Enabled/>` |
| `DisableCrashDetection` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableCrashDetection` | `<Enabled/>` |
| `DisableSecuritySettingsCheck` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableSecuritySettingsCheck` | `<Disabled/>` |
| `DisableProcessesInEnhancedProtectedMode`| `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/DisableProcessesInEnhancedProtectedMode` | `<Enabled/>` |
| `AllowCertificateAddressMismatchWarning` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/AllowCertificateAddressMismatchWarning`  | `<Enabled/>` |
| `InternetZoneEnableCrossSiteScriptingFilter` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneEnableCrossSiteScriptingFilter`| `<Enabled/><Data id=""""IZ_Partname1409"""" value=""""0""""/>` |
| `RestrictedSitesZoneEnableCrossSiteScriptingFilter`| `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneEnableCrossSiteScriptingFilter` | `<Enabled/><Data id=""""IZ_Partname1409"""" value=""""0""""/>` |
| `InternetZoneEnableProtectedMode` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneEnableProtectedMode` | `<Enabled/><Data id=""""IZ_Partname2500"""" value=""""0""""/>` |
| `RestrictedSitesZoneTurnOnProtectedMode` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneTurnOnProtectedMode` | `<Enabled/><Data id=""""IZ_Partname2500"""" value=""""0""""/>` |
| `InternetZoneUsePopupBlocker` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneUsePopupBlocker` | `<Enabled/><Data id=""""IZ_Partname1809"""" value=""""0""""/>` |
| `RestrictedSitesZoneUsePopupBlocker` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneUsePopupBlocker` | `<Enabled/><Data id=""""IZ_Partname1809"""" value=""""0""""/>` |
| `InternetZoneAllowVBScriptToRunInInternetExplorer` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/InternetZoneAllowVBScriptToRunInInternetExplorer` | `<Enabled/><Data id=""""IZ_Partname140C"""" value=""""3""""/>` |
| `LockedDownIntranetJavaPermissions` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/LockedDownIntranetJavaPermissions` | `<Enabled/><Data id=""""IZ_Partname1C00"""" value=""""0""""/>` |
| `RestrictedSitesZoneAllowVBScriptToRunInInternetExplorer` | `./Device/Vendor/MSFT/Policy/Config/InternetExplorer/RestrictedSitesZoneAllowVBScriptToRunInInternetExplorer` | `<Enabled/><Data id=""""IZ_Partname140C"""" value=""""3""""/>` |
| `ApplyUACRestrictionsToLocalAccountsOnNetworkLogon` | `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/ApplyUACRestrictionsToLocalAccountsOnNetworkLogon` | `<Enabled/>` |
| `ConfigureSMBV1Server` | `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/ConfigureSMBV1Server` | `<Disabled/>` |
| `ConfigureSMBV1ClientDriver` | `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/ConfigureSMBV1ClientDriver` | `<Enabled/><Data id=""""Pol_SecGuide_SMB1ClientDriver"""" value=""""4""""/>` |
| `EnableStructuredExceptionHandlingOverwriteProtection` | `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/EnableStructuredExceptionHandlingOverwriteProtection` | `<Enabled/>` |
| `WDigestAuthentication` | `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/WDigestAuthentication`| `<Disabled/>` |
| `TurnOnWindowsDefenderProtectionAgainstPotentiallyUnwantedApplications`| `./Device/Vendor/MSFT/Policy/Config/MSSecurityGuide/TurnOnWindowsDefenderProtectionAgainstPotentiallyUnwantedApplications`| `<Enabled/>` |
| `IPv6SourceRoutingProtectionLevel`| `./Device/Vendor/MSFT/Policy/Config/MSSLegacy/IPv6SourceRoutingProtectionLevel` | `<Enabled/><Data id=""""DisableIPSourceRoutingIPv6"""" value=""""2""""/>`|
| `IPSourceRoutingProtectionLevel` | `./Device/Vendor/MSFT/Policy/Config/MSSLegacy/IPSourceRoutingProtectionLevel` | `<Enabled/><Data id=""""DisableIPSourceRouting"""" value=""""2""""/>` |
| `AllowICMPRedirectsToOverrideOSPFGeneratedRoutes` | `./Device/Vendor/MSFT/Policy/Config/MSSLegacy/AllowICMPRedirectsToOverrideOSPFGeneratedRoutes` | `<Disabled/>` |
| `AllowTheComputerToIgnoreNetBIOSNameReleaseRequestsExceptFromWINSServers` | `./Device/Vendor/MSFT/Policy/Config/MSSLegacy/AllowTheComputerToIgnoreNetBIOSNameReleaseRequestsExceptFromWINSServers` | `<Enabled/>` |
| `AllowStandbyWhenSleepingPluggedIn` | `./Device/Vendor/MSFT/Policy/Config/Power/AllowStandbyWhenSleepingPluggedIn` | `<Disabled/>` |
| `RequirePasswordWhenComputerWakesOnBattery` | `./Device/Vendor/MSFT/Policy/Config/Power/RequirePasswordWhenComputerWakesOnBattery` | `<Enabled/>` |
| `RequirePasswordWhenComputerWakesPluggedIn` | `./Device/Vendor/MSFT/Policy/Config/Power/RequirePasswordWhenComputerWakesPluggedIn` | `<Enabled/>` |
| `AllowStandbyStatesWhenSleepingOnBattery` | `./Device/Vendor/MSFT/Policy/Config/Power/AllowStandbyStatesWhenSleepingOnBattery` | `<Disabled/>` |
| `SolicitedRemoteAssistance` | `./Device/Vendor/MSFT/Policy/Config/RemoteAssistance/SolicitedRemoteAssistance` | `<Disabled/>` |
| `DoNotAllowPasswordSaving` | `./Device/Vendor/MSFT/Policy/Config/RemoteDesktopServices/DoNotAllowPasswordSaving` | `<Enabled/>` |
| `DoNotAllowDriveRedirection` | `./Device/Vendor/MSFT/Policy/Config/RemoteDesktopServices/DoNotAllowDriveRedirection` | `<Enabled/>` |
| `PromptForPasswordUponConnection`| `./Device/Vendor/MSFT/Policy/Config/RemoteDesktopServices/PromptForPasswordUponConnection` | `<Enabled/>` |
| `RequireSecureRPCCommunication` | `./Device/Vendor/MSFT/Policy/Config/RemoteDesktopServices/RequireSecureRPCCommunication` | `<Enabled/>` |
| `ClientConnectionEncryptionLevel` | `./Device/Vendor/MSFT/Policy/Config/RemoteDesktopServices/ClientConnectionEncryptionLevel` | `<Enabled/><Data id=""""TS_ENCRYPTION_LEVEL"""" value=""""3""""/>` |
| `AllowBasicAuthentication_Client` | `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/AllowBasicAuthentication_Client` | `<Disabled/>` |
| `AllowBasicAuthentication_Service` | `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/AllowBasicAuthentication_Service` | `<Disabled/>` |
| `AllowUnencryptedTraffic_Client` | `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/AllowUnencryptedTraffic_Client` | `<Disabled/>` |
| `AllowUnencryptedTraffic_Service` | `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/AllowUnencryptedTraffic_Service` | `<Disabled/>`|
| `DisallowDigestAuthentication` | `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/DisallowDigestAuthentication` | `<Enabled/>` |
| `DisallowStoringOfRunAsCredentials` | `./Device/Vendor/MSFT/Policy/Config/RemoteManagement/DisallowStoringOfRunAsCredentials`| `<Enabled/>` |
| `RestrictUnauthenticatedRPCClients` | `./Device/Vendor/MSFT/Policy/Config/RemoteProcedureCall/RestrictUnauthenticatedRPCClients` | `<Enabled/><Data id=""""RpcRestrictRemoteClientsList"""" value=""""1""""/>` |
| `BootStartDriverInitialization`| `./Device/Vendor/MSFT/Policy/Config/System/BootStartDriverInitialization` | `<Enabled/><Data id=""""SelectDriverLoadPolicy"""" value=""""3""""/>` |
| `ProhitConnectionToNonDomainNetworksWhenConnectedToDomainAuthenticatedNetwork` | `./Device/Vendor/MSFT/Policy/Config/WindowsConnectionManager/ProhitConnectionToNonDomainNetworksWhenConnectedToDomainAuthenticatedNetwork`| `<Enabled/> `|
| `EnumerateLocalUsersOnDomainJoinedComputers` | `./Device/Vendor/MSFT/Policy/Config/WindowsLogon/EnumerateLocalUsersOnDomainJoinedComputers` | `<Disabled/>` |
| `AllowAutomaticRestartSignOn` | `./Device/Vendor/MSFT/Policy/Config/WindowsLogon/AllowAutomaticRestartSignOn` | `<Disabled/>` |
| `TurnOnPowerShellScriptBlockLogging` | `./Device/Vendor/MSFT/Policy/Config/WindowsPowerShell/TurnOnPowerShellScriptBlockLogging` | `<Enabled/><Data id=""""EnableScriptBlockInvocationLogging"""" value=""""true""""/>` |
| `AllowAutoComplete` | `./User/Vendor/MSFT/Policy/Config/InternetExplorer/AllowAutoComplete` | `<Disabled/>` |
| `AllowGameDVR` | `./Device/Vendor/MSFT/Policy/Config/ApplicationManagement/AllowGameDVR` | 0 |
| `MSIAlwaysInstallWithElevatedPrivileges` | `./Device/Vendor/MSFT/Policy/Config/ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges` | 0 |
| `MSIAllowUserControlOverInstall` | `./Device/Vendor/MSFT/Policy/Config/ApplicationManagement/MSIAllowUserControlOverInstall` | 0 |
| `AllowPasswordManager` | `./Device/Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager` | 0 |
| `AllowSmartScreen` | `./Device/Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen`| 1 |
| `PreventSmartScreenPromptOverride` | `./Device/Vendor/MSFT/Policy/Config/Browser/PreventSmartScreenPromptOverride` | 1 |
| `PreventSmartScreenPromptOverrideForFiles` | `./Device/Vendor/MSFT/Policy/Config/Browser/PreventSmartScreenPromptOverrideForFiles` | 1 |
| `AllowBehaviorMonitoring` | `./Device/Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring` | 1 |
| `AllowCloudProtection` | `./Device/Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection` | 1 |
| `AllowEmailScanning` | `./Device/Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning` | 1 |
| `AllowFullScanRemovableDriveScanning` | `./Device/Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning` | 1 |
|  `EnableNetworkProtection` | `./Device/Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection` | 1 |
|  `SubmitSamplesConsent` | `./Device/Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent` | 1 |
| `DisallowExploitProtectionOverride` | `./Device/Vendor/MSFT/Policy/Config/WindowsDefenderSecurityCenter/DisallowExploitProtectionOverride` | 1 |
| `EnableVirtualizationBasedSecurity` | `./Device/Vendor/MSFT/Policy/Config/DeviceGuard/EnableVirtualizationBasedSecurity` | 1 |
| `RequirePlatformSecurityFeatures` | `./Device/Vendor/MSFT/Policy/Config/DeviceGuard/RequirePlatformSecurityFeatures` | 3 |
| `LsaCfgFlags` | `./Device/Vendor/MSFT/Policy/Config/DeviceGuard/LsaCfgFlags` | 1 |
| `AllowThirdPartySuggestionsInWindowsSpotlight` | `./User/Vendor/MSFT/Policy/Config/Experience/AllowThirdPartySuggestionsInWindowsSpotlight` | 0 |
| `AllowWindowsConsumerFeatures` | `./Device/Vendor/MSFT/Policy/Config/Experience/AllowWindowsConsumerFeatures` | 1 |
| `EnableInsecureGuestLogons` | `./Device/Vendor/MSFT/Policy/Config/LanmanWorkstation/EnableInsecureGuestLogons` | 0 |
| `AllowIndexingEncryptedStoresOrItems` | `./Device/Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems` | 0 |
| `EnableSmartScreenInShell` | `./Device/Vendor/MSFT/Policy/Config/SmartScreen/EnableSmartScreenInShell` | 1 |
| `PreventOverrideForFilesInShell` | `./Device/Vendor/MSFT/Policy/Config/SmartScreen/PreventOverrideForFilesInShell` | 1 |
| `AllowAutoConnectToWiFiSenseHotspots` | `./Device/Vendor/MSFT/Policy/Config/Wifi/AllowAutoConnectToWiFiSenseHotspots` | 0 |
| `AllowInternetSharing` | `./Device/Vendor/MSFT/Policy/Config/Wifi/AllowInternetSharing` | 0 |
| `AllowWindowsInkWorkspace` | `./Device/Vendor/MSFT/Policy/Config/WindowsInkWorkspace/AllowWindowsInkWorkspace` | 1 |
| `InteractiveLogon_SmartCardRemovalBehavior` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/InteractiveLogon_SmartCardRemovalBehavior` | 1 |
| `NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM`| `O:BAG:BAD:(A;;RC;;;BA)` |
| `Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly`| 1 |
| `InteractiveLogon_MachineInactivityLimit` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/InteractiveLogon_MachineInactivityLimit` | 900 |
| `MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers` | 0 |
| `MicrosoftNetworkServer_DigitallySignCommunicationsAlways` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/MicrosoftNetworkServer_DigitallySignCommunicationsAlways` | 1 |
| `NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts` | 1 |
| `NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares` | 1 |
| `NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares` | 1 |
| `NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange` | 1 |
| `NetworkSecurity_LANManagerAuthenticationLevel` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkSecurity_LANManagerAuthenticationLevel` | 5 |
| `NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers` | 537395200 |
| `UserAccountControl_UseAdminApprovalMode` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_UseAdminApprovalMode` | 1 |
| `UserAccountControl_BehaviorOfTheElevationPromptForAdministrators` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_BehaviorOfTheElevationPromptForAdministrators` | 2 |
| `UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers` | 3 |
| `UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations` | 1 |
| `UserAccountControl_RunAllAdministratorsInAdminApprovalMode` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_RunAllAdministratorsInAdminApprovalMode` | 1 |
| `UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations` | 1 |
| `UserAccountControl_DetectApplicationInstallationsAndPromptForElevation` | `./Device/Vendor/MSFT/Policy/Config/LocalPoliciesSecurityOptions/UserAccountControl_DetectApplicationInstallationsAndPromptForElevation` | 1 |
| `MinimumPasswordAge` | `./Device/Vendor/MSFT/Policy/Config/DeviceLock/MinimumPasswordAge` | 1 |`
| `BackupFilesAndDirectories` | `./Device/Vendor/MSFT/Policy/Config/UserRights/BackupFilesAndDirectories` | `*S-1-5-32-544` |
| `CreatePageFile` | `./Device/Vendor/MSFT/Policy/Config/UserRights/CreatePageFile` | `*S-1-5-32-544` |
| `CreateSymbolicLinks` | `./Device/Vendor/MSFT/Policy/Config/UserRights/CreateSymbolicLinks` | `*S-1-5-32-544` |
| `DebugPrograms` | `./Device/Vendor/MSFT/Policy/Config/UserRights/DebugPrograms` | `*S-1-5-32-544` |
| `DenyLocalLogOn` | `./Device/Vendor/MSFT/Policy/Config/UserRights/DenyLocalLogOn` | `*S-1-5-32-546` |
| `RemoteShutdown` | `./Device/Vendor/MSFT/Policy/Config/UserRights/RemoteShutdown` | `*S-1-5-32-544` |
| `LoadUnloadDeviceDrivers` | `./Device/Vendor/MSFT/Policy/Config/UserRights/LoadUnloadDeviceDrivers` | `*S-1-5-32-544` |
| `ManageAuditingAndSecurityLog` | `./Device/Vendor/MSFT/Policy/Config/UserRights/ManageAuditingAndSecurityLog` | `*S-1-5-32-544` |
| `ModifyFirmwareEnvironment` | `./Device/Vendor/MSFT/Policy/Config/UserRights/ModifyFirmwareEnvironment` | `*S-1-5-32-544` |
| `ManageVolume` | `./Device/Vendor/MSFT/Policy/Config/UserRights/ManageVolume` | `*S-1-5-32-544` |
| `ProfileSingleProcess` | `./Device/Vendor/MSFT/Policy/Config/UserRights/ProfileSingleProcess` | `*S-1-5-32-544` |
| `RestoreFilesAndDirectories` | `./Device/Vendor/MSFT/Policy/Config/UserRights/RestoreFilesAndDirectories` | `*S-1-5-32-544` |
| `TakeOwnership` | `./Device/Vendor/MSFT/Policy/Config/UserRights/TakeOwnership` | `*S-1-5-32-544` |
| `AllowToasts` | `./Device/Vendor/MSFT/Policy/Config/AboveLock/AllowToasts` | 0 |
| `AllowDirectMemoryAccess` | `./Device/Vendor/MSFT/Policy/Config/DataProtection/AllowDirectMemoryAccess` | 0 |
| `AttackSurfaceReductionRules` | `./Device/Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`| `75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84=2|3b576869-a4ec-4529-8536-b80a7769e899=2|d4f940ab-401b-4efc-aadc-ad5f3c50688a=2|92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B=2|5beb7efe-fd9a-4556-801d-275e5ffc04cc=2|d3e037e1-3eb8-44c8-a917-57927947596d=2|be9ba2d9-53ea-4cdc-84e5-9b1eeee46550=2|9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2=2|b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4=2|7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c=2` |
| `FacialFeaturesUseEnhancedAntiSpoofing` | `./Device/Vendor/MSFT/PassportForWork/Biometrics/FacialFeaturesUseEnhancedAntiSpoofing` | TRUE |
| `EnableFirewall` | `./Device/Vendor/MSFT/Firewall/MdmStore/DomainProfile/EnableFirewall` | TRUE |
| `DefaultInboundAction` | `./Device/Vendor/MSFT/Firewall/MdmStore/DomainProfile/DefaultInboundAction` | 1 |
| `DefaultOutboundAction` | `./Device/Vendor/MSFT/Firewall/MdmStore/DomainProfile/DefaultOutboundAction` | 0 |
| `DisableInboundNotifications` | `./Device/Vendor/MSFT/Firewall/MdmStore/DomainProfile/DisableInboundNotifications`| TRUE |
| `EnableFirewall` | `./Device/Vendor/MSFT/Firewall/MdmStore/PrivateProfile/EnableFirewall` | TRUE |
| `DefaultInboundAction` | `./Device/Vendor/MSFT/Firewall/MdmStore/PrivateProfile/DefaultInboundAction` | 1 |
| `DefaultOutboundAction` | `./Device/Vendor/MSFT/Firewall/MdmStore/PrivateProfile/DefaultOutboundAction` | 0 |
| `DisableInboundNotifications` | `./Device/Vendor/MSFT/Firewall/MdmStore/PrivateProfile/DisableInboundNotifications` | TRUE |
| `EnableFirewall` | `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/EnableFirewall` | TRUE |
| `DefaultInboundAction` | `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/DefaultInboundAction` | 1 |
| `DefaultOutboundAction` | `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/DefaultOutboundAction` | 0 |
| `DisableInboundNotifications` | `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/DisableInboundNotifications` | TRUE |
| `AllowLocalPolicyMerge` | `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/AllowLocalPolicyMerge` | FALSE |
| `AllowLocalIpsecPolicyMerge` | `./Device/Vendor/MSFT/Firewall/MdmStore/PublicProfile/AllowLocalIpsecPolicyMerge` | FALSE |
| `ExploitProtectionSettings` | `./Device/Vendor/MSFT/Policy/Config/ExploitGuard/ExploitProtectionSettings` | `<?xml version=""""1.0"""" encoding=""""UTF-8""""?><MitigationPolicy><AppConfig Executable=""""ONEDRIVE.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><ImageLoad BlockRemoteImageLoads=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""firefox.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR ForceRelocateImages=""""true"""" RequireInfo=""""false"""" BottomUp=""""true"""" HighEntropy=""""false"""" /></AppConfig><AppConfig Executable=""""fltldr.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ImageLoad BlockRemoteImageLoads=""""true"""" /><ChildProcess DisallowChildProcessCreation=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""GROOVE.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><ImageLoad BlockRemoteImageLoads=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /><ChildProcess DisallowChildProcessCreation=""""true"""" /></AppConfig><AppConfig Executable=""""Acrobat.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR ForceRelocateImages=""""true"""" RequireInfo=""""false"""" BottomUp=""""true"""" HighEntropy=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""AcroRd32.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR ForceRelocateImages=""""true"""" RequireInfo=""""false"""" BottomUp=""""true"""" HighEntropy=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""chrome.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /></AppConfig><AppConfig Executable=""""EXCEL.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""iexplore.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR ForceRelocateImages=""""true"""" RequireInfo=""""false"""" BottomUp=""""true"""" HighEntropy=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""INFOPATH.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""java.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""javaw.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""javaws.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""LYNC.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""MSACCESS.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""MSPUB.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""OIS.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""OUTLOOK.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""plugin-container.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""POWERPNT.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""PPTVIEW.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""VISIO.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""VPREVIEW.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""WINWORD.EXE""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><ASLR Enable=""""true"""" ForceRelocateImages=""""true"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""wmplayer.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""false"""" EnableExportAddressFilterPlus=""""false"""" EnableImportAddressFilter=""""false"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig><AppConfig Executable=""""wordpad.exe""""><DEP Enable=""""true"""" EmulateAtlThunks=""""false"""" /><Payload EnableExportAddressFilter=""""true"""" EnableExportAddressFilterPlus=""""true"""" EnableImportAddressFilter=""""true"""" EnableRopStackPivot=""""true"""" EnableRopCallerCheck=""""true"""" EnableRopSimExec=""""true"""" /></AppConfig>``</MitigationPolicy>` |
| `BlockPicturePassword` | `./Device/Vendor/MSFT/Policy/Config/CredentialProviders/BlockPicturePassword` | ``<Enabled/>`` |
| `DontDisplayNetworkSelectionUI`| `.Device/Vendor/MSFT/Policy/Config/WindowsLogon/DontDisplayNetworkSelectionUI`| ``<Disabled/>`` |
| `CloudExtendedTimeout` | `./Device/Vendor/MSFT/Policy/Config/Defender/CloudExtendedTimeout` | 10 |
