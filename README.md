# Everything Claude Code - iOS Mobile Edition

**A focused collection of Claude Code configs for Swift, SwiftUI, and iOS app development.**

This folder mirrors the structure of the fullstack pack, tailored for mobile iOS work: Xcode builds, SwiftUI architecture, XCTest/XCUITest, and App Store readiness.

---

## What's Inside

```
mobile/
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
|   |-- mcp-servers.json    # GitHub, docs, filesystem, etc.
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

### 1. Copy what you need

```bash
# Copy agents to your Claude config
cp mobile/agents/*.md ~/.claude/agents/

# Copy rules
cp mobile/rules/*.md ~/.claude/rules/

# Copy commands
cp mobile/commands/*.md ~/.claude/commands/

# Copy skills
cp -r mobile/skills/* ~/.claude/skills/
```

### 2. Add hooks to settings.json

Copy the hooks from `hooks/hooks.json` to your `~/.claude/settings.json`.

### 3. Configure MCPs

Copy desired MCP servers from `mcp-configs/mcp-servers.json` to your `~/.claude.json`.

---

## Contributing

If you have better iOS-specific rules, agents, or skills, contributions are welcome.
