# iOS Code Review

Comprehensive security and quality review of uncommitted changes:

1. Get changed files: git diff --name-only HEAD
2. For each changed file, check for:

**Security Issues (CRITICAL):**
- Hardcoded secrets
- ATS disabled without justification
- Tokens stored outside Keychain
- PII in logs

**Code Quality (HIGH):**
- Force unwraps without guards
- Missing error handling
- Large views or view models (>400 lines)
- Threading issues (UI work off main thread)

**Best Practices (MEDIUM):**
- Missing tests for new code
- Accessibility labels missing
- Magic numbers without explanation

3. Generate report with severity and suggested fixes
4. Block commit if CRITICAL or HIGH issues found
