# Testing Guidelines & Standards

## 1. Test Targets
Because `zerogravity` is a configuration-based plugin, test and verification focuses on:
- JSON/YAML syntax validation.
- Path existence and structure verification.
- Content checks for YAML frontmatter headers.

## 2. Validation Suite
- **Syntax Check**: Parse JSON and YAML via Node.js utilities before commit.
- **Dry-run commands**: Test slash commands inside the Antigravity TUI to ensure prompts resolve parameters correctly.

## 3. Example Test Script
```javascript
const fs = require('fs');
const assert = require('assert');
const manifest = JSON.parse(fs.readFileSync('plugin.json', 'utf8'));
assert.strictEqual(manifest.name, 'zerogravity');
console.log('Test passed!');
```
