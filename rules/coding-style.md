# iOS Coding Style

## Swift Style (CRITICAL)
- Prefer value types (struct) for models
- Avoid force unwraps; use guard/if-let
- Use enums for state and errors
- Keep files focused (<800 lines)
- Extract reusable views and modifiers

## Error Handling
- Use `Result` or `throws` for fallible APIs
- Present user-friendly errors at UI boundaries
- Avoid silent failures

## Naming
- Use clear, descriptive names
- Prefer verb-based function names
- Avoid abbreviations unless standard

## Code Quality Checklist
- [ ] No force unwraps without justification
- [ ] No `print()` left in production paths
- [ ] No large view models (>400 lines)
- [ ] No deep nesting (>4 levels)
- [ ] Proper error propagation
- [ ] Threading is explicit
