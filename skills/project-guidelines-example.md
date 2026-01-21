---
name: project-guidelines-example
description: Example project-specific rules for an iOS app.
---

# Example Project Guidelines

These are sample project rules for a modern SwiftUI iOS app. Customize for your app context.

## Platform and Tooling
- Target iOS 17+ and Xcode 15+.
- Use Swift Concurrency for async work.
- Use SPM for dependencies; avoid manual frameworks.
- Use SwiftFormat or SwiftLint if configured.

## Architecture
- MVVM with a dedicated Flow/Coordinator layer.
- UI layer is SwiftUI-first. Use UIKit only when required.
- Domain logic lives outside views and view models.
- Services and repositories are isolated in data/core modules.

## Dependency Injection
- Dependencies injected through initializers.
- Use module-level factories for composition.
- Avoid global singletons unless strictly required.

## State and Side Effects
- View models are `@MainActor`.
- State transitions are explicit and testable.
- Side effects live in services, not views.

## Networking and Persistence
- Typed API client with structured error mapping.
- Store secrets in Keychain.
- Use Core Data or SQLite for structured data.
- Use file storage for large binary assets.

## Security and Privacy
- ATS enabled with HTTPS-only traffic.
- No secrets or tokens in source control.
- PII and analytics gated by consent.
- Accurate Info.plist usage descriptions.

## Testing
- New logic requires XCTest coverage.
- Use test doubles for network and persistence.
- XCUITest only for critical flows.

## Release Process
- Use semantic versioning.
- Create release notes for each App Store build.
- Run security checks and regression tests before release.

## Documentation
- Update README or architecture notes for behavior changes.
- Keep docs task-oriented and concise.
