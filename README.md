# zerogravity

`zerogravity` is a Google Antigravity CLI plugin to delegate coding tasks to the `zero` agent.

## Features
- **Slash Command (`/zero`)**: Quickly run coding tasks via `/zero <your-prompt>`.
- **Skill (`zero-delegate`)**: Allows Antigravity agents to delegate coding goals autonomously.
- **MCP Server**: Call tools like code-navigation and filesystem operations directly via the `zero` protocol.

## Installation

1. Symlink this plugin folder into your Antigravity plugins directory:
   ```bash
   ln -s /Users/chris/Development/zerogravity /Users/chris/.gemini/config/plugins/zerogravity
   ```

2. Register the `zero` MCP server in your `/Users/chris/.gemini/config/mcp_config.json`:
   ```json
   {
     "mcpServers": {
       "zero": {
         "command": "zero",
         "args": ["serve", "--mcp", "--allow-unsafe-tools"]
       }
     }
   }
   ```
   This will expose all coding, search, and navigation tools of `zero` to your Antigravity agent.

## Contributing
Please follow the pull request checklist in `.github/PULL_REQUEST_TEMPLATE.md`.
