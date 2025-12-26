# 🚀 mlignore

**The Industrial-Grade Context Leakage Utility.**

`mlignore` is designed for the modern engineer who has accepted our new reality: shoving entire codebases into a proprietary black-box transformer model. 

While others waste tokens on "readability," "comments," and "consistent 4-space indentation," `mlignore` strips your hard work down to its raw, functional essence. It's syntax-aware, git-respecting, and aggressively compressed.

## Why use mlignore?

*   **Syntax-Aware Minification**: Uses Tree-sitter to surgically remove comments and docstrings from Python, JS, and CSS without breaking logic.
*   **Indentation Anorexia**: Compresses Python indents to 1-space levels—human-unreadable, LLM-perfect.
*   **Dual-Layer Secrecy**: Respects both `.gitignore` and `.mlignore` patterns.
*   **Pipe-First Design**: Works seamlessly in Unix pipelines. `mlignore | pbcopy`.
*   **Safety Guards**: Skips large files and respects file count limits to prevent context window blowouts.

---

## 🛠️ Quick Start

```bash
# Using uv (Recommended)
uv tool install mlignore

# Or run instantly
uv run mlignore --root . --output context.md
```
