# Security Guardrails

## 1. Environment Safety
- Avoid hardcoding absolute paths to user home directories outside the allowed `/Users/chris/Development/` workspace.
- The `zero` MCP server requires `--allow-unsafe-tools` for full execution. Warn users in documentation that this grants write/execution permissions to the assistant.

## 2. Secrets Management
- Never store API keys, tokens, or personal identifiers inside the repository.
- Use `mcp_config.json` environment variables to inject sensitive data.

## 3. Execution Control
- Verify shell command arguments before spawning subprocesses to avoid command injection vulnerability.
