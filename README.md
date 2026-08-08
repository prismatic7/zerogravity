# zerogravity

`zerogravity` is a Google Antigravity CLI plugin to delegate coding tasks to the `zero` agent.

## Features
- **Slash Command (`/zero`)**: Quickly run coding tasks via `/zero <your-prompt>`.
- **Skill (`zero-delegate`)**: Allows Antigravity agents to delegate coding goals autonomously.
- **MCP Server**: Call code navigation and filesystem tools directly via the `zero` protocol.

## Installation

1. Symlink this plugin folder into your Antigravity plugins directory:
   ```bash
   ln -s ~/Development/zerogravity ~/.gemini/config/plugins/zerogravity
   ```

2. Register the `zero` MCP server in your `~/.gemini/config/mcp_config.json`:
   ```json
   {
     "mcpServers": {
       "zero": {
         "command": "zero",
         "args": ["serve", "--mcp"]
       }
     }
   }
   ```

   This will expose standard code navigation and search tools from `zero` to your agent.

> [!WARNING]
> The `--allow-unsafe-tools` flag is optional and should be omitted if read-only analysis
> is preferred. If enabled, it grants system-wide file modification and command execution
> capabilities. To limit access, scope the server workspace using `-C <path>` when necessary
> (e.g. `["serve", "--mcp", "--allow-unsafe-tools", "-C", "/path/to/project"]`).

## Contributing

Please follow the pull request checklist in `.github/PULL_REQUEST_TEMPLATE.md`.

### Adding New Commands

Slash commands in `zerogravity` are defined using TOML files placed inside the
[commands/](commands/) directory. Each `.toml` file corresponds to a slash command in the
Antigravity TUI.

To create a new slash command (for example, `/custom`):

1. Create a TOML file at `commands/custom.toml`.
2. Add a `description` and a multi-line `prompt` template:

```toml
# commands/custom.toml
description = "A brief description displayed in auto-complete menus"
prompt = """
Instructions for the agent when the command is invoked. \
Use {{args}} to substitute user-supplied arguments.\
"""
```

3. Verify prompt expansion and agent behaviour in the Antigravity TUI.

### Local Conventions

When contributing code or documentation to `zerogravity`, please observe the following local
conventions:

- **Spelling Register**: Always use Australian English spelling (e.g. *behaviour*,
  *localisation*, *organise*, *colour*).
- **Line Length Boundaries**: Ensure lines are wrapped to strictly under 100 characters per line.
- **Prompt Injection Prevention**: Never execute raw user input directly inside shell scripts
  or command strings. Pass user arguments (`{{args}}`) safely via temporary files or input
  sanitisation to mitigate injection risks.

