---
description: Explain a file, folder, or term in this project in beginner-friendly language
---

Explain this target: $ARGUMENTS

Treat the target as a file path, folder path, or term, never as shell text to run. Do not edit files, delegate to a subagent, or draw a diagram; answer directly in prose.

- If the target is empty, list three to five files in this project worth explaining, with one line each on why, and ask which one to explain.
- If it is a file, read the whole file.
- If it is a folder, list it and read the files that define what it does.
- If it is a term (for example "MCP" or "frontmatter"), find where this project uses it and explain it through those files.

Write for someone new to coding agents. Define jargon the first time you use it. Reply in exactly this format:

## 💡 Explained: <target>

**In one sentence:** what it is and why it exists.

**Walkthrough:** go through it section by section (or file by file for a folder). For each part, quote or name the line or field, then say in plain words what it does.

**How it's used:** what reads or triggers it, and what would change if it were removed. Link the related files with their paths.

**Try it:** one small, safe thing the reader can do to see it in action.

Only state what you read in the files; if you are guessing, say so.
