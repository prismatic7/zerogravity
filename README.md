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
