---
name: ios-patterns
description: Architecture and engineering patterns for iOS apps.
---

# iOS Patterns

## MVVM
- View renders state
- ViewModel manages state and effects
- Services handle side effects

## Coordinator
- Centralize navigation logic
- Keep view models focused on state and actions

## Persistence
- Use Core Data or SQLite for structured data
- Use file system for large binary assets
- Store secrets only in Keychain

## Networking
- Central API client with typed requests
- Codable models with explicit mapping
- Use retry/backoff for transient errors
