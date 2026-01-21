# iOS TDD

XCTest-driven workflow for new features and refactors.

## Steps
1. Define desired behavior and acceptance criteria.
2. Write failing XCTest(s) that encode that behavior.
3. Implement minimal code to pass tests.
4. Refactor for clarity and maintainability.
5. Add edge cases and regression tests.

## Rules
- Tests must be deterministic and isolated.
- Use dependency injection for mockability.
- Avoid UI tests unless the user explicitly asks.
