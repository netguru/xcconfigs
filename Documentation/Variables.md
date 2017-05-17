# xcconfigs - Variables

[netguru/xcconfigs](https://github.com/netguru/xcconfigs) takes advantage of build setting variables to allow more flexible project configuration in comparison to using raw build settings.

This document describes all public variables that you can override in your own `.xcconfig` files.

Please note that variables with similar purpose are grouped by a common prefix.

---

### Environment

#### `_ENVIRONMENT`

Name of the environment. As this variable is mapped to compilation conditions, you may use it to write conditionally compiled code.

Assuming you have a follofing `*.xcconfig` file:

```none
// Staging.xcconfig

_ENVIRONMENT = STAGING
```

You can use this in both Swift and Objective-C code:

```swift
// Swift

#if ENV_STAGING
    ...
#endif
```

```objc
// Objective-C

#if defined(ENV_STAGING)
   ...
#endif
```

Please note that when `_ENVIRONMENT` is mapped to a compilation condition, an `ENV_` prefix is applies so that the setting does not interfere with preexisting compilation conditions.

---

### Versioning

#### `_BUILD_VERSION`

Semantic version of the product or the whole project.

#### `_BUILD_NUMBER`

Build number of the product or the whole project.

---

### Bundle

#### `_BUNDLE_NAME`

Name of the product bundle.

#### `_BUNDLE_IDENTIFIER`

Identifier of the product bundle. This variable is used as `CFBundleIdentifier` in Info.plist.

#### `_BUNDLE_INFOPLIST_PATH`

Path to Info.plist file of the product bundle.

#### `_BUNDLE_TESTABLE`

Whether the product bundle is testable.

---

### Deployment

#### `_DEPLOYMENT_TARGET_IOS`

Minimum deployment target of the product on iOS.

#### `_DEPLOYMENT_TARGET_MACOS`

Minimum deployment target of the product on macOS.

#### `_DEPLOYMENT_TARGET_TVOS`

Minimum deployment target of the product on tvOS.

#### `_DEPLOYMENT_TARGET_WATCHOS`

Minimum deployment target of the product on watchOS.

---

### Code signing

#### `_CODESIGN_DEVELOPMENT_TEAM`

Development team used along with `_CODESIGN_IDENTITY` and `_CODESIGN_PROFILE_SPECIFIER` to manually code sign the product.

#### `_CODESIGN_IDENTITY`

Identity used along with `_CODESIGN_DEVELOPMENT_TEAM` and `_CODESIGN_PROFILE_SPECIFIER` to manually code sign the product.

#### `_CODESIGN_PROFILE_SPECIFIER`

Provisioning profile specifier used along with `_CODESIGN_DEVELOPMENT_TEAM` and `_CODESIGN_IDENTITY` to manually code sign the product.

#### `_CODESIGN_ENTITLEMENTS_PATH`

Path to `*.entitlements` file containing sandboxed capabilities of the product.

---

### Assets

#### `_ASSET_ICON`

Name of an asset that will be used as product application's icon.

#### `_ASSET_LAUNCHIMAGE`

Name of an asset that will be used as product application's launch image.

---

### Compiler

#### `_COMPILER_HARD_MODE`

Whether to enable hard mode in Objective-C and Swift compilers. :trollface:

#### `_COMPILER_SWIFT_VERSION`

Swift language version used by the product.

#### `_COMPILER_SWIFT_FLAGS`

Additional flags passed to Swift compiler.

#### `_COMPILER_FRAMEWORK_SEARCH_PATHS`

Framework search paths of Objective-C and Swift compilers.

#### `_COMPILER_HEADER_SEARCH_PATHS`

Header search paths of Objective-C compiler.

#### `_COMPILER_LINKED_LIBRARIES`

Additionally linked libraries by Objective-C compiler.
