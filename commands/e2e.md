# iOS E2E (XCUITest)

Create or update XCUITest coverage for critical user flows.

## Steps
1. Identify the top user flows (onboarding, purchase, core feature).
2. Add accessibility identifiers for stable UI targeting.
3. Implement XCUITest cases with expectations, not sleeps.
4. Mock network responses when possible.
5. Document setup requirements and test data.

## Rules
- Keep tests deterministic and resilient.
- Prefer stable identifiers over labels.
- Avoid flakiness by waiting on UI conditions.
