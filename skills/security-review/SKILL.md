---
name: security-review
description: iOS security checklist for Swift/SwiftUI apps.
---

# iOS Security Review

## Storage
- Keychain for credentials
- Encrypted files for sensitive data
- Avoid PII in logs

## Networking
- ATS enabled
- HTTPS only
- Validate hosts where needed

## Permissions
- Info.plist usage strings present
- Least-privilege permissions

## Build
- No secrets in source
- Debug logging removed for release
