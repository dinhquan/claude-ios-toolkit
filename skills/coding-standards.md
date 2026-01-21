---
name: coding-standards
description: Swift and SwiftUI coding standards for iOS apps.
---

# Swift Coding Standards

## Readability
- Clear naming over cleverness
- Prefer small, focused types
- Use MARKs sparingly for large files

## Safety
- Avoid force unwraps
- Prefer `guard` for early exits
- Use `Result` or `throws` for errors

## Concurrency
- Use `@MainActor` for UI updates
- Use structured concurrency (`async/await`)
- Avoid shared mutable state

## Examples

```swift
// Good: clear naming and error handling
func loadProfile(userId: String) async throws -> Profile {
    let request = ProfileRequest(userId: userId)
    return try await apiClient.send(request)
}

// Bad: force unwrap
let id = userId!
```
