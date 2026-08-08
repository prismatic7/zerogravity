# Architectural Guidelines

## 1. Separation of Concerns
- **Slash Commands**: Act as user-facing macros triggering prompts.
- **Skills**: Act as autonomous instruction sets teaching the agent how to orchestrate actions.
- **MCP Server**: Acts as the interface executing filesystem and terminal commands.

## 2. Extensibility
- Adding new delegation commands (e.g. `zero-review`) requires:
  1. Creating a command file in `/commands/`.
  2. Declaring it in `plugin.yaml`.
  3. Registering instructions in the skill folder.
