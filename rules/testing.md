# iOS Testing

## XCTest (CRITICAL)
- New logic requires XCTest coverage.
- Tests must be deterministic and isolated.
- Use dependency injection for mockability.

## XCUITest
- Use only for critical user flows.
- Add accessibility identifiers for UI elements.
- Avoid sleeps; use expectations and predicates.

## Coverage Focus
- Business logic and state transitions.
- Error handling and retry paths.
- Data persistence and migrations.

## Test Quality
- AAA structure (Arrange, Act, Assert).
- One behavior per test.
- Keep test names descriptive and consistent.
