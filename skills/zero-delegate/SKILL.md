---
name: zero-delegate
description: Instructs the agent on how to delegate tasks to the zero coding agent.
---

# Delegating Tasks to zero

When faced with complex, multi-step coding implementations or refactoring tasks that can be solved locally by the `zero` agent, you should delegate them.

## Delegation Guidelines

1. **Formulate the Prompt**: Write a clear, standalone instruction describing the changes needed, target files, and verification steps.
2. **Execute zero**: Run `zero exec` using the shell execution command:
   ```bash
   zero exec --cwd <workspace-path> --prompt "<prompt-text>" --self-correct --allow-escalation
   ```
3. **Verify Results**: Check the workspace files and run local verification checks. If issues persist, re-delegate or resolve manually.
