# Claude iOS Toolkit

A comprehensive collection of Claude Code configuration files designed for modern iOS development. This repo provides reusable agents, skills, commands, and rules that enforce architecture discipline, testability, security, and performance standards for Swift and SwiftUI apps.

If you want a consistent, production-ready workflow for iOS projects, this pack gives you opinionated defaults and ready-to-use automation patterns.

---

## What This Repo Is For

- Building and evolving Swift/SwiftUI apps with a clear architectural baseline.
- Reducing regressions with deterministic tests and review checklists.
- Enforcing iOS security and privacy best practices.
- Streamlining planning, refactoring, and documentation updates.
- Providing ready-to-use MCP integrations for common iOS tooling.

---

## Repository Layout

```
.
|-- agents/           # Specialized subagents for iOS workflows
|   |-- planner.md           # Feature implementation planning
|   |-- architect.md         # App architecture decisions
|   |-- tdd-guide.md         # XCTest-driven development
|   |-- code-reviewer.md     # Swift/SwiftUI quality review
|   |-- security-reviewer.md # iOS security checklist
|   |-- build-error-resolver.md
|   |-- e2e-runner.md        # XCUITest E2E testing
|   |-- refactor-cleaner.md  # Dead code cleanup
|   |-- doc-updater.md       # Documentation sync
|
|-- skills/           # Workflow definitions and domain knowledge
|   |-- coding-standards.md         # Swift best practices
|   |-- ios-patterns.md             # MVVM, Coordinator, persistence
|   |-- swiftui-patterns.md         # View architecture and state
|   |-- project-guidelines-example.md
|   |-- tdd-workflow/               # XCTest methodology
|   |-- security-review/            # iOS security checklist
|
|-- commands/         # Slash commands for quick execution
|   |-- tdd.md              # /tdd - XCTest workflow
|   |-- plan.md             # /plan - Implementation planning
|   |-- e2e.md              # /e2e - XCUITest generation
|   |-- code-review.md      # /code-review - Swift review
|   |-- build-fix.md        # /build-fix - Fix Xcode build errors
|   |-- refactor-clean.md   # /refactor-clean - Dead code removal
|   |-- test-coverage.md    # /test-coverage - Coverage analysis
|   |-- update-codemaps.md  # /update-codemaps - Refresh docs
|   |-- update-docs.md      # /update-docs - Sync documentation
|   |-- learn.md            # /learn - Capture key learnings
|
|-- rules/            # Always-follow guidelines
|   |-- security.md         # Keychain, data storage, secrets
|   |-- coding-style.md     # Swift style + file organization
|   |-- testing.md          # XCTest/XCUITest requirements
|   |-- git-workflow.md     # Commit format, PR process
|   |-- agents.md           # When to delegate to subagents
|   |-- performance.md      # Main-thread, Instruments, memory
|   |-- patterns.md         # MVVM/Coordinator conventions
|   |-- hooks.md            # Hook documentation
|
|-- hooks/            # Trigger-based automations
|   |-- hooks.json          # PreToolUse, PostToolUse, Stop hooks
|
|-- mcp-configs/      # MCP server configurations
|   |-- mcp-servers.json    # MCP servers for tooling
|
|-- plugins/          # Plugin ecosystem documentation
|   |-- README.md           # Useful iOS tooling and plugins
|
|-- examples/         # Example configurations
    |-- CLAUDE.md           # Example project-level config
    |-- user-CLAUDE.md      # Example user-level config
    |-- statusline.json     # Custom status line config
```

---

## Quick Start

### 1) Copy the pieces you need

```bash
# Agents
cp agents/*.md ~/.claude/agents/

# Rules
cp rules/*.md ~/.claude/rules/

# Commands
cp commands/*.md ~/.claude/commands/

# Skills
cp -r skills/* ~/.claude/skills/
```

### 2) Add hooks

Copy the hooks from `hooks/hooks.json` into your `~/.claude/settings.json`.

### 3) Configure MCP servers

Copy the servers you need from `mcp-configs/mcp-servers.json` into your `~/.claude.json` under `mcpServers`. Fill in required env vars or tokens.

---

## What You Can Do With This Repo

