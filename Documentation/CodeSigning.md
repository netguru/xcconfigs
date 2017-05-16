# xcconfigs – Code Signing

This document describes ways of flexible code signing using `xcconfigs`.

---

Assuming project setup has been done according to [Usage](Usage.md) document, you can use custom variables to define code signing build settings _per configuration_.

For example, you can map `_CODESIGN_*` build settings in the `Application.xcconfig` to custom variables:

```objc
// Application.xcconfig

_CODESIGN_DEVELOPMENT_TEAM = $(_CODESIGN_DEVELOPMENT_TEAM_APP)
_CODESIGN_IDENTITY = $(_CODESIGN_IDENTITY_APP)
_CODESIGN_PROFILE_SPECIFIER = $(_CODESIGN_PROFILE_SPECIFIER_APP)
```

And set them in configuration build settings (`Debug.xcconfig`, `Release.xcconfig`):

```objc
// Debug.xcconfig

_CODESIGN_DEVELOPMENT_TEAM_APP = A1B2C3D4E5F6
_CODESIGN_IDENTITY_APP = John Doe (A1B2C3D4E5F6)
_CODESIGN_PROFILE_SPECIFIER_APP = MyProject Debug
```

```objc
// Release.xcconfig

_CODESIGN_DEVELOPMENT_TEAM_APP = F6E5D4C3B2A1
_CODESIGN_IDENTITY_APP = Jane Roe (F6E5D4C3B2A1)
_CODESIGN_PROFILE_SPECIFIER_APP = MyProject Release
```

That way, application target will be signed using different identities and provisioning profile for Debug and Release mode and unit tests bundle target will remain unaffected, not signed.
