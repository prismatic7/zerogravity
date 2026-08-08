---
name: plugin-development
description: Guide for designing, scaffolding, securing, and documenting Antigravity plugins.
---

# Antigravity Plugin Development Workflow

This skill outlines the standard lifecycle for developing plugins for the Google
Antigravity CLI (`agy`). Follow these five structured phases for all plugin work.

## Phase 1: Planning and Discussion

1. **Purpose Alignment**: Define the core problem the plugin resolves, target user workflows,
   and expected operational outcomes.
2. **Design & Interface**: Plan user interaction boundaries, including slash commands,
   custom agent skills, subagent configurations, and statusline hooks.
3. **Architecture Mapping**: Establish required directory layouts (`commands/`, `skills/`,
   `agents/`, `hooks/`) and configuration manifests (`plugin.json`, `plugin.yaml`).
4. **References & Standards**: Consult authoritative documentation (such as `GEMINI.md` and
   `antigravity-guide`) to align with project conventions and guidelines.

## Phase 2: Optional Research

1. **API & CLI Testing**: Execute exploratory commands or test target APIs to clarify parameter
   schemas and response formats before implementing logic.
2. **MCP & Environment Inspection**: Review Model Context Protocol (MCP) server endpoints,
   tool signatures, and runtime environment dependencies where relevant.

## Phase 3: Scaffolding and Implementation

1. **Manifest Scaffolding**: Create `plugin.json` and `plugin.yaml` to declare plugin metadata,
   exported commands, and exposed skills.
2. **Component Creation**: Write slash command definitions (`.toml` in `commands/`) and skill
   instructions (`SKILL.md` in `skills/<skill-name>/`).
3. **Spec-Driven Development**: Apply structured planning workflows (using spec/plan documents)
   to execute multi-step implementation tasks incrementally.
4. **Lightweight Implementation**: Keep the plugin lean. Avoid unnecessary third-party dependencies
   and adhere to YAGNI (You Aren't Gonna Need It) principles.

## Phase 4: Mandatory Security Review

1. **Threat Modelling**: Analyse potential risk vectors, filesystem interactions, network calls,
   and child process execution paths.
2. **Injection Prevention**: Avoid unsafe shell command string formatting. Use temporary prompt
   files or parameter array execution to eliminate injection risks.
3. **Secrets & PII Safeguards**: Ensure API credentials, personal tokens, and machine-specific
   absolute paths are never committed to repository files.

## Phase 5: Mandatory Documentation

1. **Code Annotations**: Include clear comments explaining non-obvious architectural choices,
   edge-case handlers, and interface contracts.
2. **Plugin Documentation**: Maintain a comprehensive `README.md` detailing setup prerequisites,
   command usage, skill reference tables, and configuration options.
3. **Developer Guides**: Provide onboarding notes and maintainable documentation for junior
   developers and future maintainers.
