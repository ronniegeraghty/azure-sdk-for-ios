# Azure SDK for iOS

This repository is for active development of the Azure SDK for iOS. For consumers of the SDK we recommend visiting our versioned [developer docs](https://azure.github.io/azure-sdk-for-ios).

> Note: The Azure SDK for iOS replaces a previous offering, known as Azure.iOS. Source code and documentation for Azure.iOS is available in the [legacy](https://github.com/Azure/azure-sdk-for-ios/tree/legacy) branch.

## Getting started

For your convenience, each service has a separate set of libraries that you can choose to use instead of one, large Azure package. To get started with a specific library, see the **README.md** file located in the library's project folder. You can find service libraries in the `/sdk` directory.

### Prerequisites

The client libraries are written in modern Swift 5. Due to this, Xcode 10.2 or higher is required to use these libraries.

## Packages available

Currently, the client libraries are in **preview**. These libraries follow the [Azure SDK Design Guidelines for iOS](https://azure.github.io/azure-sdk/ios_introduction.html) and share a number of core features such as HTTP retries, logging, transport protocols, authentication protocols, etc., so that once you learn how to use these features in one client library, you will know how to use them in other client libraries. You can learn about these shared features in [AzureCore](sdk/core/AzureCore/README.md).

The following libraries are currently in **preview**:
- [AzureStorageBlob](sdk/storage/AzureStorageBlob)

> Note: The SDK is currently in **preview**. The API surface and feature sets are subject to change at any time before **GA**. We do not currently recommend them for production use.

## Installation

### CocoaPods

[CocoaPods](https://cocoapods.org) is a dependency manager for Cocoa projects. You can install it with the following command:

```bash
[sudo] gem install cocoapods
```

> CocoaPods 1.3+ is required.

To integrate an SDK library into your project using CocoaPods, specify it in your [Podfile](https://guides.cocoapods.org/using/the-podfile.html):

```ruby
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '13.0'
use_frameworks!

pod 'AzureStorageBlob', '~> 0.1'
```

Then, run the following command:

```bash
$ pod install
```

### Carthage

[Carthage](https://github.com/Carthage/Carthage) is a decentralized dependency manager that builds your dependencies and provides you with binary frameworks.

You can install Carthage with [Homebrew](https://brew.sh/) using the following command:

```bash
$ brew update
$ brew install carthage
```

To integrate an SDK library into your project using Carthage, specify the release feed for the library in your [Cartfile](https://github.com/Carthage/Carthage/blob/master/Documentation/Artifacts.md#cartfile):

```ruby
binary "https://github.com/Azure/azure-sdk-for-ios/raw/master/releases/AzureStorageBlob.json" ~> 0.1
```

> Note: Debug symbols are also available. To obtain builds with debug symbols, append `-symbols` to the library name in the feed URL. e.g. `AzureStorageBlob-symbols.json`

Next, run `carthage update` and drag the resulting frameworks from the `Carthage/Build/iOS` folder into the *Linked Frameworks and Libraries* section of your Xcode project.

Finally, add the frameworks' paths to the *Input Files* list for the *Run Script* build phase that runs the `carthage copy-frameworks` command:

```
$(SRCROOT)/Carthage/Build/iOS/AzureCore.framework
$(SRCROOT)/Carthage/Build/iOS/AzureStorageBlob.framework
```

## Need help?

* File an issue via [GitHub Issues](https://github.com/Azure/azure-sdk-for-ios/issues/new/choose).
* Check [previous questions](https://stackoverflow.com/questions/tagged/azure+ios) or ask new ones on StackOverflow using `azure` and `ios` tags.

### Reporting security issues and security bugs

Security issues and bugs should be reported privately, via email, to the Microsoft Security Response Center (MSRC) <secure@microsoft.com>. You should receive a response within 24 hours. If for some reason you do not, please follow up via email to ensure we received your original message. Further information, including the MSRC PGP key, can be found in the [Security TechCenter](https://www.microsoft.com/msrc/faqs-report-an-issue).

## Contributing
For details on contributing to this repository, see the [contributing guide](CONTRIBUTING.md).

This project welcomes contributions and suggestions. Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us the rights to use your contribution. For details, visit
https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions provided by the bot. You will only need to do this once across all repositories using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

![Impressions](https://azure-sdk-impressions.azurewebsites.net/api/impressions/azure-sdk-for-ios%2FREADME.png)
