# Project Instructions (iOS Example)

This is a SwiftUI iOS app targeting iOS 17+.

## Priorities
- Maintain MVVM separation.
- Keep view models `@MainActor`.
- Avoid force unwraps and implicit dependencies.
- Add XCTest for new logic.

## Architecture
- SwiftUI-first UI.
- Coordinator/Flow router for navigation.
- Services handle networking and persistence.
- Secrets stored in Keychain.

## Build
- Use Xcode 15+.
- Example build command:
  `xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 15'`

## Testing
- Prefer XCTest for new logic.
- Use XCUITest only for core flows.
- Tests must be deterministic.

## Notes
- Use accessibility identifiers for UI tests.
- Avoid logging PII.
