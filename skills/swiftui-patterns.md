---
name: swiftui-patterns
description: SwiftUI view structure, state, and layout patterns.
---

# SwiftUI Patterns

## State Management
- `@State` for local transient state.
- `@StateObject` for owned reference models.
- `@ObservedObject` for injected reference models.
- `@EnvironmentObject` for shared app-wide dependencies.
- Prefer immutable models; mutate via explicit actions.

## View Composition
- Extract subviews for readability and reuse.
- Keep `body` small and declarative.
- Use `ViewBuilder` for conditional content.
- Prefer view modifiers over nesting for styling.

## Data Flow
- Keep state changes on the main actor.
- Avoid heavy work inside `body` or `onAppear`.
- Use `task` for async operations with cancellation support.
- Model loading and error states explicitly.

## Navigation
- Use `NavigationStack` with typed routes.
- Keep route definitions in a central flow object.
- Avoid pushing navigation logic into views.

## Layout and Responsiveness
- Use flexible layouts (`Spacer`, `GeometryReader` judiciously).
- Avoid fixed sizes unless required for design.
- Support Dynamic Type and accessibility sizes.
- Test on compact and regular size classes.

## Accessibility
- Add `accessibilityLabel` for non-text controls.
- Use `accessibilityIdentifier` for UI tests.
- Support VoiceOver order and grouping.

## Performance
- Avoid expensive work in `body`.
- Minimize view recomputation by extracting subviews.
- Use `EquatableView` sparingly to optimize rendering.
- Cache images and avoid repeated decoding.

## Previews
- Provide realistic preview data.
- Include multiple size classes and color schemes.
- Test loading/error states in previews.

## Example

```swift
struct ProfileView: View {
    @StateObject private var viewModel: ProfileViewModel

    init(viewModel: ProfileViewModel) {
        _viewModel = StateObject(wrappedValue: viewModel)
    }

    var body: some View {
        content
            .task { await viewModel.load() }
            .navigationTitle("Profile")
    }

    @ViewBuilder
    private var content: some View {
        switch viewModel.state {
        case .idle, .loading:
            ProgressView()
        case .loaded(let profile):
            ProfileDetailsView(profile: profile)
        case .error:
            ErrorStateView(retryAction: viewModel.retry)
        }
    }
}
```
