# Review checklist

Apply the items relevant to this project; do not assume every codebase has a UI, network service, or database.

- **Behavior:** Does the change satisfy the request? Are existing contracts and unrelated behavior preserved? Are edge cases, empty values, missing data, and boundary limits handled?
- **State and data:** Are updates consistent? Could retries, concurrency, cancellation, partial failures, or stale state cause incorrect results or data loss? Are storage formats and migrations compatible?
- **Boundaries:** Are external inputs validated? Are authorization checks enforced where needed? Could injection, unsafe rendering, path traversal, or sensitive-data exposure occur?
- **Failure handling:** Are errors observable and actionable? Are resources cleaned up? Are retries bounded and operations safe to repeat where required?
- **Interface changes:** Are labels, focus, keyboard use, loading/error/empty states, and responsive layout preserved? Do browser checks exercise the actual changed behavior?
- **Dependencies and scope:** Does the change follow the existing architecture? Are new packages justified? Is configuration compatible with the deployed/runtime version?
- **Tests:** Do assertions establish observable behavior? Is there a regression test for each demonstrated bug? Are meaningful failure paths covered without mirroring the implementation?
- **Evidence:** Does each finding have a concrete scenario and file:line reference? Are hypotheses distinguished from reproduced failures, and executed checks distinguished from inspection?
