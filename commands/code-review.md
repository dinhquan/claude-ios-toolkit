# iOS Code Review

Comprehensive security and quality review of uncommitted changes.

## Workflow
1. Get changed files: `git diff --name-only HEAD`.
2. For each changed file, review for:

### Security (CRITICAL)
- Hardcoded secrets or API keys.
- ATS disabled without justification.
- Tokens stored outside Keychain.
- PII in logs or analytics.

### Code Quality (HIGH)
- Force unwraps without guards.
- Missing error handling.
- Large views or view models (>400 lines).
- UI work off the main thread.

### Best Practices (MEDIUM)
- Missing tests for new logic.
- Accessibility labels missing.
- Magic numbers without explanation.
- Hidden dependencies or singletons.

3. Generate a report with severity and suggested fixes.
4. Block commit if CRITICAL or HIGH issues are found.

## Review Output Template
```
[SEVERITY] Issue title
File: path/to/file.swift:line
Issue: What is wrong and why it matters
Fix: Recommended remediation
```
