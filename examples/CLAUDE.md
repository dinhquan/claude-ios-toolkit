# Project Instructions (iOS Example)

This is a SwiftUI iOS app.

## Priorities
- Maintain MVVM separation
- Keep view models `@MainActor`
- Avoid force unwraps
- Add XCTest for new logic

## Build
- Use Xcode 15+
- `xcodebuild -scheme App -destination 'platform=iOS Simulator,name=iPhone 15'`

## Notes
- Use accessibility identifiers for UI tests
- Store tokens in Keychain
