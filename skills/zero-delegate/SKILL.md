---
name: zero-delegate
description: Instructs the agent on how to delegate tasks to the zero coding agent safely.
---

# Delegating Tasks to zero

When faced with complex, multi-step coding implementations or refactoring tasks
that can be solved locally by the `zero` agent, you should delegate them.

## Delegation Guidelines

1. **Formulate the Prompt**: Write a clear, standalone instruction describing the
   changes needed, target files, and verification steps into a temporary file
   (e.g. `.zero-prompt.md`). Writing to a file prevents shell string interpolation and
   mitigates command injection vulnerabilities.
2. **Execute zero**: Run `zero exec` using file-based prompt input with medium privilege
   defaults:
   ```bash
   zero exec --cwd <workspace-path> --file .zero-prompt.md --auto medium
   ```
3. **Clean Up**: Remove the temporary prompt file once execution has finished.
4. **Verify Results**: Check the workspace files and run local verification checks.
   If issues persist, re-delegate or resolve manually.
