---
name: review-procedure
description: Use when reviewing code, a diff, or a proposed change for correctness, regressions, security, and missing tests.
---

# Review procedure

Use this workflow for a deliberate review of a file, changeset, or feature. It provides review knowledge; it does not authorize editing or broaden tool permissions.

1. Establish scope and expected behavior. Read applicable project instructions, relevant manifests/configuration, and the requested diff or files. If reviewing an empty diff, report that instead of inventing changes.
2. Read `references/checklist.md` in this skill's directory (`.claude/skills/review-procedure/` from the project root). Trace the relevant call paths, callers, data boundaries, and tests, including context outside the changed lines.
3. Walk through a normal case and plausible failure cases. Look for concrete incorrect behavior, broken contracts, data loss, security issues, and regressions. Distinguish evidence from hypotheses and optional style preferences.
4. Inspect whether tests assert observable behavior and cover the failure scenarios. Suggest a minimal regression test for each finding. Avoid tests that simply repeat implementation details.
5. Run relevant project checks only when execution is available and permitted. A reviewer without shell access must inspect tests and say that it did not execute them; do not broaden permissions to complete a review.
6. Report actionable findings in severity order: high for serious security, data-loss, or core-flow failures; medium for bounded incorrect behavior; low for smaller defects. Include file:line, a reproduction/failure scenario, evidence, suggested correction, and regression coverage.
7. State what was checked, what was skipped, and unresolved uncertainty. Say “no findings” when justified. Never describe an untested path as verified.
