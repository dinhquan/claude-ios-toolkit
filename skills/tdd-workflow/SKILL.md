---
name: tdd-workflow
description: XCTest-first workflow for iOS development.
---

# TDD Workflow (iOS)

Use this workflow to implement features with high confidence and minimal regression risk.

## Red-Green-Refactor
1. Define behavior and acceptance criteria.
2. Write failing XCTest(s) that assert the desired behavior.
3. Implement the minimal code to pass.
4. Refactor for clarity, structure, and performance.
5. Add edge cases and regression tests.

## Test Design Guidelines
- Keep tests deterministic and fast.
- Avoid hidden dependencies; inject services and clocks.
- Use test doubles for network, persistence, and time.
- Prefer unit and integration tests over UI tests.

## XCTest Structure
- Use AAA: Arrange, Act, Assert.
- Name tests with `test_<subject>_<expectedOutcome>`.
- Keep each test focused on one behavior.

## Coverage Focus
- Domain logic and state transitions.
- Error handling and retry behavior.
- Threading and main-actor boundaries.
- Persistence and migration behavior.

## When to Use XCUITest
- Critical user flows that must not regress.
- Validate integration of multiple modules.
- Only when unit/integration tests are insufficient.

## Exit Criteria
- All new logic is covered by deterministic tests.
- No flaky tests introduced.
- Refactor pass leaves code clearer than before.
