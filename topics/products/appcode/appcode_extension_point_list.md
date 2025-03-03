[//]: # (title: AppCode Extension Point List)

<!-- Copyright 2000-2022 JetBrains s.r.o. and other contributors. Use of this source code is governed by the Apache 2.0 license that can be found in the LICENSE file. -->

25 Extension Points (EP) and 4 Listeners for AppCode

See [Extension Point List](extension_point_list.md) for IntelliJ Platform EPs.

<include src="extension_point_list.md" include-id="ep_list_legend"></include>

## AppCode

### AppCode - Listeners

| Topic | Listener |
|-------|----------|
| `CocoaPodsUtils#GEM_TOPIC` | `GemListener` |
| `CocoaPodsUtils#PODS_TOPIC` | `PodsListener` |
| `AMDeviceManager#DEVICE_LISTENER_TOPIC` | `AMDeviceListener` |
| `XcodeProjectTestListener#TOPIC` | `XcodeProjectTestListener` |

### AppCodeSwiftPlugin.xml

| Extension Point | Implementation |
|-----------------|----------------|
| [appcode.swift.sourceModuleProducer](https://jb.gg/ipe?extensions=appcode.swift.sourceModuleProducer) ![Non-Dynamic][non-dynamic] | `AppcodeSourceModuleProducer` |

### CocoaCommonPlugin.xml

| Extension Point | Implementation |
|-----------------|----------------|
| [cidr.cocoa.xcodeProjectFileProvider](https://jb.gg/ipe?extensions=cidr.cocoa.xcodeProjectFileProvider) | `XcodeProjectFileProvider` |

### CocoaPlugin.xml

| Extension Point | Implementation |
|-----------------|----------------|
| [cidr.cocoa.documentation.search.candidates.helper](https://jb.gg/ipe?extensions=cidr.cocoa.documentation.search.candidates.helper) | `XcodeDocumentationCandidateBasedSearchHelper` |
| [cidr.cocoa.documentation.search.usr.provider](https://jb.gg/ipe?extensions=cidr.cocoa.documentation.search.usr.provider) | `XcodeDocumentationUsrProvider` |

### com.intellij.appcode

| Extension Point | Implementation |
|-----------------|----------------|
| [appcode.attachDebuggerProvider](https://jb.gg/ipe?extensions=appcode.attachDebuggerProvider) ![Non-Dynamic][non-dynamic] | `AppCodeAttachDebuggerExtension` |
| [appcode.runConfigurationExtension](https://jb.gg/ipe?extensions=appcode.runConfigurationExtension) ![Non-Dynamic][non-dynamic] | `AppCodeRunConfigurationExtension` |
| [appcode.xcodeExternalBuildProvider](https://jb.gg/ipe?extensions=appcode.xcodeExternalBuildProvider) ![Non-Dynamic][non-dynamic] | `XcodeExternalBuildProvider` |
| [appcode.xcodeTemplatePathsProvider](https://jb.gg/ipe?extensions=appcode.xcodeTemplatePathsProvider) ![Non-Dynamic][non-dynamic] | `XcodeTemplatePathsProvider` |
| [appcode.xcodeTemplatesProvider](https://jb.gg/ipe?extensions=appcode.xcodeTemplatesProvider) | `XcodeTemplatesProvider` |

### SwiftLanguageInternalPlugin.xml

| Extension Point | Implementation |
|-----------------|----------------|
| [swift.lang.libraryModuleImportRestriction](https://jb.gg/ipe?extensions=swift.lang.libraryModuleImportRestriction) | `SwiftLibraryModuleImportRestriction` |
| [swift.sdkInfo.extractor](https://jb.gg/ipe?extensions=swift.sdkInfo.extractor) | `OCResolveConfigurationSdkInfoExtractor` |
| [swift.sourcekit.blacklistedModulesProvider](https://jb.gg/ipe?extensions=swift.sourcekit.blacklistedModulesProvider) ![Non-Dynamic][non-dynamic] | `SourceKitBlacklistedModulesProvider` |
| [swift.sourcekit.dependenciesLoader](https://jb.gg/ipe?extensions=swift.sourcekit.dependenciesLoader) | `SourceKitPlatformBinaryDependenciesLoader` |

### SwiftPlugin.xml

| Extension Point | Implementation |
|-----------------|----------------|
| [cidr.lang.swiftCustomIncludePathProvider](https://jb.gg/ipe?extensions=cidr.lang.swiftCustomIncludePathProvider) ![Non-Dynamic][non-dynamic] | `SwiftCustomIncludePathProvider` |
| [cidr.lang.swiftSourceModuleProvider](https://jb.gg/ipe?extensions=cidr.lang.swiftSourceModuleProvider) ![Non-Dynamic][non-dynamic] | `SwiftSourceModuleProvider` |
| [cidr.lang.swiftTypeInheritorsSearch](https://jb.gg/ipe?extensions=cidr.lang.swiftTypeInheritorsSearch) ![Non-Dynamic][non-dynamic] | [`QueryExecutor`](upsource:///platform/core-api/src/com/intellij/util/QueryExecutor.java) |
| [swift.kotlinNative](https://jb.gg/ipe?extensions=swift.kotlinNative) ![Non-Dynamic][non-dynamic] | `KotlinNativeExtensionPoint` |
| [swift.lang.sourceKit.compileArgumentsCollector](https://jb.gg/ipe?extensions=swift.lang.sourceKit.compileArgumentsCollector) | `SwiftSourceKitCompileArgumentsCollector` |
| [swift.lang.sourceKit.dataGenerator](https://jb.gg/ipe?extensions=swift.lang.sourceKit.dataGenerator) ![Project-Level][project-level] | `SourceKitDataGenerator` |
| [swift.lang.sourceKit.declarationLocationValidator](https://jb.gg/ipe?extensions=swift.lang.sourceKit.declarationLocationValidator) | `SourceKitDeclarationLocationValidator` |
| [swift.lang.swiftSupportProvider](https://jb.gg/ipe?extensions=swift.lang.swiftSupportProvider) | `SwiftSupportProvider` |

### SwiftPMCommon.xml

| Extension Point | Implementation |
|-----------------|----------------|
| [swift.packageManager.appleSdk.filter](https://jb.gg/ipe?extensions=swift.packageManager.appleSdk.filter) | `SwiftPackageLoadedAppleSdkFilter` |
| [swift.packageManager.environmentConfigurator](https://jb.gg/ipe?extensions=swift.packageManager.environmentConfigurator) | `SwiftPackageManagerEnvironmentConfigurator` |
| [swift.packageManager.modulemapsCollector](https://jb.gg/ipe?extensions=swift.packageManager.modulemapsCollector) | `SwiftPackageModuleMapsCollector` |
| [swift.packageManager.systemModuleResolver](https://jb.gg/ipe?extensions=swift.packageManager.systemModuleResolver) | `SwiftPackageManagerSystemModuleResolver` |

[experimental]: https://img.shields.io/badge/-Experimental_API-red?style=flat-square
[internal]: https://img.shields.io/badge/-Internal_API-darkred?style=flat-square
[project-level]: https://img.shields.io/badge/-Project--Level-blue?style=flat-square
[non-dynamic]: https://img.shields.io/badge/-Non--Dynamic-orange?style=flat-square
[deprecated]: https://img.shields.io/badge/-Deprecated-lightgrey?style=flat-square
