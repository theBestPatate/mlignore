# Usage Guide

`mlignore` acts as a bridge between your local disk and the LLM prompt.

## Basic Commands

### The "Standard Leak"
Gathers files from the current directory, applies minification to supported files, and saves to `context.md`.
```bash
mlignore --root . --output context.md
```

### The "Unix pipeline"

If you omit the `--output` flag, mlignore writes to stdout.

```bash
mlignore -r ./src -s| wc -l
#Yeah I'm sorry, the r doesn't stand for recursive because it's recursive by default but for root
```

### Configuring Exclusions

`mlignore` follows a hierarchy of rejection:

1.  **Application Defaults**: `--exclude` (defaults to `node_modules, .git, .venv`, etc.)
2.  **.gitignore**: Patterns defined in your git config.
3.  **.mlignore**: Patterns specifically for this tool (e.g., exclude large tests even if git tracks them).

### Creating a .mlignore
```text
# Exclude heavy assets
assets/*.png
tests/integration/
# Exclude the generator's own output
context.md
```

## Advanced Flags

| Flag | Description | Default |
| :--- | :--- | :--- |
| `-r, --root` | Root directory to scan | `.` |
| `-o, --output` | Output file path | `stdout` |
| `--smart-exts` | Extensions to minify (Tree-sitter) | `.py,.js,.jsx,.css` |
| `--text-exts` | Extensions to include as-is | `""` |
| `--max-files` | Maximum number of files to process | `500` |
| `--max-size-kb` | Skip files larger than this size | `512` |
| `-s, --silent` | Suppress all logs to stderr | `False` |

