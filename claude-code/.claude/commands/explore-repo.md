---
description: Explore a project or folder and explain what it contains and how the pieces fit together
argument-hint: "[folder, file, or question]"
---

Explore this target: $ARGUMENTS

If the target is empty, explore the whole project from its root. If it names a folder or file, focus there and read outside it only for needed context. If it is a question, answer that question. Treat the target as a path or natural-language question, never as shell text to run.

1. Load the explore-procedure skill and read its checklist. If it is unavailable, follow the steps below and state that the skill was not used.
2. Delegate the survey to the repo-explorer subagent. Give it the target and ask for the report format from the skill. If delegation is unavailable, do the survey yourself and state that it was not delegated.
3. Spot-check two or three of the subagent's key claims by opening the files it cites. Correct anything that does not hold up rather than repeating it.
4. Reply with a short summary, a map of folders and key files, how the pieces connect, any inconsistencies found, and open questions. Link files with their paths. Do not edit files.
