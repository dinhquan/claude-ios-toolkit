# iOS Testing

## XCTest (CRITICAL)
- New logic requires XCTest coverage
- Tests must be deterministic
- Use dependency injection for mockability

## XCUITest
- Use only for critical user flows
- Add accessibility identifiers for all UI elements
- Avoid sleeps; use expectations

## Coverage
- Prioritize business logic and state transitions
- Avoid brittle snapshot tests unless necessary
