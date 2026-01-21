---
name: security-review
description: iOS security checklist for Swift/SwiftUI apps.
---

# iOS Security Review

Use this skill to audit changes for security, privacy, and policy compliance.

## Review Workflow
1. Inspect changed files and configuration (Info.plist, entitlements, build settings).
2. Review networking, storage, and auth flows.
3. Identify privacy/consent implications.
4. Report findings by severity with concrete fixes.

## Storage
- Keychain for credentials and refresh tokens.
- Encrypt sensitive files at rest.
- Avoid PII in `UserDefaults`.
- Use `NSFileProtection` for on-disk data.

## Networking
- ATS enabled; HTTPS only.
- Validate hostnames and pin certificates when required.
- Do not log request/response bodies with PII.
- Add timeouts and retry/backoff for transient failures.

## Authentication
- Avoid embedding secrets in the app bundle.
- Use secure token refresh flows.
- Clear tokens on logout and account deletion.

## Permissions and Privacy
- Accurate Info.plist usage strings.
- Request permissions at point of use.
- Gate tracking behind explicit consent.
- Avoid collecting more data than needed.

## Logging and Analytics
- Remove debug logging from release builds.
- Scrub PII from crash logs and analytics.
- Use privacy annotations for logging where possible.

## Build and Supply Chain
- Ensure debug symbols are handled appropriately.
- Validate third-party libraries and licenses.
- Avoid unnecessary entitlements.

## App Store Policy
- Follow App Store data collection disclosures.
- Ensure export compliance and encryption declarations are accurate.

## Output Format
```
[CRITICAL] Issue title
File: path/to/file.swift:42
Risk: Why this is a security or privacy issue
Fix: Specific remediation steps
```
