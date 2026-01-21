---
name: swiftui-patterns
description: SwiftUI view structure, state, and layout patterns.
---

# SwiftUI Patterns

## State Management
- `@State` for local view state
- `@StateObject` for owned view models
- `@ObservedObject` for injected models
- `@EnvironmentObject` for shared dependencies

## View Composition
- Extract subviews for readability
- Use ViewBuilder for conditional content
- Avoid large `body` implementations

## Accessibility
- Add labels for non-text UI
- Use `accessibilityIdentifier` for UI tests
