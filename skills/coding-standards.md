---
name: coding-standards
description: Swift and SwiftUI coding standards for iOS apps.
---

# Swift Coding Standards

These standards prioritize maintainability, testability, and predictable behavior in modern iOS apps.

## Core Principles
- Prefer clarity over cleverness.
- Make data flow explicit and testable.
- Keep UI reactive and side-effect free.
- Optimize for long-term maintenance over short-term speed.

## File and Type Organization
- One primary type per file unless tightly coupled (e.g., view + nested view model).
- Keep files focused and under 800 lines. Extract helpers and subviews.
- Use `MARK:` sections only when a file is large and it improves scanning.
- Group extensions by responsibility (e.g., `Equatable`, `Codable`, `View`).

## Naming and API Design
- Use descriptive names over abbreviations.
- Prefer verb-based method names (`loadProfile`, `refreshCache`).
- Favor noun-based types (`ProfileStore`, `SessionManager`).
- Avoid `Manager` or `Helper` without clear ownership or responsibility.

## Error Handling
- Prefer `throws` for recoverable errors and typed `Error` enums.
- Avoid silent failures; surface errors at UI boundaries with user-facing messages.
- Use `Result` when needed for composition or callback-based APIs.

## Concurrency and Actors
- Use structured concurrency (`async/await`) for asynchronous work.
- Mark UI-facing types as `@MainActor`.
- Avoid shared mutable state. Use actors or value types.
- Keep background work off the main thread and return to main for UI updates.

## SwiftUI Guidelines
- Keep `body` implementations small and declarative.
- Use subviews to avoid deeply nested view builders.
- Prefer `@State` for local state, `@StateObject` for owned models.
- Avoid heavy work inside `body` or `onAppear`.

## Dependency Injection
- Prefer initializer injection for clarity and testability.
- Avoid global singletons; use environment or explicit dependencies.
- Keep side effects at the edges (services, repositories).

## Testing Expectations
- New logic requires XCTest coverage.
- Tests should be deterministic and independent.
- Use protocols and test doubles for network and persistence.
- Avoid UI tests unless validating a critical user flow.

## Logging and Observability
- Avoid `print()` in production paths.
- Use a structured logger with privacy settings.
- Do not log secrets or PII.

## Example

```swift
// Good: explicit dependencies and error handling
@MainActor
final class ProfileViewModel: ObservableObject {
    private let profileService: ProfileService

    @Published private(set) var profile: Profile?
    @Published private(set) var state: ViewState = .idle

    init(profileService: ProfileService) {
        self.profileService = profileService
    }

    func loadProfile(userId: String) async {
        state = .loading
        do {
            profile = try await profileService.fetchProfile(userId: userId)
            state = .loaded
        } catch {
            state = .error(error)
        }
    }
}

// Bad: force unwraps and hidden dependencies
let service = Service.shared
let profile = try! await service.fetchProfile(userId: userId!)
```
