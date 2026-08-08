# Code Formatting & Style Rules

## 1. Document Formatting
- **YAML / JSON**: Indent with 2 spaces. No trailing commas in JSON.
- **TOML**: Key-value pairs should be grouped under headers. Indent values logically.
- **Markdown**: Maximum line length 100 characters. Use ATX-style headers (e.g. `# Header`).

## 2. Naming Conventions
- **Commands**: Lowercase, hyphen-separated (e.g., `zero-delegate`).
- **Skills**: Lowercase, hyphen-separated (e.g., `zero-delegate`).
- **Files**: Match command or skill names exactly.

## 3. Spelling & Localisation
- Ensure the spelling conforms to the Australian English register (e.g., *behaviour*, *optimise*, *centre*).

## 4. Code Example (Gold Standard TOML)
```toml
description = "Scaffold a new feature"
prompt = "Begin scaffolding the feature {{args}} using the design specs."
```
