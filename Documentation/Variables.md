# xcconfigs - Variables

[netguru/xcconfigs](https://github.com/netguru/xcconfigs) takes advantage of build setting variables to allow more flexible project configuration in comparison to using raw build settings.

This document describes all public variables that you can override in your own `.xcconfig` files.

Please note that variables with similar purpose are grouped by a common prefix.

---

### Environment

#### `_ENVIRONMENT`

This variable contains the name of environment that you use in schemes.

As this variable is mapped to compilation conditions, you may use it to write conditionally compiled code.

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

---

### Versioning

#### `_BUILD_VERSION`

TBD

#### `_BUILD_NUMBER`

TBD

---

### Bundle

#### `_BUNDLE_NAME`

TBD

#### `_BUNDLE_IDENTIFIER`

TBD

#### `_BUNDLE_INFOPLIST_PATH`

TBD

#### `_BUNDLE_TESTABLE`

TBD

---

### Deployment

#### `_DEPLOYMENT_TARGET_IOS`

TBD

#### `_DEPLOYMENT_TARGET_MACOS`

TBD

#### `_DEPLOYMENT_TARGET_TVOS`

TBD

#### `_DEPLOYMENT_TARGET_WATCHOS`

TBD

---

### Code signing

#### `_CODESIGN_DEVELOPMENT_TEAM`

TBD

#### `_CODESIGN_IDENTITY`

TBD

#### `_CODESIGN_PROFILE_SPECIFIER`

TBD

#### `_CODESIGN_ENTITLEMENTS_PATH`

TBD

---

### Assets

#### `_ASSET_ICON`

TBD

#### `_ASSET_LAUNCHIMAGE`

TBD

---

### Compiler

#### `_COMPILER_HARD_MODE`

TBD

#### `_COMPILER_SWIFT_VERSION`

TBD

#### `_COMPILER_SWIFT_FLAGS`

TBD

#### `_COMPILER_FRAMEWORK_SEARCH_PATHS`

TBD

#### `_COMPILER_HEADER_SEARCH_PATHS`

TBD

#### `_COMPILER_LINKED_LIBRARIES`

TBD
