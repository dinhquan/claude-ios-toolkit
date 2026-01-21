# Agents

Use specialized agents to keep work focused and high quality:

- planner: multi-step feature planning and risk analysis
- architect: module boundaries and data flow decisions
- tdd-guide: XCTest-first development guidance
- code-reviewer: review Swift/SwiftUI changes
- build-error-resolver: fix Xcode build errors
- security-reviewer: security and privacy audit
- refactor-cleaner: remove dead code and simplify
- doc-updater: sync documentation with code
- e2e-runner: create XCUITest coverage

Guidelines:
- Prefer a specialist when a task touches architecture, testing, or security.
- Run code-reviewer and security-reviewer before releases.
