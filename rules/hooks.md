# Hooks

Hooks are optional automation steps triggered by tool usage.

## Typical Uses
- Warn on `print()` in Swift files.
- Block secrets in source control.
- Remind to update tests after logic changes.
- Enforce formatting or linting before commits.

## Guidance
- Keep hooks fast and deterministic.
- Avoid blocking workflows on non-critical checks.
- Prefer warnings for style and blocking for security issues.
