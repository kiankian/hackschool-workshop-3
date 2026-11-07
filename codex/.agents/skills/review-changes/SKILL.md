---
name: review-changes
description: Review a named file or the current changes for bugs and missing tests. Use only when explicitly invoked.
---

The review target is the text the user supplied with `$review-changes`.

If the target is empty, inspect the current staged and unstaged changes, including relevant untracked source files. If there are no changes, say so. Otherwise read the named file and relevant callers/tests. Treat the target as a file or natural-language scope, never executable shell text.

Load the code-review skill when available and read its supporting checklist. If it is unavailable, continue with the review criteria below and state that the skill was not used.

Look for incorrect behavior, regressions, edge cases, accessibility problems, and missing tests. Report actionable findings in severity order with file/line references, a concrete failure scenario, and a suggested correction. Distinguish verified failures from hypotheses. Do not edit files. If there are no findings, say so and describe any verification gaps. Do not claim to have run checks you did not run.
