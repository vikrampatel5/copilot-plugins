---
name: repo-health
description: Review repository structure, tooling, documentation, Git hygiene, and maintainability with evidence-based findings. Use when asked to audit, assess, or improve the health of a repository.
license: MIT
---

# Repository health review

Perform a concise, evidence-based review of the current repository.

## Review process

1. Inspect the repository structure and identify its language, framework, package manager, and build system from repository files.
2. Inspect the README and determine whether setup, usage, testing, and contribution guidance are clear.
3. Inspect version-control hygiene, including `.gitignore`, committed generated artifacts, committed secrets, and oversized files.
4. Locate the existing build, test, lint, and formatting commands. Do not invent commands when the repository does not define them.
5. Review project organization and highlight maintainability risks such as duplicated configuration, dead entry points, or missing tests.
6. Run only safe, existing checks when they are available and report their actual results.

## Output format

Return:

- **Summary**: one paragraph describing the overall health.
- **Findings**: a prioritized table with `Priority`, `Area`, `Evidence`, and `Recommendation`.
- **Checks**: commands that were run and their results.
- **Next steps**: no more than three concrete actions.

Prioritize correctness, security, reproducibility, and developer experience. Distinguish confirmed findings from recommendations, and include evidence, file paths, and line numbers when available. Never claim that a check passed unless it was actually run.
