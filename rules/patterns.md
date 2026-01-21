# iOS Patterns

## MVVM
- Views are stateless renderers
- ViewModels own business logic and state
- Services handle API and persistence

## Navigation
- Use Coordinator/Router for complex flows
- Keep navigation out of view models when possible

## Dependency Injection
- Prefer initializer injection
- Avoid global singletons unless necessary

## SwiftUI State
- Use `@State` for local state
- Use `@StateObject` for owned models
- Use `@ObservedObject` for injected models