### Architecture and Planning
- Generate a structured plan before large changes.
- Define module boundaries and data flow with the architect agent.
- Standardize navigation and state management patterns.

### Build and Debug
- Diagnose Xcode build issues via a dedicated agent.
- Run targeted tests after fixes.

### Testing and Coverage
- Use the TDD workflow to create deterministic XCTest coverage.
- Add XCUITest coverage for critical flows only.
- Identify coverage gaps and expand tests deliberately.

### Security and Privacy
- Enforce secure storage, ATS, and logging standards.
- Audit new changes for data leakage and policy issues.

### Refactoring and Cleanup
- Remove unused code and assets safely.
- Simplify view hierarchies while preserving behavior.

### Documentation
- Keep README, architecture notes, and usage docs synced with code changes.

---

## Agents: When to Use Them

- `planner` for multi-step implementation plans and risk analysis.
- `architect` for new modules or major refactors.
- `tdd-guide` to drive new logic with tests first.
- `code-reviewer` after code changes.
- `security-reviewer` before release or when touching auth/storage.
- `build-error-resolver` for build failures.
- `e2e-runner` when validating critical UI flows.
- `refactor-cleaner` to remove dead code and simplify.
- `doc-updater` to align docs with actual behavior.

---

## Skills: Embedded Knowledge

Use skills to apply guidance quickly without repeating the same patterns.

- `coding-standards`: Swift style, concurrency, and error handling.
- `ios-patterns`: Architecture, DI, storage, networking, analytics.
- `swiftui-patterns`: SwiftUI state, layout, accessibility.
- `project-guidelines-example`: Baseline rules for a modern app.
- `tdd-workflow`: TDD steps and test quality standards.
- `security-review`: Storage, networking, privacy, and App Store checks.

---

## Commands: Quick Execution

Commands are lightweight prompts that enforce a consistent workflow.

- `/plan` for multi-step feature planning.
- `/tdd` to enforce a test-first workflow.
- `/code-review` to check quality and security issues.
- `/build-fix` to root-cause build failures.
- `/test-coverage` to identify untested logic.
- `/e2e` to design critical user flow tests.
- `/refactor-clean` to remove unused code.
- `/update-docs` and `/update-codemaps` for documentation hygiene.
- `/learn` to capture lessons and decisions.

---

## Rules: Always-On Guardrails

Rules define non-negotiable constraints for production quality.

- `rules/security.md` ensures safe storage and privacy handling.
- `rules/testing.md` requires deterministic tests for new logic.
- `rules/performance.md` protects against main-thread abuse.
- `rules/patterns.md` standardizes MVVM/Coordinator usage.
- `rules/coding-style.md` defines Swift conventions.
- `rules/git-workflow.md` enforces Conventional Commits.

---

## MCP Servers

This repo includes MCP server definitions for common iOS tooling:

- `xcodebuildmcp` for build/test/simulator automation.
- `firebase` for Firebase CLI operations.
- `asana` for task and project management.
- `growthbook` for feature flags and experiments.
- `mixpanel` for analytics operations.
- `figma` for design file access.

Edit tokens and paths in `mcp-configs/mcp-servers.json` before use.

---

## Hooks

Hooks provide lightweight automation.

Typical uses:
- Blocking secrets or sensitive logs.
- Warning on `print()` usage.
- Reminding you to update tests.

---

## Recommended Workflow

1. Use `/plan` before multi-file changes.
2. Use `tdd-guide` or `/tdd` for new logic.
3. Run `/code-review` and `security-reviewer` for release readiness.
4. Update docs with `doc-updater` or `/update-docs`.
5. Capture learnings with `/learn`.

---

## Conventions and Philosophy

- Prefer explicit data flow and clear ownership.
- Keep UI state and side effects separated.
- Avoid global mutable state.
- Test behavior, not implementation details.
- Measure performance before optimizing.

---

## Troubleshooting

- Build errors: use `build-error-resolver` to isolate root causes.
- Flaky tests: check time dependencies, network usage, and global state.
- Performance regressions: inspect heavy work on the main thread.
- UI instability: validate accessibility identifiers and deterministic state.

---

## Contributing

Contributions are welcome. Additions should prioritize practical iOS guidance, explicit workflows, and modern Swift practices.
