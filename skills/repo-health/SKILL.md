---
name: repo-health
description: Review a repository's health, including documentation, version control hygiene, automated checks, and maintainability. Use when asked to audit, assess, or improve the overall health of a repository.
license: MIT
---

# Repository health review

Perform a concise, evidence-based review of the current repository.

## Review process

1. Identify the language, framework, package manager, and build system from the repository files.
2. Inspect the README and determine whether setup, usage, testing, and contribution guidance are clear.
3. Inspect version-control hygiene, including `.gitignore`, committed generated artifacts, secrets, and oversized files.
4. Locate the existing build, test, lint, and formatting commands. Do not invent commands when the repository does not define them.
5. Review the project layout and highlight maintainability risks such as duplicated configuration, dead entry points, or missing tests.
6. Run only safe, existing checks when they are available and report their actual results.

## Output format

Return:

- **Summary**: one paragraph describing the overall health.
- **Findings**: a prioritized table with `Priority`, `Area`, `Evidence`, and `Recommendation`.
- **Checks**: commands that were run and their results.
- **Next steps**: no more than three concrete actions.

Prioritize correctness, security, reproducibility, and developer experience. Distinguish confirmed findings from suggestions, and include file paths and line numbers when available. Never claim that a check passed unless it was actually run.
