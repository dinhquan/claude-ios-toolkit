---
name: ios-patterns
description: Architecture and engineering patterns for iOS apps.
---

# iOS Architecture Patterns

This guide outlines recommended patterns for scalable, testable iOS apps.

## Module Boundaries
- Separate UI, domain, and data layers.
- Use SPM packages or targets for shared modules.
- Keep platform-specific code at the edges.

## MVVM (SwiftUI-First)
- View renders state only.
- ViewModel owns presentation logic and state.
- Services and repositories perform side effects.
- Keep ViewModels `@MainActor` when they drive UI.

## Coordinator / Flow Router
- Centralize navigation for complex flows.
- Keep navigation logic out of ViewModels when possible.
- Define routes as enums with associated data.
- Support deep links by mapping URLs to routes.

## Data Flow
- Use immutable state where practical.
- Model state changes explicitly (e.g., `.idle`, `.loading`, `.loaded`, `.error`).
- Use `@Published` or `Observable` for state updates.

## Dependency Injection
- Use initializer injection for services.
- Provide module-level factories for composition.
- Avoid global mutable state.

## Networking
- Central API client with typed requests.
- Encapsulate auth and retries in the client.
- Use `URLSession` with `async/await` and structured decoding.
- Add robust error mapping (network, decoding, server, auth).

## Persistence
- Use Core Data or SQLite for structured data.
- Use file system for large binary assets.
- Store secrets only in Keychain.
- Prefer migration strategies that are forward-compatible.

## Analytics and Observability
- Central analytics client with typed events.
- Avoid PII in analytics payloads.
- Gate tracking on consent and region rules.

## Feature Flags
- Use remote config or feature flags to protect rollouts.
- Keep flags colocated with feature boundaries.
- Remove flags after full rollout.

## App Lifecycle
- Avoid heavy work in `application(_:didFinishLaunching:)`.
- Defer non-critical work using background tasks.
- Handle scene lifecycle for state restoration.

## Security and Privacy
- ATS on by default.
- Secure local storage and avoid logging PII.
- Ensure Info.plist usage descriptions are accurate and specific.

## Example Module Layout

```
App
|-- Features
|   |-- Onboarding
|   |   |-- Views
|   |   |-- ViewModels
|   |   |-- Flow
|   |-- Profile
|-- Domain
|   |-- Models
|   |-- UseCases
|-- Data
|   |-- API
|   |-- Persistence
|-- Core
    |-- Analytics
    |-- Logging
    |-- Networking
```
