---
description: Implement a change, run project checks, obtain review, and verify behavior
argument-hint: "[change request]"
disable-model-invocation: true
---

Requested change: $ARGUMENTS

1. Restate the request and acceptance criteria. If no change was given, ask for one. Read applicable CLAUDE.md files, project documentation, relevant source/tests, and manifests. Discover the actual stack and verification commands; do not assume an application layout or tooling.
2. Implement the smallest complete change using repository conventions. Preserve unrelated work and behavior. Add meaningful regression coverage where appropriate. Do not install optional integrations as part of this workflow.
3. Run relevant tests, lint/type checks, and builds that the project actually provides. Fix failures introduced by the change; identify existing failures separately. Report missing tools and checks skipped rather than inventing results.
4. Use the review-procedure skill and checklist for a review pass. Invoke /review-code on the changed files; if that is unavailable, apply `.claude/commands/review-code.md` directly and state that fallback. Do not recursively invoke /ship.
5. Delegate an independent review to the reviewer subagent with the acceptance criteria, changed-file list, and full diff including new files. Ask it to inspect source itself. The reviewer cannot edit or run tests. Address actionable findings and rerun affected checks. If delegation is unavailable, label the fallback as self-review rather than claiming independence.
6. Choose verification relevant to the project. For browser-facing changes, use Playwright MCP when connected and the actual supplied or observed app URL; if needed, ask how to run the app and for its URL rather than guessing. Exercise the changed behavior and relevant regressions using disposable data. For non-browser changes, use the relevant API, CLI, or other checks instead. Clearly identify unavailable tools, manual checks, and skipped verification.
7. Report changed behavior/files, commands actually run and results, review findings addressed, verification evidence, and remaining issues. Do not commit, push, publish, or deploy without authorization. Do not claim readiness when required checks are failing or incomplete.
