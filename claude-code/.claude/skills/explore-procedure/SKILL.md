---
name: explore-procedure
description: Use when asked to explore, map, explain, or get oriented in a codebase, folder, or repository, including repositories that hold documentation and configuration rather than application code.
---

# Explore procedure

Use this workflow to build an accurate picture of a project before explaining or changing it. It is read-only: it does not authorize editing.

1. Set the scope: the whole project, one folder or file, or one question.
2. Start broad. List the top-level files and folders. Read the README, license, `.gitignore`, and any agent instruction files such as `CLAUDE.md` or `AGENTS.md`.
3. Read `references/checklist.md` in this skill's directory (`.claude/skills/explore-procedure/` from the project root). Use it to decide where to look next.
4. Go one level deeper where it matters: manifests and configuration, entry points, and folders that mirror each other. If the project has no application code, treat its docs, templates, and config files as the substance and say there is no code to run.
5. Trace connections: links between docs, file paths named in instructions, frontmatter fields such as `skills:` or `tools:`, and imports. Check that referenced files exist. Note duplicates and anything out of sync.
6. Report: a short summary (what it is, who it is for), a map of folders and key files with their purpose, how the pieces connect, inconsistencies, and open questions. Separate what you read from what you inferred, and name what you skipped.
