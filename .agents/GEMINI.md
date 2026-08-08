# GEMINI Master Guide - zerogravity

Welcome to the `zerogravity` project. This guide serves as the entry point for AI assistants developing this plugin.

## Project Overview
`zerogravity` is a Google Antigravity CLI plugin that integrates the `zero` coding agent, allowing delegation of tasks from the Antigravity TUI.

## Tech Stack
- **Languages**: Markdown, YAML, TOML, Shell Scripting (Bash/Zsh).
- **Runtime**: Node.js 18+ (for script hooks if added).
- **Interface**: Google Antigravity CLI (agy) plugin architecture.

## Architecture & Directory Map
- `/commands/`: Slash command definitions (TOML files).
- `/skills/`: Custom agent instructions (Markdown files with YAML frontmatter).
- `/docs/`: Specifications and plans.
- `/README.md`: General setup and user guide.
- `/.agents/`: AI assistant settings and workflows.

## Development Commands
- **Verify spelling**: `grep -i "organise" README.md`
- **Verify JSON validity**: `node -e "JSON.parse(require('fs').readFileSync('plugin.json'))"`

## Coding Conventions
- **Spelling**: Always use the Australian English spelling register (e.g. *theatre*, *organise*, *colour*).
- **Files**: Group related skills inside folders under `/skills/`. Command definitions live in `/commands/`.
- **References**: Relative file links must be fully qualified absolute URIs or relative paths in markdown formatting.

## Critical Rules
- **YAGNI**: Keep the plugin lightweight. Do not introduce dependencies unless absolutely necessary.
- **Verification**: Always verify file syntax (JSON/YAML/TOML) after creating or editing.
- **Secrets**: Never include credentials or local absolute paths in public plugin files.
