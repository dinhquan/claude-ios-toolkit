# iOS Patterns

## MVVM
- Views are declarative renderers.
- ViewModels own presentation state and orchestrate actions.
- Services and repositories handle side effects.

## Navigation
- Use Coordinator/Router for complex flows.
- Keep navigation out of ViewModels when possible.
- Route definitions should be typed (enum with data).

## Dependency Injection
- Prefer initializer injection.
- Avoid global singletons; use explicit dependencies.
- Use factories for module composition.

## SwiftUI State
- `@State` for local view state.
- `@StateObject` for owned view models.
- `@ObservedObject` for injected models.
- `@EnvironmentObject` for app-level shared dependencies.

## Error Handling
- Model errors as part of view state.
- Surface errors at UI boundaries with user-friendly messaging.
